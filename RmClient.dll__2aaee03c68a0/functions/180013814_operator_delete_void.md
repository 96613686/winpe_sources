# operator delete(void *)

- ea: `0x180013814`
- end: `0x180013819`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `20`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000a6d0`
- `0x18000ad00`
- `0x18000d740`
- `0x18000dcc0`
- `0x18000efa0`
- `0x18000efd8`
- `0x18000f018`
- `0x1800108a0`
- `0x1800136a8`
- `0x180014c00`
- `0x180014c40`
- `0x180016050`
- `0x180017fc0`
- `0x180018000`
- `0x180018040`
- `0x180018070`
- `0x1800180b0`
- `0x1800180f0`
- `0x1800191e0`
- `0x1800192e0`

## callees

- `0x180013de8`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free_0(Block);
}

```

## disassembly

```asm
0x180013814  jmp     free_0
```
