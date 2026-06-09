# WriteVariantToStream(tagVARIANT const *,ISequentialStream *)

- ea: `0x180003380`
- end: `0x180003389`
- name: `?WriteVariantToStream@@YAJPEBUtagVARIANT@@PEAUISequentialStream@@@Z`
- size: `9`
- prototype: `__int64 __fastcall(const struct tagVARIANT *, struct ISequentialStream *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003390`

## pseudocode

```c
__int64 __fastcall WriteVariantToStream(struct tagVARIANT *a1, struct ISequentialStream *a2)
{
  return WriteVariantToStreamEx(a1, a2, 0xFFFFFFFF);
}

```

## disassembly

```asm
0x180003380  or      r8d, 0FFFFFFFFh; unsigned int
0x180003384  jmp     ?WriteVariantToStreamEx@@YAJPEBUtagVARIANT@@PEAUISequentialStream@@K@Z; WriteVariantToStreamEx(tagVARIANT const *,ISequentialStream *,ulong)
```
