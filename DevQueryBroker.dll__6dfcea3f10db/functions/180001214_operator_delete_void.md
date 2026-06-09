# operator delete(void *)

- ea: `0x180001214`
- end: `0x180001219`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002c20`
- `0x18000314c`
- `0x18000383c`
- `0x180005940`

## callees

- `0x1800016f2`

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
0x180001214  jmp     free_0
```
