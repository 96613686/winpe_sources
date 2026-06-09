# operator delete(void *,unsigned __int64)

- ea: `0x180007660`
- end: `0x180007665`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `10`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001110`
- `0x180001f80`
- `0x180003690`
- `0x180005cd0`
- `0x1800067d0`
- `0x180006980`
- `0x180006ba0`
- `0x180006f30`
- `0x180007670`
- `0x18000c890`

## callees

- `0x180008034`

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
0x180007660  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
