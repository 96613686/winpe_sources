# exception::exception(exception const &)

- ea: `0x140001e6d`
- end: `0x140001e73`
- name: `??0exception@@QEAA@AEBV0@@Z_0`
- size: `6`
- prototype: `exception *__fastcall(exception *this, const struct exception *)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140001064`
- `0x1400010d4`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBV0@@Z` at `0x140001e6d`

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
0x140001e6d  jmp     cs:__imp_??0exception@@QEAA@AEBV0@@Z
```
