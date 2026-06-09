# operator delete(void *)

- ea: `0x1400038e0`
- end: `0x1400038e5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140003218`
- `0x140003230`

## callees

- `0x140003a64`

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
0x1400038e0  jmp     free
```
