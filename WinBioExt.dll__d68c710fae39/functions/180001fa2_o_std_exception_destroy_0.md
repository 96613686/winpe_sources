# _o___std_exception_destroy_0

- ea: `0x180001fa2`
- end: `0x180001fa8`
- name: `_o___std_exception_destroy_0`
- size: `6`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180002f64`
- `0x180003120`
- `0x180006ac8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_destroy` at `0x180001fa2`

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
0x180001fa2  jmp     cs:__imp___std_exception_destroy
```
