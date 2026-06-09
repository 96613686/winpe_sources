# operator delete(void *,unsigned __int64)

- ea: `0x180001cd4`
- end: `0x180001cd9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002a80`
- `0x180002cb0`
- `0x180002de0`
- `0x18000789c`
- `0x180008460`

## callees

- `0x1800022a0`

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
0x180001cd4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
