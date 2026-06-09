# operator delete(void *,unsigned __int64)

- ea: `0x18002a400`
- end: `0x18002a405`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `65`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800025a0`
- `0x180004ce0`
- `0x180005e00`
- `0x180006460`
- `0x180007d00`
- `0x180007ee4`
- `0x180009860`
- `0x1800099b0`
- `0x18000ae1c`
- `0x18000b714`
- `0x18000b788`
- `0x18000d2f0`
- `0x18000d5c0`
- `0x18001402c`
- `0x180015ea0`
- `0x18001788c`
- `0x180018780`
- `0x180018860`
- `0x180019060`
- `0x180019764`
- `0x18001cb08`
- `0x18001d2d0`
- `0x18001d818`
- `0x18001e6e0`
- `0x18001e8a0`
- `0x18001ed70`
- `0x18001ee80`
- `0x18001eef0`
- `0x18001ef50`
- `0x18001f130`
- `0x18001f5c0`
- `0x18001fa54`
- `0x1800211b0`
- `0x180025308`
- `0x180028b5c`
- `0x18002c030`
- `0x18002c070`
- `0x18002c0b0`
- `0x18002cf60`
- `0x18002cf90`
- `0x18002cfc0`
- `0x18002d000`
- `0x18002d040`
- `0x18002d080`
- `0x180030350`
- `0x180030390`
- `0x1800303cc`
- `0x180030410`
- `0x18003044c`
- `0x180030490`

## callees

- `0x18002a43c`

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
0x18002a400  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
