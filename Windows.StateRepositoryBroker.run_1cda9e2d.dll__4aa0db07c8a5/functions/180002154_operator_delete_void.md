# operator delete(void *)

- ea: `0x180002154`
- end: `0x180002159`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `11`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002160`
- `0x180002170`
- `0x180002740`
- `0x180003ee4`
- `0x180006f60`
- `0x180006fa0`
- `0x180007510`
- `0x180009970`
- `0x1800099c0`
- `0x180009d80`
- `0x18000a1b8`

## callees

- `0x1800028c4`

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
0x180002154  jmp     free
```
