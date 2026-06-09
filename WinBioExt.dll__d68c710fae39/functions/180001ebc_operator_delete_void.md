# operator delete(void *)

- ea: `0x180001ebc`
- end: `0x180001ec1`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800019e0`
- `0x1800019f0`

## callees

- `0x180002054`

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
0x180001ebc  jmp     free
```
