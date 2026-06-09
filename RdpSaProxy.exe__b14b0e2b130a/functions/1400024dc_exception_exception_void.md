# exception::~exception(void)

- ea: `0x1400024dc`
- end: `0x1400024e2`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void __fastcall(exception *this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140001c4c`
- `0x140001c64`
- `0x140001ca0`
- `0x140001ce0`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x1400024dc`

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
0x1400024dc  jmp     cs:__imp_??1exception@@UEAA@XZ
```
