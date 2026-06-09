# ATL::CComSafeArray<ushort *,8>::Add(ushort * const &,int)

- ea: `0x1800086a4`
- end: `0x180008896`
- name: `?Add@?$CComSafeArray@PEAG$07@ATL@@QEAAJAEBQEAGH@Z`
- size: `498`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800070d8`
- `0x180011810`
- `0x18001d670`
- `0x18001e7b0`

## callees

- `0x180002604`
- `0x1800086a4`
- `0x180008898`
- `0x180049b50`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180008833`
- `OLEAUT32!__imp_SysAllocString` at `0x180008833`
- `OLEAUT32!__imp_SysFreeString` at `0x180008822`
- `OLEAUT32!__imp_SysFreeString` at `0x180008822`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800086e8`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800086e8`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800087fa`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800087fa`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18000871d`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800087d1`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18000871d`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800087d1`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180008700`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180008798`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180008700`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180008798`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18000877a`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18000877a`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18000878d`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18000878d`

## pseudocode

```c
HRESULT __fastcall ATL::CComSafeArray<unsigned short *,8>::Add(SAFEARRAY **a1, const OLECHAR **a2, int a3)
{
  SAFEARRAY *v6; // rax
  HRESULT result; // eax
  SAFEARRAY *v8; // rcx
  HRESULT LBound; // eax
  int Count; // eax
  SAFEARRAY *v11; // rcx
  LONG v12; // esi
  HRESULT v13; // ebx
  HRESULT v14; // eax
  LONG v15; // ebx
  SAFEARRAY *v16; // rcx
  HRESULT v17; // eax
  SAFEARRAY *v18; // rcx
  HRESULT UBound; // eax
  __int64 v20; // rbx
  OLECHAR *v21; // rcx
  BSTR v22; // rdx
  SAFEARRAYBOUND rgsabound; // [rsp+20h] [rbp-20h] BYREF
  LONG v24; // [rsp+28h] [rbp-18h] BYREF
  LONG plLbound; // [rsp+2Ch] [rbp-14h] BYREF

  if ( !*a1 )
  {
    rgsabound = 0;
    v6 = SafeArrayCreate(8u, 1u, &rgsabound);
    *a1 = v6;
    if ( !v6 )
    {
      result = -2147024882;
LABEL_10:
      _mm_lfence();
      return result;
    }
    result = SafeArrayLock(v6);
    if ( result < 0 )
      goto LABEL_10;
  }
  v8 = *a1;
  plLbound = 0;
  LBound = SafeArrayGetLBound(v8, 1u, &plLbound);
  if ( LBound < 0 )
  {
    _mm_lfence();
    ATL::AtlThrowImpl(LBound);
  }
  Count = ATL::CComSafeArray<unsigned short *,8>::GetCount(a1);
  v11 = *a1;
  v12 = plLbound;
  rgsabound.cElements = Count + 1;
  rgsabound.lLbound = plLbound;
  if ( !v11 )
    ATL::AtlThrowImpl(-2147467259);
  if ( (v11->fFeatures & 0x10) != 0 )
  {
    v13 = -2147467259;
LABEL_9:
    result = v13;
    goto LABEL_10;
  }
  v13 = SafeArrayUnlock(v11);
  if ( v13 >= 0 )
  {
    v13 = SafeArrayRedim(*a1, &rgsabound);
    v14 = SafeArrayLock(*a1);
    if ( v13 >= 0 )
      v13 = v14;
  }
  if ( v13 < 0 )
    goto LABEL_9;
  v15 = ATL::CComSafeArray<unsigned short *,8>::GetCount(a1) + v12 - 1;
  if ( !*a2 )
    return -2147024809;
  v16 = *a1;
  v24 = 0;
  v17 = SafeArrayGetLBound(v16, 1u, &v24);
  if ( v17 < 0 )
  {
    _mm_lfence();
    ATL::AtlThrowImpl(v17);
  }
  if ( v15 < v24 )
    return -2147024809;
  _mm_lfence();
  v18 = *a1;
  rgsabound.cElements = 0;
  UBound = SafeArrayGetUBound(v18, 1u, (LONG *)&rgsabound);
  if ( UBound < 0 )
  {
    _mm_lfence();
    ATL::AtlThrowImpl(UBound);
  }
  if ( v15 > (int)rgsabound.cElements )
    return -2147024809;
  _mm_lfence();
  v20 = v15 - v24;
  v21 = (OLECHAR *)*((_QWORD *)(*a1)->pvData + v20);
  if ( v21 )
    SysFreeString(v21);
  v22 = (BSTR)*a2;
  if ( a3 )
  {
    v22 = SysAllocString(*a2);
    if ( !v22 )
      return -2147024882;
  }
  _mm_lfence();
  result = 0;
  *((_QWORD *)(*a1)->pvData + v20) = v22;
  return result;
}

```

## disassembly

```asm
0x1800086a4  mov     [rsp-28h+arg_10], rbx
0x1800086a9  push    rbp
0x1800086aa  push    rsi
0x1800086ab  push    rdi
0x1800086ac  push    r14
0x1800086ae  push    r15
0x1800086b0  mov     rbp, rsp
0x1800086b3  sub     rsp, 40h
0x1800086b7  mov     rax, cs:__security_cookie
0x1800086be  xor     rax, rsp
0x1800086c1  mov     [rbp+var_10], rax
0x1800086c5  cmp     qword ptr [rcx], 0
0x1800086c9  mov     r15d, r8d
0x1800086cc  mov     r14, rdx
0x1800086cf  mov     rdi, rcx
0x1800086d2  jnz     short loc_18000870A
0x1800086d4  mov     ecx, 8; vt
0x1800086d9  mov     qword ptr [rbp+rgsabound.cElements], 0
0x1800086e1  lea     r8, [rbp+rgsabound]; rgsabound
0x1800086e5  lea     edx, [rcx-7]; cDims
0x1800086e8  call    cs:__imp_SafeArrayCreate
0x1800086ee  mov     [rdi], rax
0x1800086f1  test    rax, rax
0x1800086f4  jnz     short loc_1800086FD
0x1800086f6  mov     eax, 8007000Eh
0x1800086fb  jmp     short loc_180008757
0x1800086fd  mov     rcx, rax; psa
0x180008700  call    cs:__imp_SafeArrayLock
0x180008706  test    eax, eax
0x180008708  js      short loc_180008757
0x18000870a  mov     rcx, [rdi]; psa
0x18000870d  lea     r8, [rbp+plLbound]; plLbound
0x180008711  mov     edx, 1; nDim
0x180008716  mov     [rbp+plLbound], 0
0x18000871d  call    cs:__imp_SafeArrayGetLBound
0x180008723  test    eax, eax
0x180008725  js      loc_180008875
0x18000872b  mov     rcx, rdi
0x18000872e  call    ?GetCount@?$CComSafeArray@PEAG$07@ATL@@QEBAKI@Z; ATL::CComSafeArray<ushort *,8>::GetCount(uint)
0x180008733  mov     rcx, [rdi]; psa
0x180008736  inc     eax
0x180008738  mov     esi, [rbp+plLbound]
0x18000873b  mov     [rbp+rgsabound.cElements], eax
0x18000873e  mov     [rbp+rgsabound.lLbound], esi
0x180008741  test    rcx, rcx
0x180008744  jz      loc_180008880
0x18000874a  test    byte ptr [rcx+2], 10h
0x18000874e  jz      short loc_18000877A
0x180008750  mov     ebx, 80004005h
0x180008755  mov     eax, ebx
0x180008757  lfence
0x18000875a  mov     rcx, [rbp+var_10]
0x18000875e  xor     rcx, rsp; StackCookie
0x180008761  call    __security_check_cookie
0x180008766  mov     rbx, [rsp+40h+arg_10]
0x18000876e  add     rsp, 40h
0x180008772  pop     r15
0x180008774  pop     r14
0x180008776  pop     rdi
0x180008777  pop     rsi
0x180008778  pop     rbp
0x180008779  retn
0x18000877a  call    cs:__imp_SafeArrayUnlock
0x180008780  mov     ebx, eax
0x180008782  test    eax, eax
0x180008784  js      short loc_1800087A3
0x180008786  mov     rcx, [rdi]; psa
0x180008789  lea     rdx, [rbp+rgsabound]; psaboundNew
0x18000878d  call    cs:__imp_SafeArrayRedim
0x180008793  mov     rcx, [rdi]; psa
0x180008796  mov     ebx, eax
0x180008798  call    cs:__imp_SafeArrayLock
0x18000879e  test    ebx, ebx
0x1800087a0  cmovns  ebx, eax
0x1800087a3  test    ebx, ebx
0x1800087a5  js      short loc_180008755
0x1800087a7  mov     rcx, rdi
0x1800087aa  call    ?GetCount@?$CComSafeArray@PEAG$07@ATL@@QEBAKI@Z; ATL::CComSafeArray<ushort *,8>::GetCount(uint)
0x1800087af  lea     ebx, [rsi-1]
0x1800087b2  add     ebx, eax
0x1800087b4  cmp     qword ptr [r14], 0
0x1800087b8  jz      loc_180008860
0x1800087be  mov     rcx, [rdi]; psa
0x1800087c1  lea     r8, [rbp+var_18]; plLbound
0x1800087c5  mov     edx, 1; nDim
0x1800087ca  mov     [rbp+var_18], 0
0x1800087d1  call    cs:__imp_SafeArrayGetLBound
0x1800087d7  test    eax, eax
0x1800087d9  js      loc_18000888B
0x1800087df  cmp     ebx, [rbp+var_18]
0x1800087e2  jl      short loc_180008860
0x1800087e4  lfence
0x1800087e7  mov     rcx, [rdi]; psa
0x1800087ea  lea     r8, [rbp+rgsabound]; plUbound
0x1800087ee  mov     edx, 1; nDim
0x1800087f3  mov     [rbp+rgsabound.cElements], 0
0x1800087fa  call    cs:__imp_SafeArrayGetUBound
0x180008800  test    eax, eax
0x180008802  js      short loc_18000886A
0x180008804  cmp     ebx, [rbp+rgsabound.cElements]
0x180008807  jg      short loc_180008860
0x180008809  lfence
0x18000880c  sub     ebx, [rbp+var_18]
0x18000880f  mov     rax, [rdi]
0x180008812  movsxd  rbx, ebx
0x180008815  mov     rcx, [rax+10h]
0x180008819  mov     rcx, [rcx+rbx*8]; bstrString
0x18000881d  test    rcx, rcx
0x180008820  jz      short loc_180008828
0x180008822  call    cs:__imp_SysFreeString
0x180008828  mov     rdx, [r14]
0x18000882b  test    r15d, r15d
0x18000882e  jz      short loc_18000884B
0x180008830  mov     rcx, rdx; psz
0x180008833  call    cs:__imp_SysAllocString
0x180008839  mov     rdx, rax
0x18000883c  test    rax, rax
0x18000883f  jnz     short loc_18000884B
0x180008841  mov     eax, 8007000Eh
0x180008846  jmp     loc_18000875A
0x18000884b  lfence
0x18000884e  mov     rax, [rdi]
0x180008851  mov     rcx, [rax+10h]
0x180008855  xor     eax, eax
0x180008857  mov     [rcx+rbx*8], rdx
0x18000885b  jmp     loc_18000875A
0x180008860  mov     eax, 80070057h
0x180008865  jmp     loc_18000875A
0x18000886a  lfence
0x18000886d  mov     ecx, eax; int
0x18000886f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180008875  lfence
0x180008878  mov     ecx, eax; int
0x18000887a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180008880  mov     ecx, 80004005h; int
0x180008885  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000888b  lfence
0x18000888e  mov     ecx, eax; int
0x180008890  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
