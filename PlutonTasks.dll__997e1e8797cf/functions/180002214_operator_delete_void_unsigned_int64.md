# operator delete(void *,unsigned __int64)

- ea: `0x180002214`
- end: `0x180002219`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003b00`
- `0x180003b40`
- `0x180003b80`
- `0x180003bc0`
- `0x180003c10`
- `0x180003c50`
- `0x180003c90`
- `0x180003cd0`

## callees

- `0x180002734`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x180002214  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
