# BayerBinningEffect::OnPropertyChanged(wchar_t const *)

- ea: `0x1804c54e0`
- end: `0x1804c5a73`
- name: `?OnPropertyChanged@BayerBinningEffect@@UEAAJPEB_W@Z`
- size: `1427`
- prototype: `int(BayerBinningEffect *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1801a2ffc`
- `0x18048c8c8`
- `0x1804c54e0`
- `0x1804c6730`
- `0x1804c6944`
- `0x18056dce0`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1804c558c`
- `KERNEL32!CompareStringW` at `0x1804c5669`
- `KERNEL32!CompareStringW` at `0x1804c5746`
- `KERNEL32!CompareStringW` at `0x1804c578f`
- `KERNEL32!CompareStringW` at `0x1804c558c`
- `KERNEL32!CompareStringW` at `0x1804c5669`
- `KERNEL32!CompareStringW` at `0x1804c5746`
- `KERNEL32!CompareStringW` at `0x1804c578f`
- `OLEAUT32!__imp_VariantInit` at `0x1804c5512`
- `OLEAUT32!__imp_VariantInit` at `0x1804c5512`
- `OLEAUT32!__imp_VariantClear` at `0x1804c5993`
- `OLEAUT32!__imp_VariantClear` at `0x1804c5993`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1804c583d`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1804c5987`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1804c583d`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1804c5987`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1804c55f2`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1804c56cf`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1804c58cb`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1804c55f2`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1804c56cf`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1804c58cb`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1804c55d1`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1804c56ae`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1804c58aa`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1804c55d1`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1804c56ae`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1804c58aa`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1804c5879`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1804c5879`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1804c5827`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1804c5975`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1804c5827`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1804c5975`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1804c585e`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1804c585e`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1804c57cb`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1804c57cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall BayerBinningEffect::OnPropertyChanged(BayerBinningEffect *this, const wchar_t *a2)
{
  int v4; // eax
  HRESULT LBound; // eax
  HRESULT UBound; // eax
  HRESULT v7; // eax
  HRESULT v8; // eax
  int v9; // edi
  SAFEARRAY *parray; // rsi
  HRESULT Vartype; // eax
  __int16 v12; // dx
  HRESULT v13; // eax
  HRESULT v14; // eax
  SAFEARRAY *v15; // rcx
  HRESULT v16; // eax
  HRESULT v17; // eax
  int i; // esi
  __int64 result; // rax
  LONG v20; // [rsp+30h] [rbp-58h] BYREF
  _DWORD v21[4]; // [rsp+38h] [rbp-50h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-40h] BYREF
  LONG plUbound; // [rsp+98h] [rbp+10h] BYREF
  LONG plLbound; // [rsp+A0h] [rbp+18h] BYREF
  SAFEARRAY *psa; // [rsp+A8h] [rbp+20h] BYREF

  try
  {
    if ( !a2 )
      ATL::BaseAtlThrow(-2147467261);
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    v4 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 16) + 96LL))(
           *((_QWORD *)this + 16),
           a2,
           &pvarg);
    if ( v4 == -2147024882 || v4 == -2045378032 || v4 == -2045312765 || v4 == -2045247216 )
      ATL::BaseAtlThrow(v4);
    if ( v4 < 0 )
      ATL::BaseAtlThrow(v4);
    if ( CompareStringW(0x7Fu, 1u, a2, -1, L"CameraCropOrigin", -1) == 2 )
    {
      ATL::CComSafeArray<int,3>::CComSafeArray<int,3>(&psa, pvarg.parray);
      plLbound = 0;
      plUbound = 0;
      LBound = SafeArrayGetLBound(psa, 1u, &plLbound);
      if ( LBound < 0 )
        ATL::BaseAtlThrow(LBound);
      UBound = SafeArrayGetUBound(psa, 1u, &plUbound);
      if ( UBound < 0 )
        ATL::BaseAtlThrow(UBound);
      if ( plUbound - plLbound != 1 )
        ATL::BaseAtlThrow(-2147024809);
      *((_DWORD *)this + 37) = *(_DWORD *)ATL::CComSafeArray<float,4>::GetAt(&psa, 0);
      *((_DWORD *)this + 36) = *(_DWORD *)ATL::CComSafeArray<float,4>::GetAt(&psa, 1);
      goto LABEL_51;
    }
    if ( CompareStringW(0x7Fu, 1u, a2, -1, L"CameraCropSize", -1) == 2 )
    {
      ATL::CComSafeArray<int,3>::CComSafeArray<int,3>(&psa, pvarg.parray);
      plLbound = 0;
      plUbound = 0;
      v7 = SafeArrayGetLBound(psa, 1u, &plLbound);
      if ( v7 < 0 )
        ATL::BaseAtlThrow(v7);
      v8 = SafeArrayGetUBound(psa, 1u, &plUbound);
      if ( v8 < 0 )
        ATL::BaseAtlThrow(v8);
      if ( plUbound - plLbound != 1 )
        ATL::BaseAtlThrow(-2147024809);
      *((_DWORD *)this + 39) = *(_DWORD *)ATL::CComSafeArray<float,4>::GetAt(&psa, 0);
      *((_DWORD *)this + 38) = *(_DWORD *)ATL::CComSafeArray<float,4>::GetAt(&psa, 1);
      goto LABEL_51;
    }
    if ( CompareStringW(0x7Fu, 1u, a2, -1, L"UsePackedPixels", -1) == 2 )
    {
      if ( pvarg.vt != 11 )
        ATL::BaseAtlThrow(-2147024809);
      *((_BYTE *)this + 168) = pvarg.iVal != 0;
      goto LABEL_54;
    }
    if ( CompareStringW(0x7Fu, 1u, a2, -1, L"CFAPattern", -1) != 2 )
    {
LABEL_54:
      VariantClear(&pvarg);
      return 0;
    }
    v9 = 0;
    parray = pvarg.parray;
    psa = 0;
    if ( !pvarg.llVal )
      ATL::BaseAtlThrow(-2147024809);
    LOWORD(plUbound) = 0;
    Vartype = SafeArrayGetVartype(pvarg.parray, (VARTYPE *)&plUbound);
    v12 = plUbound;
    if ( Vartype < 0 )
      ATL::BaseAtlThrow(Vartype);
    if ( (_WORD)plUbound == 13 && (parray->fFeatures & 0x440) == 0x440 )
    {
      v12 = 9;
      LOWORD(plUbound) = 9;
    }
    if ( v12 != 17 )
      ATL::BaseAtlThrow(-2147024809);
    if ( psa )
    {
      v13 = SafeArrayUnlock(psa);
      if ( v13 < 0 || (v13 = SafeArrayDestroy(psa), v13 < 0) )
        ATL::BaseAtlThrow(v13);
      psa = 0;
    }
    v14 = SafeArrayCopy(parray, &psa);
    if ( v14 < 0 )
      ATL::BaseAtlThrow(v14);
    v15 = psa;
    if ( psa )
    {
      v14 = SafeArrayLock(psa);
      v15 = psa;
    }
    if ( v14 < 0 )
      ATL::BaseAtlThrow(v14);
    plLbound = 0;
    plUbound = 0;
    v16 = SafeArrayGetLBound(v15, 1u, &plLbound);
    if ( v16 < 0 )
      ATL::BaseAtlThrow(v16);
    v17 = SafeArrayGetUBound(psa, 1u, &plUbound);
    if ( v17 < 0 )
      ATL::BaseAtlThrow(v17);
    if ( plUbound - plLbound != 3 )
      ATL::BaseAtlThrow(-2147024809);
    for ( i = 0; i < 4; ++i )
      v9 = (16 * v9) | *(_BYTE *)ATL::CComSafeArray<unsigned char,17>::operator[](&psa, (unsigned int)i) & 0xF;
    if ( v9 != 274 )
    {
      switch ( v9 )
      {
        case 4129:
          *((_QWORD *)this + 20) = 1;
          goto LABEL_51;
        case 4609:
          *((_DWORD *)this + 40) = 0;
          goto LABEL_48;
        case 8464:
          *((_DWORD *)this + 40) = 1;
LABEL_48:
          *((_DWORD *)this + 41) = 1;
LABEL_51:
          if ( psa && SafeArrayUnlock(psa) >= 0 )
            SafeArrayDestroy(psa);
          goto LABEL_54;
      }
    }
    *((_QWORD *)this + 20) = 0;
    goto LABEL_51;
  }
  catch ( Base::Exception v21 )
  {
    plUbound = v21[2];
    goto LABEL_55;
  }
  catch ( long v20 )
  {
    plUbound = v20;
LABEL_55:
    result = (unsigned int)plUbound;
    if ( (_WORD)plUbound == 534 )
      return 2249588993LL;
  }
  return result;
}

```

## disassembly

```asm
0x1804c54e0  push    rbx
0x1804c54e2  push    rsi
0x1804c54e3  push    rdi
0x1804c54e4  push    r14
0x1804c54e6  push    r15
0x1804c54e8  sub     rsp, 60h
0x1804c54ec  mov     rdi, rdx
0x1804c54ef  mov     rbx, rcx
0x1804c54f2  xor     r14d, r14d
0x1804c54f5  test    rdx, rdx
0x1804c54f8  jz      loc_1804C59BC
0x1804c54fe  xorps   xmm0, xmm0
0x1804c5501  xor     eax, eax
0x1804c5503  movups  xmmword ptr [rsp+88h+pvarg], xmm0
0x1804c5508  mov     qword ptr [rsp+88h+pvarg+10h], rax
0x1804c550d  lea     rcx, [rsp+88h+pvarg]; pvarg
0x1804c5512  call    cs:__imp_VariantInit
0x1804c5518  mov     rcx, [rbx+80h]
0x1804c551f  mov     rax, [rcx]
0x1804c5522  lea     r8, [rsp+88h+pvarg]
0x1804c5527  mov     rdx, rdi
0x1804c552a  mov     rax, [rax+60h]
0x1804c552e  call    cs:__guard_dispatch_icall_fptr
0x1804c5534  cmp     eax, 8007000Eh
0x1804c5539  jz      loc_1804C5A69
0x1804c553f  cmp     eax, 86160210h
0x1804c5544  jz      loc_1804C5A69
0x1804c554a  cmp     eax, 86170103h
0x1804c554f  jz      loc_1804C5A69
0x1804c5555  cmp     eax, 86180110h
0x1804c555a  jz      loc_1804C5A69
0x1804c5560  test    eax, eax
0x1804c5562  js      loc_1804C59CA
0x1804c5568  or      esi, 0FFFFFFFFh
0x1804c556b  mov     [rsp+88h+cchCount2], esi; cchCount2
0x1804c556f  lea     rax, aCameracroporig; "CameraCropOrigin"
0x1804c5576  mov     [rsp+88h+lpString2], rax; lpString2
0x1804c557b  mov     r9d, esi; cchCount1
0x1804c557e  mov     r8, rdi; lpString1
0x1804c5581  lea     r15d, [rsi+2]
0x1804c5585  mov     edx, r15d; dwCmpFlags
0x1804c5588  lea     ecx, [r15+7Eh]; Locale
0x1804c558c  call    cs:__imp_CompareStringW
0x1804c5592  cmp     eax, 2
0x1804c5595  jnz     loc_1804C564B
0x1804c559b  mov     rdx, qword ptr [rsp+88h+pvarg+8]; psa
0x1804c55a0  lea     rcx, [rsp+88h+psa]; ppsaOut
0x1804c55a8  call    ??0?$CComSafeArray@H$02@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z; ATL::CComSafeArray<int,3>::CComSafeArray<int,3>(tagSAFEARRAY const *)
0x1804c55ad  nop
0x1804c55ae  mov     [rsp+88h+plLbound], r14d
0x1804c55b6  mov     [rsp+88h+plUbound], r14d
0x1804c55be  lea     r8, [rsp+88h+plLbound]; plLbound
0x1804c55c6  mov     edx, r15d; nDim
0x1804c55c9  mov     rcx, [rsp+88h+psa]; psa
0x1804c55d1  call    cs:__imp_SafeArrayGetLBound
0x1804c55d7  test    eax, eax
0x1804c55d9  js      loc_1804C59D5
0x1804c55df  lea     r8, [rsp+88h+plUbound]; plUbound
0x1804c55e7  mov     edx, r15d; nDim
0x1804c55ea  mov     rcx, [rsp+88h+psa]; psa
0x1804c55f2  call    cs:__imp_SafeArrayGetUBound
0x1804c55f8  test    eax, eax
0x1804c55fa  js      loc_1804C59DC
0x1804c5600  mov     eax, [rsp+88h+plUbound]
0x1804c5607  sub     eax, [rsp+88h+plLbound]
0x1804c560e  cmp     eax, r15d
0x1804c5611  jnz     loc_1804C59E3
0x1804c5617  xor     edx, edx
0x1804c5619  lea     rcx, [rsp+88h+psa]
0x1804c5621  call    ?GetAt@?$CComSafeArray@M$03@ATL@@QEAAAEAMJ@Z; ATL::CComSafeArray<float,4>::GetAt(long)
0x1804c5626  mov     eax, [rax]
0x1804c5628  mov     [rbx+94h], eax
0x1804c562e  mov     edx, r15d
0x1804c5631  lea     rcx, [rsp+88h+psa]
0x1804c5639  call    ?GetAt@?$CComSafeArray@M$03@ATL@@QEAAAEAMJ@Z; ATL::CComSafeArray<float,4>::GetAt(long)
0x1804c563e  mov     eax, [rax]
0x1804c5640  mov     [rbx+90h], eax
0x1804c5646  jmp     loc_1804C5968
0x1804c564b  mov     [rsp+88h+cchCount2], esi; cchCount2
0x1804c564f  lea     rax, aCameracropsize; "CameraCropSize"
0x1804c5656  mov     [rsp+88h+lpString2], rax; lpString2
0x1804c565b  mov     r9d, esi; cchCount1
0x1804c565e  mov     r8, rdi; lpString1
0x1804c5661  mov     edx, r15d; dwCmpFlags
0x1804c5664  mov     ecx, 7Fh; Locale
0x1804c5669  call    cs:__imp_CompareStringW
0x1804c566f  cmp     eax, 2
0x1804c5672  jnz     loc_1804C5728
0x1804c5678  mov     rdx, qword ptr [rsp+88h+pvarg+8]; psa
0x1804c567d  lea     rcx, [rsp+88h+psa]; ppsaOut
0x1804c5685  call    ??0?$CComSafeArray@H$02@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z; ATL::CComSafeArray<int,3>::CComSafeArray<int,3>(tagSAFEARRAY const *)
0x1804c568a  nop
0x1804c568b  mov     [rsp+88h+plLbound], r14d
0x1804c5693  mov     [rsp+88h+plUbound], r14d
0x1804c569b  lea     r8, [rsp+88h+plLbound]; plLbound
0x1804c56a3  mov     edx, r15d; nDim
0x1804c56a6  mov     rcx, [rsp+88h+psa]; psa
0x1804c56ae  call    cs:__imp_SafeArrayGetLBound
0x1804c56b4  test    eax, eax
0x1804c56b6  js      loc_1804C59F1
0x1804c56bc  lea     r8, [rsp+88h+plUbound]; plUbound
0x1804c56c4  mov     edx, r15d; nDim
0x1804c56c7  mov     rcx, [rsp+88h+psa]; psa
0x1804c56cf  call    cs:__imp_SafeArrayGetUBound
0x1804c56d5  test    eax, eax
0x1804c56d7  js      loc_1804C59F8
0x1804c56dd  mov     eax, [rsp+88h+plUbound]
0x1804c56e4  sub     eax, [rsp+88h+plLbound]
0x1804c56eb  cmp     eax, r15d
0x1804c56ee  jnz     loc_1804C59FF
0x1804c56f4  xor     edx, edx
0x1804c56f6  lea     rcx, [rsp+88h+psa]
0x1804c56fe  call    ?GetAt@?$CComSafeArray@M$03@ATL@@QEAAAEAMJ@Z; ATL::CComSafeArray<float,4>::GetAt(long)
0x1804c5703  mov     eax, [rax]
0x1804c5705  mov     [rbx+9Ch], eax
0x1804c570b  mov     edx, r15d
0x1804c570e  lea     rcx, [rsp+88h+psa]
0x1804c5716  call    ?GetAt@?$CComSafeArray@M$03@ATL@@QEAAAEAMJ@Z; ATL::CComSafeArray<float,4>::GetAt(long)
0x1804c571b  mov     eax, [rax]
0x1804c571d  mov     [rbx+98h], eax
0x1804c5723  jmp     loc_1804C5968
0x1804c5728  mov     [rsp+88h+cchCount2], esi; cchCount2
0x1804c572c  lea     rax, aUsepackedpixel; "UsePackedPixels"
0x1804c5733  mov     [rsp+88h+lpString2], rax; lpString2
0x1804c5738  mov     r9d, esi; cchCount1
0x1804c573b  mov     r8, rdi; lpString1
0x1804c573e  mov     edx, r15d; dwCmpFlags
0x1804c5741  mov     ecx, 7Fh; Locale
0x1804c5746  call    cs:__imp_CompareStringW
0x1804c574c  cmp     eax, 2
0x1804c574f  jnz     short loc_1804C5771
0x1804c5751  cmp     word ptr [rsp+88h+pvarg], 0Bh
0x1804c5757  jnz     loc_1804C5A0D
0x1804c575d  cmp     word ptr [rsp+88h+pvarg+8], r14w
0x1804c5763  setnz   al
0x1804c5766  mov     [rbx+0A8h], al
0x1804c576c  jmp     loc_1804C598E
0x1804c5771  mov     [rsp+88h+cchCount2], esi; cchCount2
0x1804c5775  lea     rax, aCfapattern; "CFAPattern"
0x1804c577c  mov     [rsp+88h+lpString2], rax; lpString2
0x1804c5781  mov     r9d, esi; cchCount1
0x1804c5784  mov     r8, rdi; lpString1
0x1804c5787  mov     edx, r15d; dwCmpFlags
0x1804c578a  mov     ecx, 7Fh; Locale
0x1804c578f  call    cs:__imp_CompareStringW
0x1804c5795  cmp     eax, 2
0x1804c5798  jnz     loc_1804C598E
0x1804c579e  mov     edi, r14d
0x1804c57a1  mov     rsi, qword ptr [rsp+88h+pvarg+8]
0x1804c57a6  mov     [rsp+88h+psa], r14
0x1804c57ae  test    rsi, rsi
0x1804c57b1  jz      loc_1804C5A17
0x1804c57b7  mov     word ptr [rsp+88h+plUbound], r14w
0x1804c57c0  lea     rdx, [rsp+88h+plUbound]; pvt
0x1804c57c8  mov     rcx, rsi; psa
0x1804c57cb  call    cs:__imp_SafeArrayGetVartype
0x1804c57d1  movzx   edx, word ptr [rsp+88h+plUbound]
0x1804c57d9  test    eax, eax
0x1804c57db  js      loc_1804C5A21
0x1804c57e1  cmp     dx, 0Dh
0x1804c57e5  jnz     short loc_1804C5808
0x1804c57e7  movzx   ecx, word ptr [rsi+2]
0x1804c57eb  mov     r8d, 440h
0x1804c57f1  and     cx, r8w
0x1804c57f5  cmp     cx, r8w
0x1804c57f9  jnz     short loc_1804C5808
0x1804c57fb  mov     edx, 9
0x1804c5800  mov     word ptr [rsp+88h+plUbound], dx
0x1804c5808  test    eax, eax
0x1804c580a  js      loc_1804C5A21
0x1804c5810  cmp     dx, 11h
0x1804c5814  jnz     loc_1804C5A28
0x1804c581a  mov     rcx, [rsp+88h+psa]; psa
0x1804c5822  test    rcx, rcx
0x1804c5825  jz      short loc_1804C5853
0x1804c5827  call    cs:__imp_SafeArrayUnlock
0x1804c582d  test    eax, eax
0x1804c582f  js      loc_1804C5A39
0x1804c5835  mov     rcx, [rsp+88h+psa]; psa
0x1804c583d  call    cs:__imp_SafeArrayDestroy
0x1804c5843  test    eax, eax
0x1804c5845  js      loc_1804C5A39
0x1804c584b  mov     [rsp+88h+psa], r14
0x1804c5853  lea     rdx, [rsp+88h+psa]; ppsaOut
0x1804c585b  mov     rcx, rsi; psa
0x1804c585e  call    cs:__imp_SafeArrayCopy
0x1804c5864  test    eax, eax
0x1804c5866  js      loc_1804C5A32
0x1804c586c  mov     rcx, [rsp+88h+psa]; psa
0x1804c5874  test    rcx, rcx
0x1804c5877  jz      short loc_1804C5887
0x1804c5879  call    cs:__imp_SafeArrayLock
0x1804c587f  mov     rcx, [rsp+88h+psa]; psa
0x1804c5887  test    eax, eax
0x1804c5889  js      loc_1804C5A40
0x1804c588f  mov     [rsp+88h+plLbound], r14d
0x1804c5897  mov     [rsp+88h+plUbound], r14d
0x1804c589f  lea     r8, [rsp+88h+plLbound]; plLbound
0x1804c58a7  mov     edx, r15d; nDim
0x1804c58aa  call    cs:__imp_SafeArrayGetLBound
0x1804c58b0  test    eax, eax
0x1804c58b2  js      loc_1804C5A4D
0x1804c58b8  lea     r8, [rsp+88h+plUbound]; plUbound
0x1804c58c0  mov     edx, r15d; nDim
0x1804c58c3  mov     rcx, [rsp+88h+psa]; psa
0x1804c58cb  call    cs:__imp_SafeArrayGetUBound
0x1804c58d1  test    eax, eax
0x1804c58d3  js      loc_1804C5A54
0x1804c58d9  mov     eax, [rsp+88h+plUbound]
0x1804c58e0  sub     eax, [rsp+88h+plLbound]
0x1804c58e7  cmp     eax, 3
0x1804c58ea  jnz     loc_1804C5A5B
0x1804c58f0  mov     esi, r14d
0x1804c58f3  cmp     esi, 4
0x1804c58f6  jge     short loc_1804C591B
0x1804c58f8  mov     edx, esi
0x1804c58fa  lea     rcx, [rsp+88h+psa]
0x1804c5902  call    ??A?$CComSafeArray@E$0BB@@ATL@@QEAAAEAEH@Z; ATL::CComSafeArray<uchar,17>::operator[](int)
0x1804c5907  movzx   ecx, byte ptr [rax]
0x1804c590a  and     ecx, 0Fh
0x1804c590d  mov     eax, edi
0x1804c590f  shl     eax, 4
0x1804c5912  mov     edi, ecx
0x1804c5914  or      edi, eax
0x1804c5916  add     esi, r15d
0x1804c5919  jmp     short loc_1804C58F3
0x1804c591b  cmp     edi, 112h
0x1804c5921  jz      short loc_1804C5961
0x1804c5923  cmp     edi, 1021h
0x1804c5929  jz      short loc_1804C5954
0x1804c592b  cmp     edi, 1201h
0x1804c5931  jz      short loc_1804C5944
0x1804c5933  cmp     edi, 2110h
0x1804c5939  jnz     short loc_1804C5961
0x1804c593b  mov     [rbx+0A0h], r15d
0x1804c5942  jmp     short loc_1804C594B
0x1804c5944  mov     [rbx+0A0h], r14d
0x1804c594b  mov     [rbx+0A4h], r15d
0x1804c5952  jmp     short loc_1804C5968
0x1804c5954  mov     qword ptr [rbx+0A0h], 1
0x1804c595f  jmp     short loc_1804C5968
0x1804c5961  mov     [rbx+0A0h], r14
0x1804c5968  mov     rcx, [rsp+88h+psa]; psa
0x1804c5970  test    rcx, rcx
0x1804c5973  jz      short loc_1804C598E
0x1804c5975  call    cs:__imp_SafeArrayUnlock
0x1804c597b  test    eax, eax
0x1804c597d  js      short loc_1804C598E
0x1804c597f  mov     rcx, [rsp+88h+psa]; psa
0x1804c5987  call    cs:__imp_SafeArrayDestroy
0x1804c598d  nop
0x1804c598e  lea     rcx, [rsp+88h+pvarg]; pvarg
0x1804c5993  call    cs:__imp_VariantClear
0x1804c5999  xor     eax, eax
0x1804c599b  jmp     short loc_1804C59B0
0x1804c599d  mov     eax, [rsp+88h+plUbound]
0x1804c59a4  mov     edx, 86160101h
0x1804c59a9  cmp     ax, 216h
0x1804c59ad  cmovz   eax, edx
0x1804c59b0  add     rsp, 60h
0x1804c59b4  pop     r15
0x1804c59b6  pop     r14
0x1804c59b8  pop     rdi
0x1804c59b9  pop     rsi
0x1804c59ba  pop     rbx
0x1804c59bb  retn
0x1804c59bc  mov     ecx, 80004003h; int
0x1804c59c1  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1804c59c7  jmp     short $+2
0x1804c59c9  nop
0x1804c59ca  mov     ecx, eax; int
0x1804c59cc  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1804c59d2  jmp     short $+2
0x1804c59d4  nop
0x1804c59d5  mov     ecx, eax; int
0x1804c59d7  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1804c59dc  mov     ecx, eax; int
0x1804c59de  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1804c59e3  mov     ecx, 80070057h; int
0x1804c59e8  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1804c59ee  jmp     short $+2
0x1804c59f0  nop
0x1804c59f1  mov     ecx, eax; int
0x1804c59f3  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1804c59f8  mov     ecx, eax; int
0x1804c59fa  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1804c59ff  mov     ecx, 80070057h; int
0x1804c5a04  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1804c5a0a  jmp     short $+2
0x1804c5a0c  nop
0x1804c5a0d  mov     ecx, 80070057h; int
0x1804c5a12  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1804c5a17  mov     ecx, 80070057h; int
0x1804c5a1c  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1804c5a21  mov     ecx, eax; int
0x1804c5a23  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1804c5a28  mov     ecx, 80070057h; int
0x1804c5a2d  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1804c5a32  mov     ecx, eax; int
0x1804c5a34  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
  ... truncated ...
```
