# _o___std_exception_destroy_0

- ea: `0x180002eb2`
- end: `0x180002eb8`
- name: `_o___std_exception_destroy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180003bd4`
- `0x180003d90`
- `0x1800090fc`
- `0x180009118`
- `0x180009a80`
- `0x180009ad0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_destroy` at `0x180002eb2`

## pseudocode

```c
// attributes: thunk
__int64 o___std_exception_destroy_0()
{
  return __std_exception_destroy();
}

```

## disassembly

```asm
0x180002eb2  jmp     cs:__imp___std_exception_destroy
```
