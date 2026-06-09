# CNetworkItem::GetCanonicalCategory(tagPROPVARIANT *)

- ea: `0x180002560`
- end: `0x180002586`
- name: `?GetCanonicalCategory@CNetworkItem@@UEAAJPEAUtagPROPVARIANT@@@Z`
- size: `38`
- prototype: `int(CNetworkItem *__hidden this, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002560`

## import_xrefs

- `ole32!PropVariantCopy` at `0x18000257b`
- `ole32!PropVariantCopy` at `0x18000257b`

## pseudocode

```c
HRESULT __fastcall CNetworkItem::GetCanonicalCategory(const PROPVARIANT *this, PROPVARIANT *a2)
{
  HRESULT result; // eax

  result = -2147024809;
  if ( a2 )
    return PropVariantCopy(a2, this + 24);
  return result;
}

```

## disassembly

```asm
0x180002560  sub     rsp, 28h
0x180002564  mov     r8, rdx
0x180002567  mov     eax, 80070057h
0x18000256c  test    rdx, rdx
0x18000256f  jz      short loc_180002581
0x180002571  lea     rdx, [rcx+0C0h]; pvarSrc
0x180002578  mov     rcx, r8; pvarDest
0x18000257b  call    cs:__imp_PropVariantCopy
0x180002581  add     rsp, 28h
0x180002585  retn
```
