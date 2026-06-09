# operator delete(void *)

- ea: `0x180003990`
- end: `0x180003995`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `7`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003930`
- `0x180003940`
- `0x180008408`
- `0x18001af70`
- `0x18001b548`
- `0x18001b7b8`
- `0x180022994`

## callees

- `0x180003fa4`

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
0x180003990  jmp     free
```
