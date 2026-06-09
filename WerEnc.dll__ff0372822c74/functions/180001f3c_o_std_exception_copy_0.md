# _o___std_exception_copy_0

- ea: `0x180001f3c`
- end: `0x180001f42`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001cdc`
- `0x180001d48`
- `0x180001db4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180001f3c`

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
0x180001f3c  jmp     cs:__imp__o___std_exception_copy
```
