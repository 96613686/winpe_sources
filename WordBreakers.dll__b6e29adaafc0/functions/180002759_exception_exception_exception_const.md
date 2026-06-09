# exception::exception(exception const &)

- ea: `0x180002759`
- end: `0x18000275f`
- name: `??0exception@@QEAA@AEBV0@@Z_0`
- size: `6`
- prototype: `exception *__fastcall(exception *this, const struct exception *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001ec0`
- `0x180001f30`
- `0x180003a40`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBV0@@Z` at `0x180002759`

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
0x180002759  jmp     cs:__imp_??0exception@@QEAA@AEBV0@@Z
```
