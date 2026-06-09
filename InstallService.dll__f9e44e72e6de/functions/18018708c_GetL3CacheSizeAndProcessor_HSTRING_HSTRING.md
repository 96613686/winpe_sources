# _GetL3CacheSizeAndProcessor(HSTRING__ * *,HSTRING__ * *)

- ea: `0x18018708c`
- end: `0x1801876af`
- name: `?_GetL3CacheSizeAndProcessor@@YAJPEAPEAUHSTRING__@@0@Z`
- size: `1571`
- prototype: `__int64 __fastcall(HSTRING *string, HSTRING *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18018260c`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x180010b74`
- `0x18001af10`
- `0x18001c964`
- `0x180051798`
- `0x180063648`
- `0x1800d31b8`
- `0x18018708c`
- `0x180215010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180187434`
- `OLEAUT32!__imp_VariantInit` at `0x180187434`
- `OLEAUT32!__imp_VariantClear` at `0x18018757f`
- `OLEAUT32!__imp_VariantClear` at `0x18018761c`
- `OLEAUT32!__imp_VariantClear` at `0x18018757f`
- `OLEAUT32!__imp_VariantClear` at `0x18018761c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180187544`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801875ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180187544`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801875ff`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1801871fe`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1801871fe`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801870e7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801870e7`

## string_xrefs

- `0x1801870fe`: `onecoreuap\enduser\winstore\installservice\libqueue2\restore.cpp`
- `0x180187195`: `onecoreuap\enduser\winstore\installservice\libqueue2\restore.cpp`
- `0x180187215`: `onecoreuap\enduser\winstore\installservice\libqueue2\restore.cpp`
- `0x18018727e`: `onecoreuap\enduser\winstore\installservice\libqueue2\restore.cpp`
- `0x1801872f8`: `onecoreuap\enduser\winstore\installservice\libqueue2\restore.cpp`
- `0x1801873ab`: `onecoreuap\enduser\winstore\installservice\libqueue2\restore.cpp`
- `0x1801874b8`: `onecoreuap\enduser\winstore\installservice\libqueue2\restore.cpp`
- `0x180187559`: `onecoreuap\enduser\winstore\installservice\libqueue2\restore.cpp`
- `0x1801875a2`: `L3CacheSize`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall _GetL3CacheSizeAndProcessor(HSTRING *string, HSTRING *a2)
{
  HRESULT v4; // esi
  HRESULT v5; // eax
  unsigned int v6; // ebx
  LPVOID v7; // rcx
  LPVOID v9; // rdi
  __int64 (__fastcall *v10)(LPVOID, const wchar_t *, _QWORD, _QWORD); // rbx
  int v11; // eax
  unsigned int v12; // ebx
  LPVOID v13; // rcx
  __int64 v14; // r14
  HRESULT v15; // eax
  unsigned int v16; // ebx
  LPVOID v17; // rcx
  LPVOID v18; // rcx
  LPVOID v19; // rcx
  IUnknown *v20; // rdi
  ULONG (__stdcall *Release)(IUnknown *); // rbx
  int v22; // eax
  __int64 v23; // rbx
  __int64 (__fastcall *v24)(__int64, __int64, __int64, __int64 *, int *, __int64 *); // rdi
  LPVOID v25; // rcx
  HRESULT v26; // eax
  const WCHAR *v27; // rcx
  LPVOID v28; // rcx
  int ppv; // [rsp+20h] [rbp-D8h]
  int ppva; // [rsp+20h] [rbp-D8h]
  LPVOID v31; // [rsp+50h] [rbp-A8h] BYREF
  IUnknown *pProxy; // [rsp+58h] [rbp-A0h] BYREF
  int v33; // [rsp+60h] [rbp-98h] BYREF
  __int64 v34; // [rsp+68h] [rbp-90h] BYREF
  __int64 v35; // [rsp+70h] [rbp-88h] BYREF
  __int64 v36; // [rsp+78h] [rbp-80h] BYREF
  __int64 v37; // [rsp+80h] [rbp-78h] BYREF
  PCNZWCH sourceString; // [rsp+88h] [rbp-70h] BYREF
  VARIANTARG pvarg; // [rsp+90h] [rbp-68h] BYREF
  PCNZWCH v40[2]; // [rsp+A8h] [rbp-50h] BYREF
  UINT32 length; // [rsp+B8h] [rbp-40h]
  unsigned __int64 v42; // [rsp+C0h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v4 = 0;
  v31 = 0;
  v5 = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &IID_IWbemLocator, &v31);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC5,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
      (const char *)(unsigned int)v5,
      ppv);
    v7 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v7 + 16LL))(v7);
    }
    return v6;
  }
  pProxy = 0;
  v9 = v31;
  v10 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)v31 + 24LL);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&pProxy);
  v11 = v10(v9, L"ROOT\\CIMV2", 0, 0);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD5,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
      (const char *)(unsigned int)v11,
      0);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&pProxy);
    v13 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v13 + 16LL))(v13);
    }
    return v12;
  }
  v14 = -1;
  v15 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0);
  v16 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE2,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
      (const char *)(unsigned int)v15,
      ppva);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&pProxy);
    v17 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
    }
    return v16;
  }
  wil::make_bstr(&v35, L"WQL");
  if ( !v35 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE8,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
      (const char *)0x8007000ELL,
      ppva);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&pProxy);
    v18 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 16LL))(v18);
    }
    return 2147942414LL;
  }
  wil::make_bstr(&v37, L"select * from Win32_Processor");
  if ( !v37 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
      (const char *)0x8007000ELL,
      ppva);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v37);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&pProxy);
    v19 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v19 + 16LL))(v19);
    }
    return 2147942414LL;
  }
  v36 = 0;
  v20 = pProxy;
  Release = pProxy->lpVtbl[6].Release;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v36);
  v22 = ((__int64 (__fastcall *)(IUnknown *, __int64, __int64, __int64))Release)(v20, v35, v37, 48);
  if ( v22 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xF4,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
      (const char *)(unsigned int)v22,
      0);
LABEL_43:
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v36);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v37);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&pProxy);
    v28 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v28 + 16LL))(v28);
    }
    return (unsigned int)v4;
  }
  v34 = 0;
  v33 = 0;
  v23 = v36;
  if ( !v36
    || (v24 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *, int *, __int64 *))(*(_QWORD *)v36 + 32LL),
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v34),
        v4 = v24(v23, 0xFFFFFFFFLL, 1, &v34, &v33, &v36),
        v4 < 0) )
  {
LABEL_42:
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v34);
    goto LABEL_43;
  }
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( (*(int (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *))(*(_QWORD *)v34 + 32LL))(
         v34,
         L"Name",
         0,
         &pvarg) < 0 )
  {
LABEL_36:
    v4 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v34 + 32LL))(
           v34,
           L"L3CacheSize",
           0,
           &pvarg,
           0,
           0);
    if ( v4 >= 0 )
    {
      if ( pvarg.vt == 3 )
      {
        std::to_wstring(v40, pvarg.cyVal.Lo);
        v27 = (const WCHAR *)v40;
        if ( v42 > 7 )
          v27 = v40[0];
        v4 = WindowsCreateString(v27, length, string);
        std::wstring::_Tidy_deallocate(v40);
      }
      VariantClear(&pvarg);
    }
    goto LABEL_42;
  }
  if ( pvarg.vt != 8 )
  {
LABEL_35:
    VariantClear(&pvarg);
    goto LABEL_36;
  }
  wil::make_bstr(&sourceString, pvarg.llVal);
  if ( sourceString )
  {
    do
      ++v14;
    while ( sourceString[v14] );
    v26 = WindowsCreateString(sourceString, v14, a2);
    if ( v26 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x10C,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
        (const char *)(unsigned int)v26,
        0);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&sourceString);
    goto LABEL_35;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x10B,
    (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\restore.cpp",
    (const char *)0x8007000ELL,
    0);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&sourceString);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v34);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v36);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v37);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&pProxy);
  v25 = v31;
  if ( v31 )
  {
    v31 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v25 + 16LL))(v25);
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18018708c  mov     [rsp+arg_10], rbx
0x180187091  mov     [rsp+arg_18], rsi
0x180187096  push    rdi
0x180187097  push    r12
0x180187099  push    r13
0x18018709b  push    r14
0x18018709d  push    r15
0x18018709f  sub     rsp, 0D0h
0x1801870a6  mov     rax, cs:__security_cookie
0x1801870ad  xor     rax, rsp
0x1801870b0  mov     [rsp+0F8h+var_30], rax
0x1801870b8  mov     r15, rdx
0x1801870bb  mov     r12, rcx
0x1801870be  xor     r13d, r13d
0x1801870c1  mov     esi, r13d
0x1801870c4  mov     [rsp+0F8h+var_A8], r13
0x1801870c9  lea     rax, [rsp+0F8h+var_A8]
0x1801870ce  mov     [rsp+0F8h+ppv], rax; int
0x1801870d3  lea     r9, IID_IWbemLocator; riid
0x1801870da  xor     edx, edx; pUnkOuter
0x1801870dc  lea     r8d, [r13+1]; dwClsContext
0x1801870e0  lea     rcx, CLSID_WbemLocator; rclsid
0x1801870e7  call    cs:__imp_CoCreateInstance
0x1801870ed  mov     ebx, eax
0x1801870ef  test    eax, eax
0x1801870f1  jns     short loc_180187133
0x1801870f3  mov     rcx, [rsp+0F8h]; this
0x1801870fb  mov     r9d, eax; char *
0x1801870fe  lea     r8, aOnecoreuapEndu_24; "onecoreuap\\enduser\\winstore\\installs"...
0x180187105  mov     edx, 0C5h; void *
0x18018710a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018710f  nop
0x180187110  mov     rcx, [rsp+0F8h+var_A8]
0x180187115  test    rcx, rcx
0x180187118  jz      short loc_18018712C
0x18018711a  mov     [rsp+0F8h+var_A8], r13
0x18018711f  mov     rax, [rcx]
0x180187122  mov     rax, [rax+10h]
0x180187126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018712b  nop
0x18018712c  mov     eax, ebx
0x18018712e  jmp     loc_180187681
0x180187133  mov     [rsp+0F8h+pProxy], r13
0x180187138  mov     rdi, [rsp+0F8h+var_A8]
0x18018713d  mov     rax, [rdi]
0x180187140  mov     rbx, [rax+18h]
0x180187144  lea     rcx, [rsp+0F8h+pProxy]
0x180187149  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18018714e  lea     rax, [rsp+0F8h+pProxy]
0x180187153  mov     [rsp+0F8h+var_B8], rax
0x180187158  mov     qword ptr [rsp+0F8h+dwCapabilities], r13
0x18018715d  mov     [rsp+0F8h+pAuthInfo], r13
0x180187162  mov     [rsp+0F8h+dwImpLevel], r13d
0x180187167  mov     [rsp+0F8h+ppv], r13; int
0x18018716c  xor     r9d, r9d
0x18018716f  xor     r8d, r8d
0x180187172  lea     rdx, aRootCimv2; "ROOT\\CIMV2"
0x180187179  mov     rcx, rdi
0x18018717c  mov     rax, rbx
0x18018717f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180187184  mov     ebx, eax
0x180187186  test    eax, eax
0x180187188  jns     short loc_1801871D5
0x18018718a  mov     rcx, [rsp+0F8h]; this
0x180187192  mov     r9d, eax; char *
0x180187195  lea     r8, aOnecoreuapEndu_24; "onecoreuap\\enduser\\winstore\\installs"...
0x18018719c  mov     edx, 0D5h; void *
0x1801871a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801871a6  nop
0x1801871a7  lea     rcx, [rsp+0F8h+pProxy]
0x1801871ac  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801871b1  nop
0x1801871b2  mov     rcx, [rsp+0F8h+var_A8]
0x1801871b7  test    rcx, rcx
0x1801871ba  jz      short loc_1801871CE
0x1801871bc  mov     [rsp+0F8h+var_A8], r13
0x1801871c1  mov     rax, [rcx]
0x1801871c4  mov     rax, [rax+10h]
0x1801871c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801871cd  nop
0x1801871ce  mov     eax, ebx
0x1801871d0  jmp     loc_180187681
0x1801871d5  mov     [rsp+0F8h+dwCapabilities], r13d; dwCapabilities
0x1801871da  mov     [rsp+0F8h+pAuthInfo], r13; pAuthInfo
0x1801871df  mov     [rsp+0F8h+dwImpLevel], 3; dwImpLevel
0x1801871e7  mov     dword ptr [rsp+0F8h+ppv], r13d; int
0x1801871ec  or      r14, 0FFFFFFFFFFFFFFFFh
0x1801871f0  mov     r9, r14; pServerPrincName
0x1801871f3  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x1801871f6  mov     r8d, edx; dwAuthzSvc
0x1801871f9  mov     rcx, [rsp+0F8h+pProxy]; pProxy
0x1801871fe  call    cs:__imp_CoSetProxyBlanket
0x180187204  mov     ebx, eax
0x180187206  test    eax, eax
0x180187208  jns     short loc_180187255
0x18018720a  mov     rcx, [rsp+0F8h]; this
0x180187212  mov     r9d, eax; char *
0x180187215  lea     r8, aOnecoreuapEndu_24; "onecoreuap\\enduser\\winstore\\installs"...
0x18018721c  mov     edx, 0E2h; void *
0x180187221  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180187226  nop
0x180187227  lea     rcx, [rsp+0F8h+pProxy]
0x18018722c  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180187231  nop
0x180187232  mov     rcx, [rsp+0F8h+var_A8]
0x180187237  test    rcx, rcx
0x18018723a  jz      short loc_18018724E
0x18018723c  mov     [rsp+0F8h+var_A8], r13
0x180187241  mov     rax, [rcx]
0x180187244  mov     rax, [rax+10h]
0x180187248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018724d  nop
0x18018724e  mov     eax, ebx
0x180187250  jmp     loc_180187681
0x180187255  lea     rdx, aWql; "WQL"
0x18018725c  lea     rcx, [rsp+0F8h+var_88]
0x180187261  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x180187266  nop
0x180187267  cmp     [rsp+0F8h+var_88], r13
0x18018726c  jnz     short loc_1801872C9
0x18018726e  mov     rcx, [rsp+0F8h]; this
0x180187276  mov     ebx, 8007000Eh
0x18018727b  mov     r9d, ebx; char *
0x18018727e  lea     r8, aOnecoreuapEndu_24; "onecoreuap\\enduser\\winstore\\installs"...
0x180187285  mov     edx, 0E8h; void *
0x18018728a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018728f  nop
0x180187290  lea     rcx, [rsp+0F8h+var_88]
0x180187295  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18018729a  nop
0x18018729b  lea     rcx, [rsp+0F8h+pProxy]
0x1801872a0  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801872a5  nop
0x1801872a6  mov     rcx, [rsp+0F8h+var_A8]
0x1801872ab  test    rcx, rcx
0x1801872ae  jz      short loc_1801872C2
0x1801872b0  mov     [rsp+0F8h+var_A8], r13
0x1801872b5  mov     rax, [rcx]
0x1801872b8  mov     rax, [rax+10h]
0x1801872bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801872c1  nop
0x1801872c2  mov     eax, ebx
0x1801872c4  jmp     loc_180187681
0x1801872c9  lea     rdx, aSelectFromWin3; "select * from Win32_Processor"
0x1801872d0  lea     rcx, [rsp+0F8h+var_78]
0x1801872d8  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1801872dd  nop
0x1801872de  cmp     [rsp+0F8h+var_78], r13
0x1801872e6  jnz     short loc_180187351
0x1801872e8  mov     rcx, [rsp+0F8h]; this
0x1801872f0  mov     ebx, 8007000Eh
0x1801872f5  mov     r9d, ebx; char *
0x1801872f8  lea     r8, aOnecoreuapEndu_24; "onecoreuap\\enduser\\winstore\\installs"...
0x1801872ff  mov     edx, 0EBh; void *
0x180187304  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180187309  nop
0x18018730a  lea     rcx, [rsp+0F8h+var_78]
0x180187312  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180187317  nop
0x180187318  lea     rcx, [rsp+0F8h+var_88]
0x18018731d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180187322  nop
0x180187323  lea     rcx, [rsp+0F8h+pProxy]
0x180187328  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18018732d  nop
0x18018732e  mov     rcx, [rsp+0F8h+var_A8]
0x180187333  test    rcx, rcx
0x180187336  jz      short loc_18018734A
0x180187338  mov     [rsp+0F8h+var_A8], r13
0x18018733d  mov     rax, [rcx]
0x180187340  mov     rax, [rax+10h]
0x180187344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180187349  nop
0x18018734a  mov     eax, ebx
0x18018734c  jmp     loc_180187681
0x180187351  mov     [rsp+0F8h+var_80], r13
0x180187356  mov     rdi, [rsp+0F8h+pProxy]
0x18018735b  mov     rax, [rdi]
0x18018735e  mov     rbx, [rax+0A0h]
0x180187365  lea     rcx, [rsp+0F8h+var_80]
0x18018736a  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18018736f  lea     rax, [rsp+0F8h+var_80]
0x180187374  mov     qword ptr [rsp+0F8h+dwImpLevel], rax
0x180187379  mov     [rsp+0F8h+ppv], r13; int
0x18018737e  mov     r9d, 30h ; '0'
0x180187384  mov     r8, [rsp+0F8h+var_78]
0x18018738c  mov     rdx, [rsp+0F8h+var_88]
0x180187391  mov     rcx, rdi
0x180187394  mov     rax, rbx
0x180187397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018739c  mov     rcx, [rsp+0F8h]; this
0x1801873a4  test    eax, eax
0x1801873a6  jns     short loc_1801873C1
0x1801873a8  mov     r9d, eax; char *
0x1801873ab  lea     r8, aOnecoreuapEndu_24; "onecoreuap\\enduser\\winstore\\installs"...
0x1801873b2  mov     edx, 0F4h; void *
0x1801873b7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801873bc  jmp     loc_18018762E
0x1801873c1  mov     [rsp+0F8h+var_90], r13
0x1801873c6  mov     [rsp+0F8h+var_98], r13d
0x1801873cb  mov     rbx, [rsp+0F8h+var_80]
0x1801873d0  test    rbx, rbx
0x1801873d3  jz      loc_180187623
0x1801873d9  mov     rax, [rbx]
0x1801873dc  mov     rdi, [rax+20h]
0x1801873e0  lea     rcx, [rsp+0F8h+var_90]
0x1801873e5  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801873ea  lea     rax, [rsp+0F8h+var_98]
0x1801873ef  mov     [rsp+0F8h+ppv], rax
0x1801873f4  lea     r9, [rsp+0F8h+var_90]
0x1801873f9  mov     r8d, 1
0x1801873ff  mov     edx, r14d
0x180187402  mov     rcx, rbx
0x180187405  mov     rax, rdi
0x180187408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018740d  mov     esi, eax
0x18018740f  test    eax, eax
0x180187411  js      loc_180187623
0x180187417  xorps   xmm0, xmm0
0x18018741a  xor     eax, eax
0x18018741c  movups  xmmword ptr [rsp+0F8h+pvarg], xmm0
0x180187424  mov     qword ptr [rsp+0F8h+pvarg+10h], rax
0x18018742c  lea     rcx, [rsp+0F8h+pvarg]; pvarg
0x180187434  call    cs:__imp_VariantInit
0x18018743a  mov     rcx, [rsp+0F8h+var_90]
0x18018743f  mov     rax, [rcx]
0x180187442  mov     qword ptr [rsp+0F8h+dwImpLevel], r13
0x180187447  mov     [rsp+0F8h+ppv], r13; int
0x18018744c  lea     r9, [rsp+0F8h+pvarg]
0x180187454  xor     r8d, r8d
0x180187457  lea     rdx, aName; "Name"
0x18018745e  mov     rax, [rax+20h]
0x180187462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180187467  test    eax, eax
0x180187469  js      loc_180187585
0x18018746f  mov     eax, 8
0x180187474  cmp     ax, word ptr [rsp+0F8h+pvarg]
0x18018747c  jnz     loc_180187577
0x180187482  mov     rdx, qword ptr [rsp+0F8h+pvarg+8]
0x18018748a  lea     rcx, [rsp+0F8h+sourceString]
0x180187492  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x180187497  mov     rcx, [rsp+0F8h+sourceString]; sourceString
0x18018749f  test    rcx, rcx
0x1801874a2  jnz     loc_180187534
0x1801874a8  mov     rcx, [rsp+0F8h]; this
0x1801874b0  mov     ebx, 8007000Eh
0x1801874b5  mov     r9d, ebx; char *
0x1801874b8  lea     r8, aOnecoreuapEndu_24; "onecoreuap\\enduser\\winstore\\installs"...
0x1801874bf  mov     edx, 10Bh; void *
0x1801874c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801874c9  lea     rcx, [rsp+0F8h+sourceString]
0x1801874d1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801874d6  nop
0x1801874d7  lea     rcx, [rsp+0F8h+var_90]
0x1801874dc  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801874e1  nop
0x1801874e2  lea     rcx, [rsp+0F8h+var_80]
0x1801874e7  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801874ec  nop
0x1801874ed  lea     rcx, [rsp+0F8h+var_78]
0x1801874f5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801874fa  nop
0x1801874fb  lea     rcx, [rsp+0F8h+var_88]
0x180187500  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180187505  nop
0x180187506  lea     rcx, [rsp+0F8h+pProxy]
0x18018750b  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180187510  nop
0x180187511  mov     rcx, [rsp+0F8h+var_A8]
0x180187516  test    rcx, rcx
0x180187519  jz      short loc_18018752D
0x18018751b  mov     [rsp+0F8h+var_A8], r13
0x180187520  mov     rax, [rcx]
0x180187523  mov     rax, [rax+10h]
0x180187527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018752c  nop
0x18018752d  mov     eax, ebx
0x18018752f  jmp     loc_180187681
0x180187534  inc     r14
0x180187537  cmp     [rcx+r14*2], r13w
0x18018753c  jnz     short loc_180187534
0x18018753e  mov     r8, r15; string
0x180187541  mov     edx, r14d; length
0x180187544  call    cs:__imp_WindowsCreateString
0x18018754a  mov     rcx, [rsp+0F8h]; this
0x180187552  test    eax, eax
0x180187554  jns     short loc_18018756A
0x180187556  mov     r9d, eax; char *
0x180187559  lea     r8, aOnecoreuapEndu_24; "onecoreuap\\enduser\\winstore\\installs"...
0x180187560  mov     edx, 10Ch; void *
0x180187565  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18018756a  lea     rcx, [rsp+0F8h+sourceString]
0x180187572  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180187577  lea     rcx, [rsp+0F8h+pvarg]; pvarg
0x18018757f  call    cs:__imp_VariantClear
0x180187585  mov     rcx, [rsp+0F8h+var_90]
0x18018758a  mov     rax, [rcx]
0x18018758d  mov     qword ptr [rsp+0F8h+dwImpLevel], r13
0x180187592  mov     [rsp+0F8h+ppv], r13
0x180187597  lea     r9, [rsp+0F8h+pvarg]
  ... truncated ...
```
