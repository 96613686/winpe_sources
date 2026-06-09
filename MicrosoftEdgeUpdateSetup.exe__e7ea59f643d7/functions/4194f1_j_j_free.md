# j_j__free

- ea: `0x4194f1`
- end: `0x4194f6`
- name: `j_j__free`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x4016fc`
- `0x401a73`
- `0x402b80`
- `0x402b8e`
- `0x404c4b`
- `0x404c5f`

## callees

- `0x4194ec`

## pseudocode

```c
// attributes: thunk
void __cdecl j_j__free(void *Block)
{
  j__free(Block);
}

```

## disassembly

```asm
0x4194f1  jmp     j__free
```
