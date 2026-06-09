# operator delete(void *,unsigned __int64)

- ea: `0x1400026b8`
- end: `0x1400026bd`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `56`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400048f0`
- `0x140006190`
- `0x140006790`
- `0x140007010`
- `0x14000735c`
- `0x1400073c4`
- `0x1400074dc`
- `0x140007624`
- `0x140007fa0`
- `0x140007fc4`
- `0x140008060`
- `0x1400080d0`
- `0x140008160`
- `0x140008230`
- `0x14000853c`
- `0x1400085cc`
- `0x1400089d0`
- `0x140008a10`
- `0x14000de8c`
- `0x14000e884`
- `0x14000e940`
- `0x14000fd80`
- `0x14000fdc0`
- `0x14000fe00`
- `0x140010240`
- `0x140012ffc`
- `0x14001306c`
- `0x140013370`
- `0x1400133d4`
- `0x1400137e4`
- `0x140013808`
- `0x140013914`
- `0x140014770`
- `0x140015274`
- `0x1400155e4`
- `0x1400156fc`
- `0x140015720`
- `0x140015798`
- `0x140015820`
- `0x1400159f4`
- `0x140015b40`
- `0x140015cdc`
- `0x140015d7c`
- `0x140016020`
- `0x140016060`
- `0x1400160c0`
- `0x1400166ec`
- `0x1400168e0`
- `0x14001a9cc`
- `0x14001abc8`

## callees

- `0x140002ce0`

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
0x1400026b8  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
