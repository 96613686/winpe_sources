# operator delete(void *)

- ea: `0x180001b80`
- end: `0x180001b85`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001544`
- `0x1800015e0`

## callees

- `0x180001fa4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free(Block);
}

```

## disassembly

```asm
0x180001b80  jmp     free
```
