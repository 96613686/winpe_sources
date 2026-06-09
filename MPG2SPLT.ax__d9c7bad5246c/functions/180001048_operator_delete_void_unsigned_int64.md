# operator delete(void *,unsigned __int64)

- ea: `0x180001048`
- end: `0x18000104d`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `202`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002190`
- `0x180003044`
- `0x1800030c8`
- `0x1800031a0`
- `0x180003200`
- `0x180003240`
- `0x180003280`
- `0x180004890`
- `0x18000676c`
- `0x18000681c`
- `0x180006860`
- `0x180007430`
- `0x180007490`
- `0x1800074d0`
- `0x180007510`
- `0x180007550`
- `0x1800076c0`
- `0x180008750`
- `0x18000a470`
- `0x18000a4b0`
- `0x18000a870`
- `0x18000b934`
- `0x18000b9f0`
- `0x18000ba30`
- `0x18000ba70`
- `0x18000bab0`
- `0x18000bb00`
- `0x18000bb40`
- `0x18000bda0`
- `0x18000bed0`
- `0x18000cf40`
- `0x18000d148`
- `0x18000d960`
- `0x18000e280`
- `0x18000e520`
- `0x18000ef40`
- `0x18000f010`
- `0x18000f420`
- `0x18000f470`
- `0x18000f610`
- `0x18000fb20`
- `0x180011120`
- `0x180011190`
- `0x180011200`
- `0x180011270`
- `0x1800112e0`
- `0x180011350`
- `0x1800113c0`
- `0x180011430`
- `0x1800114a0`

## callees

- `0x180001060`

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
0x180001048  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
