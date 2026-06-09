# operator delete(void *,unsigned __int64)

- ea: `0x180002f90`
- end: `0x180002f95`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `12`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004530`
- `0x180004570`
- `0x1800087a0`
- `0x1800087f0`
- `0x180008830`
- `0x180008870`
- `0x1800088d0`
- `0x180008930`
- `0x18000dcdc`
- `0x18000df78`
- `0x18000e2b0`
- `0x18000e2ec`

## callees

- `0x18000343c`

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
0x180002f90  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
