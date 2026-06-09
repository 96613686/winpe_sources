# exception::~exception(void)

- ea: `0x140001b2c`
- end: `0x140001b32`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void __fastcall(exception *this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1400015bc`
- `0x1400015d4`
- `0x1400015e0`
- `0x140001620`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x140001b2c`

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
0x140001b2c  jmp     cs:__imp_??1exception@@UEAA@XZ
```
