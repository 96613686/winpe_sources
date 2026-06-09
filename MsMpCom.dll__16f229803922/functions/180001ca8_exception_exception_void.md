# exception::~exception(void)

- ea: `0x180001ca8`
- end: `0x180001cae`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void(exception *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180001374`
- `0x18000138c`
- `0x1800013a0`
- `0x1800013e0`
- `0x180007bb0`
- `0x180007bd0`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x180001ca8`

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
0x180001ca8  jmp     cs:__imp_??1exception@@UEAA@XZ
```
