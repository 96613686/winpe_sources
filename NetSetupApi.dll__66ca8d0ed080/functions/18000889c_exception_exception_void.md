# exception::~exception(void)

- ea: `0x18000889c`
- end: `0x1800088a2`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void __fastcall(exception *this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180008070`
- `0x1800080e0`
- `0x1800081bc`
- `0x1800081d0`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x18000889c`

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
0x18000889c  jmp     cs:__imp_??1exception@@UEAA@XZ
```
