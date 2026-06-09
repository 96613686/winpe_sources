# exception::~exception(void)

- ea: `0x180001cfc`
- end: `0x180001d02`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void __fastcall(exception *this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800015bc`
- `0x1800015d4`
- `0x1800015e0`
- `0x180001620`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x180001cfc`

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
0x180001cfc  jmp     cs:__imp_??1exception@@UEAA@XZ
```
