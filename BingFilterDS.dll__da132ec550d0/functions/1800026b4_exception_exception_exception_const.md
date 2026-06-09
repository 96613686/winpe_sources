# exception::exception(exception const &)

- ea: `0x1800026b4`
- end: `0x1800026ba`
- name: `??0exception@@QEAA@AEBV0@@Z_0`
- size: `6`
- prototype: `exception *__fastcall(exception *this, const struct exception *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001de0`
- `0x180001e50`
- `0x180001ea8`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBV0@@Z` at `0x1800026b4`

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
0x1800026b4  jmp     cs:__imp_??0exception@@QEAA@AEBV0@@Z
```
