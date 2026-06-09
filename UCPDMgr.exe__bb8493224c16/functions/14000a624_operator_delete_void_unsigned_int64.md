# operator delete(void *,unsigned __int64)

- ea: `0x14000a624`
- end: `0x14000a629`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140001360`
- `0x140002450`

## callees

- `0x14000aff8`

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
0x14000a624  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
