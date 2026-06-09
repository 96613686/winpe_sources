# _o___std_exception_copy

- ea: `0x180005d16`
- end: `0x180005d1c`
- name: `_o___std_exception_copy`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180006ae0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180005d16`

## pseudocode

```c
// attributes: thunk
__int64 o___std_exception_copy()
{
  return _o___std_exception_copy();
}

```

## disassembly

```asm
0x180005d16  jmp     cs:__imp__o___std_exception_copy
```
