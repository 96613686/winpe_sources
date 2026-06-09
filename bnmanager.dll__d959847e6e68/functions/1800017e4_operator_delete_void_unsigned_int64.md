# operator delete(void *,unsigned __int64)

- ea: `0x1800017e4`
- end: `0x1800017e9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `11`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800030a0`
- `0x18000322c`
- `0x180003be4`
- `0x180005178`
- `0x180005970`
- `0x1800059a0`
- `0x1800059d0`
- `0x180005a10`
- `0x180005a50`
- `0x180005a90`
- `0x18000c510`

## callees

- `0x180001c30`

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
0x1800017e4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
