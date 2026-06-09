# _o___std_exception_copy_0

- ea: `0x180001f46`
- end: `0x180001f4c`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002108`
- `0x180002174`
- `0x180002ec4`
- `0x1800030a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180001f46`

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
0x180001f46  jmp     cs:__imp__o___std_exception_copy
```
