# operator delete(void *,unsigned __int64)

- ea: `0x140003444`
- end: `0x140003449`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `7`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140005170`
- `0x1400051b0`
- `0x1400051f0`
- `0x140005230`
- `0x140005270`
- `0x1400052b0`
- `0x14000a000`

## callees

- `0x1400034a0`

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
0x140003444  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
