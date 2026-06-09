# PreprocessRawEffect::OnPropertyChanged(wchar_t const *)

- ea: `0x1804742e0`
- end: `0x1804748f1`
- name: `?OnPropertyChanged@PreprocessRawEffect@@UEAAJPEB_W@Z`
- size: `1553`
- prototype: `int(PreprocessRawEffect *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x1801a2ffc`
- `0x1801b1354`
- `0x180201a9c`
- `0x1804742e0`
- `0x180475634`
- `0x1804756d8`
- `0x1804c6944`
- `0x18056dc2e`
- `0x18056dcb2`
- `0x18056dce0`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1804743ae`
- `KERNEL32!CompareStringW` at `0x1804743ed`
- `KERNEL32!CompareStringW` at `0x18047447d`
- `KERNEL32!CompareStringW` at `0x1804745c7`
- `KERNEL32!CompareStringW` at `0x1804746d2`
- `KERNEL32!CompareStringW` at `0x18047475b`
- `KERNEL32!CompareStringW` at `0x1804747a7`
- `KERNEL32!CompareStringW` at `0x1804747f4`
- `KERNEL32!CompareStringW` at `0x1804743ae`
- `KERNEL32!CompareStringW` at `0x1804743ed`
- `KERNEL32!CompareStringW` at `0x18047447d`
- `KERNEL32!CompareStringW` at `0x1804745c7`
- `KERNEL32!CompareStringW` at `0x1804746d2`
- `KERNEL32!CompareStringW` at `0x18047475b`
- `KERNEL32!CompareStringW` at `0x1804747a7`
- `KERNEL32!CompareStringW` at `0x1804747f4`
- `OLEAUT32!__imp_VariantInit` at `0x18047432e`
- `OLEAUT32!__imp_VariantInit` at `0x18047432e`
- `OLEAUT32!__imp_VariantClear` at `0x18047481e`
- `OLEAUT32!__imp_VariantClear` at `0x18047481e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1804746aa`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1804746aa`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18047462b`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18047462b`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18047460a`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18047460a`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180474694`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180474694`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PreprocessRawEffect::OnPropertyChanged(PreprocessRawEffect *this, const wchar_t *a2)
{
  __int64 v4; // rbx
  int v6; // eax
  int v7; // eax
  int Count; // r14d
  float *v9; // rax
  float v10; // xmm0_4
  int v11; // eax
  int v12; // r14d
  float v13; // xmm7_4
  float v14; // xmm6_4
  int i; // r15d
  float v16; // xmm6_4
  int j; // r15d
  float *v18; // rax
  float v19; // xmm0_4
  unsigned int k; // r15d
  float *v21; // rax
  float v22; // xmm0_4
  HRESULT LBound; // eax
  HRESULT UBound; // eax
  __int64 v25; // r8
  __int64 v26; // rcx
  __int64 v27; // r9
  __int16 v28; // r10
  __int64 v29; // rcx
  __int16 v30; // dx
  float dblVal; // xmm1_4
  int pExceptionObject; // [rsp+30h] [rbp-88h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-70h] BYREF
  LONG plUbound; // [rsp+C8h] [rbp+10h] BYREF
  LONG plLbound; // [rsp+D0h] [rbp+18h] BYREF
  SAFEARRAY *psa; // [rsp+D8h] [rbp+20h] BYREF

  v4 = 0;
  if ( !a2 )
    return 2147500035LL;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v6 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 16) + 96LL))(
         *((_QWORD *)this + 16),
         a2,
         &pvarg);
  if ( v6 == -2147024882 || v6 == -2045378032 || v6 == -2045312765 || v6 == -2045247216 )
    ATL::BaseAtlThrow(v6);
  if ( v6 < 0 )
    ATL::BaseAtlThrow(v6);
  if ( CompareStringW(0x7Fu, 1u, a2, -1, L"Gain", -1) == 2 )
  {
    *((float *)this + 48) = pvarg.dblVal;
  }
  else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"BlackPointColumn", -1) == 2 )
  {
    v7 = ATL::CComSafeArray<float,4>::CopyFrom((SAFEARRAY **)this + 21, pvarg.parray);
    if ( v7 < 0 )
      ATL::BaseAtlThrow(v7);
    *((_DWORD *)this + 46) = 0;
    Count = ATL::CComSafeArray<IUnknown *,13>::GetCount((char *)this + 168);
    while ( (int)v4 < Count )
    {
      v9 = (float *)ATL::CComSafeArray<float,4>::GetAt((char *)this + 168, (unsigned int)v4);
      v10 = *((float *)this + 46);
      if ( v10 <= *v9 )
        v10 = *(float *)ATL::CComSafeArray<float,4>::GetAt((char *)this + 168, (unsigned int)v4);
      *((float *)this + 46) = v10;
      LODWORD(v4) = v4 + 1;
    }
  }
  else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"BlackPointRow", -1) == 2 )
  {
    v11 = ATL::CComSafeArray<float,4>::CopyFrom((SAFEARRAY **)this + 20, pvarg.parray);
    if ( v11 < 0 )
      ATL::BaseAtlThrow(v11);
    *((_DWORD *)this + 45) = 0;
    v12 = ATL::CComSafeArray<IUnknown *,13>::GetCount((char *)this + 160);
    if ( v12 > 0 )
    {
      v13 = 0.0;
      v14 = 0.0;
      for ( i = 0; i < v12; ++i )
        v14 = v14 + *(float *)ATL::CComSafeArray<float,4>::GetAt((char *)this + 160, (unsigned int)i);
      v16 = v14 / (float)v12;
      for ( j = 0; j < v12; ++j )
      {
        v18 = (float *)ATL::CComSafeArray<float,4>::GetAt((char *)this + 160, (unsigned int)j);
        v13 = v13 + (float)((float)(v16 - *v18) * (float)(v16 - *v18));
      }
      v19 = powf_0(v13 / (float)v12, 0.5);
      for ( k = 0; (int)k < v12; ++k )
      {
        if ( COERCE_FLOAT(COERCE_UNSIGNED_INT(*(float *)ATL::CComSafeArray<float,4>::GetAt((char *)this + 160, k) - v16) & _xmm) > (float)(v19 + v19) )
          *(float *)ATL::CComSafeArray<float,4>::GetAt((char *)this + 160, k) = v16;
      }
    }
    while ( (int)v4 < v12 )
    {
      v21 = (float *)ATL::CComSafeArray<float,4>::GetAt((char *)this + 160, (unsigned int)v4);
      v22 = *((float *)this + 45);
      if ( v22 <= *v21 )
        v22 = *(float *)ATL::CComSafeArray<float,4>::GetAt((char *)this + 160, (unsigned int)v4);
      *((float *)this + 45) = v22;
      LODWORD(v4) = v4 + 1;
    }
  }
  else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"BlackPointRepeatSize", -1) == 2 )
  {
    ATL::CComSafeArray<unsigned short,18>::CComSafeArray<unsigned short,18>(&psa, pvarg.parray);
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
    if ( *(_WORD *)ATL::CComSafeArray<unsigned short,18>::operator[](&psa, 0) != 1
      || *(_WORD *)ATL::CComSafeArray<unsigned short,18>::operator[](&psa, 1) != 1 )
    {
      ATL::BaseAtlThrow(-2147024809);
    }
    if ( psa && SafeArrayUnlock(psa) >= 0 )
      SafeArrayDestroy(psa);
  }
  else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"LinearizationTable", -1) == 2 )
  {
    v25 = *(_QWORD *)(pvarg.llVal + 16);
    v26 = *(int *)(pvarg.llVal + 24);
    if ( (unsigned int)v26 > 0x7FFFFFFF )
    {
      pExceptionObject = -2147024809;
      throw (long *)&pExceptionObject;
    }
    if ( (int)v26 <= 0 )
      ATL::BaseAtlThrow(-2147024809);
    v27 = *(int *)(pvarg.llVal + 24);
    v28 = *(_WORD *)(v25 + 2 * v26 - 2);
    do
    {
      v29 = 2 * v4;
      if ( v4 >= v27 )
        v30 = v28;
      else
        v30 = *(_WORD *)(v29 + v25);
      *(_WORD *)(v29 + *((_QWORD *)this + 18)) = v30;
      ++v4;
    }
    while ( v4 < 0x10000 );
    *((_BYTE *)this + 152) = 1;
  }
  else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"WhitePoint", -1) == 2 )
  {
    if ( pvarg.lVal > 0xFFFF )
      ATL::BaseAtlThrow(-2147024809);
    *((float *)this + 47) = (float)pvarg.lVal;
  }
  else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"BlackPoint", -1) == 2 )
  {
    dblVal = pvarg.dblVal;
    if ( dblVal > 65535.0 )
      ATL::BaseAtlThrow(-2147024809);
    *((float *)this + 44) = dblVal;
  }
  else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"UsePackedPixels", -1) == 2 )
  {
    if ( pvarg.vt != 11 )
      ATL::BaseAtlThrow(-2147024809);
    *((_BYTE *)this + 196) = pvarg.iVal != 0;
  }
  VariantClear(&pvarg);
  return 0;
}

```

## disassembly

```asm
0x1804742e0  mov     rax, rsp
0x1804742e3  mov     [rax+8], rbx
0x1804742e7  push    rsi
0x1804742e8  push    rdi
0x1804742e9  push    r12
0x1804742eb  push    r14
0x1804742ed  push    r15
0x1804742ef  sub     rsp, 90h
0x1804742f6  movaps  xmmword ptr [rax-38h], xmm6
0x1804742fa  movaps  xmmword ptr [rax-48h], xmm7
0x1804742fe  movaps  xmmword ptr [rax-58h], xmm8
0x180474303  mov     rsi, rdx
0x180474306  mov     rdi, rcx
0x180474309  xor     ebx, ebx
0x18047430b  test    rdx, rdx
0x18047430e  jnz     short loc_18047431A
0x180474310  mov     eax, 80004003h
0x180474315  jmp     loc_18047483B
0x18047431a  xorps   xmm0, xmm0
0x18047431d  xor     eax, eax
0x18047431f  movups  xmmword ptr [rsp+0B8h+pvarg], xmm0
0x180474324  mov     qword ptr [rsp+0B8h+pvarg+10h], rax
0x180474329  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x18047432e  call    cs:__imp_VariantInit
0x180474334  mov     rcx, [rdi+80h]
0x18047433b  mov     rax, [rcx]
0x18047433e  lea     r8, [rsp+0B8h+pvarg]
0x180474343  mov     rdx, rsi
0x180474346  mov     rax, [rax+60h]
0x18047434a  call    cs:__guard_dispatch_icall_fptr
0x180474350  cmp     eax, 8007000Eh
0x180474355  jz      loc_1804748E8
0x18047435b  cmp     eax, 86160210h
0x180474360  jz      loc_1804748E8
0x180474366  cmp     eax, 86170103h
0x18047436b  jz      loc_1804748E8
0x180474371  cmp     eax, 86180110h
0x180474376  jz      loc_1804748E8
0x18047437c  test    eax, eax
0x18047437e  js      loc_180474862
0x180474384  or      r14d, 0FFFFFFFFh
0x180474388  mov     [rsp+0B8h+cchCount2], r14d; cchCount2
0x18047438d  lea     rax, aGain; "Gain"
0x180474394  mov     [rsp+0B8h+lpString2], rax; lpString2
0x180474399  mov     r9d, r14d; cchCount1
0x18047439c  mov     r8, rsi; lpString1
0x18047439f  lea     r12d, [r14+2]
0x1804743a3  mov     edx, r12d; dwCmpFlags
0x1804743a6  lea     r15d, [r12+7Eh]
0x1804743ab  mov     ecx, r15d; Locale
0x1804743ae  call    cs:__imp_CompareStringW
0x1804743b4  cmp     eax, 2
0x1804743b7  jnz     short loc_1804743D0
0x1804743b9  movsd   xmm0, qword ptr [rsp+0B8h+pvarg+8]
0x1804743bf  cvtpd2ps xmm0, xmm0
0x1804743c3  movss   dword ptr [rdi+0C0h], xmm0
0x1804743cb  jmp     loc_180474819
0x1804743d0  mov     [rsp+0B8h+cchCount2], r14d; cchCount2
0x1804743d5  lea     rax, aBlackpointcolu; "BlackPointColumn"
0x1804743dc  mov     [rsp+0B8h+lpString2], rax; lpString2
0x1804743e1  mov     r9d, r14d; cchCount1
0x1804743e4  mov     r8, rsi; lpString1
0x1804743e7  mov     edx, r12d; dwCmpFlags
0x1804743ea  mov     ecx, r15d; Locale
0x1804743ed  call    cs:__imp_CompareStringW
0x1804743f3  cmp     eax, 2
0x1804743f6  jnz     short loc_180474460
0x1804743f8  lea     rsi, [rdi+0A8h]
0x1804743ff  mov     rdx, qword ptr [rsp+0B8h+pvarg+8]; psa
0x180474404  mov     rcx, rsi; ppsaOut
0x180474407  call    ?CopyFrom@?$CComSafeArray@M$03@ATL@@QEAAJPEBUtagSAFEARRAY@@@Z; ATL::CComSafeArray<float,4>::CopyFrom(tagSAFEARRAY const *)
0x18047440c  test    eax, eax
0x18047440e  js      loc_180474869
0x180474414  mov     [rdi+0B8h], ebx
0x18047441a  mov     rcx, rsi
0x18047441d  call    ?GetCount@?$CComSafeArray@PEAUIUnknown@@$0N@@ATL@@QEBAKI@Z; ATL::CComSafeArray<IUnknown *,13>::GetCount(uint)
0x180474422  mov     r14d, eax
0x180474425  cmp     ebx, r14d
0x180474428  jge     loc_180474819
0x18047442e  mov     edx, ebx
0x180474430  mov     rcx, rsi
0x180474433  call    ?GetAt@?$CComSafeArray@M$03@ATL@@QEAAAEAMJ@Z; ATL::CComSafeArray<float,4>::GetAt(long)
0x180474438  movss   xmm0, dword ptr [rdi+0B8h]
0x180474440  comiss  xmm0, dword ptr [rax]
0x180474443  ja      short loc_180474453
0x180474445  mov     edx, ebx
0x180474447  mov     rcx, rsi
0x18047444a  call    ?GetAt@?$CComSafeArray@M$03@ATL@@QEAAAEAMJ@Z; ATL::CComSafeArray<float,4>::GetAt(long)
0x18047444f  movss   xmm0, dword ptr [rax]
0x180474453  movss   dword ptr [rdi+0B8h], xmm0
0x18047445b  add     ebx, r12d
0x18047445e  jmp     short loc_180474425
0x180474460  mov     [rsp+0B8h+cchCount2], r14d; cchCount2
0x180474465  lea     rax, aBlackpointrow; "BlackPointRow"
0x18047446c  mov     [rsp+0B8h+lpString2], rax; lpString2
0x180474471  mov     r9d, r14d; cchCount1
0x180474474  mov     r8, rsi; lpString1
0x180474477  mov     edx, r12d; dwCmpFlags
0x18047447a  mov     ecx, r15d; Locale
0x18047447d  call    cs:__imp_CompareStringW
0x180474483  cmp     eax, 2
0x180474486  jnz     loc_1804745AA
0x18047448c  lea     rsi, [rdi+0A0h]
0x180474493  mov     rdx, qword ptr [rsp+0B8h+pvarg+8]; psa
0x180474498  mov     rcx, rsi; ppsaOut
0x18047449b  call    ?CopyFrom@?$CComSafeArray@M$03@ATL@@QEAAJPEBUtagSAFEARRAY@@@Z; ATL::CComSafeArray<float,4>::CopyFrom(tagSAFEARRAY const *)
0x1804744a0  test    eax, eax
0x1804744a2  js      loc_180474870
0x1804744a8  mov     [rdi+0B4h], ebx
0x1804744ae  mov     rcx, rsi
0x1804744b1  call    ?GetCount@?$CComSafeArray@PEAUIUnknown@@$0N@@ATL@@QEBAKI@Z; ATL::CComSafeArray<IUnknown *,13>::GetCount(uint)
0x1804744b6  mov     r14d, eax
0x1804744b9  test    eax, eax
0x1804744bb  jle     loc_18047456F
0x1804744c1  xorps   xmm7, xmm7
0x1804744c4  xorps   xmm6, xmm6
0x1804744c7  mov     r15d, ebx
0x1804744ca  cmp     r15d, r14d
0x1804744cd  jge     short loc_1804744E3
0x1804744cf  mov     edx, r15d
0x1804744d2  mov     rcx, rsi
0x1804744d5  call    ?GetAt@?$CComSafeArray@M$03@ATL@@QEAAAEAMJ@Z; ATL::CComSafeArray<float,4>::GetAt(long)
0x1804744da  addss   xmm6, dword ptr [rax]
0x1804744de  add     r15d, r12d
0x1804744e1  jmp     short loc_1804744CA
0x1804744e3  movd    xmm8, r14d
0x1804744e8  cvtdq2ps xmm8, xmm8
0x1804744ec  divss   xmm6, xmm8
0x1804744f1  mov     r15d, ebx
0x1804744f4  cmp     r15d, r14d
0x1804744f7  jge     short loc_180474518
0x1804744f9  mov     edx, r15d
0x1804744fc  mov     rcx, rsi
0x1804744ff  call    ?GetAt@?$CComSafeArray@M$03@ATL@@QEAAAEAMJ@Z; ATL::CComSafeArray<float,4>::GetAt(long)
0x180474504  movaps  xmm0, xmm6
0x180474507  subss   xmm0, dword ptr [rax]
0x18047450b  mulss   xmm0, xmm0
0x18047450f  addss   xmm7, xmm0
0x180474513  add     r15d, r12d
0x180474516  jmp     short loc_1804744F4
0x180474518  divss   xmm7, xmm8
0x18047451d  movss   xmm1, cs:__real@3f000000; Y
0x180474525  movaps  xmm0, xmm7; X
0x180474528  call    powf_0
0x18047452d  movaps  xmm7, xmm0
0x180474530  addss   xmm7, xmm7
0x180474534  mov     r15d, ebx
0x180474537  cmp     r15d, r14d
0x18047453a  jge     short loc_18047456F
0x18047453c  mov     edx, r15d
0x18047453f  mov     rcx, rsi
0x180474542  call    ?GetAt@?$CComSafeArray@M$03@ATL@@QEAAAEAMJ@Z; ATL::CComSafeArray<float,4>::GetAt(long)
0x180474547  movss   xmm0, dword ptr [rax]
0x18047454b  subss   xmm0, xmm6
0x18047454f  andps   xmm0, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x180474556  comiss  xmm0, xmm7
0x180474559  jbe     short loc_18047456A
0x18047455b  mov     edx, r15d
0x18047455e  mov     rcx, rsi
0x180474561  call    ?GetAt@?$CComSafeArray@M$03@ATL@@QEAAAEAMJ@Z; ATL::CComSafeArray<float,4>::GetAt(long)
0x180474566  movss   dword ptr [rax], xmm6
0x18047456a  add     r15d, r12d
0x18047456d  jmp     short loc_180474537
0x18047456f  cmp     ebx, r14d
0x180474572  jge     loc_180474819
0x180474578  mov     edx, ebx
0x18047457a  mov     rcx, rsi
0x18047457d  call    ?GetAt@?$CComSafeArray@M$03@ATL@@QEAAAEAMJ@Z; ATL::CComSafeArray<float,4>::GetAt(long)
0x180474582  movss   xmm0, dword ptr [rdi+0B4h]
0x18047458a  comiss  xmm0, dword ptr [rax]
0x18047458d  ja      short loc_18047459D
0x18047458f  mov     edx, ebx
0x180474591  mov     rcx, rsi
0x180474594  call    ?GetAt@?$CComSafeArray@M$03@ATL@@QEAAAEAMJ@Z; ATL::CComSafeArray<float,4>::GetAt(long)
0x180474599  movss   xmm0, dword ptr [rax]
0x18047459d  movss   dword ptr [rdi+0B4h], xmm0
0x1804745a5  add     ebx, r12d
0x1804745a8  jmp     short loc_18047456F
0x1804745aa  mov     [rsp+0B8h+cchCount2], r14d; cchCount2
0x1804745af  lea     rax, aBlackpointrepe; "BlackPointRepeatSize"
0x1804745b6  mov     [rsp+0B8h+lpString2], rax; lpString2
0x1804745bb  mov     r9d, r14d; cchCount1
0x1804745be  mov     r8, rsi; lpString1
0x1804745c1  mov     edx, r12d; dwCmpFlags
0x1804745c4  mov     ecx, r15d; Locale
0x1804745c7  call    cs:__imp_CompareStringW
0x1804745cd  cmp     eax, 2
0x1804745d0  jnz     loc_1804746B5
0x1804745d6  mov     rdx, qword ptr [rsp+0B8h+pvarg+8]; psa
0x1804745db  lea     rcx, [rsp+0B8h+psa]; ppsaOut
0x1804745e3  call    ??0?$CComSafeArray@G$0BC@@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z; ATL::CComSafeArray<ushort,18>::CComSafeArray<ushort,18>(tagSAFEARRAY const *)
0x1804745e8  nop
0x1804745e9  mov     [rsp+0B8h+plLbound], ebx
0x1804745f0  mov     [rsp+0B8h+plUbound], ebx
0x1804745f7  lea     r8, [rsp+0B8h+plLbound]; plLbound
0x1804745ff  mov     edx, r12d; nDim
0x180474602  mov     rcx, [rsp+0B8h+psa]; psa
0x18047460a  call    cs:__imp_SafeArrayGetLBound
0x180474610  test    eax, eax
0x180474612  js      loc_180474881
0x180474618  lea     r8, [rsp+0B8h+plUbound]; plUbound
0x180474620  mov     edx, r12d; nDim
0x180474623  mov     rcx, [rsp+0B8h+psa]; psa
0x18047462b  call    cs:__imp_SafeArrayGetUBound
0x180474631  test    eax, eax
0x180474633  js      loc_180474888
0x180474639  mov     eax, [rsp+0B8h+plUbound]
0x180474640  sub     eax, [rsp+0B8h+plLbound]
0x180474647  cmp     eax, r12d
0x18047464a  jnz     loc_18047488F
0x180474650  xor     edx, edx
0x180474652  lea     rcx, [rsp+0B8h+psa]
0x18047465a  call    ??A?$CComSafeArray@G$0BC@@ATL@@QEAAAEAGH@Z; ATL::CComSafeArray<ushort,18>::operator[](int)
0x18047465f  cmp     [rax], r12w
0x180474663  jnz     loc_180474899
0x180474669  mov     edx, r12d
0x18047466c  lea     rcx, [rsp+0B8h+psa]
0x180474674  call    ??A?$CComSafeArray@G$0BC@@ATL@@QEAAAEAGH@Z; ATL::CComSafeArray<ushort,18>::operator[](int)
0x180474679  cmp     [rax], r12w
0x18047467d  jnz     loc_180474899
0x180474683  mov     rcx, [rsp+0B8h+psa]; psa
0x18047468b  test    rcx, rcx
0x18047468e  jz      loc_180474819
0x180474694  call    cs:__imp_SafeArrayUnlock
0x18047469a  test    eax, eax
0x18047469c  js      loc_180474819
0x1804746a2  mov     rcx, [rsp+0B8h+psa]; psa
0x1804746aa  call    cs:__imp_SafeArrayDestroy
0x1804746b0  jmp     loc_180474819
0x1804746b5  mov     [rsp+0B8h+cchCount2], r14d; cchCount2
0x1804746ba  lea     rax, aLinearizationt; "LinearizationTable"
0x1804746c1  mov     [rsp+0B8h+lpString2], rax; lpString2
0x1804746c6  mov     r9d, r14d; cchCount1
0x1804746c9  mov     r8, rsi; lpString1
0x1804746cc  mov     edx, r12d; dwCmpFlags
0x1804746cf  mov     ecx, r15d; Locale
0x1804746d2  call    cs:__imp_CompareStringW
0x1804746d8  cmp     eax, 2
0x1804746db  jnz     short loc_18047473E
0x1804746dd  mov     rax, qword ptr [rsp+0B8h+pvarg+8]
0x1804746e2  mov     r8, [rax+10h]
0x1804746e6  movsxd  rcx, dword ptr [rax+18h]
0x1804746ea  cmp     ecx, 7FFFFFFFh
0x1804746f0  ja      loc_1804748A7
0x1804746f6  test    ecx, ecx
0x1804746f8  jle     loc_1804748C0
0x1804746fe  mov     r9, rcx
0x180474701  movzx   r10d, word ptr [r8+rcx*2-2]
0x180474707  lea     rcx, [rbx+rbx]
0x18047470b  cmp     rbx, r9
0x18047470e  jge     short loc_180474717
0x180474710  movzx   edx, word ptr [rcx+r8]
0x180474715  jmp     short loc_18047471B
0x180474717  movzx   edx, r10w
0x18047471b  mov     rax, [rdi+90h]
0x180474722  mov     [rcx+rax], dx
0x180474726  add     rbx, r12
0x180474729  cmp     rbx, 10000h
0x180474730  jl      short loc_180474707
0x180474732  mov     [rdi+98h], r12b
0x180474739  jmp     loc_180474819
0x18047473e  mov     [rsp+0B8h+cchCount2], r14d; cchCount2
0x180474743  lea     rax, aWhitepoint; "WhitePoint"
0x18047474a  mov     [rsp+0B8h+lpString2], rax; lpString2
0x18047474f  mov     r9d, r14d; cchCount1
0x180474752  mov     r8, rsi; lpString1
0x180474755  mov     edx, r12d; dwCmpFlags
0x180474758  mov     ecx, r15d; Locale
0x18047475b  call    cs:__imp_CompareStringW
0x180474761  cmp     eax, 2
0x180474764  jnz     short loc_18047478A
0x180474766  cmp     dword ptr [rsp+0B8h+pvarg+8], 0FFFFh
0x18047476e  jg      loc_1804748CA
0x180474774  movd    xmm0, dword ptr [rsp+0B8h+pvarg+8]
0x18047477a  cvtdq2ps xmm0, xmm0
0x18047477d  movss   dword ptr [rdi+0BCh], xmm0
0x180474785  jmp     loc_180474819
0x18047478a  mov     [rsp+0B8h+cchCount2], r14d; cchCount2
0x18047478f  lea     rax, aBlackpoint; "BlackPoint"
0x180474796  mov     [rsp+0B8h+lpString2], rax; lpString2
0x18047479b  mov     r9d, r14d; cchCount1
0x18047479e  mov     r8, rsi; lpString1
0x1804747a1  mov     edx, r12d; dwCmpFlags
0x1804747a4  mov     ecx, r15d; Locale
0x1804747a7  call    cs:__imp_CompareStringW
0x1804747ad  cmp     eax, 2
0x1804747b0  jnz     short loc_1804747D7
0x1804747b2  movsd   xmm1, qword ptr [rsp+0B8h+pvarg+8]
0x1804747b8  cvtpd2ps xmm1, xmm1
0x1804747bc  movss   xmm0, cs:__real@477fff00
0x1804747c4  comiss  xmm0, xmm1
0x1804747c7  jb      loc_1804748D4
0x1804747cd  movss   dword ptr [rdi+0B0h], xmm1
0x1804747d5  jmp     short loc_180474819
0x1804747d7  mov     [rsp+0B8h+cchCount2], r14d; cchCount2
0x1804747dc  lea     rax, aUsepackedpixel; "UsePackedPixels"
0x1804747e3  mov     [rsp+0B8h+lpString2], rax; lpString2
0x1804747e8  mov     r9d, r14d; cchCount1
0x1804747eb  mov     r8, rsi; lpString1
0x1804747ee  mov     edx, r12d; dwCmpFlags
  ... truncated ...
```
