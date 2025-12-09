# 🚀 Taxi Hotspot Hunt – Uncover the Lost Pulse of Our Startup

When Yassir started the mobility startup, he noticed an unusual rhythm hidden in the daily taxi traffic. Amid the usual bustle — crowded streets, overlapping routes, and constant movement — a secret hotspot seemed to pulse quietly, revealing subtle patterns that no one else had detected.

The dataset was recorded carefully but altered slightly: some trips are incomplete, some clusters are decoys, and in certain places, the fares themselves were subtly shifted. To find the real fares and uncover the true hotspot, you will need to read the text carefully — a hint is hidden for those who look closely.

## 📂 Your Mission

You have received a file: `taxi_hotspot_dataset.csv`. Each row represents a taxi trip.

Hidden within this dataset are clusters — sequences of 3 trips at the same location that follow a special fare pattern.

A cluster is considered valid if all of the following hold:

### 1️⃣ Different taxis
All 3 trips must have distinct car IDs.

### 2️⃣ Fare pattern
The middle trip's fare B follows this formula:

```
B = |A - C| + (A mod C)
```

Where:
- A = first trip fare
- B = second (middle) trip fare
- C = third trip fare

### 3️⃣ Chronological order
Trips at that location must occur in order by timestamp.

### 4️⃣ Overlapping clusters
Trips can appear in overlapping clusters. Some clusters are decoys: they may look correct but fail one or more rules. Only the correct clusters reveal the hidden hotspot, emerging with the highest combined score.

## 💎 Scoring

- Each valid cluster carries a signature, calculated as the **sum of its fares**.
- The **total score per coordinate** is the sum of all valid cluster signatures at that location.
- More valid clusters → higher total score.
- Decoys and inconsistent trips exist to mislead you.

## ⚖️ Tie-Breaking

If multiple coordinates share the highest score:

1. Pick the coordinate whose **earliest valid cluster** occurs first.
2. If still tied, pick the **largest latitude**.
3. If still tied, pick the **largest longitude**.

## 🕵️‍♂️ Your Tasks

1. Detect all valid clusters following the rules above.
2. Compute total scores per coordinate.
3. Apply tie-breaking rules to determine the true hotspot.

## 📌 Deliverables

**(latitude, longitude)** of the hotspot.