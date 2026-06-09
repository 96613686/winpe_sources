# operator delete(void *)

- ea: `0x18004cf10`
- end: `0x18004cf15`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `13`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004814`
- `0x18003004c`
- `0x1800310a0`
- `0x180031154`
- `0x18003d4a0`
- `0x180042270`
- `0x180055148`
- `0x180055160`
- `0x18006bdd0`
- `0x18006be1c`
- `0x18006c2c4`
- `0x18006c394`
- `0x18006d5bc`

## callees

- `0x18004dccc`

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
0x18004cf10  jmp     free
```
