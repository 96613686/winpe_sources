# operator delete(void *,unsigned __int64)

- ea: `0x180002490`
- end: `0x180002495`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `22`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005310`
- `0x180005350`
- `0x180005390`
- `0x1800053d0`
- `0x180005410`
- `0x180005450`
- `0x18000ac6c`
- `0x18000b8b0`
- `0x18000b908`
- `0x18000b9c0`
- `0x18000b9e8`
- `0x18000ba14`
- `0x18000bac8`
- `0x18000c280`
- `0x18000d400`
- `0x18000d440`
- `0x18000d47c`
- `0x18000d4b0`
- `0x18000e220`
- `0x18000ea2c`
- `0x18000ecb0`
- `0x180010ca4`

## callees

- `0x18000298c`

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
0x180002490  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
