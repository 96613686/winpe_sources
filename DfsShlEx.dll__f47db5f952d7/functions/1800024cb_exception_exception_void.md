# exception::~exception(void)

- ea: `0x1800024cb`
- end: `0x1800024d1`
- name: `??1exception@@UEAA@XZ_0`
- size: `6`
- prototype: `void(exception *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001278`
- `0x180001290`
- `0x1800012d0`
- `0x180001310`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x1800024cb`

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
0x1800024cb  jmp     cs:__imp_??1exception@@UEAA@XZ
```
