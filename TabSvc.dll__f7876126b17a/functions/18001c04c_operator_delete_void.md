# operator delete(void *)

- ea: `0x18001c04c`
- end: `0x18001c051`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `12`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180010d90`
- `0x180011400`
- `0x1800117c0`
- `0x1800119b0`
- `0x1800169d0`
- `0x18001a8c4`
- `0x18001bc04`
- `0x18001c020`
- `0x180025bbc`
- `0x1800282a0`
- `0x18002e6e0`
- `0x18002e710`

## callees

- `0x18001c654`

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
0x18001c04c  jmp     free
```
