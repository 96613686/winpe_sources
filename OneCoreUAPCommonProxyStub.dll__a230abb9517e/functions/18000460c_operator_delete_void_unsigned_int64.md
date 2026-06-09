# operator delete(void *,unsigned __int64)

- ea: `0x18000460c`
- end: `0x180004611`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800069ec`
- `0x180007670`
- `0x1800076b0`
- `0x1800076f0`
- `0x180007730`

## callees

- `0x18000469c`

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
0x18000460c  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
