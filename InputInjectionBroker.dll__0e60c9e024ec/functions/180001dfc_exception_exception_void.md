# exception::~exception(void)

- ea: `0x180001dfc`
- end: `0x180001e02`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void __fastcall(exception *this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800016c8`
- `0x1800016e0`
- `0x1800016f0`
- `0x180001730`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x180001dfc`

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
0x180001dfc  jmp     cs:__imp_??1exception@@UEAA@XZ
```
