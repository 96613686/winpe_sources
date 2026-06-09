# operator delete(void *,unsigned __int64)

- ea: `0x180001e90`
- end: `0x180001e95`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `27`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003b50`
- `0x180003b90`
- `0x180008fe0`
- `0x180009020`
- `0x180009060`
- `0x1800090a0`
- `0x18000a3e0`
- `0x18000a410`
- `0x18000a440`
- `0x18000a6d0`
- `0x18000b1f0`
- `0x18000c5d0`
- `0x18000ef08`
- `0x18000ef80`
- `0x18000efe0`
- `0x18000f020`
- `0x18000f0a0`
- `0x18000f120`
- `0x18000f1a0`
- `0x18000f1e0`
- `0x180012af4`
- `0x1800146b0`
- `0x180014e14`
- `0x180016450`
- `0x180016480`
- `0x1800166e8`
- `0x180016b00`

## callees

- `0x180001ecc`

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
0x180001e90  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
