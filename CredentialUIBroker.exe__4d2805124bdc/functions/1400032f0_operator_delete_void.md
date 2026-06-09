# operator delete(void *)

- ea: `0x1400032f0`
- end: `0x1400032f5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `6`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400032e4`
- `0x140004030`
- `0x140004100`
- `0x140007300`
- `0x140008920`
- `0x14001c3d4`

## callees

- `0x140004264`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free(Block);
}

```

## disassembly

```asm
0x1400032f0  jmp     free
```
