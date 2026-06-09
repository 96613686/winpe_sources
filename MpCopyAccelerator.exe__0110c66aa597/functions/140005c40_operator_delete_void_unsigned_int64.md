# operator delete(void *,unsigned __int64)

- ea: `0x140005c40`
- end: `0x140005c45`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `36`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14000283c`
- `0x140002e30`
- `0x14000329c`
- `0x140003310`
- `0x140003414`
- `0x14000355c`
- `0x140003814`
- `0x140003a24`
- `0x140003bc0`
- `0x140003c50`
- `0x1400054e8`
- `0x140005c50`
- `0x14001d230`
- `0x14001d2b4`
- `0x14001d330`
- `0x14001d464`
- `0x14001d700`
- `0x14001e068`
- `0x14001e268`
- `0x140020578`
- `0x140020594`
- `0x140020610`
- `0x1400221f4`
- `0x1400222c0`
- `0x140022568`
- `0x140022ac4`
- `0x140022c68`
- `0x140022d28`
- `0x1400231f0`
- `0x1400234b0`
- `0x1400235e4`
- `0x140023d3c`
- `0x1400242c4`
- `0x1400244c4`
- `0x14002476c`
- `0x140026395`

## callees

- `0x14000618c`

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
0x140005c40  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
