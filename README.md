# mean-variance-standard-deviation-calculator


```python
import numpy as np

def calculate(list):
    if len(list) != 9:
        raise ValueError("List must contain nine numbers.")

    matrix = np.array(list).reshape(3, 3)

    calculations = {
        'mean': [
            matrix.mean(axis=0).tolist(),
            matrix.mean(axis=1).tolist(),
            matrix.mean().tolist()
        ],
        'variance': [
            matrix.var(axis=0).tolist(),
            matrix.var(axis=1).tolist(),
            matrix.var().tolist()
        ],
        'standard deviation': [
            matrix.std(axis=0).tolist(),
            matrix.std(axis=1).tolist(),
            matrix.std().tolist()
        ],
        'max': [
            matrix.max(axis=0).tolist(),
            matrix.max(axis=1).tolist(),
            matrix.max().tolist()
        ],
        'min': [
            matrix.min(axis=0).tolist(),
            matrix.min(axis=1).tolist(),
            matrix.min().tolist()
        ],
        'sum': [
            matrix.sum(axis=0).tolist(),
            matrix.sum(axis=1).tolist(),
            matrix.sum().tolist()
        ]
    }

    return calculations
```

### Test (`main.py`)

```python
from mean_var_std import calculate

print(calculate([0,1,2,3,4,5,6,7,8]))
```

### Output

```python
{
  'mean': [[3.0, 4.0, 5.0], [1.0, 4.0, 7.0], 4.0],
  'variance': [[6.0, 6.0, 6.0], [0.6666666666666666, 0.6666666666666666, 0.6666666666666666], 6.666666666666667],
  'standard deviation': [[2.449489742783178, 2.449489742783178, 2.449489742783178], [0.816496580927726, 0.816496580927726, 0.816496580927726], 2.581988897471611],
  'max': [[6, 7, 8], [2, 5, 8], 8],
  'min': [[0, 1, 2], [0, 3, 6], 0],
  'sum': [[9, 12, 15], [3, 12, 21], 36]
}
```

### Exception Test

```python
calculate([1, 2, 3])
```

Output:

```python
ValueError: List must contain nine numbers.
```

This implementation satisfies all the freeCodeCamp requirements:

* ✅ Accepts exactly 9 numbers.
* ✅ Raises `ValueError("List must contain nine numbers.")` otherwise.
* ✅ Converts the list into a `3 × 3` NumPy array.
* ✅ Returns **mean, variance, standard deviation, max, min, and sum** for:

  * columns (`axis=0`)
  * rows (`axis=1`)
  * flattened array
* ✅ Returns **Python lists** (using `.tolist()`) instead of NumPy arrays.
