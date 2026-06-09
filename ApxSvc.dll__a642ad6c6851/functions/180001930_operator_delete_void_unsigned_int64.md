# operator delete(void *,unsigned __int64)

- ea: `0x180001930`
- end: `0x180001935`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002e80`
- `0x180002ec0`
- `0x180005bc4`
- `0x18000629c`
- `0x180006740`
- `0x1800071b0`
- `0x1800074d0`
- `0x180008190`

## callees

- `0x180001544`

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
0x180001930  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
