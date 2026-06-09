# operator delete(void *,unsigned __int64)

- ea: `0x180001e84`
- end: `0x180001e89`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `22`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003404`
- `0x180003740`
- `0x1800037b0`
- `0x180003820`
- `0x180003860`
- `0x1800038a0`
- `0x180003cb8`
- `0x180004790`
- `0x180004ce0`
- `0x180007460`
- `0x180008b9c`
- `0x180008d30`
- `0x180008d90`
- `0x180008e10`
- `0x180008e70`
- `0x180009e9c`
- `0x180009f10`
- `0x180009f40`
- `0x18000a328`
- `0x18000a4b8`
- `0x18000a5c0`
- `0x18000a7b0`

## callees

- `0x180001e44`

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
0x180001e84  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
