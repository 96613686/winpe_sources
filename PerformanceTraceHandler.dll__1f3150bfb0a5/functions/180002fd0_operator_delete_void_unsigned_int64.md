# operator delete(void *,unsigned __int64)

- ea: `0x180002fd0`
- end: `0x180002fd5`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `18`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004d50`
- `0x180004d90`
- `0x180004dd0`
- `0x180004e10`
- `0x18000b7b0`
- `0x18000b7f0`
- `0x18000b830`
- `0x18000b870`
- `0x18000b8a0`
- `0x18000b8e0`
- `0x18000f528`
- `0x180010e70`
- `0x180010ec0`
- `0x1800148a4`
- `0x1800148f0`
- `0x180014930`
- `0x180014970`
- `0x180019984`

## callees

- `0x180003074`

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
0x180002fd0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
