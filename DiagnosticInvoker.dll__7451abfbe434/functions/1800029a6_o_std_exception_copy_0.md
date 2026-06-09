# _o___std_exception_copy_0

- ea: `0x1800029a6`
- end: `0x1800029ac`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800027ec`
- `0x180002858`
- `0x1800036ec`
- `0x180003800`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x1800029a6`

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
0x1800029a6  jmp     cs:__imp__o___std_exception_copy
```
