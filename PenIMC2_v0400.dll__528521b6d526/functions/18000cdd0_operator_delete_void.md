# operator delete(void *)

- ea: `0x18000cdd0`
- end: `0x18000cdd5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000ce0c`

## callees

- `0x18000e0f0`

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
0x18000cdd0  jmp     free_0
```
