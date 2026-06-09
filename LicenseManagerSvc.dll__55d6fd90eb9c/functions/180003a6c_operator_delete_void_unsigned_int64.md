# operator delete(void *,unsigned __int64)

- ea: `0x180003a6c`
- end: `0x180003a71`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `6`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005270`
- `0x1800052a0`
- `0x1800052d0`
- `0x180005310`
- `0x1800082d0`
- `0x180008310`

## callees

- `0x180003a60`

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
0x180003a6c  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
