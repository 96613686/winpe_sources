# operator delete(void *,unsigned __int64)

- ea: `0x180005070`
- end: `0x180005075`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `11`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800020e0`
- `0x180002840`
- `0x1800031f0`
- `0x180006d38`
- `0x180007270`
- `0x1800072a0`
- `0x1800072e0`
- `0x180007320`
- `0x180007360`
- `0x18000b670`
- `0x18000b6b0`

## callees

- `0x180005064`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x180005070  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
