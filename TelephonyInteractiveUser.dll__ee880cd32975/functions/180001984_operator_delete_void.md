# operator delete(void *)

- ea: `0x180001984`
- end: `0x180001989`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `27`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800021b4`
- `0x1800077a0`
- `0x180007800`
- `0x180007880`
- `0x180007900`
- `0x180007960`
- `0x1800079c0`
- `0x1800079ec`
- `0x180007a24`
- `0x180007a70`
- `0x180007ad0`
- `0x180007b30`
- `0x180007b60`
- `0x180007bb0`
- `0x180007bf0`
- `0x180007c30`
- `0x180007c70`
- `0x180007cb0`
- `0x180007d20`
- `0x180007d60`
- `0x180007db0`
- `0x18000bd40`
- `0x18000be50`
- `0x18000bf50`
- `0x18000c050`
- `0x180011840`
- `0x180011ba0`

## callees

- `0x180002784`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free(Block);
}

```

## disassembly

```asm
0x180001984  jmp     free
```
