# ReadVariantFromStream(tagVARIANT *,ISequentialStream *)

- ea: `0x180002d20`
- end: `0x180002d29`
- name: `?ReadVariantFromStream@@YAJPEAUtagVARIANT@@PEAUISequentialStream@@@Z`
- size: `9`
- prototype: `__int64 __fastcall(struct tagVARIANT *, struct ISequentialStream *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002d30`

## pseudocode

```c
__int64 __fastcall ReadVariantFromStream(struct tagVARIANT *a1, struct ISequentialStream *a2)
{
  return ReadVariantFromStreamEx(a1, a2, 0xFFFFFFFF);
}

```

## disassembly

```asm
0x180002d20  or      r8d, 0FFFFFFFFh; unsigned int
0x180002d24  jmp     ?ReadVariantFromStreamEx@@YAJPEAUtagVARIANT@@PEAUISequentialStream@@K@Z; ReadVariantFromStreamEx(tagVARIANT *,ISequentialStream *,ulong)
```
