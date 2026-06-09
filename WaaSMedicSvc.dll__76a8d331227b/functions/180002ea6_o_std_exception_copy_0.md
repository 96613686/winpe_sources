# _o___std_exception_copy_0

- ea: `0x180002ea6`
- end: `0x180002eac`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x1800039bc`
- `0x180003ad0`
- `0x180008794`
- `0x18000898c`
- `0x1800089e0`
- `0x180008a24`
- `0x180008a90`
- `0x180008cd4`
- `0x180008d18`
- `0x180008d78`
- `0x180008dd8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180002ea6`

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
0x180002ea6  jmp     cs:__imp__o___std_exception_copy
```
