# exception::~exception(void)

- ea: `0x140001e79`
- end: `0x140001e7f`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void __fastcall(exception *this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140001134`
- `0x14000114c`
- `0x140001190`
- `0x1400011d0`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x140001e79`

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
0x140001e79  jmp     cs:__imp_??1exception@@UEAA@XZ
```
