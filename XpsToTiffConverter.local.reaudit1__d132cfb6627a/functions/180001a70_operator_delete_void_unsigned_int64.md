# operator delete(void *,unsigned __int64)

- ea: `0x180001a70`
- end: `0x180001a75`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `16`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800039b0`
- `0x1800039f0`
- `0x180003a30`
- `0x180003a70`
- `0x180009c48`
- `0x180009cd4`
- `0x180009d6c`
- `0x180009eb0`
- `0x18000a640`
- `0x18000a6e0`
- `0x18000a760`
- `0x18000b5d8`
- `0x18000b850`
- `0x18000bd08`
- `0x18000c1d0`
- `0x18000d78c`

## callees

- `0x180001f8c`

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
0x180001a70  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
