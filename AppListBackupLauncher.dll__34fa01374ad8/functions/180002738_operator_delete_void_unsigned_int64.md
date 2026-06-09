# operator delete(void *,unsigned __int64)

- ea: `0x180002738`
- end: `0x18000273d`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `15`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004428`
- `0x1800045b4`
- `0x180005878`
- `0x180005ac4`
- `0x180005bfc`
- `0x180006650`
- `0x180006690`
- `0x1800066d0`
- `0x180006710`
- `0x180006770`
- `0x1800067c0`
- `0x180006800`
- `0x180006860`
- `0x18000b6b0`
- `0x18000b770`

## callees

- `0x180002ca8`

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
0x180002738  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
