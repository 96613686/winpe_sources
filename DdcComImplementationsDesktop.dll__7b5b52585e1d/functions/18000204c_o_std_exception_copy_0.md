# _o___std_exception_copy_0

- ea: `0x18000204c`
- end: `0x180002052`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180003f68`
- `0x180003fac`
- `0x180004018`
- `0x1800056bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x18000204c`

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
0x18000204c  jmp     cs:__imp__o___std_exception_copy
```
