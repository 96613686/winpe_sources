# ATL::CComSafeArray<ulong,19>::Add(ulong const &,int)

- ea: `0x1800248b4`
- end: `0x180024afa`
- name: `?Add@?$CComSafeArray@K$0BD@@ATL@@QEAAJAEBKH@Z`
- size: `582`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001e0d0`

## callees

- `0x180002604`
- `0x1800248b4`
- `0x180049b50`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x180024903`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180024903`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180024969`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180024a19`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180024a70`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180024969`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180024a19`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180024a70`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180024939`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180024951`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180024a01`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180024a4c`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180024939`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180024951`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180024a01`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180024a4c`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18002491e`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1800249e8`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18002491e`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1800249e8`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1800249ca`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1800249ca`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x1800249dd`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x1800249dd`

## pseudocode

```c
HRESULT __fastcall ATL::CComSafeArray<unsigned long,19>::Add(SAFEARRAY **a1, _DWORD *a2)
{
  SAFEARRAY *v4; // rax
  HRESULT result; // eax
  SAFEARRAY *v6; // rcx
  HRESULT LBound; // eax
  HRESULT v8; // eax
  HRESULT UBound; // eax
  SAFEARRAY *v10; // rcx
  LONG v11; // esi
  HRESULT v12; // ebx
  HRESULT v13; // eax
  HRESULT v14; // eax
  HRESULT v15; // eax
  SAFEARRAY *v16; // rcx
  LONG v17; // ebx
  int v18; // ebx
  HRESULT v19; // eax
  SAFEARRAY *v20; // rcx
  HRESULT v21; // eax
  __int64 v22; // rdx
  LONG plUbound; // [rsp+20h] [rbp-20h] BYREF
  LONG plLbound; // [rsp+24h] [rbp-1Ch] BYREF
  LONG v25; // [rsp+28h] [rbp-18h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+30h] [rbp-10h] BYREF

  if ( !*a1 )
  {
    rgsabound = 0;
    v4 = SafeArrayCreate(0x13u, 1u, &rgsabound);
    *a1 = v4;
    if ( !v4 )
    {
      result = -2147024882;
LABEL_12:
      _mm_lfence();
      return result;
    }
    result = SafeArrayLock(v4);
    if ( result < 0 )
      goto LABEL_12;
  }
  v6 = *a1;
  plLbound = 0;
  LBound = SafeArrayGetLBound(v6, 1u, &plLbound);
  if ( LBound < 0 )
  {
    _mm_lfence();
    ATL::AtlThrowImpl(LBound);
  }
  v8 = SafeArrayGetLBound(*a1, 1u, &v25);
  if ( v8 < 0 )
  {
    _mm_lfence();
    ATL::AtlThrowImpl(v8);
  }
  UBound = SafeArrayGetUBound(*a1, 1u, &plUbound);
  if ( UBound < 0 )
  {
    _mm_lfence();
    ATL::AtlThrowImpl(UBound);
  }
  v10 = *a1;
  v11 = plLbound;
  rgsabound.cElements = plUbound - v25 + 2;
  rgsabound.lLbound = plLbound;
  if ( !v10 )
    ATL::AtlThrowImpl(-2147467259);
  if ( (v10->fFeatures & 0x10) != 0 )
  {
    v12 = -2147467259;
LABEL_11:
    result = v12;
    goto LABEL_12;
  }
  v12 = SafeArrayUnlock(v10);
  if ( v12 >= 0 )
  {
    v12 = SafeArrayRedim(*a1, &rgsabound);
    v13 = SafeArrayLock(*a1);
    if ( v12 >= 0 )
      v12 = v13;
  }
  if ( v12 < 0 )
    goto LABEL_11;
  v14 = SafeArrayGetLBound(*a1, 1u, (LONG *)&rgsabound);
  if ( v14 < 0 )
  {
    _mm_lfence();
    ATL::AtlThrowImpl(v14);
  }
  v15 = SafeArrayGetUBound(*a1, 1u, &v25);
  if ( v15 < 0 )
  {
    _mm_lfence();
    ATL::AtlThrowImpl(v15);
  }
  v16 = *a1;
  v17 = v11 + v25 - rgsabound.cElements;
  if ( !*a1 )
    return -2147467259;
  plUbound = 0;
  v19 = SafeArrayGetLBound(v16, 1u, &plUbound);
  if ( v19 < 0 )
  {
    _mm_lfence();
    ATL::AtlThrowImpl(v19);
  }
  if ( v17 < plUbound )
    return -2147024809;
  v20 = *a1;
  plLbound = 0;
  v21 = SafeArrayGetUBound(v20, 1u, &plLbound);
  if ( v21 < 0 )
  {
    _mm_lfence();
    ATL::AtlThrowImpl(v21);
  }
  if ( v17 > plLbound )
    return -2147024809;
  v22 = v17 - plUbound;
  v18 = 0;
  *((_DWORD *)(*a1)->pvData + v22) = *a2;
  return v18;
}

```

## disassembly

```asm
0x1800248b4  mov     [rsp-18h+arg_8], rbx
0x1800248b9  mov     [rsp-18h+arg_10], rsi
0x1800248be  mov     [rsp-18h+arg_18], rdi
0x1800248c3  push    rbp
0x1800248c4  push    r12
0x1800248c6  push    r14
0x1800248c8  mov     rbp, rsp
0x1800248cb  sub     rsp, 40h
0x1800248cf  mov     rax, cs:__security_cookie
0x1800248d6  xor     rax, rsp
0x1800248d9  mov     [rbp+var_8], rax
0x1800248dd  cmp     qword ptr [rcx], 0
0x1800248e1  mov     r14, rdx
0x1800248e4  mov     rdi, rcx
0x1800248e7  mov     r12d, 1
0x1800248ed  jnz     short loc_180024928
0x1800248ef  lea     ecx, [r12+12h]; vt
0x1800248f4  mov     qword ptr [rbp+rgsabound.cElements], 0
0x1800248fc  lea     r8, [rbp+rgsabound]; rgsabound
0x180024900  mov     edx, r12d; cDims
0x180024903  call    cs:__imp_SafeArrayCreate
0x180024909  mov     [rdi], rax
0x18002490c  test    rax, rax
0x18002490f  jnz     short loc_18002491B
0x180024911  mov     eax, 8007000Eh
0x180024916  jmp     loc_1800249A2
0x18002491b  mov     rcx, rax; psa
0x18002491e  call    cs:__imp_SafeArrayLock
0x180024924  test    eax, eax
0x180024926  js      short loc_1800249A2
0x180024928  mov     rcx, [rdi]; psa
0x18002492b  lea     r8, [rbp+plLbound]; plLbound
0x18002492f  mov     edx, r12d; nDim
0x180024932  mov     [rbp+plLbound], 0
0x180024939  call    cs:__imp_SafeArrayGetLBound
0x18002493f  test    eax, eax
0x180024941  js      loc_180024AAD
0x180024947  mov     rcx, [rdi]; psa
0x18002494a  lea     r8, [rbp+var_18]; plLbound
0x18002494e  mov     edx, r12d; nDim
0x180024951  call    cs:__imp_SafeArrayGetLBound
0x180024957  test    eax, eax
0x180024959  js      loc_180024AB8
0x18002495f  mov     rcx, [rdi]; psa
0x180024962  lea     r8, [rbp+plUbound]; plUbound
0x180024966  mov     edx, r12d; nDim
0x180024969  call    cs:__imp_SafeArrayGetUBound
0x18002496f  test    eax, eax
0x180024971  js      loc_180024AC3
0x180024977  mov     eax, [rbp+plUbound]
0x18002497a  sub     eax, [rbp+var_18]
0x18002497d  mov     rcx, [rdi]; psa
0x180024980  add     eax, 2
0x180024983  mov     esi, [rbp+plLbound]
0x180024986  mov     [rbp+rgsabound.cElements], eax
0x180024989  mov     [rbp+rgsabound.lLbound], esi
0x18002498c  test    rcx, rcx
0x18002498f  jz      loc_180024ACE
0x180024995  test    byte ptr [rcx+2], 10h
0x180024999  jz      short loc_1800249CA
0x18002499b  mov     ebx, 80004005h
0x1800249a0  mov     eax, ebx
0x1800249a2  lfence
0x1800249a5  mov     rcx, [rbp+var_8]
0x1800249a9  xor     rcx, rsp; StackCookie
0x1800249ac  call    __security_check_cookie
0x1800249b1  mov     rbx, [rsp+40h+arg_8]
0x1800249b6  mov     rsi, [rsp+40h+arg_10]
0x1800249bb  mov     rdi, [rsp+40h+arg_18]
0x1800249c0  add     rsp, 40h
0x1800249c4  pop     r14
0x1800249c6  pop     r12
0x1800249c8  pop     rbp
0x1800249c9  retn
0x1800249ca  call    cs:__imp_SafeArrayUnlock
0x1800249d0  mov     ebx, eax
0x1800249d2  test    eax, eax
0x1800249d4  js      short loc_1800249F3
0x1800249d6  mov     rcx, [rdi]; psa
0x1800249d9  lea     rdx, [rbp+rgsabound]; psaboundNew
0x1800249dd  call    cs:__imp_SafeArrayRedim
0x1800249e3  mov     rcx, [rdi]; psa
0x1800249e6  mov     ebx, eax
0x1800249e8  call    cs:__imp_SafeArrayLock
0x1800249ee  test    ebx, ebx
0x1800249f0  cmovns  ebx, eax
0x1800249f3  test    ebx, ebx
0x1800249f5  js      short loc_1800249A0
0x1800249f7  mov     rcx, [rdi]; psa
0x1800249fa  lea     r8, [rbp+rgsabound]; plLbound
0x1800249fe  mov     edx, r12d; nDim
0x180024a01  call    cs:__imp_SafeArrayGetLBound
0x180024a07  test    eax, eax
0x180024a09  js      loc_180024AD9
0x180024a0f  mov     rcx, [rdi]; psa
0x180024a12  lea     r8, [rbp+var_18]; plUbound
0x180024a16  mov     edx, r12d; nDim
0x180024a19  call    cs:__imp_SafeArrayGetUBound
0x180024a1f  test    eax, eax
0x180024a21  js      loc_180024AE4
0x180024a27  mov     ebx, [rbp+var_18]
0x180024a2a  sub     ebx, [rbp+rgsabound.cElements]
0x180024a2d  mov     rcx, [rdi]; psa
0x180024a30  add     ebx, esi
0x180024a32  test    rcx, rcx
0x180024a35  jnz     short loc_180024A3E
0x180024a37  mov     ebx, 80004005h
0x180024a3c  jmp     short loc_180024A9B
0x180024a3e  lea     r8, [rbp+plUbound]; plLbound
0x180024a42  mov     [rbp+plUbound], 0
0x180024a49  mov     edx, r12d; nDim
0x180024a4c  call    cs:__imp_SafeArrayGetLBound
0x180024a52  test    eax, eax
0x180024a54  js      loc_180024AEF
0x180024a5a  cmp     ebx, [rbp+plUbound]
0x180024a5d  jl      short loc_180024A96
0x180024a5f  mov     rcx, [rdi]; psa
0x180024a62  lea     r8, [rbp+plLbound]; plUbound
0x180024a66  mov     edx, r12d; nDim
0x180024a69  mov     [rbp+plLbound], 0
0x180024a70  call    cs:__imp_SafeArrayGetUBound
0x180024a76  test    eax, eax
0x180024a78  js      short loc_180024AA2
0x180024a7a  cmp     ebx, [rbp+plLbound]
0x180024a7d  jg      short loc_180024A96
0x180024a7f  mov     rax, [rdi]
0x180024a82  sub     ebx, [rbp+plUbound]
0x180024a85  movsxd  rdx, ebx
0x180024a88  xor     ebx, ebx
0x180024a8a  mov     rcx, [rax+10h]
0x180024a8e  mov     eax, [r14]
0x180024a91  mov     [rcx+rdx*4], eax
0x180024a94  jmp     short loc_180024A9B
0x180024a96  mov     ebx, 80070057h
0x180024a9b  mov     eax, ebx
0x180024a9d  jmp     loc_1800249A5
0x180024aa2  lfence
0x180024aa5  mov     ecx, eax; int
0x180024aa7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180024aad  lfence
0x180024ab0  mov     ecx, eax; int
0x180024ab2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180024ab8  lfence
0x180024abb  mov     ecx, eax; int
0x180024abd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180024ac3  lfence
0x180024ac6  mov     ecx, eax; int
0x180024ac8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180024ace  mov     ecx, 80004005h; int
0x180024ad3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180024ad9  lfence
0x180024adc  mov     ecx, eax; int
0x180024ade  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180024ae4  lfence
0x180024ae7  mov     ecx, eax; int
0x180024ae9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180024aef  lfence
0x180024af2  mov     ecx, eax; int
0x180024af4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
