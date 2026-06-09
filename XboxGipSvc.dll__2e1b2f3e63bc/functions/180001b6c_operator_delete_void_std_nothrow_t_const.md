# operator delete(void *,std::nothrow_t const &)

- ea: `0x180001b6c`
- end: `0x180001b71`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `55`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800016e4`
- `0x180002420`
- `0x1800037b8`
- `0x180003c58`
- `0x1800048e0`
- `0x180004940`
- `0x180004980`
- `0x1800049e0`
- `0x180004a40`
- `0x180004a80`
- `0x180004ac0`
- `0x180004b40`
- `0x180004b74`
- `0x180004bec`
- `0x1800065cc`
- `0x180007330`
- `0x180007370`
- `0x180009508`
- `0x180009820`
- `0x180009a08`
- `0x180009bf8`
- `0x180009c64`
- `0x180009d20`
- `0x180009da8`
- `0x18000ae98`
- `0x18000b11c`
- `0x18000bf80`
- `0x18000c8fc`
- `0x18000ca50`
- `0x18000cad0`
- `0x18000cb30`
- `0x18000cb60`
- `0x18000cba0`
- `0x18000cbe0`
- `0x18000cc60`
- `0x18000d190`
- `0x18000dc70`
- `0x18000df30`
- `0x18000e2c4`
- `0x18000e414`
- `0x18000e90c`
- `0x18000ecf8`
- `0x18000ed1c`
- `0x18000ed8c`
- `0x18000ee1c`
- `0x18000ee70`
- `0x18000ef74`
- `0x18000f3f0`
- `0x18000f440`
- `0x18000f470`

## callees

- `0x180001ffc`

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
0x180001b6c  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
