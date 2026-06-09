# MsixPackage::Provisioning::Library::MsixProvisioningManager::ValidateRegion(ushort *)

- ea: `0x18003a678`
- end: `0x18003aafe`
- name: `?ValidateRegion@MsixProvisioningManager@Library@Provisioning@MsixPackage@@SAJPEAG@Z`
- size: `1158`
- prototype: `__int64 __fastcall(wchar_t *Source)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800335d8`
- `0x180035260`

## callees

- `0x180002f64`
- `0x18000cfe8`
- `0x18001bf0c`
- `0x18002535c`
- `0x180039e9c`
- `0x18003a678`
- `0x180066df0`
- `0x18006a010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18003a71a`
- `msvcrt!wcscpy_s` at `0x18003a728`
- `msvcrt!wcscpy_s` at `0x18003a71a`
- `msvcrt!wcscpy_s` at `0x18003a728`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a89f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a976`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003aa2e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003aaa4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a89f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a976`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003aa2e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003aaa4`
- `msvcrt!towupper` at `0x18003a7ce`
- `msvcrt!wcstok_s` at `0x18003a742`
- `msvcrt!wcstok_s` at `0x18003a9f9`
- `msvcrt!wcstok_s` at `0x18003a742`
- `msvcrt!wcstok_s` at `0x18003a9f9`
- `OLEAUT32!__imp_SysStringLen` at `0x18003a6db`
- `OLEAUT32!__imp_SysStringLen` at `0x18003a6db`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003a6c9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003a9b4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003a9e0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003a6c9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003a9b4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003a9e0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003a84e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003a84e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003a80d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003a904`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003a80d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003a904`

## string_xrefs

- `0x18003a865`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003a93c`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003aa6a`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall MsixPackage::Provisioning::Library::MsixProvisioningManager::ValidateRegion(wchar_t *Source)
{
  __int64 result; // rax
  int v3; // eax
  bool v4; // zf
  unsigned __int64 v5; // rdi
  wchar_t *v6; // r14
  wchar_t *v7; // rsi
  char *v8; // rbx
  unsigned __int64 v9; // r8
  PCWSTR *v10; // rbx
  PCWSTR *v11; // rcx
  PCWSTR *v12; // rsi
  PCWSTR *v13; // rdi
  HRESULT v14; // eax
  int v15; // edx
  unsigned int v16; // r8d
  HSTRING v17; // rbx
  _QWORD *v18; // rcx
  int ActivationFactory; // eax
  unsigned int v20; // r8d
  unsigned int v21; // ebx
  _QWORD *v22; // rcx
  _QWORD *v23; // rbx
  __int64 v24; // rdi
  const WCHAR *v25; // rcx
  unsigned __int64 v26; // rdx
  HRESULT v27; // eax
  int v28; // edx
  unsigned int v29; // r8d
  int v30; // eax
  unsigned int v31; // ebx
  _QWORD *v32; // rcx
  const WCHAR *v33; // rcx
  const WCHAR *v34; // rcx
  _QWORD *v35; // rcx
  PCWSTR *v36; // rax
  _QWORD *v37; // rcx
  int bIgnoreCase; // [rsp+20h] [rbp-A8h]
  _BYTE v39[8]; // [rsp+30h] [rbp-98h] BYREF
  _QWORD *v40; // [rsp+38h] [rbp-90h] BYREF
  wchar_t *Context; // [rsp+40h] [rbp-88h] BYREF
  PCWSTR sourceString[2]; // [rsp+48h] [rbp-80h] BYREF
  __int64 v43; // [rsp+58h] [rbp-70h]
  unsigned __int64 v44; // [rsp+60h] [rbp-68h]
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-60h] BYREF
  HSTRING string; // [rsp+80h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

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
    v8 = (char *)wcstok_s(v6, L";", &Context);
    while ( 1 )
    {
      if ( !v8 )
        return 0;
      v44 = 7;
      v43 = 0;
      LOWORD(sourceString[0]) = 0;
      if ( *(_WORD *)v8 )
      {
        v9 = -1;
        do
          ++v9;
        while ( *(_WORD *)&v8[2 * v9] );
      }
      else
      {
        v9 = 0;
      }
      std::wstring::assign(sourceString, v8, v9);
      v10 = sourceString;
      if ( v44 >= 8 )
        v10 = (PCWSTR *)sourceString[0];
      v11 = sourceString;
      if ( v44 >= 8 )
        v11 = (PCWSTR *)sourceString[0];
      v12 = (PCWSTR *)((char *)v11 + 2 * v43);
      v13 = sourceString;
      if ( v44 >= 8 )
        v13 = (PCWSTR *)sourceString[0];
      if ( v13 != v12 )
      {
        while ( v13 != v12 )
        {
          *(_WORD *)v10 = ((__int64 (__fastcall *)(_QWORD))towupper)(*(unsigned __int16 *)v13);
          v13 = (PCWSTR *)((char *)v13 + 2);
          v10 = (PCWSTR *)((char *)v10 + 2);
        }
      }
      v40 = 0;
      string = 0;
      v14 = WindowsCreateStringReference(L"Windows.Globalization.GeographicRegion", 0x26u, &hstringHeader, &string);
      if ( v14 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v14, v15, v16);
        __debugbreak();
      }
      v17 = string;
      v18 = v40;
      if ( v40 )
      {
        v40 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v18 + 16LL))(v18);
      }
      ActivationFactory = RoGetActivationFactory(v17, &GUID_29e28974_7ad9_4ef4_8799_b3b44fadec08, &v40);
      v21 = ActivationFactory;
      if ( ActivationFactory < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x58E,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
          (const char *)(unsigned int)ActivationFactory,
          bIgnoreCase);
        v22 = v40;
        if ( v40 )
        {
          v40 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v22 + 16LL))(v22);
        }
        if ( v44 >= 8 )
          operator delete((void *)sourceString[0]);
        return v21;
      }
      v39[0] = 0;
      v23 = v40;
      v24 = *v40;
      v25 = (const WCHAR *)sourceString;
      if ( v44 >= 8 )
        v25 = sourceString[0];
      string = 0;
      v26 = -1;
      do
        ++v26;
      while ( v25[v26] );
      if ( v26 > 0xFFFFFFFF )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v26, v20);
        JUMPOUT(0x18003AAFCLL);
      }
      if ( (int)v26 + 1 < (unsigned int)v26 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v26, v20);
        __debugbreak();
      }
      v27 = WindowsCreateStringReference(v25, v26, &hstringHeader, &string);
      if ( v27 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v27, v28, v29);
        __debugbreak();
      }
      v30 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, _BYTE *))(v24 + 48))(v23, string, v39);
      v31 = v30;
      if ( v30 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x591,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
          (const char *)(unsigned int)v30,
          bIgnoreCase);
        v32 = v40;
        if ( v40 )
        {
          v40 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v32 + 16LL))(v32);
        }
        if ( v44 >= 8 )
          operator delete((void *)sourceString[0]);
        return v31;
      }
      if ( !v39[0] )
        break;
      v33 = (const WCHAR *)sourceString;
      if ( v44 >= 8 )
        v33 = sourceString[0];
      if ( CompareStringOrdinal(v33, -1, L"ZZ", -1, 1) == 2 )
        break;
      v34 = (const WCHAR *)sourceString;
      if ( v44 >= 8 )
        v34 = sourceString[0];
      if ( CompareStringOrdinal(v34, -1, L"ZZZ", -1, 1) == 2 )
        break;
      v8 = (char *)wcstok_s(0, L";", &Context);
      v35 = v40;
      if ( v40 )
      {
        v40 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v35 + 16LL))(v35);
      }
      if ( v44 >= 8 )
        operator delete((void *)sourceString[0]);
    }
    v36 = sourceString;
    if ( v44 >= 8 )
      v36 = (PCWSTR *)sourceString[0];
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x596,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
      (const char *)0xC1570115LL,
      (int)"Invalid region: %ws",
      (const char *)v36);
    v37 = v40;
    if ( v40 )
    {
      v40 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v37 + 16LL))(v37);
    }
    if ( v44 >= 8 )
      operator delete((void *)sourceString[0]);
    return 3243704597LL;
  }
  return result;
}

```

## disassembly

```asm
0x18003a678  push    rbx
0x18003a67a  push    rsi
0x18003a67b  push    rdi
0x18003a67c  push    r12
0x18003a67e  push    r14
0x18003a680  push    r15
0x18003a682  sub     rsp, 98h
0x18003a689  mov     rax, cs:__security_cookie
0x18003a690  xor     rax, rsp
0x18003a693  mov     [rsp+0C8h+var_40], rax
0x18003a69b  mov     rbx, rcx
0x18003a69e  xor     r15d, r15d
0x18003a6a1  test    rcx, rcx
0x18003a6a4  jnz     short loc_18003A6B0
0x18003a6a6  mov     eax, 80004003h
0x18003a6ab  jmp     loc_18003AAB6
0x18003a6b0  mov     [rsp+0C8h+bIgnoreCase], 1; int
0x18003a6b8  or      r12, 0FFFFFFFFFFFFFFFFh
0x18003a6bc  mov     r9d, r12d; cchCount2
0x18003a6bf  lea     r8, aAll; "all"
0x18003a6c6  mov     edx, r12d; cchCount1
0x18003a6c9  call    cs:__imp_CompareStringOrdinal
0x18003a6cf  add     eax, 0FFFFFFFEh
0x18003a6d2  jz      loc_18003AAB6
0x18003a6d8  mov     rcx, rbx; pbstr
0x18003a6db  call    cs:__imp_SysStringLen
0x18003a6e1  lea     edi, [rax+1]
0x18003a6e4  mov     eax, 2
0x18003a6e9  mul     rdi
0x18003a6ec  cmovb   rax, r12
0x18003a6f0  mov     rcx, rax; unsigned __int64
0x18003a6f3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003a6f8  mov     r14, rax
0x18003a6fb  mov     eax, 2
0x18003a700  mul     rdi
0x18003a703  cmovb   rax, r12
0x18003a707  mov     rcx, rax; unsigned __int64
0x18003a70a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003a70f  mov     rsi, rax
0x18003a712  mov     r8, rbx; Source
0x18003a715  mov     edx, edi; SizeInWords
0x18003a717  mov     rcx, r14; Destination
0x18003a71a  call    cs:__imp_wcscpy_s
0x18003a720  mov     r8, rbx; Source
0x18003a723  mov     edx, edi; SizeInWords
0x18003a725  mov     rcx, rsi; Destination
0x18003a728  call    cs:__imp_wcscpy_s
0x18003a72e  mov     [rsp+0C8h+Context], r15
0x18003a733  lea     r8, [rsp+0C8h+Context]; Context
0x18003a738  lea     rdx, Delimiter; ";"
0x18003a73f  mov     rcx, r14; String
0x18003a742  call    cs:__imp_wcstok_s
0x18003a748  mov     rbx, rax
0x18003a74b  mov     r14d, 8
0x18003a751  test    rbx, rbx
0x18003a754  jz      loc_18003AAAE
0x18003a75a  mov     [rsp+0C8h+var_68], 7
0x18003a763  mov     [rsp+0C8h+var_70], r15
0x18003a768  mov     word ptr [rsp+0C8h+sourceString], r15w
0x18003a76e  cmp     [rbx], r15w
0x18003a772  jnz     short loc_18003A779
0x18003a774  mov     r8, r15
0x18003a777  jmp     short loc_18003A786
0x18003a779  mov     r8, r12
0x18003a77c  inc     r8
0x18003a77f  cmp     [rbx+r8*2], r15w
0x18003a784  jnz     short loc_18003A77C
0x18003a786  mov     rdx, rbx; Src
0x18003a789  lea     rcx, [rsp+0C8h+sourceString]; void *
0x18003a78e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18003a793  lea     rbx, [rsp+0C8h+sourceString]
0x18003a798  mov     r8, [rsp+0C8h+sourceString]
0x18003a79d  cmp     [rsp+0C8h+var_68], r14
0x18003a7a2  cmovnb  rbx, r8
0x18003a7a6  lea     rcx, [rsp+0C8h+sourceString]
0x18003a7ab  cmovnb  rcx, r8
0x18003a7af  mov     rax, [rsp+0C8h+var_70]
0x18003a7b4  lea     rsi, [rcx+rax*2]
0x18003a7b8  lea     rdi, [rsp+0C8h+sourceString]
0x18003a7bd  cmovnb  rdi, r8
0x18003a7c1  cmp     rdi, rsi
0x18003a7c4  jz      short loc_18003A7E7
0x18003a7c6  cmp     rdi, rsi
0x18003a7c9  jz      short loc_18003A7E7
0x18003a7cb  movzx   ecx, word ptr [rdi]
0x18003a7ce  mov     rax, cs:__imp_towupper
0x18003a7d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a7da  mov     [rbx], ax
0x18003a7dd  add     rdi, 2
0x18003a7e1  add     rbx, 2
0x18003a7e5  jmp     short loc_18003A7C6
0x18003a7e7  mov     [rsp+0C8h+var_90], r15
0x18003a7ec  mov     [rsp+0C8h+string], r15
0x18003a7f4  lea     r9, [rsp+0C8h+string]; string
0x18003a7fc  lea     r8, [rsp+0C8h+hstringHeader]; hstringHeader
0x18003a801  mov     edx, 26h ; '&'; length
0x18003a806  lea     rcx, ?RuntimeClass_Windows_Globalization_GeographicRegion@@3QBGB; "Windows.Globalization.GeographicRegion"
0x18003a80d  call    cs:__imp_WindowsCreateStringReference
0x18003a813  test    eax, eax
0x18003a815  js      loc_18003AAD7
0x18003a81b  mov     rbx, [rsp+0C8h+string]
0x18003a823  mov     rcx, [rsp+0C8h+var_90]
0x18003a828  test    rcx, rcx
0x18003a82b  jz      short loc_18003A83F
0x18003a82d  mov     [rsp+0C8h+var_90], r15
0x18003a832  mov     rax, [rcx]
0x18003a835  mov     rax, [rax+10h]
0x18003a839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a83e  nop
0x18003a83f  lea     r8, [rsp+0C8h+var_90]
0x18003a844  lea     rdx, _GUID_29e28974_7ad9_4ef4_8799_b3b44fadec08
0x18003a84b  mov     rcx, rbx
0x18003a84e  call    cs:__imp_RoGetActivationFactory
0x18003a854  mov     ebx, eax
0x18003a856  test    eax, eax
0x18003a858  jns     short loc_18003A8AC
0x18003a85a  mov     rcx, [rsp+0C8h]; this
0x18003a862  mov     r9d, eax; char *
0x18003a865  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003a86c  mov     edx, 58Eh; void *
0x18003a871  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a876  nop
0x18003a877  mov     rcx, [rsp+0C8h+var_90]
0x18003a87c  test    rcx, rcx
0x18003a87f  jz      short loc_18003A893
0x18003a881  mov     [rsp+0C8h+var_90], r15
0x18003a886  mov     rax, [rcx]
0x18003a889  mov     rax, [rax+10h]
0x18003a88d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a892  nop
0x18003a893  cmp     [rsp+0C8h+var_68], r14
0x18003a898  jb      short loc_18003A8A5
0x18003a89a  mov     rcx, [rsp+0C8h+sourceString]
0x18003a89f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003a8a5  mov     eax, ebx
0x18003a8a7  jmp     loc_18003AAB6
0x18003a8ac  mov     [rsp+0C8h+var_98], r15b
0x18003a8b1  mov     rbx, [rsp+0C8h+var_90]
0x18003a8b6  mov     rdi, [rbx]
0x18003a8b9  lea     rcx, [rsp+0C8h+sourceString]
0x18003a8be  cmp     [rsp+0C8h+var_68], r14
0x18003a8c3  cmovnb  rcx, [rsp+0C8h+sourceString]; sourceString
0x18003a8c9  mov     [rsp+0C8h+string], r15
0x18003a8d1  mov     rdx, r12
0x18003a8d4  inc     rdx; int
0x18003a8d7  cmp     [rcx+rdx*2], r15w
0x18003a8dc  jnz     short loc_18003A8D4
0x18003a8de  mov     eax, 0FFFFFFFFh
0x18003a8e3  cmp     rdx, rax
0x18003a8e6  ja      loc_18003AAF2
0x18003a8ec  lea     eax, [rdx+1]
0x18003a8ef  cmp     eax, edx
0x18003a8f1  jb      loc_18003AAE7
0x18003a8f7  lea     r9, [rsp+0C8h+string]; string
0x18003a8ff  lea     r8, [rsp+0C8h+hstringHeader]; hstringHeader
0x18003a904  call    cs:__imp_WindowsCreateStringReference
0x18003a90a  test    eax, eax
0x18003a90c  js      loc_18003AADF
0x18003a912  lea     r8, [rsp+0C8h+var_98]
0x18003a917  mov     rdx, [rsp+0C8h+string]
0x18003a91f  mov     rcx, rbx
0x18003a922  mov     rax, [rdi+30h]
0x18003a926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a92b  mov     ebx, eax
0x18003a92d  test    eax, eax
0x18003a92f  jns     short loc_18003A983
0x18003a931  mov     rcx, [rsp+0C8h]; this
0x18003a939  mov     r9d, eax; char *
0x18003a93c  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003a943  mov     edx, 591h; void *
0x18003a948  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a94d  nop
0x18003a94e  mov     rcx, [rsp+0C8h+var_90]
0x18003a953  test    rcx, rcx
0x18003a956  jz      short loc_18003A96A
0x18003a958  mov     [rsp+0C8h+var_90], r15
0x18003a95d  mov     rax, [rcx]
0x18003a960  mov     rax, [rax+10h]
0x18003a964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a969  nop
0x18003a96a  cmp     [rsp+0C8h+var_68], r14
0x18003a96f  jb      short loc_18003A97C
0x18003a971  mov     rcx, [rsp+0C8h+sourceString]
0x18003a976  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003a97c  mov     eax, ebx
0x18003a97e  jmp     loc_18003AAB6
0x18003a983  cmp     [rsp+0C8h+var_98], r15b
0x18003a988  jz      loc_18003AA39
0x18003a98e  lea     rcx, [rsp+0C8h+sourceString]
0x18003a993  cmp     [rsp+0C8h+var_68], r14
0x18003a998  cmovnb  rcx, [rsp+0C8h+sourceString]; lpString1
0x18003a99e  mov     ebx, 1
0x18003a9a3  mov     [rsp+0C8h+bIgnoreCase], ebx; bIgnoreCase
0x18003a9a7  mov     r9d, r12d; cchCount2
0x18003a9aa  lea     r8, aZz; "ZZ"
0x18003a9b1  mov     edx, r12d; cchCount1
0x18003a9b4  call    cs:__imp_CompareStringOrdinal
0x18003a9ba  add     eax, 0FFFFFFFEh
0x18003a9bd  jz      short loc_18003AA39
0x18003a9bf  lea     rcx, [rsp+0C8h+sourceString]
0x18003a9c4  cmp     [rsp+0C8h+var_68], r14
0x18003a9c9  cmovnb  rcx, [rsp+0C8h+sourceString]; lpString1
0x18003a9cf  mov     [rsp+0C8h+bIgnoreCase], ebx; bIgnoreCase
0x18003a9d3  mov     r9d, r12d; cchCount2
0x18003a9d6  lea     r8, aZzz; "ZZZ"
0x18003a9dd  mov     edx, r12d; cchCount1
0x18003a9e0  call    cs:__imp_CompareStringOrdinal
0x18003a9e6  add     eax, 0FFFFFFFEh
0x18003a9e9  jz      short loc_18003AA39
0x18003a9eb  lea     r8, [rsp+0C8h+Context]; Context
0x18003a9f0  lea     rdx, Delimiter; ";"
0x18003a9f7  xor     ecx, ecx; String
0x18003a9f9  call    cs:__imp_wcstok_s
0x18003a9ff  mov     rbx, rax
0x18003aa02  mov     rcx, [rsp+0C8h+var_90]
0x18003aa07  test    rcx, rcx
0x18003aa0a  jz      short loc_18003AA1E
0x18003aa0c  mov     [rsp+0C8h+var_90], r15
0x18003aa11  mov     rax, [rcx]
0x18003aa14  mov     rax, [rax+10h]
0x18003aa18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aa1d  nop
0x18003aa1e  cmp     [rsp+0C8h+var_68], r14
0x18003aa23  jb      loc_18003A751
0x18003aa29  mov     rcx, [rsp+0C8h+sourceString]
0x18003aa2e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003aa34  jmp     loc_18003A751
0x18003aa39  lea     rax, [rsp+0C8h+sourceString]
0x18003aa3e  cmp     [rsp+0C8h+var_68], r14
0x18003aa43  cmovnb  rax, [rsp+0C8h+sourceString]
0x18003aa49  mov     rcx, [rsp+0C8h]; this
0x18003aa51  mov     [rsp+0C8h+var_A0], rax; char *
0x18003aa56  lea     rax, aInvalidRegionW; "Invalid region: %ws"
0x18003aa5d  mov     qword ptr [rsp+0C8h+bIgnoreCase], rax; int
0x18003aa62  mov     ebx, 0C1570115h
0x18003aa67  mov     r9d, ebx; char *
0x18003aa6a  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003aa71  mov     edx, 596h; void *
0x18003aa76  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003aa7b  nop
0x18003aa7c  mov     rcx, [rsp+0C8h+var_90]
0x18003aa81  test    rcx, rcx
0x18003aa84  jz      short loc_18003AA98
0x18003aa86  mov     [rsp+0C8h+var_90], r15
0x18003aa8b  mov     rax, [rcx]
0x18003aa8e  mov     rax, [rax+10h]
0x18003aa92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aa97  nop
0x18003aa98  cmp     [rsp+0C8h+var_68], r14
0x18003aa9d  jb      short loc_18003AAAA
0x18003aa9f  mov     rcx, [rsp+0C8h+sourceString]
0x18003aaa4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003aaaa  mov     eax, ebx
0x18003aaac  jmp     short loc_18003AAB6
0x18003aaae  xor     eax, eax
0x18003aab0  jmp     short loc_18003AAB6
0x18003aab2  mov     eax, dword ptr [rsp+0C8h+var_90]
0x18003aab6  mov     rcx, [rsp+0C8h+var_40]
0x18003aabe  xor     rcx, rsp; StackCookie
0x18003aac1  call    __security_check_cookie
0x18003aac6  add     rsp, 98h
0x18003aacd  pop     r15
0x18003aacf  pop     r14
0x18003aad1  pop     r12
0x18003aad3  pop     rdi
0x18003aad4  pop     rsi
0x18003aad5  pop     rbx
0x18003aad6  retn
0x18003aad7  mov     ecx, eax; this
0x18003aad9  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18003aade  int     3; Trap to Debugger
0x18003aadf  mov     ecx, eax; this
0x18003aae1  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18003aae6  int     3; Trap to Debugger
0x18003aae7  mov     ecx, 80070216h; this
0x18003aaec  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18003aaf1  int     3; Trap to Debugger
0x18003aaf2  mov     ecx, 80070216h; this
0x18003aaf7  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
