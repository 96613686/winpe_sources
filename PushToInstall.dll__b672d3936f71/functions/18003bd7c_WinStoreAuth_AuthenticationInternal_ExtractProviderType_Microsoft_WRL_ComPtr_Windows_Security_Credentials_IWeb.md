# WinStoreAuth::AuthenticationInternal::ExtractProviderType(Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider> const &,WinStoreAuth::AccountProviderType &)

- ea: `0x18003bd7c`
- end: `0x18003c121`
- name: `?ExtractProviderType@AuthenticationInternal@WinStoreAuth@@YAJAEBV?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@AEAW4AccountProviderType@2@@Z`
- size: `933`
- prototype: `__int64 __fastcall(_QWORD *, _DWORD *)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18003b010`
- `0x18003c128`
- `0x18003e828`
- `0x180040ef8`

## callees

- `0x180010b84`
- `0x18002fbb4`
- `0x18003bd7c`
- `0x18004441c`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18003c03b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18003c062`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18003c089`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18003c0b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18003c03b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18003c062`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18003c089`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18003c0b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bdd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bfb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bff3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c01b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c0ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c0f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bdd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bfb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bff3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c01b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c0ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c0f6`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18003be9c`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18003bef8`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18003be9c`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18003bef8`

## pseudocode

```c
__int64 __fastcall WinStoreAuth::AuthenticationInternal::ExtractProviderType(_QWORD *a1, _DWORD *a2)
{
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, HSTRING *); // rbx
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // eax
  IUnknown *v10; // rcx
  IUnknown *v11; // rbx
  HRESULT v12; // edi
  HRESULT v13; // eax
  IUnknown *v14; // rcx
  IUnknown *v15; // rcx
  IUnknown *v16; // rcx
  IUnknown *v17; // rdi
  ULONG (__stdcall *AddRef)(IUnknown *); // rbx
  int v19; // eax
  IUnknown *v20; // rcx
  HRESULT v21; // eax
  int v22; // edx
  unsigned int v23; // r8d
  HRESULT v24; // eax
  int v25; // edx
  unsigned int v26; // r8d
  HRESULT v27; // eax
  int v28; // edx
  unsigned int v29; // r8d
  HRESULT v30; // eax
  int v31; // edx
  unsigned int v32; // r8d
  IUnknown *v33; // rcx
  DWORD dwAuthnLevel; // [rsp+20h] [rbp-30h]
  DWORD dwAuthnLevela; // [rsp+20h] [rbp-30h]
  DWORD dwAuthnLevelb; // [rsp+20h] [rbp-30h]
  HSTRING string1[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  IUnknown *result; // [rsp+88h] [rbp+38h] BYREF
  IUnknown *pProxy; // [rsp+90h] [rbp+40h] BYREF
  HSTRING string; // [rsp+98h] [rbp+48h] BYREF

  *a2 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExtractProviderTypeCrashFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ExtractProviderTypeCrashFix>::GetImpl'::`2'::impl)
    && !*a1 )
  {
    return 0;
  }
  string1[0] = 0;
  v5 = *a1;
  v6 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)*a1 + 48LL);
  WindowsDeleteString(0);
  string1[0] = 0;
  v7 = v6(v5, string1);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA4E,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v7,
      dwAuthnLevel);
    goto LABEL_26;
  }
  pProxy = 0;
  v9 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, IUnknown **))*a1)(
         *a1,
         &GUID_4a01eb05_4e42_41d4_b518_e008a5163614,
         &pProxy);
  v8 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA51,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v9,
      dwAuthnLevel);
    v10 = pProxy;
    if ( pProxy )
    {
      pProxy = 0;
      ((void (__fastcall *)(IUnknown *))v10->lpVtbl->Release)(v10);
    }
    goto LABEL_26;
  }
  v11 = pProxy;
  v12 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x40u);
  if ( v12 != -2147467262 )
  {
    result = 0;
    if ( ((__int64 (__fastcall *)(IUnknown *, GUID *, IUnknown **))v11->lpVtbl->QueryInterface)(
           v11,
           &GUID_00000000_0000_0000_c000_000000000046,
           &result) >= 0 )
    {
      v13 = CoSetProxyBlanket(result, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x40u);
      v8 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF0,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v13,
          dwAuthnLevela);
        v14 = result;
        if ( result )
        {
          result = 0;
          ((void (__fastcall *)(IUnknown *))v14->lpVtbl->Release)(v14);
        }
        goto LABEL_20;
      }
    }
    v15 = result;
    if ( result )
    {
      result = 0;
      ((void (__fastcall *)(IUnknown *))v15->lpVtbl->Release)(v15);
    }
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF3,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)v12,
        dwAuthnLevela);
      v8 = v12;
LABEL_20:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA52,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)v8,
        dwAuthnLevelb);
      v16 = pProxy;
      if ( pProxy )
      {
        pProxy = 0;
        ((void (__fastcall *)(IUnknown *))v16->lpVtbl->Release)(v16);
      }
      goto LABEL_26;
    }
  }
  string = 0;
  v17 = pProxy;
  AddRef = pProxy->lpVtbl[2].AddRef;
  WindowsDeleteString(0);
  string = 0;
  v19 = ((__int64 (__fastcall *)(IUnknown *, HSTRING *))AddRef)(v17, &string);
  v8 = v19;
  if ( v19 >= 0 )
  {
    LODWORD(result) = 0;
    v21 = WindowsCompareStringOrdinal(string1[0], string2, (INT32 *)&result);
    if ( v21 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v21, v22, v23);
      __debugbreak();
    }
    if ( !(_DWORD)result )
      goto LABEL_31;
    LODWORD(result) = 0;
    v24 = WindowsCompareStringOrdinal(string1[0], qword_180066588, (INT32 *)&result);
    if ( v24 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v24, v25, v26);
      __debugbreak();
    }
    if ( !(_DWORD)result )
    {
LABEL_31:
      LODWORD(result) = 0;
      v27 = WindowsCompareStringOrdinal(string, qword_1800665A8, (INT32 *)&result);
      if ( v27 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v27, v28, v29);
        __debugbreak();
      }
      if ( (_DWORD)result )
      {
        LODWORD(result) = 0;
        v30 = WindowsCompareStringOrdinal(string, ::string, (INT32 *)&result);
        if ( v30 < 0 )
        {
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v30, v31, v32);
          JUMPOUT(0x18003C120LL);
        }
        if ( !(_DWORD)result )
          *a2 = 2;
      }
      else
      {
        *a2 = 1;
      }
    }
    WindowsDeleteString(string);
    string = 0;
    v33 = pProxy;
    if ( pProxy )
    {
      pProxy = 0;
      ((void (__fastcall *)(IUnknown *))v33->lpVtbl->Release)(v33);
    }
    WindowsDeleteString(string1[0]);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xA55,
    (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
    (const char *)(unsigned int)v19,
    dwAuthnLevela);
  WindowsDeleteString(string);
  string = 0;
  v20 = pProxy;
  if ( pProxy )
  {
    pProxy = 0;
    ((void (__fastcall *)(IUnknown *))v20->lpVtbl->Release)(v20);
  }
LABEL_26:
  WindowsDeleteString(string1[0]);
  return v8;
}

```

## disassembly

```asm
0x18003bd7c  mov     [rsp-28h+arg_0], rbx
0x18003bd81  push    rbp
0x18003bd82  push    rsi
0x18003bd83  push    rdi
0x18003bd84  push    r14
0x18003bd86  push    r15
0x18003bd88  mov     rbp, rsp
0x18003bd8b  sub     rsp, 50h
0x18003bd8f  mov     rsi, rdx
0x18003bd92  mov     r14, rcx
0x18003bd95  xor     r15d, r15d
0x18003bd98  mov     [rdx], r15d
0x18003bd9b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ExtractProviderTypeCrashFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ExtractProviderTypeCrashFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExtractProviderTypeCrashFix> `wil::Feature<__WilFeatureTraits_Feature_ExtractProviderTypeCrashFix>::GetImpl(void)'::`2'::impl
0x18003bda2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ExtractProviderTypeCrashFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExtractProviderTypeCrashFix>::__private_IsEnabled(void)
0x18003bda7  test    al, al
0x18003bda9  jz      short loc_18003BDC6
0x18003bdab  cmp     [r14], r15
0x18003bdae  jnz     short loc_18003BDC6
0x18003bdb0  xor     eax, eax
0x18003bdb2  mov     rbx, [rsp+50h+arg_0]
0x18003bdba  add     rsp, 50h
0x18003bdbe  pop     r15
0x18003bdc0  pop     r14
0x18003bdc2  pop     rdi
0x18003bdc3  pop     rsi
0x18003bdc4  pop     rbp
0x18003bdc5  retn
0x18003bdc6  mov     [rbp+string1], r15
0x18003bdca  mov     rdi, [r14]
0x18003bdcd  mov     rax, [rdi]
0x18003bdd0  mov     rbx, [rax+30h]
0x18003bdd4  xor     ecx, ecx; string
0x18003bdd6  call    cs:__imp_WindowsDeleteString
0x18003bddc  mov     [rbp+string1], r15
0x18003bde0  lea     rdx, [rbp+string1]
0x18003bde4  mov     rcx, rdi
0x18003bde7  mov     rax, rbx
0x18003bdea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bdef  mov     ebx, eax
0x18003bdf1  test    eax, eax
0x18003bdf3  jns     short loc_18003BE12
0x18003bdf5  mov     rcx, [rbp+28h]; this
0x18003bdf9  mov     r9d, eax; char *
0x18003bdfc  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003be03  mov     edx, 0A4Eh; void *
0x18003be08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003be0d  jmp     loc_18003C017
0x18003be12  mov     [rbp+pProxy], r15
0x18003be16  mov     rcx, [r14]
0x18003be19  mov     rax, [rcx]
0x18003be1c  lea     r8, [rbp+pProxy]
0x18003be20  lea     rdx, _GUID_4a01eb05_4e42_41d4_b518_e008a5163614
0x18003be27  mov     rax, [rax]
0x18003be2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be2f  mov     ebx, eax
0x18003be31  test    eax, eax
0x18003be33  jns     short loc_18003BE6D
0x18003be35  mov     rcx, [rbp+28h]; this
0x18003be39  mov     r9d, eax; char *
0x18003be3c  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003be43  mov     edx, 0A51h; void *
0x18003be48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003be4d  nop
0x18003be4e  mov     rcx, [rbp+pProxy]
0x18003be52  test    rcx, rcx
0x18003be55  jz      short loc_18003BE68
0x18003be57  mov     [rbp+pProxy], r15
0x18003be5b  mov     rax, [rcx]
0x18003be5e  mov     rax, [rax+10h]
0x18003be62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be67  nop
0x18003be68  jmp     loc_18003C017
0x18003be6d  mov     rbx, [rbp+pProxy]
0x18003be71  mov     [rsp+50h+dwCapabilities], 40h ; '@'; dwCapabilities
0x18003be79  mov     [rsp+50h+pAuthInfo], r15; pAuthInfo
0x18003be7e  mov     [rsp+50h+dwImpLevel], 3; dwImpLevel
0x18003be86  mov     [rsp+50h+dwAuthnLevel], r15d; int
0x18003be8b  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18003be8f  or      r14d, 0FFFFFFFFh
0x18003be93  mov     r8d, r14d; dwAuthzSvc
0x18003be96  mov     edx, r14d; dwAuthnSvc
0x18003be99  mov     rcx, rbx; pProxy
0x18003be9c  call    cs:__imp_CoSetProxyBlanket
0x18003bea2  mov     edi, eax
0x18003bea4  cmp     eax, 80004002h
0x18003bea9  jz      loc_18003BFA6
0x18003beaf  mov     [rbp+result], r15
0x18003beb3  mov     rdx, [rbx]
0x18003beb6  mov     rax, [rdx]
0x18003beb9  lea     r8, [rbp+result]
0x18003bebd  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18003bec4  mov     rcx, rbx
0x18003bec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003becc  test    eax, eax
0x18003bece  js      short loc_18003BF39
0x18003bed0  mov     [rsp+50h+dwCapabilities], 40h ; '@'; dwCapabilities
0x18003bed8  mov     [rsp+50h+pAuthInfo], r15; pAuthInfo
0x18003bedd  mov     [rsp+50h+dwImpLevel], 3; dwImpLevel
0x18003bee5  mov     [rsp+50h+dwAuthnLevel], r15d; int
0x18003beea  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18003beee  mov     r8d, r14d; dwAuthzSvc
0x18003bef1  mov     edx, r14d; dwAuthnSvc
0x18003bef4  mov     rcx, [rbp+result]; pProxy
0x18003bef8  call    cs:__imp_CoSetProxyBlanket
0x18003befe  mov     ebx, eax
0x18003bf00  test    eax, eax
0x18003bf02  jns     short loc_18003BF39
0x18003bf04  mov     rcx, [rbp+28h]; this
0x18003bf08  mov     r9d, eax; char *
0x18003bf0b  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003bf12  mov     edx, 0F0h; void *
0x18003bf17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bf1c  nop
0x18003bf1d  mov     rcx, [rbp+result]
0x18003bf21  test    rcx, rcx
0x18003bf24  jz      short loc_18003BF37
0x18003bf26  mov     [rbp+result], r15
0x18003bf2a  mov     rax, [rcx]
0x18003bf2d  mov     rax, [rax+10h]
0x18003bf31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bf36  nop
0x18003bf37  jmp     short loc_18003BF71
0x18003bf39  mov     rcx, [rbp+result]
0x18003bf3d  test    rcx, rcx
0x18003bf40  jz      short loc_18003BF53
0x18003bf42  mov     [rbp+result], r15
0x18003bf46  mov     rax, [rcx]
0x18003bf49  mov     rax, [rax+10h]
0x18003bf4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bf52  nop
0x18003bf53  test    edi, edi
0x18003bf55  jns     short loc_18003BFA6
0x18003bf57  mov     rcx, [rbp+28h]; this
0x18003bf5b  mov     r9d, edi; char *
0x18003bf5e  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003bf65  mov     edx, 0F3h; void *
0x18003bf6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bf6f  mov     ebx, edi
0x18003bf71  mov     rcx, [rbp+28h]; this
0x18003bf75  mov     r9d, ebx; char *
0x18003bf78  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003bf7f  mov     edx, 0A52h; void *
0x18003bf84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bf89  nop
0x18003bf8a  mov     rcx, [rbp+pProxy]
0x18003bf8e  test    rcx, rcx
0x18003bf91  jz      short loc_18003BFA4
0x18003bf93  mov     [rbp+pProxy], r15
0x18003bf97  mov     rax, [rcx]
0x18003bf9a  mov     rax, [rax+10h]
0x18003bf9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bfa3  nop
0x18003bfa4  jmp     short loc_18003C017
0x18003bfa6  mov     [rbp+string], r15
0x18003bfaa  mov     rdi, [rbp+pProxy]
0x18003bfae  mov     rax, [rdi]
0x18003bfb1  mov     rbx, [rax+38h]
0x18003bfb5  xor     ecx, ecx; string
0x18003bfb7  call    cs:__imp_WindowsDeleteString
0x18003bfbd  mov     [rbp+string], r15
0x18003bfc1  lea     rdx, [rbp+string]
0x18003bfc5  mov     rcx, rdi
0x18003bfc8  mov     rax, rbx
0x18003bfcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bfd0  mov     ebx, eax
0x18003bfd2  test    eax, eax
0x18003bfd4  jns     short loc_18003C028
0x18003bfd6  mov     rcx, [rbp+28h]; this
0x18003bfda  mov     r9d, eax; char *
0x18003bfdd  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003bfe4  mov     edx, 0A55h; void *
0x18003bfe9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bfee  nop
0x18003bfef  mov     rcx, [rbp+string]; string
0x18003bff3  call    cs:__imp_WindowsDeleteString
0x18003bff9  mov     [rbp+string], r15
0x18003bffd  mov     rcx, [rbp+pProxy]
0x18003c001  test    rcx, rcx
0x18003c004  jz      short loc_18003C017
0x18003c006  mov     [rbp+pProxy], r15
0x18003c00a  mov     rax, [rcx]
0x18003c00d  mov     rax, [rax+10h]
0x18003c011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c016  nop
0x18003c017  mov     rcx, [rbp+string1]; string
0x18003c01b  call    cs:__imp_WindowsDeleteString
0x18003c021  mov     eax, ebx
0x18003c023  jmp     loc_18003BDB2
0x18003c028  mov     dword ptr [rbp+result], r15d
0x18003c02c  lea     r8, [rbp+result]; result
0x18003c030  mov     rdx, cs:string2; string2
0x18003c037  mov     rcx, [rbp+string1]; string1
0x18003c03b  call    cs:__imp_WindowsCompareStringOrdinal
0x18003c041  test    eax, eax
0x18003c043  js      loc_18003C109
0x18003c049  cmp     dword ptr [rbp+result], r15d
0x18003c04d  jz      short loc_18003C076
0x18003c04f  mov     dword ptr [rbp+result], r15d
0x18003c053  lea     r8, [rbp+result]; result
0x18003c057  mov     rdx, cs:qword_180066588; string2
0x18003c05e  mov     rcx, [rbp+string1]; string1
0x18003c062  call    cs:__imp_WindowsCompareStringOrdinal
0x18003c068  test    eax, eax
0x18003c06a  js      loc_18003C111
0x18003c070  cmp     dword ptr [rbp+result], r15d
0x18003c074  jnz     short loc_18003C0CA
0x18003c076  mov     dword ptr [rbp+result], r15d
0x18003c07a  lea     r8, [rbp+result]; result
0x18003c07e  mov     rdx, cs:qword_1800665A8; string2
0x18003c085  mov     rcx, [rbp+string]; string1
0x18003c089  call    cs:__imp_WindowsCompareStringOrdinal
0x18003c08f  test    eax, eax
0x18003c091  js      short loc_18003C101
0x18003c093  cmp     dword ptr [rbp+result], r15d
0x18003c097  jnz     short loc_18003C0A1
0x18003c099  mov     dword ptr [rsi], 1
0x18003c09f  jmp     short loc_18003C0CA
0x18003c0a1  mov     dword ptr [rbp+result], r15d
0x18003c0a5  lea     r8, [rbp+result]; result
0x18003c0a9  mov     rdx, cs:string; string2
0x18003c0b0  mov     rcx, [rbp+string]; string1
0x18003c0b4  call    cs:__imp_WindowsCompareStringOrdinal
0x18003c0ba  test    eax, eax
0x18003c0bc  js      short loc_18003C119
0x18003c0be  cmp     dword ptr [rbp+result], r15d
0x18003c0c2  jnz     short loc_18003C0CA
0x18003c0c4  mov     dword ptr [rsi], 2
0x18003c0ca  mov     rcx, [rbp+string]; string
0x18003c0ce  call    cs:__imp_WindowsDeleteString
0x18003c0d4  mov     [rbp+string], r15
0x18003c0d8  mov     rcx, [rbp+pProxy]
0x18003c0dc  test    rcx, rcx
0x18003c0df  jz      short loc_18003C0F2
0x18003c0e1  mov     [rbp+pProxy], r15
0x18003c0e5  mov     rax, [rcx]
0x18003c0e8  mov     rax, [rax+10h]
0x18003c0ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c0f1  nop
0x18003c0f2  mov     rcx, [rbp+string1]; string
0x18003c0f6  call    cs:__imp_WindowsDeleteString
0x18003c0fc  jmp     loc_18003BDB0
0x18003c101  mov     ecx, eax; this
0x18003c103  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18003c108  int     3; Trap to Debugger
0x18003c109  mov     ecx, eax; this
0x18003c10b  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18003c110  int     3; Trap to Debugger
0x18003c111  mov     ecx, eax; this
0x18003c113  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18003c118  int     3; Trap to Debugger
0x18003c119  mov     ecx, eax; this
0x18003c11b  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
