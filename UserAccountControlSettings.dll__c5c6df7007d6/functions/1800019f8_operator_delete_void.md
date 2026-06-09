# operator delete(void *)

- ea: `0x1800019f8`
- end: `0x1800019fd`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `11`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003320`
- `0x180003490`
- `0x180003740`
- `0x180004c1c`
- `0x180004cd0`
- `0x180004d10`
- `0x1800074a0`
- `0x180008cb0`
- `0x180009320`
- `0x180009e00`
- `0x180009e60`

## callees

- `0x1800021c1`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free_0(Block);
}

```

## disassembly

```asm
0x1800019f8  jmp     free_0
```
