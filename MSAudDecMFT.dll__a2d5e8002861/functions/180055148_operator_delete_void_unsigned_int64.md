# operator delete(void *,unsigned __int64)

- ea: `0x180055148`
- end: `0x18005514d`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `15`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18002ff70`
- `0x1800445b0`
- `0x180056c60`
- `0x180056ca0`
- `0x180058b80`
- `0x180058bc0`
- `0x180058c00`
- `0x18006bf40`
- `0x18006bf80`
- `0x18006bfc0`
- `0x18006bffc`
- `0x18006c5a4`
- `0x18009468c`
- `0x180096142`
- `0x1800962d3`

## callees

- `0x18004cf10`

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
0x180055148  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
