# operator delete(void *)

- ea: `0x1800080d4`
- end: `0x1800080d9`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `19`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005060`
- `0x180005558`
- `0x180007274`
- `0x1800072d8`
- `0x18000732c`
- `0x1800081d0`
- `0x1800088d0`
- `0x180009600`
- `0x180009640`
- `0x18000b4b8`
- `0x18000cfd0`
- `0x18000d420`
- `0x18000eb78`
- `0x18000ec70`
- `0x18000f870`
- `0x180010f18`
- `0x180012226`
- `0x1800141cc`
- `0x1800142b8`

## callees

- `0x18000891e`

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
0x1800080d4  jmp     free_0
```
