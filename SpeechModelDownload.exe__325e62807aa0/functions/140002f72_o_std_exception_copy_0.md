# _o___std_exception_copy_0

- ea: `0x140002f72`
- end: `0x140002f78`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1400048a4`
- `0x1400049b8`
- `0x14001397c`
- `0x1400139c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x140002f72`

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
0x140002f72  jmp     cs:__imp__o___std_exception_copy
```
