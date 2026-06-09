# operator delete(void *,std::nothrow_t const &)

- ea: `0x18001bc04`
- end: `0x18001bc09`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `42`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000ea80`
- `0x180010e94`
- `0x180010f30`
- `0x180013950`
- `0x180014124`
- `0x180014418`
- `0x1800169d0`
- `0x180019204`
- `0x180019248`
- `0x180019e20`
- `0x18001a8a4`
- `0x18001f394`
- `0x18001f3d0`
- `0x18001f410`
- `0x18001f450`
- `0x18001f484`
- `0x18001f4b0`
- `0x18001f4f0`
- `0x18001f550`
- `0x18001f590`
- `0x18001fd50`
- `0x18001fe10`
- `0x180025bbc`
- `0x1800282a0`
- `0x18002a310`
- `0x18002bca0`
- `0x18002bec4`
- `0x18002c090`
- `0x18002c0e0`
- `0x18002c120`
- `0x18002c160`
- `0x18002c1b0`
- `0x18002c1f0`
- `0x18002c3c4`
- `0x18002dca0`
- `0x18002dff0`
- `0x18002f0c0`
- `0x18002f19c`
- `0x18002fc10`
- `0x18002fc40`
- `0x18003054a`
- `0x1800305a3`

## callees

- `0x18001c04c`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block, const struct std::nothrow_t *a2)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x18001bc04  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
