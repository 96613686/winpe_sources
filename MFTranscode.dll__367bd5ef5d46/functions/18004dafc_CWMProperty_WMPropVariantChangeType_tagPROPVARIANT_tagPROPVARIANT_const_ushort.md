# CWMProperty::WMPropVariantChangeType(tagPROPVARIANT *,tagPROPVARIANT const &,ushort)

- ea: `0x18004dafc`
- end: `0x18004db9a`
- name: `?WMPropVariantChangeType@CWMProperty@@IEAAJPEAUtagPROPVARIANT@@AEBU2@G@Z`
- size: `158`
- prototype: `int(CWMProperty *__hidden this, struct tagPROPVARIANT *, const struct tagPROPVARIANT *, unsigned __int16)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18004d62c`

## callees

- `0x1800085a0`
- `0x18004a398`
- `0x18004dafc`
- `0x180055d04`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004db4c`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004db4c`
- `PROPSYS!PropVariantChangeType` at `0x18004db18`
- `PROPSYS!PropVariantChangeType` at `0x18004db18`

## pseudocode

```c
__int64 __fastcall CWMProperty::WMPropVariantChangeType(
        CWMProperty *this,
        struct tagPROPVARIANT *a2,
        struct tagPROPVARIANT *a3,
        VARTYPE a4)
{
  HRESULT v7; // ebx
  PROPVARIANT pvarSrc; // [rsp+20h] [rbp-48h] BYREF

  v7 = PropVariantChangeType(a2, a3, 0, a4);
  if ( v7 < 0 )
  {
    CMFPropVariant::CMFPropVariant(&pvarSrc, a3);
    v7 = CMFPropVariantConvert::Convert(&pvarSrc, a4);
    if ( v7 >= 0 )
      v7 = PropVariantCopy(a2, &pvarSrc);
    CMFPropVariant::Clear(&pvarSrc);
    if ( v7 < 0 && a3->vt == 21 && a4 == 64 )
    {
      *(_OWORD *)&a2->vt = 0;
      a2->bstrblobVal.pData = 0;
      v7 = 0;
      a2->vt = 64;
      a2->lVal = a3->lVal;
      a2->hVal.HighPart = a3->hVal.HighPart;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18004dafc  push    rbx
0x18004dafe  push    rbp
0x18004daff  push    rsi
0x18004db00  push    rdi
0x18004db01  sub     rsp, 48h
0x18004db05  mov     rsi, r8
0x18004db08  mov     rdi, rdx
0x18004db0b  mov     rdx, rsi; propvarSrc
0x18004db0e  mov     rcx, rdi; ppropvarDest
0x18004db11  xor     r8d, r8d; flags
0x18004db14  movzx   ebp, r9w
0x18004db18  call    cs:__imp_PropVariantChangeType
0x18004db1e  mov     ebx, eax
0x18004db20  test    eax, eax
0x18004db22  jns     short loc_18004DB8F
0x18004db24  mov     rdx, rsi; pvarSrc
0x18004db27  lea     rcx, [rsp+68h+pvarSrc]; pvarDest
0x18004db2c  call    ??0CMFPropVariant@@QEAA@AEBUtagPROPVARIANT@@@Z; CMFPropVariant::CMFPropVariant(tagPROPVARIANT const &)
0x18004db31  movzx   edx, bp; unsigned __int16
0x18004db34  lea     rcx, [rsp+68h+pvarSrc]; pvar
0x18004db39  call    ?Convert@CMFPropVariantConvert@@SAJPEAVCMFPropVariant@@G@Z; CMFPropVariantConvert::Convert(CMFPropVariant *,ushort)
0x18004db3e  mov     ebx, eax
0x18004db40  test    eax, eax
0x18004db42  js      short loc_18004DB54
0x18004db44  lea     rdx, [rsp+68h+pvarSrc]; pvarSrc
0x18004db49  mov     rcx, rdi; pvarDest
0x18004db4c  call    cs:__imp_PropVariantCopy
0x18004db52  mov     ebx, eax
0x18004db54  lea     rcx, [rsp+68h+pvarSrc]; pvar
0x18004db59  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x18004db5e  test    ebx, ebx
0x18004db60  jns     short loc_18004DB8F
0x18004db62  cmp     word ptr [rsi], 15h
0x18004db66  jnz     short loc_18004DB8F
0x18004db68  mov     ecx, 40h ; '@'
0x18004db6d  cmp     bp, cx
0x18004db70  jnz     short loc_18004DB8F
0x18004db72  xor     eax, eax
0x18004db74  xorps   xmm0, xmm0
0x18004db77  movups  xmmword ptr [rdi], xmm0
0x18004db7a  mov     [rdi+10h], rax
0x18004db7e  xor     ebx, ebx
0x18004db80  mov     [rdi], cx
0x18004db83  mov     eax, [rsi+8]
0x18004db86  mov     [rdi+8], eax
0x18004db89  mov     eax, [rsi+0Ch]
0x18004db8c  mov     [rdi+0Ch], eax
0x18004db8f  mov     eax, ebx
0x18004db91  add     rsp, 48h
0x18004db95  pop     rdi
0x18004db96  pop     rsi
0x18004db97  pop     rbp
0x18004db98  pop     rbx
0x18004db99  retn
```
