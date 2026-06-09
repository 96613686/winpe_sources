# operator delete(void *,unsigned __int64)

- ea: `0x1800025d0`
- end: `0x1800025d5`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `25`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003d50`
- `0x180003d90`
- `0x180007b54`
- `0x180007c4c`
- `0x180007da0`
- `0x180007ea4`
- `0x180007fc0`
- `0x180008134`
- `0x18000826c`
- `0x1800083ac`
- `0x180008eb8`
- `0x180008f20`
- `0x180009168`
- `0x1800097e0`
- `0x180009820`
- `0x180009860`
- `0x1800098a0`
- `0x180009920`
- `0x180009990`
- `0x1800099f0`
- `0x180009a50`
- `0x180009a80`
- `0x180009ad0`
- `0x18000ae6c`
- `0x18000c4bc`

## callees

- `0x180002e1c`

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
0x1800025d0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
