# CNetworkItem::GetCategory(tagPROPVARIANT *)

- ea: `0x180002590`
- end: `0x1800025b3`
- name: `?GetCategory@CNetworkItem@@UEAAJPEAUtagPROPVARIANT@@@Z`
- size: `35`
- prototype: `int(CNetworkItem *__hidden this, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002590`

## import_xrefs

- `ole32!PropVariantCopy` at `0x1800025a8`
- `ole32!PropVariantCopy` at `0x1800025a8`

## pseudocode

```c
HRESULT __fastcall CNetworkItem::GetCategory(const PROPVARIANT *this, PROPVARIANT *a2)
{
  HRESULT result; // eax

  result = -2147024809;
  if ( a2 )
    return PropVariantCopy(a2, this + 9);
  return result;
}

```

## disassembly

```asm
0x180002590  sub     rsp, 28h
0x180002594  mov     r8, rdx
0x180002597  mov     eax, 80070057h
0x18000259c  test    rdx, rdx
0x18000259f  jz      short loc_1800025AE
0x1800025a1  lea     rdx, [rcx+48h]; pvarSrc
0x1800025a5  mov     rcx, r8; pvarDest
0x1800025a8  call    cs:__imp_PropVariantCopy
0x1800025ae  add     rsp, 28h
0x1800025b2  retn
```
