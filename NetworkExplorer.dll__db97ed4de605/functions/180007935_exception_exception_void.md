# exception::~exception(void)

- ea: `0x180007935`
- end: `0x18000793b`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void(exception *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180007328`
- `0x180007340`
- `0x180007350`
- `0x180007390`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x180007935`

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
0x180007935  jmp     cs:__imp_??1exception@@UEAA@XZ
```
