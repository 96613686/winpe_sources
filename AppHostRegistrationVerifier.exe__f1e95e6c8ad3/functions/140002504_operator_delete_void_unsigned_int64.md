# operator delete(void *,unsigned __int64)

- ea: `0x140002504`
- end: `0x140002509`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `15`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140003cd8`
- `0x140004d80`
- `0x140004dc0`
- `0x14000a0c4`
- `0x14000a670`
- `0x14000a6c0`
- `0x14000a6fc`
- `0x14000a740`
- `0x14000a790`
- `0x14000a7d0`
- `0x14000a810`
- `0x14000a850`
- `0x14000a890`
- `0x14000a934`
- `0x140010398`

## callees

- `0x140002b7c`

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
0x140002504  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
