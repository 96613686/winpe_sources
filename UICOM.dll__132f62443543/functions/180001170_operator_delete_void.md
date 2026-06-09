# operator delete(void *)

- ea: `0x180001170`
- end: `0x180001175`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `10`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000117c`
- `0x18000226c`
- `0x180002390`
- `0x1800023d0`
- `0x1800051a0`
- `0x180005200`
- `0x180005440`
- `0x1800058d0`
- `0x1800059b0`
- `0x180005a10`

## callees

- `0x180001ae5`

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
0x180001170  jmp     free_0
```
