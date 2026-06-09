# operator delete[](void *,unsigned __int64)

- ea: `0x180002388`
- end: `0x18000238d`
- name: `??_V@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180012d34`

## callees

- `0x180001450`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete[](void *Block)
{
  operator delete(Block);
}

```

## disassembly

```asm
0x180002388  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
