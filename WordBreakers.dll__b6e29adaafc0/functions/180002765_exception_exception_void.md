# exception::~exception(void)

- ea: `0x180002765`
- end: `0x18000276b`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void __fastcall(exception *this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001f90`
- `0x180001fa8`
- `0x180001fc0`
- `0x180002000`
- `0x180003d14`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x180002765`

## pseudocode

```c
// attributes: thunk
void __fastcall exception::~exception(exception *this)
{
  __imp_??1exception@@UEAA@XZ(this);
}

```

## disassembly

```asm
0x180002765  jmp     cs:__imp_??1exception@@UEAA@XZ
```
