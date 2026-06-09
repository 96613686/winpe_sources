# _o___std_exception_copy_0

- ea: `0x1800031c6`
- end: `0x1800031cc`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180003990`
- `0x180003e80`
- `0x180004580`
- `0x180004620`
- `0x180004670`
- `0x18000655c`
- `0x180010784`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x1800031c6`

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
0x1800031c6  jmp     cs:__imp__o___std_exception_copy
```
