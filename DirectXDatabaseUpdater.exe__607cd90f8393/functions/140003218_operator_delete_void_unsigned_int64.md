# operator delete(void *,unsigned __int64)

- ea: `0x140003218`
- end: `0x14000321d`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `19`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140004f44`
- `0x1400064d0`
- `0x140006510`
- `0x140006550`
- `0x14000658c`
- `0x1400065d0`
- `0x140006610`
- `0x140006650`
- `0x140006690`
- `0x14000e5e0`
- `0x140012030`
- `0x14001206c`
- `0x14001366c`
- `0x14001376c`
- `0x1400140c0`
- `0x140014820`
- `0x14001485c`
- `0x1400148a0`
- `0x140018e9f`

## callees

- `0x1400038e0`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x140003218  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
