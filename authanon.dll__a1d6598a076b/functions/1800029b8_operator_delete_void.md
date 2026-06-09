# operator delete(void *)

- ea: `0x1800029b8`
- end: `0x1800029bd`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `6`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800032a0`
- `0x1800033e0`
- `0x180003420`
- `0x1800040c0`
- `0x180004340`
- `0x180004380`

## callees

- `0x180002e96`

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
0x1800029b8  jmp     free_0
```
