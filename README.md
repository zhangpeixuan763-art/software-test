# CRTCP code and synthetic dataset

This package accompanies the paper "覆盖率与变更风险联合驱动的软件测试用例优先级排序方法".

## Contents

- `src/crtcp.py`: CRTCP ranking algorithm, baseline algorithms, and metrics.
- `src/generate_synthetic_dataset.py`: deterministic generator for the version-level dataset.
- `src/run_experiment.py`: runs all ranking methods and writes result CSV files.
- `data/*.csv`: generated dataset files.
- `results/*.csv`: experiment outputs generated from the included data.

## Run

```bash
python src/generate_synthetic_dataset.py --out data
python src/run_experiment.py --data data --out results
```

The code uses only the Python standard library.

## Dataset schema

- `systems.csv`: system-level metadata.
- `entities.csv`: program entity features used for change-risk scoring.
- `test_cases.csv`: test duration and failure-history metadata.
- `coverage.csv`: sparse test-to-entity coverage matrix.
- `versions.csv`: version metadata.
- `changed_entities.csv`: changed entities for each system version.
- `faults.csv`: fault-to-entity labels for each version.

