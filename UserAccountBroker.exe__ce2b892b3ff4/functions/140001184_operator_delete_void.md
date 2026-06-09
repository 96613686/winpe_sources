# operator delete(void *)

- ea: `0x140001184`
- end: `0x140001189`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `11`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140001fac`
- `0x1400027e0`
- `0x140002810`
- `0x140002880`
- `0x1400028e0`
- `0x140002920`
- `0x140002950`
- `0x140002980`
- `0x1400029c0`
- `0x140003090`
- `0x14000369c`

## callees

- `0x140001657`

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
0x140001184  jmp     free_0
```
