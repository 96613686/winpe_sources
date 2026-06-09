# operator delete(void *,unsigned __int64)

- ea: `0x180001518`
- end: `0x18000151d`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180007630`
- `0x180007674`

## callees

- `0x180001c88`

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
0x180001518  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
