# operator delete(void *,unsigned __int64)

- ea: `0x180001c6c`
- end: `0x180001c71`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `17`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800017e4`
- `0x180003af0`
- `0x180003b30`
- `0x180003b70`
- `0x180003bb0`
- `0x180008d08`
- `0x180008dc0`
- `0x180009380`
- `0x1800095f0`
- `0x180009b00`
- `0x180009ef0`
- `0x180009f50`
- `0x18000ba00`
- `0x18000ba40`
- `0x18000cec0`
- `0x18000d900`
- `0x18000d940`

## callees

- `0x180001370`

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
0x180001c6c  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
