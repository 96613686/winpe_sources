# operator delete(void *,unsigned __int64)

- ea: `0x140003644`
- end: `0x140003649`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `17`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140005480`
- `0x1400054c0`
- `0x1400082ec`
- `0x14000859c`
- `0x140008610`
- `0x140008670`
- `0x1400086ac`
- `0x1400086f0`
- `0x140008af0`
- `0x14000b9f4`
- `0x14000c890`
- `0x14000c8c0`
- `0x14000c8f0`
- `0x14000c930`
- `0x14000d5d8`
- `0x14000e2c8`
- `0x14000e3ec`

## callees

- `0x140003708`

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
0x140003644  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
