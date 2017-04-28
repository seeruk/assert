# assert

<p>
    <a href="https://travis-ci.org/SeerUK/assert">
        <img src="https://api.travis-ci.org/SeerUK/assert.svg?branch=master" />
    </a>
    <a href="https://goreportcard.com/report/github.com/SeerUK/assert">
        <img src="https://goreportcard.com/badge/github.com/SeerUK/assert" />
    </a>
    <a href="https://github.com/SeerUK/assert/releases">
        <img src="https://img.shields.io/github/release/SeerUK/assert.svg" />
    </a>
</p>

Ludicrously simple assertion library for Go, just to make using the built-in test a little easier.

Package assert provides some simple but powerful testing helpers. They are designed to greatly
simplify testing code, reduce code verbosity, and produce consistent and useful output during tests.

## Usage

All assertions take a `testing.T` instance as the first argument, and will fail the test they're
used in if the assertion fails.

### `assert.True`:

```go
// Take a predicate, and a message to use in the error created for when the predicate is not truthy.
assert.True(t, 1 == 2, "expected 1 to equal 2")
assert.True(t, something.IsTruthy(), "expected something to be truthy")
```

### `assert.False`:

```go
// Take a predicate, and a message to use in the error created for when the predicate is not falsey.
assert.False(t, true == true, "expected true not to equal true")
assert.False(t, something.IsTruthy(), "expected something to be falsey")
```

### `assert.Equal`:

```go
// Take the expected value, then the actual value, and assert that they are equal.
assert.Equal(t, 1, 1)
assert.Equal(t, 23, mathy.TenPlusThirteen())
```

### `assert.NotEqual`:

```go
// Take the expected value, then the actual value, and assert that they are not equal.
assert.NotEqual(t, 1, 2)
assert.NotEqual(t, 24, mathy.TenPlusThirteen())
```

### `assert.OK`:

```go
// Assert the given `error` is nil.
assert.OK(t, something.ThatMayReturnAnError())
```

### `assert.NotOK`:

```go
// Assert the given `error` is not nil.
assert.OK(t, something.ThatMayReturnAnError())
```

## License

MIT
