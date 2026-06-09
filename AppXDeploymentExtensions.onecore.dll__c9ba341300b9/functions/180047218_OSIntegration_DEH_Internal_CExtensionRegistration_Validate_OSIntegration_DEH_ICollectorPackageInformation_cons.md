# OSIntegration::DEH::Internal::CExtensionRegistration::Validate(OSIntegration::DEH::ICollectorPackageInformation const *)

- ea: `0x180047218`
- end: `0x180047795`
- name: `?Validate@CExtensionRegistration@Internal@DEH@OSIntegration@@QEAAJPEBUICollectorPackageInformation@34@@Z`
- size: `1405`
- prototype: `__int64 __fastcall(OSIntegration::DEH::Internal::CExtensionRegistration *__hidden this, const struct OSIntegration::DEH::ICollectorPackageInformation *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180046f34`

## callees

- `0x18000b3bc`
- `0x18003a300`
- `0x180047218`
- `0x180098ed0`
- `0x18009aff4`
- `0x1800cd9e4`
- `0x1800f0260`
- `0x1801a4794`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004727f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004727f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004735a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004735a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180047292`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180047292`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004733b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800474d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800474e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180047504`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180047513`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004760b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004761a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004763a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180047649`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004769c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800476ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800476cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800476da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004733b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800474d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800474e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180047504`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180047513`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004760b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004761a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004763a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180047649`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004769c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800476ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800476cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800476da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004739c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800473ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004739c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800473ac`

## string_xrefs

- `0x1800474b5`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\extensioncatalogcollector.cpp`
- `0x1800475eb`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\extensioncatalogcollector.cpp`
- `0x180047680`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\extensioncatalogcollector.cpp`
- `0x180047706`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\extensioncatalogcollector.cpp`
- `0x180047771`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\extensioncatalogcollector.cpp`
- `0x180047451`: `_outOfProcessActivatableClasses->HasKey(activatableClassId, found)`
- `0x180047562`: `_outOfProcessActivatableClasses->Lookup(activatableClassId, &registration)`
- `0x1800474ae`: `OSIntegration::DEH::Internal::CExtensionRegistration::Validate`
- `0x1800475e4`: `OSIntegration::DEH::Internal::CExtensionRegistration::Validate`
- `0x180047679`: `OSIntegration::DEH::Internal::CExtensionRegistration::Validate`
- `0x18004770d`: `OSIntegration::DEH::Internal::CExtensionRegistration::Validate`
- `0x18004776a`: `OSIntegration::DEH::Internal::CExtensionRegistration::Validate`
- `0x1800475a6`: `collectors->GetActivationCatalogCollector()->RetrieveOutOfProcessActivatableClassRegistration( activatableClassId, &found, &outOfProcessRegistration)`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall OSIntegration::DEH::Internal::CExtensionRegistration::Validate(
        OSIntegration::DEH::Internal::CExtensionRegistration *this,
        const struct OSIntegration::DEH::ICollectorPackageInformation *a2)
{
  __int64 v4; // rax
  const WCHAR *v5; // rsi
  unsigned __int64 v6; // rbx
  __int64 v7; // rsi
  __int64 v8; // rcx
  __int64 v9; // rbx
  int v10; // edi
  const WCHAR *v11; // rax
  __int64 v12; // rcx
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING, __int64 *); // rbx
  int v17; // eax
  PCWSTR v18; // rbx
  unsigned int v19; // eax
  int v20; // ecx
  int v21; // r8d
  PCWSTR v22; // rbx
  PCWSTR v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r9
  __int64 v27; // rdx
  __int64 v28; // rcx
  PCWSTR StringRawBuffer; // rbx
  unsigned int v30; // eax
  int v31; // ecx
  int v32; // r8d
  PCWSTR v33; // rbx
  PCWSTR v34; // rax
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // r9
  PCWSTR v38; // rbx
  unsigned int v39; // eax
  int v40; // ecx
  int v41; // r8d
  PCWSTR v42; // rbx
  PCWSTR v43; // rax
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // r9
  char *v47; // [rsp+28h] [rbp-58h]
  char *v48; // [rsp+28h] [rbp-58h]
  char *v49; // [rsp+28h] [rbp-58h]
  int v50; // [rsp+30h] [rbp-50h] BYREF
  HSTRING v51; // [rsp+38h] [rbp-48h] BYREF
  HSTRING v52; // [rsp+40h] [rbp-40h] BYREF
  __int64 v53; // [rsp+48h] [rbp-38h] BYREF
  __int64 v54; // [rsp+50h] [rbp-30h] BYREF
  HSTRING string; // [rsp+58h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+A8h] [rbp+28h]

  v4 = (**(__int64 (__fastcall ***)(const struct OSIntegration::DEH::ICollectorPackageInformation *))a2)(a2);
  v5 = (const WCHAR *)v4;
  v6 = -1;
  do
    ++v6;
  while ( *(_WORD *)(v4 + 2 * v6) );
  if ( v6 > 0xFFFFFFFF )
  {
    LODWORD(v6) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(v5, v6, &hstringHeader, &string);
  (*(void (__fastcall **)(OSIntegration::DEH::Internal::CExtensionRegistration *, HSTRING *))(*(_QWORD *)this + 48LL))(
    this,
    &v51);
  (*(void (__fastcall **)(OSIntegration::DEH::Internal::CExtensionRegistration *, HSTRING *))(*(_QWORD *)this + 56LL))(
    this,
    &v52);
  v7 = *(_QWORD *)((*(__int64 (__fastcall **)(const struct OSIntegration::DEH::ICollectorPackageInformation *))(*(_QWORD *)a2 + 72LL))(a2)
                 + 40);
  LOBYTE(v50) = 0;
  v8 = *(_QWORD *)(v7 + 48);
  if ( !v8 )
  {
    v9 = 0;
LABEL_7:
    v10 = 0;
    goto LABEL_8;
  }
  v14 = (*(__int64 (__fastcall **)(__int64, HSTRING, int *))(*(_QWORD *)v8 + 64LL))(v8, v51, &v50);
  v10 = v14;
  if ( v14 < 0 )
  {
    LODWORD(v47) = v14;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0xC3,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
      "OSIntegration::DEH::ActivationCatalogCollector::RetrieveOutOfProcessActivatableClassRegistration",
      "_outOfProcessActivatableClasses->HasKey(activatableClassId, found)",
      v47,
      v50);
  }
  else
  {
    v9 = 0;
    if ( !(_BYTE)v50 )
      goto LABEL_7;
    v53 = 0;
    v15 = *(_QWORD *)(v7 + 48);
    v16 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v15 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
    v17 = v16(v15, v51, &v53);
    v10 = v17;
    if ( v17 >= 0 )
    {
      v9 = (v53 - 16) & -(__int64)(v53 != 0);
      goto LABEL_7;
    }
    LODWORD(v47) = v17;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0xC7,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
      "OSIntegration::DEH::ActivationCatalogCollector::RetrieveOutOfProcessActivatableClassRegistration",
      "_outOfProcessActivatableClasses->Lookup(activatableClassId, &registration)",
      v47,
      v50);
    v28 = v53;
    if ( v53 )
    {
      v53 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    }
  }
  v9 = 0;
LABEL_8:
  if ( v10 < 0 )
  {
    LODWORD(v47) = v10;
    wil::details::in1diag5::_Log_Hr(
      retaddr,
      (void *)0x33A,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
      "OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Retrieve",
      "collectors->GetActivationCatalogCollector()->RetrieveOutOfProcessActivatableClassRegistration( activatableClassId,"
      " &found, &outOfProcessRegistration)",
      v47,
      v50);
  }
  else if ( (_BYTE)v50 )
  {
    v53 = v9;
    goto LABEL_11;
  }
  v53 = 0;
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  v9 = 0;
LABEL_11:
  if ( !v9 )
  {
    LODWORD(v47) = -2147024809;
    wil::details::in1diag5::_Log_Hr(
      retaddr,
      (void *)0x154,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\extensioncatalogcollector.cpp",
      "OSIntegration::DEH::Internal::CExtensionRegistration::Validate",
      "((HRESULT)0x80070057L)",
      v47,
      v50);
    if ( (byte_1802E21C5 & 0x20) != 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(v52, 0);
      v30 = (unsigned int)WindowsGetStringRawBuffer(v51, 0);
      McTemplateU0dzz_EventWriteTransfer(
        v31,
        (unsigned int)CollectorExtensionMissingACID,
        v32,
        v30,
        (__int64)StringRawBuffer);
    }
    v33 = WindowsGetStringRawBuffer(v52, 0);
    v34 = WindowsGetStringRawBuffer(v51, 0);
    details::appxLog<long,unsigned short const *,unsigned short const *>(
      v36,
      v35,
      (const struct _EVENT_DESCRIPTOR *)CollectorExtensionMissingACID,
      v37,
      v34,
      v33);
    LODWORD(v49) = -2147024809;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x158,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\extensioncatalogcollector.cpp",
      "OSIntegration::DEH::Internal::CExtensionRegistration::Validate",
      "E_INVALIDARG",
      v49,
      v50);
    goto LABEL_43;
  }
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v9 + 136LL))(v9, &v54);
  if ( !v54 )
  {
    LODWORD(v47) = -2147024809;
    wil::details::in1diag5::_Log_Hr(
      retaddr,
      (void *)0x163,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\extensioncatalogcollector.cpp",
      "OSIntegration::DEH::Internal::CExtensionRegistration::Validate",
      "((HRESULT)0x80070057L)",
      v47,
      v50);
    if ( (byte_1802E21C5 & 0x20) != 0 )
    {
      v38 = WindowsGetStringRawBuffer(v52, 0);
      v39 = (unsigned int)WindowsGetStringRawBuffer(v51, 0);
      McTemplateU0dzz_EventWriteTransfer(v40, (unsigned int)CollectorExtensionNeedOutOfProc, v41, v39, (__int64)v38);
    }
    v42 = WindowsGetStringRawBuffer(v52, 0);
    v43 = WindowsGetStringRawBuffer(v51, 0);
    details::appxLog<long,unsigned short const *,unsigned short const *>(
      v45,
      v44,
      (const struct _EVENT_DESCRIPTOR *)CollectorExtensionNeedOutOfProc,
      v46,
      v43,
      v42);
    v27 = 359;
    goto LABEL_42;
  }
  v11 = WindowsGetStringRawBuffer(v52, 0);
  if ( CompareStringOrdinal(v11, -1, L"Windows.RestrictedLaunch", -1, 1) != 2
    && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v54 + 152LL))(v54) != 2 )
  {
    LODWORD(v47) = -2147024809;
    wil::details::in1diag5::_Log_Hr(
      retaddr,
      (void *)0x173,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\extensioncatalogcollector.cpp",
      "OSIntegration::DEH::Internal::CExtensionRegistration::Validate",
      "((HRESULT)0x80070057L)",
      v47,
      v50);
    if ( (byte_1802E21C5 & 0x20) != 0 )
    {
      v18 = WindowsGetStringRawBuffer(v52, 0);
      v19 = (unsigned int)WindowsGetStringRawBuffer(v51, 0);
      McTemplateU0dzz_EventWriteTransfer(
        v20,
        (unsigned int)CollectorExtensionNeedActivateAsPackage,
        v21,
        v19,
        (__int64)v18);
    }
    v22 = WindowsGetStringRawBuffer(v52, 0);
    v23 = WindowsGetStringRawBuffer(v51, 0);
    details::appxLog<long,unsigned short const *,unsigned short const *>(
      v25,
      v24,
      (const struct _EVENT_DESCRIPTOR *)CollectorExtensionNeedActivateAsPackage,
      v26,
      v23,
      v22);
    v27 = 375;
LABEL_42:
    LODWORD(v48) = -2147024809;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\extensioncatalogcollector.cpp",
      "OSIntegration::DEH::Internal::CExtensionRegistration::Validate",
      "E_INVALIDARG",
      v48,
      v50);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
LABEL_43:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v52);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v51);
    return 2147942487LL;
  }
  v12 = v54;
  if ( v54 )
  {
    v54 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  if ( v52 )
    WindowsDeleteString(v52);
  if ( v51 )
    WindowsDeleteString(v51);
  return 0;
}

```

## disassembly

```asm
0x180047218  mov     [rsp-28h+arg_10], rbx
0x18004721d  push    rbp
0x18004721e  push    rsi
0x18004721f  push    rdi
0x180047220  push    r14
0x180047222  push    r15
0x180047224  mov     rbp, rsp
0x180047227  sub     rsp, 80h
0x18004722e  mov     rax, cs:__security_cookie
0x180047235  xor     rax, rsp
0x180047238  mov     [rbp+var_8], rax
0x18004723c  mov     rdi, rdx
0x18004723f  mov     r14, rcx
0x180047242  mov     rax, [rdx]
0x180047245  mov     rcx, rdx
0x180047248  mov     rax, [rax]
0x18004724b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047250  mov     rsi, rax
0x180047253  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180047257  xor     r15d, r15d
0x18004725a  inc     rbx
0x18004725d  cmp     [rax+rbx*2], r15w
0x180047262  jnz     short loc_18004725A
0x180047264  mov     eax, 0FFFFFFFFh
0x180047269  cmp     rbx, rax
0x18004726c  jbe     short loc_180047285
0x18004726e  mov     ebx, eax
0x180047270  xor     r9d, r9d; lpArguments
0x180047273  xor     r8d, r8d; nNumberOfArguments
0x180047276  lea     edx, [r9+1]; dwExceptionFlags
0x18004727a  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004727f  call    cs:__imp_RaiseException
0x180047285  lea     r9, [rbp+string]; string
0x180047289  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18004728d  mov     edx, ebx; length
0x18004728f  mov     rcx, rsi; sourceString
0x180047292  call    cs:__imp_WindowsCreateStringReference
0x180047298  mov     rax, [r14]
0x18004729b  lea     rdx, [rbp+var_48]
0x18004729f  mov     rcx, r14
0x1800472a2  mov     rax, [rax+30h]
0x1800472a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800472ab  nop
0x1800472ac  mov     rax, [r14]
0x1800472af  lea     rdx, [rbp+var_40]
0x1800472b3  mov     rcx, r14
0x1800472b6  mov     rax, [rax+38h]
0x1800472ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800472bf  nop
0x1800472c0  mov     rax, [rdi]
0x1800472c3  mov     rcx, rdi
0x1800472c6  mov     rax, [rax+48h]
0x1800472ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800472cf  mov     rsi, [rax+28h]
0x1800472d3  mov     byte ptr [rbp+var_50], r15b
0x1800472d7  mov     rcx, [rsi+30h]
0x1800472db  lea     r14, aOnecoreAdminAp_86; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800472e2  test    rcx, rcx
0x1800472e5  jnz     loc_1800473D7
0x1800472eb  mov     rbx, r15
0x1800472ee  mov     edi, r15d
0x1800472f1  mov     rcx, [rbp+28h]; this
0x1800472f5  test    edi, edi
0x1800472f7  js      loc_1800475A2
0x1800472fd  cmp     byte ptr [rbp+var_50], r15b
0x180047301  jz      loc_180047539
0x180047307  mov     [rbp+var_38], rbx
0x18004730b  test    rbx, rbx
0x18004730e  jz      loc_1800475CB
0x180047314  mov     rax, [rbx]
0x180047317  lea     rdx, [rbp+var_30]
0x18004731b  mov     rcx, rbx
0x18004731e  mov     rax, [rax+88h]
0x180047325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004732a  nop
0x18004732b  cmp     [rbp+var_30], r15
0x18004732f  jz      loc_180047751
0x180047335  xor     edx, edx; length
0x180047337  mov     rcx, [rbp+var_40]; string
0x18004733b  call    cs:__imp_WindowsGetStringRawBuffer
0x180047341  mov     [rsp+80h+bIgnoreCase], 1; bIgnoreCase
0x180047349  or      r9d, 0FFFFFFFFh; cchCount2
0x18004734d  lea     r8, aWindowsRestric_0; "Windows.RestrictedLaunch"
0x180047354  or      edx, r9d; cchCount1
0x180047357  mov     rcx, rax; lpString1
0x18004735a  call    cs:__imp_CompareStringOrdinal
0x180047360  cmp     eax, 2
0x180047363  jnz     loc_180047479
0x180047369  mov     rcx, [rbp+var_30]
0x18004736d  test    rcx, rcx
0x180047370  jz      short loc_180047383
0x180047372  mov     [rbp+var_30], r15
0x180047376  mov     rax, [rcx]
0x180047379  mov     rax, [rax+10h]
0x18004737d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047382  nop
0x180047383  mov     rax, [rbx]
0x180047386  mov     rcx, rbx
0x180047389  mov     rax, [rax+10h]
0x18004738d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047392  nop
0x180047393  mov     rcx, [rbp+var_40]; string
0x180047397  test    rcx, rcx
0x18004739a  jz      short loc_1800473A3
0x18004739c  call    cs:__imp_WindowsDeleteString
0x1800473a2  nop
0x1800473a3  mov     rcx, [rbp+var_48]; string
0x1800473a7  test    rcx, rcx
0x1800473aa  jz      short loc_1800473B2
0x1800473ac  call    cs:__imp_WindowsDeleteString
0x1800473b2  xor     eax, eax
0x1800473b4  mov     rcx, [rbp+var_8]
0x1800473b8  xor     rcx, rsp; StackCookie
0x1800473bb  call    __security_check_cookie
0x1800473c0  mov     rbx, [rsp+80h+arg_10]
0x1800473c8  add     rsp, 80h
0x1800473cf  pop     r15
0x1800473d1  pop     r14
0x1800473d3  pop     rdi
0x1800473d4  pop     rsi
0x1800473d5  pop     rbp
0x1800473d6  retn
0x1800473d7  mov     rax, [rcx]
0x1800473da  lea     r8, [rbp+var_50]
0x1800473de  mov     rdx, [rbp+var_48]
0x1800473e2  mov     rax, [rax+40h]
0x1800473e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800473eb  mov     edi, eax
0x1800473ed  test    eax, eax
0x1800473ef  js      short loc_180047449
0x1800473f1  mov     rbx, r15
0x1800473f4  cmp     byte ptr [rbp+var_50], r15b
0x1800473f8  jz      loc_1800472EE
0x1800473fe  mov     [rbp+var_38], r15
0x180047402  mov     rdi, [rsi+30h]
0x180047406  mov     rax, [rdi]
0x180047409  mov     rbx, [rax+30h]
0x18004740d  lea     rcx, [rbp+var_38]
0x180047411  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180047416  lea     r8, [rbp+var_38]
0x18004741a  mov     rdx, [rbp+var_48]
0x18004741e  mov     rcx, rdi
0x180047421  mov     rax, rbx
0x180047424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047429  mov     edi, eax
0x18004742b  test    eax, eax
0x18004742d  js      loc_18004755A
0x180047433  mov     rax, [rbp+var_38]
0x180047437  lea     rcx, [rax-10h]
0x18004743b  neg     rax
0x18004743e  sbb     rbx, rbx
0x180047441  and     rbx, rcx
0x180047444  jmp     loc_1800472EE
0x180047449  mov     rcx, [rbp+28h]; this
0x18004744d  mov     dword ptr [rsp+80h+var_58], eax; char *
0x180047451  lea     rax, aOutofprocessac_6; "_outOfProcessActivatableClasses->HasKey"...
0x180047458  mov     qword ptr [rsp+80h+bIgnoreCase], rax; char *
0x18004745d  lea     r9, aOsintegrationD_403; "OSIntegration::DEH::ActivationCatalogCo"...
0x180047464  mov     r8, r14; unsigned int
0x180047467  mov     edx, 0C3h; void *
0x18004746c  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180047471  mov     rbx, r15
0x180047474  jmp     loc_1800472F1
0x180047479  mov     rcx, [rbp+var_30]
0x18004747d  mov     rax, [rcx]
0x180047480  mov     rax, [rax+98h]
0x180047487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004748c  cmp     eax, 2
0x18004748f  jz      loc_180047369
0x180047495  mov     rcx, [rbp+28h]; this
0x180047499  mov     edi, 80070057h
0x18004749e  mov     dword ptr [rsp+80h+var_58], edi; char *
0x1800474a2  lea     rax, aHresult0x80070; "((HRESULT)0x80070057L)"
0x1800474a9  mov     qword ptr [rsp+80h+bIgnoreCase], rax; char *
0x1800474ae  lea     r9, aOsintegrationD_383; "OSIntegration::DEH::Internal::CExtensio"...
0x1800474b5  lea     r8, aOnecoreAdminAp_21; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800474bc  mov     edx, 173h; void *
0x1800474c1  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800474c6  test    cs:byte_1802E21C5, 20h
0x1800474cd  jz      short loc_1800474FE
0x1800474cf  xor     edx, edx; length
0x1800474d1  mov     rcx, [rbp+var_40]; string
0x1800474d5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800474db  mov     rbx, rax
0x1800474de  xor     edx, edx; length
0x1800474e0  mov     rcx, [rbp+var_48]; string
0x1800474e4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800474ea  mov     qword ptr [rsp+80h+bIgnoreCase], rbx
0x1800474ef  mov     r9, rax
0x1800474f2  lea     rdx, CollectorExtensionNeedActivateAsPackage
0x1800474f9  call    McTemplateU0dzz_EventWriteTransfer
0x1800474fe  xor     edx, edx; length
0x180047500  mov     rcx, [rbp+var_40]; string
0x180047504  call    cs:__imp_WindowsGetStringRawBuffer
0x18004750a  mov     rbx, rax
0x18004750d  xor     edx, edx; length
0x18004750f  mov     rcx, [rbp+var_48]; string
0x180047513  call    cs:__imp_WindowsGetStringRawBuffer
0x180047519  mov     [rsp+80h+var_58], rbx
0x18004751e  mov     qword ptr [rsp+80h+bIgnoreCase], rax
0x180047523  lea     r8, CollectorExtensionNeedActivateAsPackage
0x18004752a  call    ??$appxLog@JPEBGPEBG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@JPEBG2@Z; details::appxLog<long,ushort const *,ushort const *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,long,ushort const *,ushort const *)
0x18004752f  mov     edx, 177h
0x180047534  jmp     loc_1800476FB
0x180047539  mov     [rbp+var_38], r15
0x18004753d  test    rbx, rbx
0x180047540  jz      short loc_180047552
0x180047542  mov     rax, [rbx]
0x180047545  mov     rcx, rbx
0x180047548  mov     rax, [rax+10h]
0x18004754c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047551  nop
0x180047552  mov     rbx, r15
0x180047555  jmp     loc_18004730B
0x18004755a  mov     rcx, [rbp+28h]; this
0x18004755e  mov     dword ptr [rsp+80h+var_58], eax; char *
0x180047562  lea     rax, aOutofprocessac_0; "_outOfProcessActivatableClasses->Lookup"...
0x180047569  mov     qword ptr [rsp+80h+bIgnoreCase], rax; char *
0x18004756e  lea     r9, aOsintegrationD_403; "OSIntegration::DEH::ActivationCatalogCo"...
0x180047575  mov     r8, r14; unsigned int
0x180047578  mov     edx, 0C7h; void *
0x18004757d  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180047582  nop
0x180047583  mov     rcx, [rbp+var_38]
0x180047587  test    rcx, rcx
0x18004758a  jz      short loc_18004759D
0x18004758c  mov     [rbp+var_38], r15
0x180047590  mov     rax, [rcx]
0x180047593  mov     rax, [rax+10h]
0x180047597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004759c  nop
0x18004759d  jmp     loc_180047471
0x1800475a2  mov     dword ptr [rsp+80h+var_58], edi; char *
0x1800475a6  lea     rax, aCollectorsGeta_7; "collectors->GetActivationCatalogCollect"...
0x1800475ad  mov     qword ptr [rsp+80h+bIgnoreCase], rax; char *
0x1800475b2  lea     r9, aOsintegrationD_222; "OSIntegration::DEH::OutOfProcessActivat"...
0x1800475b9  mov     r8, r14; unsigned int
0x1800475bc  mov     edx, 33Ah; void *
0x1800475c1  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800475c6  jmp     loc_180047539
0x1800475cb  mov     rcx, [rbp+28h]; this
0x1800475cf  mov     edi, 80070057h
0x1800475d4  mov     dword ptr [rsp+80h+var_58], edi; char *
0x1800475d8  lea     rax, aHresult0x80070; "((HRESULT)0x80070057L)"
0x1800475df  mov     qword ptr [rsp+80h+bIgnoreCase], rax; char *
0x1800475e4  lea     r9, aOsintegrationD_383; "OSIntegration::DEH::Internal::CExtensio"...
0x1800475eb  lea     r8, aOnecoreAdminAp_21; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800475f2  mov     edx, 154h; void *
0x1800475f7  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800475fc  test    cs:byte_1802E21C5, 20h
0x180047603  jz      short loc_180047634
0x180047605  xor     edx, edx; length
0x180047607  mov     rcx, [rbp+var_40]; string
0x18004760b  call    cs:__imp_WindowsGetStringRawBuffer
0x180047611  mov     rbx, rax
0x180047614  xor     edx, edx; length
0x180047616  mov     rcx, [rbp+var_48]; string
0x18004761a  call    cs:__imp_WindowsGetStringRawBuffer
0x180047620  mov     qword ptr [rsp+80h+bIgnoreCase], rbx
0x180047625  mov     r9, rax
0x180047628  lea     rdx, CollectorExtensionMissingACID
0x18004762f  call    McTemplateU0dzz_EventWriteTransfer
0x180047634  xor     edx, edx; length
0x180047636  mov     rcx, [rbp+var_40]; string
0x18004763a  call    cs:__imp_WindowsGetStringRawBuffer
0x180047640  mov     rbx, rax
0x180047643  xor     edx, edx; length
0x180047645  mov     rcx, [rbp+var_48]; string
0x180047649  call    cs:__imp_WindowsGetStringRawBuffer
0x18004764f  mov     [rsp+80h+var_58], rbx
0x180047654  mov     qword ptr [rsp+80h+bIgnoreCase], rax
0x180047659  lea     r8, CollectorExtensionMissingACID
0x180047660  call    ??$appxLog@JPEBGPEBG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@JPEBG2@Z; details::appxLog<long,ushort const *,ushort const *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,long,ushort const *,ushort const *)
0x180047665  mov     rcx, [rbp+28h]; this
0x180047669  mov     dword ptr [rsp+80h+var_58], edi; char *
0x18004766d  lea     rax, aEInvalidarg; "E_INVALIDARG"
0x180047674  mov     qword ptr [rsp+80h+bIgnoreCase], rax; char *
0x180047679  lea     r9, aOsintegrationD_383; "OSIntegration::DEH::Internal::CExtensio"...
0x180047680  lea     r8, aOnecoreAdminAp_21; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180047687  mov     edx, 158h; void *
0x18004768c  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180047691  jmp     loc_18004772D
0x180047696  xor     edx, edx; length
0x180047698  mov     rcx, [rbp+var_40]; string
0x18004769c  call    cs:__imp_WindowsGetStringRawBuffer
0x1800476a2  mov     rbx, rax
0x1800476a5  xor     edx, edx; length
0x1800476a7  mov     rcx, [rbp+var_48]; string
0x1800476ab  call    cs:__imp_WindowsGetStringRawBuffer
0x1800476b1  mov     qword ptr [rsp+80h+bIgnoreCase], rbx
0x1800476b6  mov     r9, rax
0x1800476b9  lea     rdx, CollectorExtensionNeedOutOfProc
0x1800476c0  call    McTemplateU0dzz_EventWriteTransfer
0x1800476c5  xor     edx, edx; length
0x1800476c7  mov     rcx, [rbp+var_40]; string
0x1800476cb  call    cs:__imp_WindowsGetStringRawBuffer
0x1800476d1  mov     rbx, rax
0x1800476d4  xor     edx, edx; length
0x1800476d6  mov     rcx, [rbp+var_48]; string
0x1800476da  call    cs:__imp_WindowsGetStringRawBuffer
  ... truncated ...
```
