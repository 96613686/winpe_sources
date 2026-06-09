# exception::~exception(void)

- ea: `0x1800026cd`
- end: `0x1800026d3`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void __fastcall(exception *this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001838`
- `0x180001850`
- `0x180001890`
- `0x1800018d0`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x1800026cd`

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
0x1800026cd  jmp     cs:__imp_??1exception@@UEAA@XZ
```
