# OSIntegration::DEH::Internal::DownloadUploadClassHelper::SubmitBackgroundTasksExtension(OSIntegration::Package const *,Windows::Internal::String const &)

- ea: `0x180070c34`
- end: `0x180071088`
- name: `?SubmitBackgroundTasksExtension@DownloadUploadClassHelper@Internal@DEH@OSIntegration@@CAJPEBVPackage@4@AEBVString@2Windows@@@Z`
- size: `1108`
- prototype: `__int64 __fastcall(const struct OSIntegration::Package *, const struct Windows::Internal::String *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800b86dc`

## callees

- `0x18003a300`
- `0x180070c34`
- `0x180071090`
- `0x18009aff4`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180070cd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180070d4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180070dc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180070cd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180070d4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180070dc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070cec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070d67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070de0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070e24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070e34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070e5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070ea3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070ecd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070f2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070f7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070f8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070fb4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070cec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070d67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070de0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070e24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070e34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070e5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070ea3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070ecd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070f2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070f7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070f8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180070fb4`

## string_xrefs

- `0x180070ca8`: `OSIntegration::DEH::Internal::DownloadUploadClassHelper::SubmitBackgroundTasksExtension`
- `0x180070e02`: `OSIntegration::DEH::Internal::DownloadUploadClassHelper::SubmitBackgroundTasksExtension`
- `0x180070e81`: `OSIntegration::DEH::Internal::DownloadUploadClassHelper::SubmitBackgroundTasksExtension`
- `0x180070f0d`: `OSIntegration::DEH::Internal::DownloadUploadClassHelper::SubmitBackgroundTasksExtension`
- `0x180070fe4`: `OSIntegration::DEH::Internal::DownloadUploadClassHelper::SubmitBackgroundTasksExtension`
- `0x18007103e`: `OSIntegration::DEH::Internal::DownloadUploadClassHelper::SubmitBackgroundTasksExtension`
- `0x180070e75`: `capabilitiesProperty.Initialize(DownloadUploadClassConstants::backgroundTasksPropCapabilities)`
- `0x180070f01`: `!(wil::verify_bool(extensionRegistration->AddAttribute(capabilitiesProperty, capabilities)))`
- `0x180070df6`: `iconPath.Initialize(DownloadUploadClassConstants::extensionIconPath)`
- `0x180070c9c`: `contractId.Initialize(DownloadUploadClassConstants::backgroundTasksContractId)`
- `0x180071032`: `!(wil::verify_bool(extensionRegistration->put_Icon(iconPath)))`
- `0x180070fd8`: `extensionRegistration`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall OSIntegration::DEH::Internal::DownloadUploadClassHelper::SubmitBackgroundTasksExtension(
        const struct OSIntegration::Package *a1,
        const struct Windows::Internal::String *a2)
{
  HSTRING v2; // rbx
  unsigned __int64 v3; // r14
  unsigned __int64 v4; // rdx
  HRESULT v5; // esi
  HRESULT v6; // edi
  HSTRING v7; // rcx
  unsigned __int64 v8; // rdx
  HSTRING v9; // rcx
  HSTRING v10; // rcx
  struct OSIntegration::DEH::ExtensionRegistration *v11; // rcx
  struct OSIntegration::DEH::ExtensionRegistration *v13; // rcx
  struct OSIntegration::DEH::ExtensionRegistration *v14; // rcx
  struct OSIntegration::DEH::ExtensionRegistration *v15; // rcx
  struct OSIntegration::DEH::ExtensionRegistration *v16; // rcx
  struct OSIntegration::DEH::ExtensionRegistration *v17; // rcx
  char *v18; // [rsp+28h] [rbp-28h]
  HSTRING v19; // [rsp+30h] [rbp-20h] BYREF
  HSTRING v20; // [rsp+38h] [rbp-18h] BYREF
  HSTRING string[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+88h] [rbp+38h]
  struct OSIntegration::DEH::ExtensionRegistration *v23; // [rsp+A0h] [rbp+50h] BYREF
  HSTRING v24; // [rsp+A8h] [rbp+58h] BYREF

  v2 = 0;
  v19 = 0;
  if ( !off_1802E0698 )
  {
    v6 = -2147467261;
    goto LABEL_7;
  }
  string[0] = 0;
  v3 = -1;
  v4 = -1;
  do
    ++v4;
  while ( off_1802E0698[v4] );
  v5 = -2147024362;
  if ( v4 <= 0xFFFFFFFF )
  {
    v6 = WindowsCreateString(off_1802E0698, v4, string);
    if ( v6 >= 0 )
    {
      v2 = string[0];
      v19 = string[0];
      WindowsDeleteString(0);
    }
  }
  else
  {
    v6 = -2147024362;
  }
  if ( v6 < 0 )
  {
LABEL_7:
    LODWORD(v18) = v6;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x17F,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\downloaduploaddeh\\downloaduploadclasshelper.cpp",
      "OSIntegration::DEH::Internal::DownloadUploadClassHelper::SubmitBackgroundTasksExtension",
      "contractId.Initialize(DownloadUploadClassConstants::backgroundTasksContractId)",
      v18,
      (int)v19);
    if ( v2 )
    {
      v7 = v2;
LABEL_43:
      WindowsDeleteString(v7);
    }
    return (unsigned int)v6;
  }
  OSIntegration::DEH::ExtensionRegistration::Create(&v23);
  if ( !v23 )
  {
    v6 = -2147467261;
    LODWORD(v18) = -2147467261;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x183,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\downloaduploaddeh\\downloaduploadclasshelper.cpp",
      "OSIntegration::DEH::Internal::DownloadUploadClassHelper::SubmitBackgroundTasksExtension",
      "extensionRegistration",
      v18,
      (int)v19);
    v16 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(struct OSIntegration::DEH::ExtensionRegistration *))(*(_QWORD *)v16 + 16LL))(v16);
    }
    goto LABEL_64;
  }
  v24 = 0;
  if ( !off_1802E0690 )
  {
    v6 = -2147467261;
LABEL_38:
    LODWORD(v18) = v6;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x186,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\downloaduploaddeh\\downloaduploadclasshelper.cpp",
      "OSIntegration::DEH::Internal::DownloadUploadClassHelper::SubmitBackgroundTasksExtension",
      "capabilitiesProperty.Initialize(DownloadUploadClassConstants::backgroundTasksPropCapabilities)",
      v18,
      (int)v19);
    if ( v24 )
      WindowsDeleteString(v24);
    v13 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(struct OSIntegration::DEH::ExtensionRegistration *))(*(_QWORD *)v13 + 16LL))(v13);
    }
LABEL_42:
    v7 = v19;
    if ( v19 )
      goto LABEL_43;
    return (unsigned int)v6;
  }
  string[0] = 0;
  v8 = -1;
  do
    ++v8;
  while ( off_1802E0690[v8] );
  if ( v8 > 0xFFFFFFFF )
  {
    v6 = -2147024362;
  }
  else
  {
    v6 = WindowsCreateString(off_1802E0690, v8, string);
    if ( v6 >= 0 )
    {
      v9 = v24;
      v24 = string[0];
      WindowsDeleteString(v9);
    }
  }
  if ( v6 < 0 )
    goto LABEL_38;
  if ( !(*(unsigned __int8 (__fastcall **)(struct OSIntegration::DEH::ExtensionRegistration *, HSTRING *, __int64))(*(_QWORD *)v23 + 136LL))(
          v23,
          &v24,
          4100) )
  {
    v6 = -2147024882;
    LODWORD(v18) = -2147024882;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x18B,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\downloaduploaddeh\\downloaduploadclasshelper.cpp",
      "OSIntegration::DEH::Internal::DownloadUploadClassHelper::SubmitBackgroundTasksExtension",
      "!(wil::verify_bool(extensionRegistration->AddAttribute(capabilitiesProperty, capabilities)))",
      v18,
      (int)v19);
    if ( v24 )
      WindowsDeleteString(v24);
    v14 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(struct OSIntegration::DEH::ExtensionRegistration *))(*(_QWORD *)v14 + 16LL))(v14);
    }
    goto LABEL_42;
  }
  v20 = 0;
  if ( !off_1802E0688 )
  {
    v5 = -2147467261;
LABEL_28:
    LODWORD(v18) = v5;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x18F,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\downloaduploaddeh\\downloaduploadclasshelper.cpp",
      "OSIntegration::DEH::Internal::DownloadUploadClassHelper::SubmitBackgroundTasksExtension",
      "iconPath.Initialize(DownloadUploadClassConstants::extensionIconPath)",
      v18,
      (int)v19);
    if ( v20 )
      WindowsDeleteString(v20);
    if ( v24 )
      WindowsDeleteString(v24);
    v11 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(struct OSIntegration::DEH::ExtensionRegistration *))(*(_QWORD *)v11 + 16LL))(v11);
    }
    if ( v19 )
      WindowsDeleteString(v19);
    return (unsigned int)v5;
  }
  string[0] = 0;
  do
    ++v3;
  while ( off_1802E0688[v3] );
  if ( v3 <= 0xFFFFFFFF )
  {
    v5 = WindowsCreateString(off_1802E0688, v3, string);
    if ( v5 >= 0 )
    {
      v10 = v20;
      v20 = string[0];
      WindowsDeleteString(v10);
    }
  }
  if ( v5 < 0 )
    goto LABEL_28;
  if ( !(*(unsigned __int8 (__fastcall **)(struct OSIntegration::DEH::ExtensionRegistration *, HSTRING *))(*(_QWORD *)v23 + 88LL))(
          v23,
          &v20) )
  {
    v6 = -2147024882;
    LODWORD(v18) = -2147024882;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x191,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\downloaduploaddeh\\downloaduploadclasshelper.cpp",
      "OSIntegration::DEH::Internal::DownloadUploadClassHelper::SubmitBackgroundTasksExtension",
      "!(wil::verify_bool(extensionRegistration->put_Icon(iconPath)))",
      v18,
      (int)v19);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v20);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v24);
    v17 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(struct OSIntegration::DEH::ExtensionRegistration *))(*(_QWORD *)v17 + 16LL))(v17);
    }
LABEL_64:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v19);
    return (unsigned int)v6;
  }
  if ( v20 )
    WindowsDeleteString(v20);
  if ( v24 )
    WindowsDeleteString(v24);
  v15 = v23;
  if ( v23 )
  {
    v23 = 0;
    (*(void (__fastcall **)(struct OSIntegration::DEH::ExtensionRegistration *))(*(_QWORD *)v15 + 16LL))(v15);
  }
  if ( v19 )
    WindowsDeleteString(v19);
  return 0;
}

```

## disassembly

```asm
0x180070c34  mov     [rsp-38h+arg_0], rbx
0x180070c39  push    rbp
0x180070c3a  push    rsi
0x180070c3b  push    rdi
0x180070c3c  push    r12
0x180070c3e  push    r13
0x180070c40  push    r14
0x180070c42  push    r15
0x180070c44  mov     rbp, rsp
0x180070c47  sub     rsp, 50h
0x180070c4b  mov     r15, rdx
0x180070c4e  mov     r13, rcx
0x180070c51  xor     r12d, r12d
0x180070c54  mov     ebx, r12d
0x180070c57  mov     [rbp+var_20], rbx
0x180070c5b  mov     rcx, cs:off_1802E0698; sourceString
0x180070c62  test    rcx, rcx
0x180070c65  jz      short loc_180070C8F
0x180070c67  mov     [rbp+string], r12
0x180070c6b  or      r14, 0FFFFFFFFFFFFFFFFh
0x180070c6f  mov     rdx, r14
0x180070c72  inc     rdx; length
0x180070c75  cmp     [rcx+rdx*2], r12w
0x180070c7a  jnz     short loc_180070C72
0x180070c7c  mov     eax, 0FFFFFFFFh
0x180070c81  mov     esi, 80070216h
0x180070c86  cmp     rdx, rax
0x180070c89  jbe     short loc_180070CD2
0x180070c8b  mov     edi, esi
0x180070c8d  jmp     short loc_180070CF2
0x180070c8f  mov     edi, 80004003h
0x180070c94  mov     rcx, [rbp+38h]; this
0x180070c98  mov     dword ptr [rsp+50h+var_28], edi; char *
0x180070c9c  lea     rax, aContractidInit; "contractId.Initialize(DownloadUploadCla"...
0x180070ca3  mov     [rsp+50h+var_30], rax; char *
0x180070ca8  lea     r9, aOsintegrationD_115; "OSIntegration::DEH::Internal::DownloadU"...
0x180070caf  lea     r8, aOnecoreAdminAp_114; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180070cb6  mov     edx, 17Fh; void *
0x180070cbb  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180070cc0  nop
0x180070cc1  test    rbx, rbx
0x180070cc4  jz      loc_180070ED3
0x180070cca  mov     rcx, rbx
0x180070ccd  jmp     loc_180070ECD
0x180070cd2  lea     r8, [rbp+string]; string
0x180070cd6  call    cs:__imp_WindowsCreateString
0x180070cdc  mov     edi, eax
0x180070cde  test    eax, eax
0x180070ce0  js      short loc_180070CF2
0x180070ce2  mov     rbx, [rbp+string]
0x180070ce6  mov     [rbp+var_20], rbx
0x180070cea  xor     ecx, ecx; string
0x180070cec  call    cs:__imp_WindowsDeleteString
0x180070cf2  test    edi, edi
0x180070cf4  js      short loc_180070C94
0x180070cf6  mov     r9, [r13+328h]
0x180070cfd  mov     r8, r15
0x180070d00  lea     rdx, [rbp+var_20]
0x180070d04  lea     rcx, [rbp+arg_10]; struct OSIntegration::DEH::ExtensionRegistration **
0x180070d08  call    ?Create@ExtensionRegistration@DEH@OSIntegration@@SA?AV?$ComPtr@UExtensionRegistration@DEH@OSIntegration@@@WRL@Microsoft@@AEBVString@Internal@Windows@@0PEAVCollectors@23@@Z; OSIntegration::DEH::ExtensionRegistration::Create(Windows::Internal::String const &,Windows::Internal::String const &,OSIntegration::DEH::Collectors *)
0x180070d0d  nop
0x180070d0e  cmp     [rbp+arg_10], r12
0x180070d12  jz      loc_180070FCB
0x180070d18  mov     [rbp+arg_18], r12
0x180070d1c  mov     rcx, cs:off_1802E0690; sourceString
0x180070d23  test    rcx, rcx
0x180070d26  jz      loc_180070E68
0x180070d2c  mov     [rbp+string], r12
0x180070d30  mov     rdx, r14
0x180070d33  inc     rdx; length
0x180070d36  cmp     [rcx+rdx*2], r12w
0x180070d3b  jnz     short loc_180070D33
0x180070d3d  mov     ebx, 0FFFFFFFFh
0x180070d42  cmp     rdx, rbx
0x180070d45  ja      loc_180070EED
0x180070d4b  lea     r8, [rbp+string]; string
0x180070d4f  call    cs:__imp_WindowsCreateString
0x180070d55  mov     edi, eax
0x180070d57  test    eax, eax
0x180070d59  js      short loc_180070D6D
0x180070d5b  mov     rcx, [rbp+arg_18]; string
0x180070d5f  mov     rax, [rbp+string]
0x180070d63  mov     [rbp+arg_18], rax
0x180070d67  call    cs:__imp_WindowsDeleteString
0x180070d6d  test    edi, edi
0x180070d6f  js      loc_180070E6D
0x180070d75  mov     rcx, [rbp+arg_10]
0x180070d79  mov     rax, [rcx]
0x180070d7c  mov     r8d, 1004h
0x180070d82  lea     rdx, [rbp+arg_18]
0x180070d86  mov     rax, [rax+88h]
0x180070d8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070d92  test    al, al
0x180070d94  jz      loc_180070EF4
0x180070d9a  mov     [rbp+var_18], r12
0x180070d9e  mov     rcx, cs:off_1802E0688; sourceString
0x180070da5  test    rcx, rcx
0x180070da8  jz      loc_180070FC1
0x180070dae  mov     [rbp+string], r12
0x180070db2  inc     r14
0x180070db5  cmp     [rcx+r14*2], r12w
0x180070dba  jnz     short loc_180070DB2
0x180070dbc  cmp     r14, rbx
0x180070dbf  ja      short loc_180070DE6
0x180070dc1  mov     edx, r14d; length
0x180070dc4  lea     r8, [rbp+string]; string
0x180070dc8  call    cs:__imp_WindowsCreateString
0x180070dce  mov     esi, eax
0x180070dd0  test    eax, eax
0x180070dd2  js      short loc_180070DE6
0x180070dd4  mov     rcx, [rbp+var_18]; string
0x180070dd8  mov     rax, [rbp+string]
0x180070ddc  mov     [rbp+var_18], rax
0x180070de0  call    cs:__imp_WindowsDeleteString
0x180070de6  test    esi, esi
0x180070de8  jns     loc_180070F55
0x180070dee  mov     rcx, [rbp+38h]; this
0x180070df2  mov     dword ptr [rsp+50h+var_28], esi; char *
0x180070df6  lea     rax, aIconpathInitia; "iconPath.Initialize(DownloadUploadClass"...
0x180070dfd  mov     [rsp+50h+var_30], rax; char *
0x180070e02  lea     r9, aOsintegrationD_115; "OSIntegration::DEH::Internal::DownloadU"...
0x180070e09  lea     r8, aOnecoreAdminAp_114; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180070e10  mov     edx, 18Fh; void *
0x180070e15  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180070e1a  nop
0x180070e1b  mov     rcx, [rbp+var_18]; string
0x180070e1f  test    rcx, rcx
0x180070e22  jz      short loc_180070E2B
0x180070e24  call    cs:__imp_WindowsDeleteString
0x180070e2a  nop
0x180070e2b  mov     rcx, [rbp+arg_18]; string
0x180070e2f  test    rcx, rcx
0x180070e32  jz      short loc_180070E3B
0x180070e34  call    cs:__imp_WindowsDeleteString
0x180070e3a  nop
0x180070e3b  mov     rcx, [rbp+arg_10]
0x180070e3f  test    rcx, rcx
0x180070e42  jz      short loc_180070E55
0x180070e44  mov     [rbp+arg_10], r12
0x180070e48  mov     rax, [rcx]
0x180070e4b  mov     rax, [rax+10h]
0x180070e4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070e54  nop
0x180070e55  mov     rcx, [rbp+var_20]; string
0x180070e59  test    rcx, rcx
0x180070e5c  jz      short loc_180070E64
0x180070e5e  call    cs:__imp_WindowsDeleteString
0x180070e64  mov     eax, esi
0x180070e66  jmp     short loc_180070ED5
0x180070e68  mov     edi, 80004003h
0x180070e6d  mov     rcx, [rbp+38h]; this
0x180070e71  mov     dword ptr [rsp+50h+var_28], edi; char *
0x180070e75  lea     rax, aCapabilitiespr; "capabilitiesProperty.Initialize(Downloa"...
0x180070e7c  mov     [rsp+50h+var_30], rax; char *
0x180070e81  lea     r9, aOsintegrationD_115; "OSIntegration::DEH::Internal::DownloadU"...
0x180070e88  lea     r8, aOnecoreAdminAp_114; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180070e8f  mov     edx, 186h; void *
0x180070e94  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180070e99  nop
0x180070e9a  mov     rcx, [rbp+arg_18]; string
0x180070e9e  test    rcx, rcx
0x180070ea1  jz      short loc_180070EAA
0x180070ea3  call    cs:__imp_WindowsDeleteString
0x180070ea9  nop
0x180070eaa  mov     rcx, [rbp+arg_10]
0x180070eae  test    rcx, rcx
0x180070eb1  jz      short loc_180070EC4
0x180070eb3  mov     [rbp+arg_10], r12
0x180070eb7  mov     rax, [rcx]
0x180070eba  mov     rax, [rax+10h]
0x180070ebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070ec3  nop
0x180070ec4  mov     rcx, [rbp+var_20]; string
0x180070ec8  test    rcx, rcx
0x180070ecb  jz      short loc_180070ED3
0x180070ecd  call    cs:__imp_WindowsDeleteString
0x180070ed3  mov     eax, edi
0x180070ed5  mov     rbx, [rsp+50h+arg_0]
0x180070edd  add     rsp, 50h
0x180070ee1  pop     r15
0x180070ee3  pop     r14
0x180070ee5  pop     r13
0x180070ee7  pop     r12
0x180070ee9  pop     rdi
0x180070eea  pop     rsi
0x180070eeb  pop     rbp
0x180070eec  retn
0x180070eed  mov     edi, esi
0x180070eef  jmp     loc_180070D6D
0x180070ef4  mov     rcx, [rbp+38h]; this
0x180070ef8  mov     edi, 8007000Eh
0x180070efd  mov     dword ptr [rsp+50h+var_28], edi; char *
0x180070f01  lea     rax, aWilVerifyBoolE; "!(wil::verify_bool(extensionRegistratio"...
0x180070f08  mov     [rsp+50h+var_30], rax; char *
0x180070f0d  lea     r9, aOsintegrationD_115; "OSIntegration::DEH::Internal::DownloadU"...
0x180070f14  lea     r8, aOnecoreAdminAp_114; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180070f1b  mov     edx, 18Bh; void *
0x180070f20  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180070f25  nop
0x180070f26  mov     rcx, [rbp+arg_18]; string
0x180070f2a  test    rcx, rcx
0x180070f2d  jz      short loc_180070F36
0x180070f2f  call    cs:__imp_WindowsDeleteString
0x180070f35  nop
0x180070f36  mov     rcx, [rbp+arg_10]
0x180070f3a  test    rcx, rcx
0x180070f3d  jz      short loc_180070F50
0x180070f3f  mov     [rbp+arg_10], r12
0x180070f43  mov     rax, [rcx]
0x180070f46  mov     rax, [rax+10h]
0x180070f4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070f4f  nop
0x180070f50  jmp     loc_180070EC4
0x180070f55  mov     rcx, [rbp+arg_10]
0x180070f59  mov     rax, [rcx]
0x180070f5c  lea     rdx, [rbp+var_18]
0x180070f60  mov     rax, [rax+58h]
0x180070f64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070f69  test    al, al
0x180070f6b  jz      loc_180071025
0x180070f71  mov     rcx, [rbp+var_18]; string
0x180070f75  test    rcx, rcx
0x180070f78  jz      short loc_180070F81
0x180070f7a  call    cs:__imp_WindowsDeleteString
0x180070f80  nop
0x180070f81  mov     rcx, [rbp+arg_18]; string
0x180070f85  test    rcx, rcx
0x180070f88  jz      short loc_180070F91
0x180070f8a  call    cs:__imp_WindowsDeleteString
0x180070f90  nop
0x180070f91  mov     rcx, [rbp+arg_10]
0x180070f95  test    rcx, rcx
0x180070f98  jz      short loc_180070FAB
0x180070f9a  mov     [rbp+arg_10], r12
0x180070f9e  mov     rax, [rcx]
0x180070fa1  mov     rax, [rax+10h]
0x180070fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070faa  nop
0x180070fab  mov     rcx, [rbp+var_20]; string
0x180070faf  test    rcx, rcx
0x180070fb2  jz      short loc_180070FBA
0x180070fb4  call    cs:__imp_WindowsDeleteString
0x180070fba  xor     eax, eax
0x180070fbc  jmp     loc_180070ED5
0x180070fc1  mov     esi, 80004003h
0x180070fc6  jmp     loc_180070DEE
0x180070fcb  mov     rcx, [rbp+38h]; this
0x180070fcf  mov     edi, 80004003h
0x180070fd4  mov     dword ptr [rsp+50h+var_28], edi; char *
0x180070fd8  lea     rax, aExtensionregis_1; "extensionRegistration"
0x180070fdf  mov     [rsp+50h+var_30], rax; char *
0x180070fe4  lea     r9, aOsintegrationD_115; "OSIntegration::DEH::Internal::DownloadU"...
0x180070feb  lea     r8, aOnecoreAdminAp_114; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180070ff2  mov     edx, 183h; void *
0x180070ff7  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180070ffc  nop
0x180070ffd  mov     rcx, [rbp+arg_10]
0x180071001  test    rcx, rcx
0x180071004  jz      short loc_180071017
0x180071006  mov     [rbp+arg_10], r12
0x18007100a  mov     rax, [rcx]
0x18007100d  mov     rax, [rax+10h]
0x180071011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071016  nop
0x180071017  lea     rcx, [rbp+var_20]
0x18007101b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x180071020  jmp     loc_180070ED3
0x180071025  mov     rcx, [rbp+38h]; this
0x180071029  mov     edi, 8007000Eh
0x18007102e  mov     dword ptr [rsp+50h+var_28], edi; char *
0x180071032  lea     rax, aWilVerifyBoolE_0; "!(wil::verify_bool(extensionRegistratio"...
0x180071039  mov     [rsp+50h+var_30], rax; char *
0x18007103e  lea     r9, aOsintegrationD_115; "OSIntegration::DEH::Internal::DownloadU"...
0x180071045  lea     r8, aOnecoreAdminAp_114; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18007104c  mov     edx, 191h; void *
0x180071051  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180071056  nop
0x180071057  lea     rcx, [rbp+var_18]
0x18007105b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x180071060  nop
0x180071061  lea     rcx, [rbp+arg_18]
0x180071065  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x18007106a  nop
0x18007106b  mov     rcx, [rbp+arg_10]
0x18007106f  test    rcx, rcx
0x180071072  jz      short loc_180071085
0x180071074  mov     [rbp+arg_10], r12
0x180071078  mov     rax, [rcx]
0x18007107b  mov     rax, [rax+10h]
0x18007107f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071084  nop
0x180071085  jmp     short loc_180071017
```
