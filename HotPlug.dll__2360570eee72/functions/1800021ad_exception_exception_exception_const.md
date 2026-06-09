# exception::exception(exception const &)

- ea: `0x1800021ad`
- end: `0x1800021b3`
- name: `??0exception@@QEAA@AEBV0@@Z_0`
- size: `6`
- prototype: `exception *(exception *__hidden this, const struct exception *)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000109c`
- `0x18000110c`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBV0@@Z` at `0x1800021ad`

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
0x1800021ad  jmp     cs:__imp_??0exception@@QEAA@AEBV0@@Z
```
