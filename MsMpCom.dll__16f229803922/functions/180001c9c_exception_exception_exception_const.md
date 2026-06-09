# exception::exception(exception const &)

- ea: `0x180001c9c`
- end: `0x180001ca2`
- name: `??0exception@@QEAA@AEBV0@@Z_0`
- size: `6`
- prototype: `exception *(exception *__hidden this, const struct exception *)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800012a4`
- `0x180001314`
- `0x180007ae4`
- `0x180007b0c`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBV0@@Z` at `0x180001c9c`

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
0x180001c9c  jmp     cs:__imp_??0exception@@QEAA@AEBV0@@Z
```
