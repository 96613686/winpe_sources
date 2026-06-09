# operator delete(void *,unsigned __int64)

- ea: `0x18002aae4`
- end: `0x18002aae9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `13`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18001953c`
- `0x18001f208`
- `0x180025da4`
- `0x18002b860`
- `0x18002b898`
- `0x18002b8e0`
- `0x18002eb5c`
- `0x18002eb80`
- `0x18002ebbc`
- `0x18002ee08`
- `0x180037980`
- `0x1800379d0`
- `0x18003a310`

## callees

- `0x18002a6b0`

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
0x18002aae4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
