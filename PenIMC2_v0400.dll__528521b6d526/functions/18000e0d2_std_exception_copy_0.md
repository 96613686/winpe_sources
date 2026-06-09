# __std_exception_copy_0

- ea: `0x18000e0d2`
- end: `0x18000e0d8`
- name: `__std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18000dd94`
- `0x18000ddf0`
- `0x18000de4c`

## import_xrefs

- `VCRUNTIME140_CLR0400!__std_exception_copy` at `0x18000e0d2`

## pseudocode

```c
// attributes: thunk
__int64 _std_exception_copy_0()
{
  return __std_exception_copy();
}

```

## disassembly

```asm
0x18000e0d2  jmp     cs:__imp___std_exception_copy
```
