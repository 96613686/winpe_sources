# operator delete(void *,unsigned __int64)

- ea: `0x1400015f4`
- end: `0x1400015f9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `52`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400029a0`
- `0x1400029bc`
- `0x140002a10`
- `0x140002a50`
- `0x140002c18`
- `0x140002ce8`
- `0x140002f00`
- `0x14000329c`
- `0x1400036d0`
- `0x140003a94`
- `0x140003c94`
- `0x140003cf0`
- `0x140003d24`
- `0x140003db4`
- `0x140003e58`
- `0x140004588`
- `0x140004e84`
- `0x140005e1c`
- `0x140006008`
- `0x140006714`
- `0x140007248`
- `0x140007384`
- `0x140007448`
- `0x140007538`
- `0x140008610`
- `0x140008650`
- `0x140008690`
- `0x1400086d0`
- `0x14000cc78`
- `0x14000ce04`
- `0x14000d5a8`
- `0x14000d640`
- `0x14000de3c`
- `0x14000e1c8`
- `0x14000e220`
- `0x14000e4c0`
- `0x14000e6b0`
- `0x14000e800`
- `0x14000ea5c`
- `0x14000eb7c`
- `0x14000ed24`
- `0x14000f194`
- `0x14000f3dc`
- `0x14000f8f0`
- `0x14000fb20`
- `0x140011260`
- `0x140011d80`
- `0x140011e50`
- `0x140011ef0`
- `0x140012343`

## callees

- `0x140001b90`

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
0x1400015f4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
