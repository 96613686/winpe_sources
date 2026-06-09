# operator delete(void *)

- ea: `0x140001008`
- end: `0x14000100d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `11`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140001aa4`
- `0x140001bf4`
- `0x140002014`
- `0x140002480`
- `0x140002a00`
- `0x1400031c4`
- `0x140003554`
- `0x1400035bc`
- `0x140003804`
- `0x140003884`
- `0x140004010`

## callees

- `0x1400013ed`

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
0x140001008  jmp     free_0
```
