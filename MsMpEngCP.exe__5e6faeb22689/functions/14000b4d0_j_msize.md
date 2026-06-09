# j__msize

- ea: `0x14000b4d0`
- end: `0x14000b4d5`
- name: `j__msize`
- size: `5`
- prototype: `size_t __cdecl(void *Block)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x14000b490`

## pseudocode

```c
// attributes: thunk
size_t __cdecl j__msize(void *Block)
{
  return msize(Block);
}

```

## disassembly

```asm
0x14000b4d0  jmp     _msize
```
