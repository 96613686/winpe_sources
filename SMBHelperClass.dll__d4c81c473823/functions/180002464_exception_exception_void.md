# exception::~exception(void)

- ea: `0x180002464`
- end: `0x18000246a`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void(exception *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001344`
- `0x18000135c`
- `0x1800013a0`
- `0x1800013e0`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x180002464`

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
0x180002464  jmp     cs:__imp_??1exception@@UEAA@XZ
```
