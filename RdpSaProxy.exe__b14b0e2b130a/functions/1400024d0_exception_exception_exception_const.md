# exception::exception(exception const &)

- ea: `0x1400024d0`
- end: `0x1400024d6`
- name: `??0exception@@QEAA@AEBV0@@Z_0`
- size: `6`
- prototype: `exception *__fastcall(exception *this, const struct exception *)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140001b7c`
- `0x140001bec`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBV0@@Z` at `0x1400024d0`

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
0x1400024d0  jmp     cs:__imp_??0exception@@QEAA@AEBV0@@Z
```
