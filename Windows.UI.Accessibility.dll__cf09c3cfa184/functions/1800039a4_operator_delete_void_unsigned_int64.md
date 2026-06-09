# operator delete(void *,unsigned __int64)

- ea: `0x1800039a4`
- end: `0x1800039a9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `56`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005d00`
- `0x180005d40`
- `0x1800079f0`
- `0x180009440`
- `0x180009480`
- `0x18000df78`
- `0x18000e010`
- `0x18000e880`
- `0x18000e900`
- `0x180010dec`
- `0x180013c70`
- `0x180013ca0`
- `0x180013ce0`
- `0x180013d20`
- `0x180013d60`
- `0x180013da0`
- `0x180013de0`
- `0x180013e20`
- `0x180013e60`
- `0x180013ea0`
- `0x180013ee0`
- `0x180013f20`
- `0x180016ffc`
- `0x180019a70`
- `0x18001d26c`
- `0x180020c20`
- `0x180020c60`
- `0x180020ca0`
- `0x180020ce0`
- `0x180020d20`
- `0x180020d60`
- `0x180022d00`
- `0x180022d50`
- `0x180023510`
- `0x180025db0`
- `0x180025df0`
- `0x180025e30`
- `0x1800260f0`
- `0x180027830`
- `0x180027870`
- `0x1800278b0`
- `0x1800278f0`
- `0x180028f9c`
- `0x180029060`
- `0x1800290a0`
- `0x1800298f0`
- `0x18002d064`
- `0x18002d0b0`
- `0x180032c18`
- `0x180032e80`

## callees

- `0x180003f50`

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
0x1800039a4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
