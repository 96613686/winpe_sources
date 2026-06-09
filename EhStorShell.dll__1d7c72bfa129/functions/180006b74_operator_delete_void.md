# operator delete(void *)

- ea: `0x180006b74`
- end: `0x180006b79`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `17`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001eb0`
- `0x1800021c0`
- `0x180002ea0`
- `0x180003450`
- `0x180005b80`
- `0x180006b80`
- `0x180007480`
- `0x180007b40`
- `0x180007b80`
- `0x180007bc0`
- `0x180007c00`
- `0x18000a7c0`
- `0x18000b160`
- `0x18000b1a0`
- `0x18000b1e0`
- `0x18000b340`
- `0x18000b3b0`

## callees

- `0x18000745c`

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
0x180006b74  jmp     free_0
```
