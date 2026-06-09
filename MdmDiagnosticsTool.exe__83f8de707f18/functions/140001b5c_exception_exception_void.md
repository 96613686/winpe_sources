# exception::~exception(void)

- ea: `0x140001b5c`
- end: `0x140001b62`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void(exception *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1400015ec`
- `0x140001604`
- `0x140001610`
- `0x140001650`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x140001b5c`

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
0x140001b5c  jmp     cs:__imp_??1exception@@UEAA@XZ
```
