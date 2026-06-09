# _o___std_exception_copy_0

- ea: `0x18000220a`
- end: `0x180002210`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001d10`
- `0x180001d7c`
- `0x180001de8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x18000220a`

## pseudocode

```c
// attributes: thunk
__int64 o___std_exception_copy_0()
{
  return _o___std_exception_copy();
}

```

## disassembly

```asm
0x18000220a  jmp     cs:__imp__o___std_exception_copy
```
