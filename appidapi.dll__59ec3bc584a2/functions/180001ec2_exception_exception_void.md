# exception::~exception(void)

- ea: `0x180001ec2`
- end: `0x180001ec8`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void(exception *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001374`
- `0x1800013d0`
- `0x180009670`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x180001ec2`

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
0x180001ec2  jmp     cs:__imp_??1exception@@UEAA@XZ
```
