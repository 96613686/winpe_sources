# exception::~exception(void)

- ea: `0x14000256c`
- end: `0x140002572`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void(exception *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140001f48`
- `0x140001f60`
- `0x140001f70`
- `0x140001fb0`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x14000256c`

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
0x14000256c  jmp     cs:__imp_??1exception@@UEAA@XZ
```
