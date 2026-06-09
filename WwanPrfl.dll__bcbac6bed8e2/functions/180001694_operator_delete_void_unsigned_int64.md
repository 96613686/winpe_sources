# operator delete(void *,unsigned __int64)

- ea: `0x180001694`
- end: `0x180001699`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `7`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003a00`
- `0x180003a40`
- `0x180003a80`
- `0x180003ac0`
- `0x18000da50`
- `0x18000db40`
- `0x1800114a0`

## callees

- `0x180001654`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x180001694  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
