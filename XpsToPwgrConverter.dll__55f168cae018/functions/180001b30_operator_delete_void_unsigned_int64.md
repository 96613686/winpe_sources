# operator delete(void *,unsigned __int64)

- ea: `0x180001b30`
- end: `0x180001b35`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `27`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003710`
- `0x180003750`
- `0x180003790`
- `0x1800037d0`
- `0x180009470`
- `0x1800094a0`
- `0x1800098c0`
- `0x180009c90`
- `0x18000a130`
- `0x18000a2d0`
- `0x18000a310`
- `0x18000a350`
- `0x18000a390`
- `0x18000a3d0`
- `0x18000acc0`
- `0x18000c33c`
- `0x18000c4e0`
- `0x18000ca20`
- `0x18000cd74`
- `0x18000e0fc`
- `0x18000e1a0`
- `0x18000ee20`
- `0x18000eec0`
- `0x18000ef40`
- `0x18000f36c`
- `0x180010071`
- `0x1800106cd`

## callees

- `0x180001b90`

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
0x180001b30  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
