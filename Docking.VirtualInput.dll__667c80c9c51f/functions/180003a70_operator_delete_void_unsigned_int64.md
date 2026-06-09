# operator delete(void *,unsigned __int64)

- ea: `0x180003a70`
- end: `0x180003a75`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `26`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005040`
- `0x180005080`
- `0x180008050`
- `0x180008090`
- `0x1800080d0`
- `0x180008110`
- `0x180008150`
- `0x18000ce90`
- `0x18000cee0`
- `0x18000cf30`
- `0x18000cf74`
- `0x18000cfc0`
- `0x18000d010`
- `0x18000d060`
- `0x1800135f0`
- `0x180013640`
- `0x180013690`
- `0x1800136e0`
- `0x180013730`
- `0x180015bd0`
- `0x1800170a0`
- `0x1800170f0`
- `0x180017140`
- `0x180017190`
- `0x18001a2c0`
- `0x18001b649`

## callees

- `0x180003f1c`

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
0x180003a70  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
