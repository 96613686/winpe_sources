# operator delete(void *,unsigned __int64)

- ea: `0x180001f30`
- end: `0x180001f35`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180021850`
- `0x180021f80`
- `0x180023860`
- `0x1800238a0`

## callees

- `0x180002498`

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
0x180001f30  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
