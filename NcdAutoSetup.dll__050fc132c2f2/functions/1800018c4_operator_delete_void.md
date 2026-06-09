# operator delete(void *)

- ea: `0x1800018c4`
- end: `0x1800018c9`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800039f0`
- `0x180003a20`
- `0x18000c170`
- `0x18000c850`
- `0x18000d094`
- `0x18000dee0`
- `0x18000e038`
- `0x1800124dc`

## callees

- `0x180001e91`

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
0x1800018c4  jmp     free_0
```
