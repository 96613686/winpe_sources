# operator delete(void *,unsigned __int64)

- ea: `0x140001754`
- end: `0x140001759`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140003370`
- `0x1400033b0`
- `0x1400033f0`
- `0x140003430`
- `0x140007e80`

## callees

- `0x140001d10`

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
0x140001754  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
