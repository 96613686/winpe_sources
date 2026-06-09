# _o___std_exception_copy_0

- ea: `0x18007888e`
- end: `0x180078894`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800a8af0`
- `0x1800a8b28`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x18007888e`

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
0x18007888e  jmp     cs:__imp__o___std_exception_copy
```
