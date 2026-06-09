# exception::~exception(void)

- ea: `0x18000269c`
- end: `0x1800026a2`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void __fastcall(exception *this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001f08`
- `0x180001f20`
- `0x180001f30`
- `0x180001f70`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x18000269c`

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
0x18000269c  jmp     cs:__imp_??1exception@@UEAA@XZ
```
