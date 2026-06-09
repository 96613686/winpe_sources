# exception::~exception(void)

- ea: `0x14000213c`
- end: `0x140002142`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void __fastcall(exception *this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140001b18`
- `0x140001b30`
- `0x140001b40`
- `0x140001b80`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x14000213c`

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
0x14000213c  jmp     cs:__imp_??1exception@@UEAA@XZ
```
