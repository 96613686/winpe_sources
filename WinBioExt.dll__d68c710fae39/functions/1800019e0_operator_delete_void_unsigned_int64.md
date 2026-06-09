# operator delete(void *,unsigned __int64)

- ea: `0x1800019e0`
- end: `0x1800019e5`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `13`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800030e0`
- `0x180003120`
- `0x180006380`
- `0x1800063c0`
- `0x18000698c`
- `0x180006af0`
- `0x180006d18`
- `0x180006e30`
- `0x180006e90`
- `0x1800077b0`
- `0x1800077f0`
- `0x18000a4a5`
- `0x18000a610`

## callees

- `0x180001ebc`

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
0x1800019e0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
