# MsixPackage::Provisioning::Library::MsixProvisioningManager::ValidateRegion(ushort *)

- ea: `0x18003dd38`
- end: `0x18003e1c4`
- name: `?ValidateRegion@MsixProvisioningManager@Library@Provisioning@MsixPackage@@SAJPEAG@Z`
- size: `1164`
- prototype: `__int64 __fastcall(wchar_t *Source)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180036618`
- `0x18003856c`

## callees

- `0x180002fb4`
- `0x18000d3dc`
- `0x18001d160`
- `0x180026e3c`
- `0x18002b8c0`
- `0x18003d4ec`
- `0x18003dd38`
- `0x18006c910`
- `0x180070010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18003dde6`
- `msvcrt!wcscpy_s` at `0x18003ddfa`
- `msvcrt!wcscpy_s` at `0x18003dde6`
- `msvcrt!wcscpy_s` at `0x18003ddfa`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003df89`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003e031`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003e105`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003e181`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003df89`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003e031`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003e105`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003e181`
- `msvcrt!towupper` at `0x18003deac`
- `msvcrt!wcstok_s` at `0x18003de1a`
- `msvcrt!wcstok_s` at `0x18003e0ca`
- `msvcrt!wcstok_s` at `0x18003de1a`
- `msvcrt!wcstok_s` at `0x18003e0ca`
- `OLEAUT32!__imp_SysStringLen` at `0x18003dda1`
- `OLEAUT32!__imp_SysStringLen` at `0x18003dda1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003dd89`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003e075`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003e0ab`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003dd89`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003e075`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003e0ab`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003df32`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003df32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003deeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003deeb`

## string_xrefs

- `0x18003df4f`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003dff7`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003e147`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall MsixPackage::Provisioning::Library::MsixProvisioningManager::ValidateRegion(wchar_t *Source)
{
  __int64 result; // rax
  int v3; // eax
  bool v4; // zf
  unsigned __int64 v5; // rdi
  wchar_t *v6; // rsi
  wchar_t *v7; // r14
  wchar_t *v8; // rbx
  __int64 v9; // r8
  LPCWCH *v10; // rbx
  LPCWCH *v11; // rcx
  LPCWCH *v12; // rsi
  LPCWCH *v13; // rdi
  HRESULT v14; // eax
  int v15; // edx
  unsigned int v16; // r8d
  HSTRING v17; // rbx
  __int64 v18; // rcx
  int ActivationFactory; // eax
  unsigned int v20; // ebx
  __int64 v21; // rcx
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, _QWORD, _BYTE *); // rbx
  LPCWCH *v24; // rdx
  __int64 v25; // rax
  int v26; // eax
  unsigned int v27; // ebx
  __int64 v28; // rcx
  const WCHAR *v29; // rcx
  const WCHAR *v30; // rcx
  __int64 v31; // rcx
  LPCWCH *v32; // rax
  __int64 v33; // rcx
  int bIgnoreCase; // [rsp+20h] [rbp-B8h]
  _BYTE v35[8]; // [rsp+30h] [rbp-A8h] BYREF
  __int64 v36; // [rsp+38h] [rbp-A0h] BYREF
  wchar_t *Context; // [rsp+40h] [rbp-98h] BYREF
  LPCWCH *v38; // [rsp+48h] [rbp-90h] BYREF
  LPCWCH lpString1[2]; // [rsp+50h] [rbp-88h] BYREF
  __int64 v40; // [rsp+60h] [rbp-78h]
  unsigned __int64 v41; // [rsp+68h] [rbp-70h]
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-68h] BYREF
  HSTRING string; // [rsp+88h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  if ( !Source )
    return 2147500035LL;
  v3 = CompareStringOrdinal(Source, -1, L"all", -1, 1);
  v4 = v3 == 2;
  result = (unsigned int)(v3 - 2);
  if ( !v4 )
  {
    v5 = SysStringLen(Source) + 1;
    v6 = (wchar_t *)operator new[](saturated_mul(v5, 2u));
    v7 = (wchar_t *)operator new[](saturated_mul(v5, 2u));
    wcscpy_s(v6, (unsigned int)v5, Source);
    wcscpy_s(v7, (unsigned int)v5, Source);
    Context = 0;
    v8 = wcstok_s(v6, L";", &Context);
    while ( 1 )
    {
      if ( !v8 )
        return 0;
      v41 = 7;
      v40 = 0;
      LOWORD(lpString1[0]) = 0;
      if ( *v8 )
      {
        v9 = -1;
        do
          ++v9;
        while ( v8[v9] );
      }
      std::wstring::assign(lpString1, v8);
      v10 = lpString1;
      if ( v41 >= 8 )
        v10 = (LPCWCH *)lpString1[0];
      v11 = lpString1;
      if ( v41 >= 8 )
        v11 = (LPCWCH *)lpString1[0];
      v12 = (LPCWCH *)((char *)v11 + 2 * v40);
      v13 = lpString1;
      if ( v41 >= 8 )
        v13 = (LPCWCH *)lpString1[0];
      if ( v13 != v12 )
      {
        while ( v13 != v12 )
        {
          *(_WORD *)v10 = ((__int64 (__fastcall *)(_QWORD))towupper)(*(unsigned __int16 *)v13);
          v13 = (LPCWCH *)((char *)v13 + 2);
          v10 = (LPCWCH *)((char *)v10 + 2);
        }
      }
      v36 = 0;
      string = 0;
      v14 = WindowsCreateStringReference(L"Windows.Globalization.GeographicRegion", 0x26u, &hstringHeader, &string);
      if ( v14 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v14, v15, v16);
        JUMPOUT(0x18003E1C2LL);
      }
      v17 = string;
      v18 = v36;
      if ( v36 )
      {
        v36 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      }
      ActivationFactory = RoGetActivationFactory(v17, &GUID_29e28974_7ad9_4ef4_8799_b3b44fadec08, &v36);
      v20 = ActivationFactory;
      if ( ActivationFactory < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x58E,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
          (const char *)(unsigned int)ActivationFactory,
          bIgnoreCase);
        v21 = v36;
        if ( v36 )
        {
          v36 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        }
        if ( v41 >= 8 )
          operator delete((void *)lpString1[0]);
        return v20;
      }
      v35[0] = 0;
      v22 = v36;
      v23 = *(__int64 (__fastcall **)(__int64, _QWORD, _BYTE *))(*(_QWORD *)v36 + 48LL);
      v24 = lpString1;
      if ( v41 >= 8 )
        v24 = (LPCWCH *)lpString1[0];
      v38 = v24;
      v25 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v38);
      v26 = v23(v22, *(_QWORD *)(v25 + 24), v35);
      v27 = v26;
      if ( v26 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x591,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
          (const char *)(unsigned int)v26,
          bIgnoreCase);
        v28 = v36;
        if ( v36 )
        {
          v36 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
        }
        if ( v41 >= 8 )
          operator delete((void *)lpString1[0]);
        return v27;
      }
      if ( !v35[0] )
        break;
      v29 = (const WCHAR *)lpString1;
      if ( v41 >= 8 )
        v29 = lpString1[0];
      if ( CompareStringOrdinal(v29, -1, L"ZZ", -1, 1) == 2 )
        break;
      v30 = (const WCHAR *)lpString1;
      if ( v41 >= 8 )
        v30 = lpString1[0];
      if ( CompareStringOrdinal(v30, -1, L"ZZZ", -1, 1) == 2 )
        break;
      v8 = wcstok_s(0, L";", &Context);
      v31 = v36;
      if ( v36 )
      {
        v36 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
      }
      if ( v41 >= 8 )
        operator delete((void *)lpString1[0]);
    }
    v32 = lpString1;
    if ( v41 >= 8 )
      v32 = (LPCWCH *)lpString1[0];
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x596,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
      (const char *)0xC1570115LL,
      (int)"Invalid region: %ws",
      (const char *)v32);
    v33 = v36;
    if ( v36 )
    {
      v36 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    }
    if ( v41 >= 8 )
      operator delete((void *)lpString1[0]);
    return 3243704597LL;
  }
  return result;
}

```

## disassembly

```asm
0x18003dd38  push    rbx
0x18003dd3a  push    rsi
0x18003dd3b  push    rdi
0x18003dd3c  push    r12
0x18003dd3e  push    r14
0x18003dd40  push    r15
0x18003dd42  sub     rsp, 0A8h
0x18003dd49  mov     rax, cs:__security_cookie
0x18003dd50  xor     rax, rsp
0x18003dd53  mov     [rsp+0D8h+var_48], rax
0x18003dd5b  mov     rbx, rcx
0x18003dd5e  xor     r15d, r15d
0x18003dd61  test    rcx, rcx
0x18003dd64  jnz     short loc_18003DD70
0x18003dd66  mov     eax, 80004003h
0x18003dd6b  jmp     loc_18003E199
0x18003dd70  mov     [rsp+0D8h+bIgnoreCase], 1; int
0x18003dd78  or      r12, 0FFFFFFFFFFFFFFFFh
0x18003dd7c  mov     r9d, r12d; cchCount2
0x18003dd7f  lea     r8, aAll; "all"
0x18003dd86  mov     edx, r12d; cchCount1
0x18003dd89  call    cs:__imp_CompareStringOrdinal
0x18003dd90  nop     dword ptr [rax+rax+00h]
0x18003dd95  add     eax, 0FFFFFFFEh
0x18003dd98  jz      loc_18003E199
0x18003dd9e  mov     rcx, rbx; pbstr
0x18003dda1  call    cs:__imp_SysStringLen
0x18003dda8  nop     dword ptr [rax+rax+00h]
0x18003ddad  lea     edi, [rax+1]
0x18003ddb0  mov     eax, 2
0x18003ddb5  mul     rdi
0x18003ddb8  cmovb   rax, r12
0x18003ddbc  mov     rcx, rax; unsigned __int64
0x18003ddbf  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003ddc4  mov     rsi, rax
0x18003ddc7  mov     eax, 2
0x18003ddcc  mul     rdi
0x18003ddcf  cmovb   rax, r12
0x18003ddd3  mov     rcx, rax; unsigned __int64
0x18003ddd6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003dddb  mov     r14, rax
0x18003ddde  mov     r8, rbx; Source
0x18003dde1  mov     edx, edi; SizeInWords
0x18003dde3  mov     rcx, rsi; Destination
0x18003dde6  call    cs:__imp_wcscpy_s
0x18003dded  nop     dword ptr [rax+rax+00h]
0x18003ddf2  mov     r8, rbx; Source
0x18003ddf5  mov     edx, edi; SizeInWords
0x18003ddf7  mov     rcx, r14; Destination
0x18003ddfa  call    cs:__imp_wcscpy_s
0x18003de01  nop     dword ptr [rax+rax+00h]
0x18003de06  mov     [rsp+0D8h+Context], r15
0x18003de0b  lea     r8, [rsp+0D8h+Context]; Context
0x18003de10  lea     rdx, Delimiter; ";"
0x18003de17  mov     rcx, rsi; String
0x18003de1a  call    cs:__imp_wcstok_s
0x18003de21  nop     dword ptr [rax+rax+00h]
0x18003de26  mov     rbx, rax
0x18003de29  mov     r14d, 8
0x18003de2f  test    rbx, rbx
0x18003de32  jz      loc_18003E191
0x18003de38  mov     [rsp+0D8h+var_70], 7
0x18003de41  mov     [rsp+0D8h+var_78], r15
0x18003de46  mov     word ptr [rsp+0D8h+lpString1], r15w
0x18003de4c  cmp     [rbx], r15w
0x18003de50  jnz     short loc_18003DE57
0x18003de52  mov     r8, r15
0x18003de55  jmp     short loc_18003DE64
0x18003de57  mov     r8, r12
0x18003de5a  inc     r8
0x18003de5d  cmp     [rbx+r8*2], r15w
0x18003de62  jnz     short loc_18003DE5A
0x18003de64  mov     rdx, rbx; Src
0x18003de67  lea     rcx, [rsp+0D8h+lpString1]; void *
0x18003de6c  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18003de71  lea     rbx, [rsp+0D8h+lpString1]
0x18003de76  mov     r8, [rsp+0D8h+lpString1]
0x18003de7b  cmp     [rsp+0D8h+var_70], r14
0x18003de80  cmovnb  rbx, r8
0x18003de84  lea     rcx, [rsp+0D8h+lpString1]
0x18003de89  cmovnb  rcx, r8
0x18003de8d  mov     rax, [rsp+0D8h+var_78]
0x18003de92  lea     rsi, [rcx+rax*2]
0x18003de96  lea     rdi, [rsp+0D8h+lpString1]
0x18003de9b  cmovnb  rdi, r8
0x18003de9f  cmp     rdi, rsi
0x18003dea2  jz      short loc_18003DEC5
0x18003dea4  cmp     rdi, rsi
0x18003dea7  jz      short loc_18003DEC5
0x18003dea9  movzx   ecx, word ptr [rdi]
0x18003deac  mov     rax, cs:__imp_towupper
0x18003deb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003deb8  mov     [rbx], ax
0x18003debb  add     rdi, 2
0x18003debf  add     rbx, 2
0x18003dec3  jmp     short loc_18003DEA4
0x18003dec5  mov     [rsp+0D8h+var_A0], r15
0x18003deca  mov     [rsp+0D8h+string], r15
0x18003ded2  lea     r9, [rsp+0D8h+string]; string
0x18003deda  lea     r8, [rsp+0D8h+hstringHeader]; hstringHeader
0x18003dedf  mov     edx, 26h ; '&'; length
0x18003dee4  lea     rcx, ?RuntimeClass_Windows_Globalization_GeographicRegion@@3QBGB; "Windows.Globalization.GeographicRegion"
0x18003deeb  call    cs:__imp_WindowsCreateStringReference
0x18003def2  nop     dword ptr [rax+rax+00h]
0x18003def7  test    eax, eax
0x18003def9  js      loc_18003E1BB
0x18003deff  mov     rbx, [rsp+0D8h+string]
0x18003df07  mov     rcx, [rsp+0D8h+var_A0]
0x18003df0c  test    rcx, rcx
0x18003df0f  jz      short loc_18003DF23
0x18003df11  mov     [rsp+0D8h+var_A0], r15
0x18003df16  mov     rax, [rcx]
0x18003df19  mov     rax, [rax+10h]
0x18003df1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003df22  nop
0x18003df23  lea     r8, [rsp+0D8h+var_A0]
0x18003df28  lea     rdx, _GUID_29e28974_7ad9_4ef4_8799_b3b44fadec08
0x18003df2f  mov     rcx, rbx
0x18003df32  call    cs:__imp_RoGetActivationFactory
0x18003df39  nop     dword ptr [rax+rax+00h]
0x18003df3e  mov     ebx, eax
0x18003df40  test    eax, eax
0x18003df42  jns     short loc_18003DF9C
0x18003df44  mov     rcx, [rsp+0D8h]; this
0x18003df4c  mov     r9d, eax; char *
0x18003df4f  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003df56  mov     edx, 58Eh; void *
0x18003df5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003df60  nop
0x18003df61  mov     rcx, [rsp+0D8h+var_A0]
0x18003df66  test    rcx, rcx
0x18003df69  jz      short loc_18003DF7D
0x18003df6b  mov     [rsp+0D8h+var_A0], r15
0x18003df70  mov     rax, [rcx]
0x18003df73  mov     rax, [rax+10h]
0x18003df77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003df7c  nop
0x18003df7d  cmp     [rsp+0D8h+var_70], r14
0x18003df82  jb      short loc_18003DF95
0x18003df84  mov     rcx, [rsp+0D8h+lpString1]
0x18003df89  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003df90  nop     dword ptr [rax+rax+00h]
0x18003df95  mov     eax, ebx
0x18003df97  jmp     loc_18003E199
0x18003df9c  mov     [rsp+0D8h+var_A8], r15b
0x18003dfa1  mov     rdi, [rsp+0D8h+var_A0]
0x18003dfa6  mov     rax, [rdi]
0x18003dfa9  mov     rbx, [rax+30h]
0x18003dfad  lea     rdx, [rsp+0D8h+lpString1]
0x18003dfb2  cmp     [rsp+0D8h+var_70], r14
0x18003dfb7  cmovnb  rdx, [rsp+0D8h+lpString1]
0x18003dfbd  mov     [rsp+0D8h+var_90], rdx
0x18003dfc2  lea     rdx, [rsp+0D8h+var_90]
0x18003dfc7  lea     rcx, [rsp+0D8h+hstringHeader]
0x18003dfcc  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18003dfd1  nop
0x18003dfd2  lea     r8, [rsp+0D8h+var_A8]
0x18003dfd7  mov     rdx, [rax+18h]
0x18003dfdb  mov     rcx, rdi
0x18003dfde  mov     rax, rbx
0x18003dfe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dfe6  mov     ebx, eax
0x18003dfe8  test    eax, eax
0x18003dfea  jns     short loc_18003E044
0x18003dfec  mov     rcx, [rsp+0D8h]; this
0x18003dff4  mov     r9d, eax; char *
0x18003dff7  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003dffe  mov     edx, 591h; void *
0x18003e003  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e008  nop
0x18003e009  mov     rcx, [rsp+0D8h+var_A0]
0x18003e00e  test    rcx, rcx
0x18003e011  jz      short loc_18003E025
0x18003e013  mov     [rsp+0D8h+var_A0], r15
0x18003e018  mov     rax, [rcx]
0x18003e01b  mov     rax, [rax+10h]
0x18003e01f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e024  nop
0x18003e025  cmp     [rsp+0D8h+var_70], r14
0x18003e02a  jb      short loc_18003E03D
0x18003e02c  mov     rcx, [rsp+0D8h+lpString1]
0x18003e031  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003e038  nop     dword ptr [rax+rax+00h]
0x18003e03d  mov     eax, ebx
0x18003e03f  jmp     loc_18003E199
0x18003e044  cmp     [rsp+0D8h+var_A8], r15b
0x18003e049  jz      loc_18003E116
0x18003e04f  lea     rcx, [rsp+0D8h+lpString1]
0x18003e054  cmp     [rsp+0D8h+var_70], r14
0x18003e059  cmovnb  rcx, [rsp+0D8h+lpString1]; lpString1
0x18003e05f  mov     ebx, 1
0x18003e064  mov     [rsp+0D8h+bIgnoreCase], ebx; bIgnoreCase
0x18003e068  mov     r9d, r12d; cchCount2
0x18003e06b  lea     r8, aZz; "ZZ"
0x18003e072  mov     edx, r12d; cchCount1
0x18003e075  call    cs:__imp_CompareStringOrdinal
0x18003e07c  nop     dword ptr [rax+rax+00h]
0x18003e081  add     eax, 0FFFFFFFEh
0x18003e084  jz      loc_18003E116
0x18003e08a  lea     rcx, [rsp+0D8h+lpString1]
0x18003e08f  cmp     [rsp+0D8h+var_70], r14
0x18003e094  cmovnb  rcx, [rsp+0D8h+lpString1]; lpString1
0x18003e09a  mov     [rsp+0D8h+bIgnoreCase], ebx; bIgnoreCase
0x18003e09e  mov     r9d, r12d; cchCount2
0x18003e0a1  lea     r8, aZzz; "ZZZ"
0x18003e0a8  mov     edx, r12d; cchCount1
0x18003e0ab  call    cs:__imp_CompareStringOrdinal
0x18003e0b2  nop     dword ptr [rax+rax+00h]
0x18003e0b7  add     eax, 0FFFFFFFEh
0x18003e0ba  jz      short loc_18003E116
0x18003e0bc  lea     r8, [rsp+0D8h+Context]; Context
0x18003e0c1  lea     rdx, Delimiter; ";"
0x18003e0c8  xor     ecx, ecx; String
0x18003e0ca  call    cs:__imp_wcstok_s
0x18003e0d1  nop     dword ptr [rax+rax+00h]
0x18003e0d6  mov     rbx, rax
0x18003e0d9  mov     rcx, [rsp+0D8h+var_A0]
0x18003e0de  test    rcx, rcx
0x18003e0e1  jz      short loc_18003E0F5
0x18003e0e3  mov     [rsp+0D8h+var_A0], r15
0x18003e0e8  mov     rax, [rcx]
0x18003e0eb  mov     rax, [rax+10h]
0x18003e0ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e0f4  nop
0x18003e0f5  cmp     [rsp+0D8h+var_70], r14
0x18003e0fa  jb      loc_18003DE2F
0x18003e100  mov     rcx, [rsp+0D8h+lpString1]
0x18003e105  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003e10c  nop     dword ptr [rax+rax+00h]
0x18003e111  jmp     loc_18003DE2F
0x18003e116  lea     rax, [rsp+0D8h+lpString1]
0x18003e11b  cmp     [rsp+0D8h+var_70], r14
0x18003e120  cmovnb  rax, [rsp+0D8h+lpString1]
0x18003e126  mov     rcx, [rsp+0D8h]; this
0x18003e12e  mov     [rsp+0D8h+var_B0], rax; char *
0x18003e133  lea     rax, aInvalidRegionW; "Invalid region: %ws"
0x18003e13a  mov     qword ptr [rsp+0D8h+bIgnoreCase], rax; int
0x18003e13f  mov     ebx, 0C1570115h
0x18003e144  mov     r9d, ebx; char *
0x18003e147  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003e14e  mov     edx, 596h; void *
0x18003e153  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003e158  nop
0x18003e159  mov     rcx, [rsp+0D8h+var_A0]
0x18003e15e  test    rcx, rcx
0x18003e161  jz      short loc_18003E175
0x18003e163  mov     [rsp+0D8h+var_A0], r15
0x18003e168  mov     rax, [rcx]
0x18003e16b  mov     rax, [rax+10h]
0x18003e16f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e174  nop
0x18003e175  cmp     [rsp+0D8h+var_70], r14
0x18003e17a  jb      short loc_18003E18D
0x18003e17c  mov     rcx, [rsp+0D8h+lpString1]
0x18003e181  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003e188  nop     dword ptr [rax+rax+00h]
0x18003e18d  mov     eax, ebx
0x18003e18f  jmp     short loc_18003E199
0x18003e191  xor     eax, eax
0x18003e193  jmp     short loc_18003E199
0x18003e195  mov     eax, dword ptr [rsp+0D8h+var_A0]
0x18003e199  mov     rcx, [rsp+0D8h+var_48]
0x18003e1a1  xor     rcx, rsp; StackCookie
0x18003e1a4  call    __security_check_cookie
0x18003e1a9  add     rsp, 0A8h
0x18003e1b0  pop     r15
0x18003e1b2  pop     r14
0x18003e1b4  pop     r12
0x18003e1b6  pop     rdi
0x18003e1b7  pop     rsi
0x18003e1b8  pop     rbx
0x18003e1b9  retn
0x18003e1bb  mov     ecx, eax; this
0x18003e1bd  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
