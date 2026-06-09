# _o___std_exception_copy_0

- ea: `0x140008f9e`
- end: `0x140008fa4`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x14000a4a4`
- `0x14000a5b8`
- `0x14000a624`
- `0x14000a65c`
- `0x14000a6a0`
- `0x14000d800`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x140008f9e`

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
0x140008f9e  jmp     cs:__imp__o___std_exception_copy
```
