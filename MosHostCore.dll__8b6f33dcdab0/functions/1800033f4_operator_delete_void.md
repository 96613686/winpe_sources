# operator delete(void *)

- ea: `0x1800033f4`
- end: `0x1800033f9`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `15`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003434`
- `0x1800037f0`
- `0x180004fe0`
- `0x180005020`
- `0x180007b60`
- `0x180007b90`
- `0x1800090c0`
- `0x1800090f0`
- `0x18000ea30`
- `0x1800120b4`
- `0x180012198`
- `0x1800125f8`
- `0x180012690`
- `0x180021a10`
- `0x180021a48`

## callees

- `0x180003f40`

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
0x1800033f4  jmp     free
```
