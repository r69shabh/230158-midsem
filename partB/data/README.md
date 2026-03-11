# Data Folder

This submission uses a generated toy dataset instead of downloading an external benchmark.

## What is in this folder
- `noisy_moons_seed42.csv`: a saved snapshot of the seed-42 dataset used in the notebooks.

## How the dataset is obtained
The notebooks generate the data with:
- `make_moons(n_samples=1200, noise=0.22, random_state=42)`
- stratified `60/20/20` train/validation/test split
- `12%` label flips applied only to the training split

## Column meanings
- `x1`, `x2`: the two raw input features
- `split`: one of `train`, `val`, or `test`
- `clean_label`: the label before synthetic noise injection
- `observed_label`: the label actually given to the learner
- `was_flipped`: whether the training label was flipped; always `False` for validation and test rows

This folder exists to make the toy dataset explicit and reproducible. The later notebooks regenerate the same distribution from code, but the CSV here gives one concrete snapshot that can be inspected without rerunning anything.
