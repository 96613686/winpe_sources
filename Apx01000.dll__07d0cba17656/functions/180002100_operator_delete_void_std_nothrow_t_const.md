# operator delete(void *,std::nothrow_t const &)

- ea: `0x180002100`
- end: `0x180002105`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `58`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003e50`
- `0x180003e90`
- `0x180003ed0`
- `0x180003f10`
- `0x1800099e0`
- `0x180009a40`
- `0x18000b3ec`
- `0x18000c290`
- `0x18000c514`
- `0x18000c7b0`
- `0x18000ce2c`
- `0x18000d680`
- `0x18000d6c0`
- `0x18000e83c`
- `0x18000e940`
- `0x18000e980`
- `0x18000e9c0`
- `0x1800109e0`
- `0x180010a20`
- `0x180012558`
- `0x180012670`
- `0x1800126ac`
- `0x180012a2c`
- `0x180012b40`
- `0x18001665c`
- `0x1800167c0`
- `0x1800167fc`
- `0x180016b58`
- `0x180016db0`
- `0x180019740`
- `0x180019ac0`
- `0x18001ad40`
- `0x18001b100`
- `0x18001bd20`
- `0x18001c7ac`
- `0x18001c870`
- `0x18001e6b4`
- `0x18001e7b0`
- `0x18001e7ec`
- `0x18001ecb4`
- `0x18001f700`
- `0x180022770`
- `0x1800228d0`
- `0x18002309c`
- `0x180024da0`
- `0x180025a70`
- `0x1800272f0`
- `0x180027660`
- `0x180027990`
- `0x180028010`

## callees

- `0x18000263c`

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
0x180002100  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
