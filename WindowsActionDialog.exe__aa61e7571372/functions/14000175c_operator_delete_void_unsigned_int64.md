# operator delete(void *,unsigned __int64)

- ea: `0x14000175c`
- end: `0x140001761`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `15`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140003298`
- `0x1400032f4`
- `0x140003430`
- `0x140003a40`
- `0x140003a80`
- `0x140003ac0`
- `0x140003b00`
- `0x140003b40`
- `0x140003b80`
- `0x140003bd0`
- `0x1400076a0`
- `0x140007a78`
- `0x140007f30`
- `0x140007f60`
- `0x140008d50`

## callees

- `0x140001448`

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
0x14000175c  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
