# operator delete(void *,unsigned __int64)

- ea: `0x180010abc`
- end: `0x180010ac1`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180013c80`
- `0x180013cc0`

## callees

- `0x1800102c4`

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
0x180010abc  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
