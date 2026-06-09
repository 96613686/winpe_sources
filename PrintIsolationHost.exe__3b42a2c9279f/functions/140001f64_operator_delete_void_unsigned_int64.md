# operator delete(void *,unsigned __int64)

- ea: `0x140001f64`
- end: `0x140001f69`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `7`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140003180`
- `0x1400031e0`
- `0x140005aa0`
- `0x140005c30`
- `0x140006220`
- `0x1400062a0`
- `0x140006bb0`

## callees

- `0x140001960`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x140001f64  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
