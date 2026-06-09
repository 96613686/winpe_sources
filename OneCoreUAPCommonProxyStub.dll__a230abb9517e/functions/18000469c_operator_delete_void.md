# operator delete(void *)

- ea: `0x18000469c`
- end: `0x1800046a1`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000460c`
- `0x180004620`

## callees

- `0x180004596`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free(Block);
}

```

## disassembly

```asm
0x18000469c  jmp     free
```
