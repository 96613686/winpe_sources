# operator delete(void *,unsigned __int64)

- ea: `0x180002540`
- end: `0x180002545`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `13`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003e00`
- `0x180003e40`
- `0x180007b50`
- `0x180007b90`
- `0x180007bd0`
- `0x180007c30`
- `0x18000a1a8`
- `0x18000c284`
- `0x18000c310`
- `0x18000cc80`
- `0x18000cd40`
- `0x18000cdc0`
- `0x18000d4fc`

## callees

- `0x180002a7c`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x180002540  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
