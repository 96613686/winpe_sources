# operator delete[](void *,unsigned __int64)

- ea: `0x180002aac`
- end: `0x180002ab1`
- name: `??_V@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180014f80`
- `0x18001505c`
- `0x180018a60`
- `0x180035e40`
- `0x180035ea8`

## callees

- `0x180001bc8`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete[](void *Block)
{
  operator delete(Block);
}

```

## disassembly

```asm
0x180002aac  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
