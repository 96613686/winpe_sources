# CNetworkItem::GetMACAddress(tagPROPVARIANT *)

- ea: `0x180002730`
- end: `0x180002753`
- name: `?GetMACAddress@CNetworkItem@@UEAAJPEAUtagPROPVARIANT@@@Z`
- size: `35`
- prototype: `int(CNetworkItem *__hidden this, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002730`

## import_xrefs

- `ole32!PropVariantCopy` at `0x180002748`
- `ole32!PropVariantCopy` at `0x180002748`

## pseudocode

```c
HRESULT __fastcall CNetworkItem::GetMACAddress(const PROPVARIANT *this, PROPVARIANT *a2)
{
  HRESULT result; // eax

  result = -2147024809;
  if ( a2 )
    return PropVariantCopy(a2, this + 12);
  return result;
}

```

## disassembly

```asm
0x180002730  sub     rsp, 28h
0x180002734  mov     r8, rdx
0x180002737  mov     eax, 80070057h
0x18000273c  test    rdx, rdx
0x18000273f  jz      short loc_18000274E
0x180002741  lea     rdx, [rcx+60h]; pvarSrc
0x180002745  mov     rcx, r8; pvarDest
0x180002748  call    cs:__imp_PropVariantCopy
0x18000274e  add     rsp, 28h
0x180002752  retn
```
