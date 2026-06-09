# operator delete(void *)

- ea: `0x180001144`
- end: `0x180001149`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `10`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001574`
- `0x180001950`
- `0x180001ff4`
- `0x1800023b0`
- `0x1800035d0`
- `0x180003e54`
- `0x180003f08`
- `0x180003ff8`
- `0x18000428c`
- `0x180004e68`

## callees

- `0x180001e94`

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
0x180001144  jmp     free
```
