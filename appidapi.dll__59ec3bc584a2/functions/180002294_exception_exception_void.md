# exception::exception(void)

- ea: `0x180002294`
- end: `0x18000229a`
- name: `??0exception@@QEAA@XZ_0`
- size: `6`
- prototype: `exception *(exception *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000115c`
- `0x1800012b8`

## import_xrefs

- `msvcrt!??0exception@@QEAA@XZ` at `0x180002294`

## pseudocode

```c
// attributes: thunk
exception *__fastcall exception::exception(exception *this)
{
  return __imp_??0exception@@QEAA@XZ(this);
}

```

## disassembly

```asm
0x180002294  jmp     cs:__imp_??0exception@@QEAA@XZ
```
