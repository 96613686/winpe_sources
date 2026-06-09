# operator delete(void *)

- ea: `0x180001390`
- end: `0x180001395`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003700`
- `0x180003730`

## callees

- `0x18000195c`

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
0x180001390  jmp     free_0
```
