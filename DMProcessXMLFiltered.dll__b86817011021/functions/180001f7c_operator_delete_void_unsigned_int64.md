# operator delete(void *,unsigned __int64)

- ea: `0x180001f7c`
- end: `0x180001f81`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003430`
- `0x180003470`

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
0x180001f7c  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
