# operator delete(void *)

- ea: `0x180001434`
- end: `0x180001439`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001914`
- `0x180001cf0`
- `0x18001b34c`
- `0x18001ec68`
- `0x18001ed1c`
- `0x18001ee18`
- `0x18001f0bc`
- `0x1800201a0`

## callees

- `0x180002258`

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
0x180001434  jmp     free
```
