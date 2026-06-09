# exception::exception(exception const &)

- ea: `0x180002534`
- end: `0x18000253a`
- name: `??0exception@@QEAA@AEBV0@@Z_0`
- size: `6`
- prototype: `exception *(exception *__hidden this, const struct exception *)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180001b80`
- `0x180001bf0`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBV0@@Z` at `0x180002534`

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
0x180002534  jmp     cs:__imp_??0exception@@QEAA@AEBV0@@Z
```
