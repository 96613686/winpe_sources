# GetRuntimeId(IUiaNode *,BasicArrayPair<int> *)

- ea: `0x1800313a0`
- end: `0x18003160d`
- name: `?GetRuntimeId@@YAJPEAVIUiaNode@@PEAU?$BasicArrayPair@H@@@Z`
- size: `621`
- prototype: ``
- caller_count: `21`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000cec8`
- `0x18000f058`
- `0x180012b54`
- `0x1800183d0`
- `0x18001afb0`
- `0x1800248f0`
- `0x180029d54`
- `0x180045340`
- `0x18005f228`
- `0x1800637c0`
- `0x180064788`
- `0x180067070`
- `0x180069c98`
- `0x1800c7fe0`
- `0x1800c8d84`
- `0x1800c9b68`
- `0x1801102d0`
- `0x180111564`
- `0x1801274bc`
- `0x18013969c`
- `0x1801da444`

## callees

- `0x18002f580`
- `0x180030ee4`
- `0x1800313a0`
- `0x180032724`
- `0x1801e8344`
- `0x1801e8840`
- `0x1801e9240`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18003157a`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18003157a`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800313e2`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800313e2`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180031469`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180031469`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18003144a`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18003144a`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180031494`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180031494`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18003156a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18003156a`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18003140c`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18003140c`

## string_xrefs

- `0x180031598`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x18003153e`: `onecore\windows\accessibletech\uiautomationcore\SafeApis.h`
- `0x1800314b2`: `onecore\windows\accessibletech\uiautomationcore\uiautil.cpp`
- `0x180031520`: `onecore\windows\accessibletech\uiautomationcore\uiautil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetRuntimeId(__int64 a1, __int64 a2)
{
  const char *v3; // r9
  SAFEARRAY *v4; // rcx
  HRESULT Vartype; // eax
  int v6; // ebx
  HRESULT LBound; // eax
  HRESULT UBound; // eax
  HRESULT v9; // eax
  unsigned int v10; // r14d
  void *v11; // rsi
  unsigned __int64 v12; // rcx
  int v13; // ebx
  __int64 result; // rax
  __int64 v15; // r9
  __int64 v16; // rdx
  LONG plLbound; // [rsp+20h] [rbp-48h] BYREF
  SAFEARRAY *psa; // [rsp+28h] [rbp-40h] BYREF
  SAFEARRAY *v19; // [rsp+30h] [rbp-38h]
  int v20; // [rsp+38h] [rbp-30h]
  void *ppvData; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  void *pvt; // [rsp+80h] [rbp+18h] BYREF
  LONG plUbound; // [rsp+88h] [rbp+20h] BYREF

  try
  {
    GetRuntimeIdSafeArray(&psa, a1);
    v4 = psa;
    if ( !psa )
    {
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)a2 = 0;
LABEL_20:
      if ( v4 )
        SafeArrayDestroy(v4);
      return 0;
    }
    v20 = 0;
    ppvData = 0;
    v19 = psa;
    if ( SafeArrayGetDim(psa) == 1 )
    {
      LOWORD(pvt) = 0;
      Vartype = SafeArrayGetVartype(v19, (VARTYPE *)&pvt);
      v6 = Vartype;
      if ( Vartype < 0 )
      {
        v15 = (unsigned int)Vartype;
        v16 = 95;
        goto LABEL_24;
      }
      if ( (_WORD)pvt == 3 || (_WORD)pvt == 22 )
      {
        plLbound = 0;
        plUbound = 0;
        LBound = SafeArrayGetLBound(v19, 1u, &plLbound);
        v6 = LBound;
        if ( LBound < 0 )
        {
          v15 = (unsigned int)LBound;
          v16 = 111;
        }
        else
        {
          UBound = SafeArrayGetUBound(v19, 1u, &plUbound);
          v6 = UBound;
          if ( UBound < 0 )
          {
            v15 = (unsigned int)UBound;
            v16 = 112;
          }
          else
          {
            v20 = plUbound - plLbound + 1;
            v9 = SafeArrayAccessData(v19, &ppvData);
            v6 = v9;
            if ( v9 >= 0 )
            {
              v6 = 0;
LABEL_10:
              if ( v6 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x138,
                  (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uiautil.cpp",
                  (const char *)(unsigned int)v6,
                  plLbound);
              v10 = v20;
              v11 = operator new[](saturated_mul(v20, 4u));
              pvt = v11;
              v12 = 4LL * v10;
              if ( v12 > 0xFFFFFFFF )
              {
                v13 = -2147024362;
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x46,
                  (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\SafeApis.h",
                  (const char *)0x80070216LL,
                  plLbound);
              }
              else
              {
                memcpy_0(v11, ppvData, (unsigned int)v12);
                v13 = 0;
              }
              if ( v13 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x13C,
                  (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uiautil.cpp",
                  (const char *)(unsigned int)v13,
                  plLbound);
              *(_QWORD *)(a2 + 8) = v11;
              *(_DWORD *)a2 = v10;
              operator delete(0);
              if ( v19 )
                SafeArrayUnaccessData(v19);
              v4 = psa;
              goto LABEL_20;
            }
            v15 = (unsigned int)v9;
            v16 = 115;
          }
        }
LABEL_24:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v16,
          (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
          (const char *)v15,
          plLbound);
        goto LABEL_10;
      }
      v16 = 106;
    }
    else
    {
      v16 = 92;
    }
    v6 = -2147024809;
    v15 = 2147942487LL;
    goto LABEL_24;
  }
  catch ( ... )
  {
    LODWORD(pvt) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x151,
                     (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uiautil.cpp",
                     v3);
    return (unsigned int)pvt;
  }
  return result;
}

```

## disassembly

```asm
0x1800313a0  mov     [rsp+arg_0], rbx
0x1800313a5  push    rsi
0x1800313a6  push    rdi
0x1800313a7  push    r14
0x1800313a9  sub     rsp, 50h
0x1800313ad  mov     rdi, rdx
0x1800313b0  mov     rdx, rcx
0x1800313b3  lea     rcx, [rsp+68h+psa]
0x1800313b8  call    ?GetRuntimeIdSafeArray@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUtagSAFEARRAY@@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAVIUiaNode@@@Z; GetRuntimeIdSafeArray(IUiaNode *)
0x1800313bd  nop
0x1800313be  mov     rcx, [rsp+68h+psa]; psa
0x1800313c3  test    rcx, rcx
0x1800313c6  jz      loc_1800315D1
0x1800313cc  mov     [rsp+68h+var_30], 0
0x1800313d4  mov     [rsp+68h+ppvData], 0
0x1800313dd  mov     [rsp+68h+var_38], rcx
0x1800313e2  call    cs:__imp_SafeArrayGetDim
0x1800313e8  mov     esi, 1
0x1800313ed  cmp     eax, esi
0x1800313ef  jnz     loc_1800315B8
0x1800313f5  xor     eax, eax
0x1800313f7  mov     word ptr [rsp+68h+pvt], ax
0x1800313ff  lea     rdx, [rsp+68h+pvt]; pvt
0x180031407  mov     rcx, [rsp+68h+var_38]; psa
0x18003140c  call    cs:__imp_SafeArrayGetVartype
0x180031412  mov     ebx, eax
0x180031414  test    eax, eax
0x180031416  js      loc_1800315C7
0x18003141c  cmp     word ptr [rsp+68h+pvt], 3
0x180031425  jnz     loc_1800315EB
0x18003142b  mov     [rsp+68h+plLbound], 0; int
0x180031433  mov     [rsp+68h+plUbound], 0
0x18003143e  lea     r8, [rsp+68h+plLbound]; plLbound
0x180031443  mov     edx, esi; nDim
0x180031445  mov     rcx, [rsp+68h+var_38]; psa
0x18003144a  call    cs:__imp_SafeArrayGetLBound
0x180031450  mov     ebx, eax
0x180031452  test    eax, eax
0x180031454  js      loc_180031590
0x18003145a  lea     r8, [rsp+68h+plUbound]; plUbound
0x180031462  mov     edx, esi; nDim
0x180031464  mov     rcx, [rsp+68h+var_38]; psa
0x180031469  call    cs:__imp_SafeArrayGetUBound
0x18003146f  mov     ebx, eax
0x180031471  test    eax, eax
0x180031473  js      loc_1800315AE
0x180031479  mov     eax, [rsp+68h+plUbound]
0x180031480  sub     eax, [rsp+68h+plLbound]
0x180031484  add     eax, esi
0x180031486  mov     [rsp+68h+var_30], eax
0x18003148a  lea     rdx, [rsp+68h+ppvData]; ppvData
0x18003148f  mov     rcx, [rsp+68h+var_38]; psa
0x180031494  call    cs:__imp_SafeArrayAccessData
0x18003149a  mov     ebx, eax
0x18003149c  test    eax, eax
0x18003149e  js      loc_1800315E1
0x1800314a4  xor     ebx, ebx
0x1800314a6  mov     rcx, [rsp+68h]; this
0x1800314ab  test    ebx, ebx
0x1800314ad  jns     short loc_1800314C3
0x1800314af  mov     r9d, ebx; char *
0x1800314b2  lea     r8, aOnecoreWindows_110; "onecore\\windows\\accessibletech\\uiaut"...
0x1800314b9  mov     edx, 138h; void *
0x1800314be  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800314c3  mov     r14d, [rsp+68h+var_30]
0x1800314c8  movsxd  rcx, r14d
0x1800314cb  mov     eax, 4
0x1800314d0  mul     rcx
0x1800314d3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800314da  cmovb   rax, rcx
0x1800314de  mov     rcx, rax; unsigned __int64
0x1800314e1  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800314e6  mov     rsi, rax
0x1800314e9  mov     [rsp+68h+pvt], rax
0x1800314f1  mov     ecx, r14d
0x1800314f4  shl     rcx, 2
0x1800314f8  mov     eax, 0FFFFFFFFh
0x1800314fd  cmp     rcx, rax
0x180031500  ja      short loc_180031531
0x180031502  mov     r8d, ecx; Size
0x180031505  mov     rdx, [rsp+68h+ppvData]; Src
0x18003150a  mov     rcx, rsi; void *
0x18003150d  call    memcpy_0
0x180031512  xor     ebx, ebx
0x180031514  mov     rcx, [rsp+68h]; this
0x180031519  test    ebx, ebx
0x18003151b  jns     short loc_180031551
0x18003151d  mov     r9d, ebx; char *
0x180031520  lea     r8, aOnecoreWindows_110; "onecore\\windows\\accessibletech\\uiaut"...
0x180031527  mov     edx, 13Ch; void *
0x18003152c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031531  mov     rcx, [rsp+68h]; this
0x180031536  mov     ebx, 80070216h
0x18003153b  mov     r9d, ebx; char *
0x18003153e  lea     r8, aOnecoreWindows_51; "onecore\\windows\\accessibletech\\uiaut"...
0x180031545  mov     edx, 46h ; 'F'; void *
0x18003154a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003154f  jmp     short loc_180031514
0x180031551  mov     [rdi+8], rsi
0x180031555  mov     [rdi], r14d
0x180031558  xor     ecx, ecx; Block
0x18003155a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003155f  nop
0x180031560  mov     rcx, [rsp+68h+var_38]; psa
0x180031565  test    rcx, rcx
0x180031568  jz      short loc_180031570
0x18003156a  call    cs:__imp_SafeArrayUnaccessData
0x180031570  mov     rcx, [rsp+68h+psa]; psa
0x180031575  test    rcx, rcx
0x180031578  jz      short loc_180031580
0x18003157a  call    cs:__imp_SafeArrayDestroy
0x180031580  xor     eax, eax
0x180031582  mov     rbx, [rsp+68h+arg_0]
0x180031587  add     rsp, 50h
0x18003158b  pop     r14
0x18003158d  pop     rdi
0x18003158e  pop     rsi
0x18003158f  retn
0x180031590  mov     r9d, eax; char *
0x180031593  mov     edx, 6Fh ; 'o'; void *
0x180031598  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x18003159f  mov     rcx, [rsp+68h]; this
0x1800315a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800315a9  jmp     loc_1800314A6
0x1800315ae  mov     r9d, eax
0x1800315b1  mov     edx, 70h ; 'p'
0x1800315b6  jmp     short loc_180031598
0x1800315b8  mov     edx, 5Ch ; '\'
0x1800315bd  mov     ebx, 80070057h
0x1800315c2  mov     r9d, ebx
0x1800315c5  jmp     short loc_180031598
0x1800315c7  mov     r9d, eax
0x1800315ca  mov     edx, 5Fh ; '_'
0x1800315cf  jmp     short loc_180031598
0x1800315d1  mov     qword ptr [rdi+8], 0
0x1800315d9  mov     dword ptr [rdi], 0
0x1800315df  jmp     short loc_180031575
0x1800315e1  mov     r9d, eax
0x1800315e4  mov     edx, 73h ; 's'
0x1800315e9  jmp     short loc_180031598
0x1800315eb  cmp     word ptr [rsp+68h+pvt], 16h
0x1800315f4  jz      loc_18003142B
0x1800315fa  mov     edx, 6Ah ; 'j'
0x1800315ff  jmp     short loc_1800315BD
0x180031601  mov     eax, dword ptr [rsp+68h+pvt]
0x180031608  jmp     loc_180031582
```
