# operator delete(void *,unsigned __int64)

- ea: `0x1800131e4`
- end: `0x1800131e9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `39`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004a50`
- `0x180004ab0`
- `0x180004b00`
- `0x180004b70`
- `0x180005c50`
- `0x180006070`
- `0x1800061e0`
- `0x1800074c0`
- `0x180008370`
- `0x18000c990`
- `0x18000cec0`
- `0x18000e820`
- `0x18000ed80`
- `0x18000ef50`
- `0x180010b34`
- `0x180011320`
- `0x180014440`
- `0x180014480`
- `0x1800144d0`
- `0x180014520`
- `0x1800153b0`
- `0x1800153f0`
- `0x180015430`
- `0x1800159b0`
- `0x180016560`
- `0x1800184c0`
- `0x18001969c`
- `0x18001aa83`
- `0x18001aaa9`
- `0x18001aacf`
- `0x18001aaf5`
- `0x18001ab1b`
- `0x18001ab41`
- `0x18001abc6`
- `0x18001af27`
- `0x18001af4d`
- `0x18001b081`
- `0x18001b0a7`
- `0x18001b60a`

## callees

- `0x18001382c`

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
0x1800131e4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
