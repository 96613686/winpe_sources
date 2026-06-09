# operator delete(void *)

- ea: `0x18000b1b0`
- end: `0x18000b1b5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `22`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180006590`
- `0x18000785c`
- `0x180007ae0`
- `0x180007be4`
- `0x1800085d0`
- `0x1800092c4`
- `0x18000a430`
- `0x18000a5c4`
- `0x18000a688`
- `0x18000b2b0`
- `0x18000b5f0`
- `0x180011020`
- `0x18006d760`
- `0x18007ff40`
- `0x180080740`
- `0x1800807f0`
- `0x180080cb0`
- `0x180080cf0`
- `0x180081478`
- `0x180081574`
- `0x180081810`
- `0x180083cd0`

## callees

- `0x18000b70c`

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
0x18000b1b0  jmp     free
```
