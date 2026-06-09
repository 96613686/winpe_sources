# _o___std_exception_copy_0

- ea: `0x1800052c6`
- end: `0x1800052cc`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x18000aa58`
- `0x18000ac34`
- `0x180014da4`
- `0x180014de8`
- `0x180014e54`
- `0x180014e98`
- `0x180014ef4`
- `0x180020584`
- `0x180028b18`
- `0x180028b5c`
- `0x180028bb8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x1800052c6`

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
0x1800052c6  jmp     cs:__imp__o___std_exception_copy
```
