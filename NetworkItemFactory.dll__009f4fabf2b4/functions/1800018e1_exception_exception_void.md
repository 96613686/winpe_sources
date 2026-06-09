# exception::~exception(void)

- ea: `0x1800018e1`
- end: `0x1800018e7`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void(exception *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001174`
- `0x18000118c`
- `0x1800011a0`
- `0x1800011e0`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x1800018e1`

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
0x1800018e1  jmp     cs:__imp_??1exception@@UEAA@XZ
```
