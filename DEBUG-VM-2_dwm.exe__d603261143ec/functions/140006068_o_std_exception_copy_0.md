# _o___std_exception_copy_0

- ea: `0x140006068`
- end: `0x14000606e`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140005dfc`
- `0x140005e68`
- `0x140005ed4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x140006068`

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
0x140006068  jmp     cs:__imp__o___std_exception_copy
```
