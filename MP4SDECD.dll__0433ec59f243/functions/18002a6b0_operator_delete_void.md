# operator delete(void *)

- ea: `0x18002a6b0`
- end: `0x18002a6b5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `20`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180012cd0`
- `0x180012e50`
- `0x180013fa0`
- `0x1800149ac`
- `0x18001863c`
- `0x18001932c`
- `0x18001dea0`
- `0x18001e6c4`
- `0x18001e858`
- `0x18001ea58`
- `0x180025cbc`
- `0x180025dd0`
- `0x180029020`
- `0x18002aae4`
- `0x18002bc14`
- `0x18002e240`
- `0x18002e720`
- `0x18002ebbc`
- `0x18003a2b8`
- `0x1800447ac`

## callees

- `0x18002b364`

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
0x18002a6b0  jmp     free
```
