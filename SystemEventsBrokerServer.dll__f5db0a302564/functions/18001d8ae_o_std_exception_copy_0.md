# _o___std_exception_copy_0

- ea: `0x18001d8ae`
- end: `0x18001d8b4`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18000b180`
- `0x1800195e0`
- `0x18001e774`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x18001d8ae`

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
0x18001d8ae  jmp     cs:__imp__o___std_exception_copy
```
