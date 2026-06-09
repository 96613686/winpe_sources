# exception::exception(exception const &)

- ea: `0x180001f06`
- end: `0x180001f0c`
- name: `??0exception@@QEAA@AEBV0@@Z_0`
- size: `6`
- prototype: `exception *(exception *__hidden this, const struct exception *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800010e4`
- `0x1800011d4`
- `0x180001240`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBV0@@Z` at `0x180001f06`

## pseudocode

```c
// attributes: thunk
exception *__fastcall exception::exception(exception *this, const struct exception *a2)
{
  return __imp_??0exception@@QEAA@AEBV0@@Z(this, a2);
}

```

## disassembly

```asm
0x180001f06  jmp     cs:__imp_??0exception@@QEAA@AEBV0@@Z
```
