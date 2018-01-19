
## Nonlinear Solve Answers

### Solution to Problem 1


```julia
using Roots
f(x) = 10 - x + e*sin(x)
fzero(f,BigFloat(2.0))
```

### Solution to Problem 2


```julia
f! = function (x,dx)
  dx[1] = x[1]   + x[2]   + x[3]^2 -12
  dx[2] = x[1]^2 - x[2]   + x[3]   - 2
  dx[3] = 2x[1]  - x[2]^2 + x[3]   - 1
end
using NLsolve
res = nlsolve(f!,[1.0;1.0;1.0])
res.zero
res = nlsolve(f!,[1.0;1.0;1.0],autodiff=true)
res.zero
```
