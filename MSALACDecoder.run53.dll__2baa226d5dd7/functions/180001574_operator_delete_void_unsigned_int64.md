# operator delete(void *,unsigned __int64)

- ea: `0x180001574`
- end: `0x180001579`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `10`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001f78`
- `0x180002110`
- `0x1800023b0`
- `0x180004120`
- `0x180004190`
- `0x180004200`
- `0x180004250`
- `0x1800051b0`
- `0x180006980`
- `0x180006acc`

## callees

- `0x180001144`

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
0x180001574  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
