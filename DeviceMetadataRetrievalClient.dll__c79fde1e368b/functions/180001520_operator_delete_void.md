# operator delete(void *)

- ea: `0x180001520`
- end: `0x180001525`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `15`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800041a0`
- `0x180006904`
- `0x180008544`
- `0x18000a4c4`
- `0x18000afd0`
- `0x18000dabc`
- `0x18000f33c`
- `0x180011310`
- `0x180011390`
- `0x180011730`
- `0x180011d50`
- `0x180012a64`
- `0x180012b10`
- `0x180013210`
- `0x180013240`

## callees

- `0x180001a4e`

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
0x180001520  jmp     free_0
```
