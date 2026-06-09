# operator delete(void *,unsigned __int64)

- ea: `0x18001d364`
- end: `0x18001d369`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `55`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180009340`
- `0x180009740`
- `0x18000a7d0`
- `0x18000b3d0`
- `0x18000bb50`
- `0x18000bbc0`
- `0x18000cc40`
- `0x18000e804`
- `0x18000ec10`
- `0x18000f370`
- `0x18000f680`
- `0x180011e10`
- `0x180012440`
- `0x180012480`
- `0x1800126a0`
- `0x1800126e0`
- `0x180013f60`
- `0x180014470`
- `0x180015aa0`
- `0x180015c1c`
- `0x180016970`
- `0x180016b40`
- `0x180017368`
- `0x180019130`
- `0x180019768`
- `0x18001dec0`
- `0x18001df00`
- `0x18001e810`
- `0x18001e850`
- `0x18001e890`
- `0x18001e8d0`
- `0x18001e900`
- `0x18001e950`
- `0x18001f950`
- `0x18001fea0`
- `0x180020590`
- `0x1800205d0`
- `0x180020b88`
- `0x1800212e0`
- `0x1800217b0`
- `0x1800218e0`
- `0x180021a70`
- `0x180021ab0`
- `0x1800232e0`
- `0x180023360`
- `0x1800234f0`
- `0x180024920`
- `0x180024c40`
- `0x180024d94`
- `0x180025ab2`

## callees

- `0x18001d86c`

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
0x18001d364  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
