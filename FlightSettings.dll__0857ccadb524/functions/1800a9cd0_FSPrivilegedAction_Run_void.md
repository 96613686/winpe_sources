# FSPrivilegedAction::Run(void)

- ea: `0x1800a9cd0`
- end: `0x1800aa127`
- name: `?Run@FSPrivilegedAction@@UEAAJXZ`
- size: `1111`
- prototype: `__int64 __fastcall(FSPrivilegedAction *__hidden this)`
- caller_count: `0`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180004b80`
- `0x18000879c`
- `0x18000b19c`
- `0x18000cc6c`
- `0x18000cc8c`
- `0x180010e9c`
- `0x180013da0`
- `0x1800177bc`
- `0x180017870`
- `0x18001a090`
- `0x18001c6f4`
- `0x18002035c`
- `0x18008b214`
- `0x1800a9514`
- `0x1800a9710`
- `0x1800a97a0`
- `0x1800a9cd0`
- `0x1800aa130`
- `0x1800ace74`
- `0x1800c1d64`
- `0x1800c2bb0`
- `0x1800c2cc8`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800aa0b8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800aa0b8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a9e35`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a9e35`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800a9d1e`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800a9d1e`

## string_xrefs

- `0x1800a9d2f`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsprivilegedaction.cpp`
- `0x1800a9da2`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsprivilegedaction.cpp`
- `0x1800a9e53`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsprivilegedaction.cpp`
- `0x1800a9e81`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsprivilegedaction.cpp`
- `0x1800a9eeb`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsprivilegedaction.cpp`
- `0x1800a9f41`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsprivilegedaction.cpp`
- `0x1800a9f60`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsprivilegedaction.cpp`
- `0x1800aa065`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsprivilegedaction.cpp`
- `0x1800a9db4`: `Actions.json`
- `0x1800a9d73`: `PrivilegedActions.cab`
- `0x1800a9d7e`: `%sFlightingTemp\%s`
- `0x1800a9dbf`: `%sFlightingTemp\%s`
- `0x1800a9fe1`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsprivilegedactionsjsondescriptor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall FSPrivilegedAction::Run(FSPrivilegedAction *this)
{
  const char *v2; // r9
  unsigned __int64 v3; // rdx
  unsigned __int8 v4; // cl
  int LastError; // ebx
  __int64 v6; // rcx
  FlightSettingsAPITelemetryClass *v7; // rax
  LPCWSTR *v9; // r15
  __int64 v10; // rdx
  __int64 v11; // rsi
  HANDLE FileW; // rax
  const char *v13; // r9
  void *v14; // rbx
  int v15; // edi
  __int64 v16; // rdx
  int v17; // eax
  int v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, char *); // rbx
  FSPrivilegedAction *v24; // rcx
  const WCHAR *v25; // rbx
  const WCHAR *v26; // rcx
  unsigned __int64 v27; // rdx
  unsigned __int8 v28; // cl
  __int64 v29; // rcx
  FlightSettingsAPITelemetryClass *v30; // rax
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationDispositionb; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+40h] [rbp-C0h] BYREF
  void *v35; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE v36; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v37; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v38; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v39; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v40; // [rsp+70h] [rbp-90h] BYREF
  __int64 v41; // [rsp+78h] [rbp-88h]
  __int64 v42; // [rsp+80h] [rbp-80h]
  __int64 *v43; // [rsp+88h] [rbp-78h]
  int *v44; // [rsp+90h] [rbp-70h]
  char v45; // [rsp+98h] [rbp-68h]
  __int64 v46; // [rsp+A0h] [rbp-60h]
  char v47; // [rsp+A8h] [rbp-58h]
  _BYTE v48[528]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  v34 = 0;
  v44 = &v34;
  v45 = 1;
  if ( !(unsigned int)GetTempPath2W(260, v48) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x43,
                  (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsprivilegedaction.cpp",
                  v2);
LABEL_3:
    if ( v34 < 0 && FlightSettingsAPITelemetryClass::IsEnabled(v4, v3) )
    {
      v7 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                                v6,
                                                _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
      FlightSettingsAPITelemetryClass::PrivilegedActionFailed_(v7, v34);
    }
    return (unsigned int)LastError;
  }
  v9 = (LPCWSTR *)((char *)this + 72);
  LastError = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                (char *)this + 72,
                L"%sFlightingTemp\\%s",
                v48,
                L"PrivilegedActions.cab");
  if ( LastError < 0 )
  {
    v10 = 70;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsprivilegedaction.cpp",
      (const char *)(unsigned int)LastError,
      dwCreationDisposition);
    goto LABEL_3;
  }
  LastError = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                (char *)this + 120,
                L"%sFlightingTemp\\%s",
                v48,
                L"Actions.json");
  if ( LastError < 0 )
  {
    v10 = 71;
    goto LABEL_9;
  }
  LastError = CabUtils::CreateCabFile(*v9, *((LPCVOID *)this + 7), *((_DWORD *)this + 16));
  v34 = LastError;
  if ( LastError < 0 )
  {
    v10 = 74;
    goto LABEL_9;
  }
  v11 = *(_QWORD *)winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Internal::Flighting::FeatureConfiguration::SmartRolloutConfiguration,std::vector<winrt::Windows::Internal::Flighting::FeatureConfiguration::SmartRolloutConfiguration>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Internal::Flighting::FeatureConfiguration::SmartRolloutConfiguration,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::Flighting::FeatureConfiguration::SmartRolloutConfiguration>>::abi_guard::abi_guard(
                     &v38,
                     this);
  v46 = v11;
  v47 = 1;
  FileW = CreateFileW(*v9, 0x120089u, 1u, 0, 3u, 0x100u, 0);
  v14 = FileW;
  v36 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    v15 = CabUtils::VerifyCabIntegrity(FileW);
    v34 = v15;
    if ( v15 < 0 )
    {
      v16 = 96;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsprivilegedaction.cpp",
        (const char *)(unsigned int)v15,
        dwCreationDispositiona);
      goto LABEL_37;
    }
    v15 = CabUtils::VerifyCabAuthenticity(v14, *v9);
    v34 = v15;
    if ( v15 < 0 )
    {
      v16 = 99;
      goto LABEL_18;
    }
    v35 = (void *)-1LL;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v35,
      -1);
    v17 = FSPrivilegedAction::ExtractJsonFileFromCab((const unsigned __int16 **)this, &v35);
    v15 = v17;
    v34 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x67,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsprivilegedaction.cpp",
        (const char *)(unsigned int)v17,
        dwCreationDispositiona);
LABEL_36:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v35);
      goto LABEL_37;
    }
    v40 = 0;
    v41 = 0;
    v42 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v40);
    v41 = -1;
    v42 = -1;
    v18 = FlightSettingsAPICommon::ReadFileIntoString(v35, &v40);
    v15 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x96,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsprivilegedaction.cpp",
        (const char *)(unsigned int)v18,
        dwCreationDispositiona);
      v34 = v15;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6B,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsprivilegedaction.cpp",
        (const char *)(unsigned int)v15,
        dwCreationDispositionb);
LABEL_35:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v40);
      goto LABEL_36;
    }
    v34 = v18;
    v37 = 0;
    v39 = *((_QWORD *)this + 18);
    Microsoft::WRL::ComPtr<CFlightStore>::InternalAddRef(&v39);
    v43 = &v39;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v37);
    v38 = v39;
    Microsoft::WRL::ComPtr<CFlightStore>::InternalAddRef(&v38);
    v20 = FSPrivilegedActionsJsonDescriptor::s_CreateInstance(v19, &v37, v40, &v38);
    v15 = v20;
    if ( v20 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x37,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsprivilegedactionsjsondescriptor.cpp",
        (const char *)(unsigned int)v20,
        dwCreationDispositiona);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v39);
    v34 = v15;
    if ( v15 >= 0 )
    {
      v22 = v37;
      v23 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v37 + 24LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)this + 152);
      v15 = v23(v22, (char *)this + 152);
      v34 = v15;
      if ( v15 >= 0 )
      {
        v15 = FSPrivilegedAction::RunAllServiceDrivenActions(v24, *((struct IObjectArray **)this + 19));
        v34 = v15;
        if ( v15 >= 0 )
        {
LABEL_34:
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v37);
          goto LABEL_35;
        }
        v21 = 115;
      }
      else
      {
        v21 = 113;
      }
    }
    else
    {
      v21 = 111;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsprivilegedaction.cpp",
      (const char *)(unsigned int)v15,
      dwCreationDispositiona);
    goto LABEL_34;
  }
  v15 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0x5D,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsprivilegedaction.cpp",
          v13);
LABEL_37:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v36);
  v25 = &LocaleName;
  v26 = &LocaleName;
  if ( *(_QWORD *)(v11 + 96) )
    v26 = *(const WCHAR **)(v11 + 96);
  if ( GetFileAttributesW(v26) != -1 )
  {
    if ( *(_QWORD *)(v11 + 96) )
      v25 = *(const WCHAR **)(v11 + 96);
    wil::RemoveDirectoryRecursiveNoThrow(v25, 0, -1);
  }
  if ( v34 < 0 && FlightSettingsAPITelemetryClass::IsEnabled(v28, v27) )
  {
    v30 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                               v29,
                                               _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
    FlightSettingsAPITelemetryClass::PrivilegedActionFailed_(v30, v34);
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800a9cd0  push    rbp
0x1800a9cd2  push    rbx
0x1800a9cd3  push    rsi
0x1800a9cd4  push    rdi
0x1800a9cd5  push    r12
0x1800a9cd7  push    r13
0x1800a9cd9  push    r14
0x1800a9cdb  push    r15
0x1800a9cdd  lea     rbp, [rsp-1D8h]
0x1800a9ce5  sub     rsp, 2D8h
0x1800a9cec  mov     rax, cs:__security_cookie
0x1800a9cf3  xor     rax, rsp
0x1800a9cf6  mov     [rbp+210h+var_50], rax
0x1800a9cfd  mov     r14, rcx
0x1800a9d00  xor     r12d, r12d
0x1800a9d03  mov     [rsp+310h+var_2D0], r12d
0x1800a9d08  lea     rax, [rsp+310h+var_2D0]
0x1800a9d0d  mov     [rbp+210h+var_280], rax
0x1800a9d11  mov     [rbp+210h+var_278], 1
0x1800a9d15  lea     rdx, [rbp+210h+var_260]
0x1800a9d19  mov     ecx, 104h
0x1800a9d1e  call    cs:__imp_GetTempPath2W
0x1800a9d24  test    eax, eax
0x1800a9d26  jnz     short loc_1800A9D6F
0x1800a9d28  mov     rcx, [rbp+218h]; this
0x1800a9d2f  lea     r8, aOnecoreBaseFli_78; "onecore\\base\\flighting\\flightsetting"...
0x1800a9d36  lea     edx, [rax+43h]; void *
0x1800a9d39  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a9d3e  mov     ebx, eax
0x1800a9d40  cmp     [rsp+310h+var_2D0], r12d
0x1800a9d45  jge     short loc_1800A9D68
0x1800a9d47  call    ?IsEnabled@FlightSettingsAPITelemetryClass@@SA_NE_K@Z; FlightSettingsAPITelemetryClass::IsEnabled(uchar,unsigned __int64)
0x1800a9d4c  test    al, al
0x1800a9d4e  jz      short loc_1800A9D68
0x1800a9d50  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_144f2b6777ef104894e0ad961c1a2ea1_@@CA@XZ; _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_(void)
0x1800a9d57  call    ?get@?$static_lazy@VFlightSettingsAPITelemetryClass@@@details@wil@@QEAAPEAVFlightSettingsAPITelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(void (*)(void))
0x1800a9d5c  mov     edx, [rsp+310h+var_2D0]; int
0x1800a9d60  mov     rcx, rax; this
0x1800a9d63  call    ?PrivilegedActionFailed_@FlightSettingsAPITelemetryClass@@QEAAXJ@Z; FlightSettingsAPITelemetryClass::PrivilegedActionFailed_(long)
0x1800a9d68  mov     eax, ebx
0x1800a9d6a  jmp     loc_1800AA104
0x1800a9d6f  lea     r15, [r14+48h]
0x1800a9d73  lea     r9, WideCharStr; "PrivilegedActions.cab"
0x1800a9d7a  lea     r8, [rbp+210h+var_260]
0x1800a9d7e  lea     rdx, aSflightingtemp; "%sFlightingTemp\\%s"
0x1800a9d85  mov     rcx, r15
0x1800a9d88  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800a9d8d  mov     ebx, eax
0x1800a9d8f  test    eax, eax
0x1800a9d91  jns     short loc_1800A9DB0
0x1800a9d93  mov     edx, 46h ; 'F'; void *
0x1800a9d98  mov     rcx, [rbp+218h]; this
0x1800a9d9f  mov     r9d, ebx; char *
0x1800a9da2  lea     r8, aOnecoreBaseFli_78; "onecore\\base\\flighting\\flightsetting"...
0x1800a9da9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a9dae  jmp     short loc_1800A9D40
0x1800a9db0  lea     rcx, [r14+78h]
0x1800a9db4  lea     r9, aActionsJson; "Actions.json"
0x1800a9dbb  lea     r8, [rbp+210h+var_260]
0x1800a9dbf  lea     rdx, aSflightingtemp; "%sFlightingTemp\\%s"
0x1800a9dc6  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800a9dcb  mov     ebx, eax
0x1800a9dcd  test    eax, eax
0x1800a9dcf  jns     short loc_1800A9DD8
0x1800a9dd1  mov     edx, 47h ; 'G'
0x1800a9dd6  jmp     short loc_1800A9D98
0x1800a9dd8  mov     r8d, [r14+40h]; nNumberOfBytesToWrite
0x1800a9ddc  mov     rdx, [r14+38h]; lpBuffer
0x1800a9de0  mov     rcx, [r15]; lpFileName
0x1800a9de3  call    ?CreateCabFile@CabUtils@@SAJPEBGPEAEK@Z; CabUtils::CreateCabFile(ushort const *,uchar *,ulong)
0x1800a9de8  mov     ebx, eax
0x1800a9dea  mov     [rsp+310h+var_2D0], eax
0x1800a9dee  test    eax, eax
0x1800a9df0  jns     short loc_1800A9DF9
0x1800a9df2  mov     edx, 4Ah ; 'J'
0x1800a9df7  jmp     short loc_1800A9D98
0x1800a9df9  mov     rdx, r14
0x1800a9dfc  lea     rcx, [rsp+310h+var_2B0]
0x1800a9e01  call    ??0abi_guard@?$root_implements@Uiterator@?$iterable_base@U?$vector_impl@USmartRolloutConfiguration@FeatureConfiguration@Flighting@Internal@Windows@winrt@@V?$vector@USmartRolloutConfiguration@FeatureConfiguration@Flighting@Internal@Windows@winrt@@V?$allocator@USmartRolloutConfiguration@FeatureConfiguration@Flighting@Internal@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@6@@impl@winrt@@USmartRolloutConfiguration@FeatureConfiguration@Flighting@Internal@Windows@3@Ucollection_version@23@@winrt@@U?$IIterator@USmartRolloutConfiguration@FeatureConfiguration@Flighting@Internal@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@QEAA@AEAUiterator@?$iterable_base@U?$vector_impl@USmartRolloutConfiguration@FeatureConfiguration@Flighting@Internal@Windows@winrt@@V?$vector@USmartRolloutConfiguration@FeatureConfiguration@Flighting@Internal@Windows@winrt@@V?$allocator@USmartRolloutConfiguration@FeatureConfiguration@Flighting@Internal@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@6@@impl@winrt@@USmartRolloutConfiguration@FeatureConfiguration@Flighting@Internal@Windows@3@Ucollection_version@23@@3@@Z; winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Internal::Flighting::FeatureConfiguration::SmartRolloutConfiguration,std::vector<winrt::Windows::Internal::Flighting::FeatureConfiguration::SmartRolloutConfiguration>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Internal::Flighting::FeatureConfiguration::SmartRolloutConfiguration,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::Flighting::FeatureConfiguration::SmartRolloutConfiguration>>::abi_guard::abi_guard(winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Internal::Flighting::FeatureConfiguration::SmartRolloutConfiguration,std::vector<winrt::Windows::Internal::Flighting::FeatureConfiguration::SmartRolloutConfiguration>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Internal::Flighting::FeatureConfiguration::SmartRolloutConfiguration,winrt::impl::collection_version>::iterator &)
0x1800a9e06  mov     rsi, [rax]
0x1800a9e09  mov     [rbp+210h+var_270], rsi
0x1800a9e0d  mov     [rbp+210h+var_268], 1
0x1800a9e11  mov     [rsp+310h+hTemplateFile], r12; hTemplateFile
0x1800a9e16  mov     [rsp+310h+dwFlagsAndAttributes], 100h; dwFlagsAndAttributes
0x1800a9e1e  mov     [rsp+310h+dwCreationDisposition], 3; int
0x1800a9e26  xor     r9d, r9d; lpSecurityAttributes
0x1800a9e29  mov     edx, 120089h; dwDesiredAccess
0x1800a9e2e  lea     r8d, [r9+1]; dwShareMode
0x1800a9e32  mov     rcx, [r15]; lpFileName
0x1800a9e35  call    cs:__imp_CreateFileW
0x1800a9e3b  mov     rbx, rax
0x1800a9e3e  mov     [rsp+310h+var_2C0], rax
0x1800a9e43  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800a9e47  cmp     rax, r13
0x1800a9e4a  jnz     short loc_1800A9E6A
0x1800a9e4c  mov     rcx, [rbp+218h]; this
0x1800a9e53  lea     r8, aOnecoreBaseFli_78; "onecore\\base\\flighting\\flightsetting"...
0x1800a9e5a  lea     edx, [r13+5Eh]; void *
0x1800a9e5e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a9e63  mov     edi, eax
0x1800a9e65  jmp     loc_1800AA09A
0x1800a9e6a  mov     rcx, rbx; hFile
0x1800a9e6d  call    ?VerifyCabIntegrity@CabUtils@@SAJPEAX@Z; CabUtils::VerifyCabIntegrity(void *)
0x1800a9e72  mov     edi, eax
0x1800a9e74  mov     [rsp+310h+var_2D0], eax
0x1800a9e78  test    eax, eax
0x1800a9e7a  jns     short loc_1800A9E9C
0x1800a9e7c  mov     edx, 60h ; '`'; void *
0x1800a9e81  lea     r8, aOnecoreBaseFli_78; "onecore\\base\\flighting\\flightsetting"...
0x1800a9e88  mov     r9d, edi; char *
0x1800a9e8b  mov     rcx, [rbp+218h]; this
0x1800a9e92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a9e97  jmp     loc_1800AA09A
0x1800a9e9c  mov     rdx, [r15]; unsigned __int16 *
0x1800a9e9f  mov     rcx, rbx; void *
0x1800a9ea2  call    ?VerifyCabAuthenticity@CabUtils@@SAJPEAXPEBG@Z; CabUtils::VerifyCabAuthenticity(void *,ushort const *)
0x1800a9ea7  mov     edi, eax
0x1800a9ea9  mov     [rsp+310h+var_2D0], eax
0x1800a9ead  test    eax, eax
0x1800a9eaf  jns     short loc_1800A9EB8
0x1800a9eb1  mov     edx, 63h ; 'c'
0x1800a9eb6  jmp     short loc_1800A9E81
0x1800a9eb8  mov     [rsp+310h+var_2C8], r13
0x1800a9ebd  mov     rdx, r13
0x1800a9ec0  lea     rcx, [rsp+310h+var_2C8]
0x1800a9ec5  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800a9eca  lea     rdx, [rsp+310h+var_2C8]; void **
0x1800a9ecf  mov     rcx, r14; this
0x1800a9ed2  call    ?ExtractJsonFileFromCab@FSPrivilegedAction@@AEAAJPEAPEAX@Z; FSPrivilegedAction::ExtractJsonFileFromCab(void * *)
0x1800a9ed7  mov     edi, eax
0x1800a9ed9  mov     [rsp+310h+var_2D0], eax
0x1800a9edd  test    eax, eax
0x1800a9edf  jns     short loc_1800A9F01
0x1800a9ee1  mov     rcx, [rbp+218h]; this
0x1800a9ee8  mov     r9d, eax; char *
0x1800a9eeb  lea     r8, aOnecoreBaseFli_78; "onecore\\base\\flighting\\flightsetting"...
0x1800a9ef2  mov     edx, 67h ; 'g'; void *
0x1800a9ef7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a9efc  jmp     loc_1800AA08F
0x1800a9f01  mov     [rsp+310h+var_2A0], r12
0x1800a9f06  mov     [rsp+310h+var_298], r12
0x1800a9f0b  mov     [rbp+210h+var_290], r12
0x1800a9f0f  lea     rcx, [rsp+310h+var_2A0]
0x1800a9f14  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800a9f19  mov     [rsp+310h+var_298], r13
0x1800a9f1e  mov     [rbp+210h+var_290], r13
0x1800a9f22  lea     rdx, [rsp+310h+var_2A0]; unsigned __int16 **
0x1800a9f27  mov     rcx, [rsp+310h+var_2C8]; void *
0x1800a9f2c  call    ?ReadFileIntoString@FlightSettingsAPICommon@@SAJPEAXPEAPEAG@Z; FlightSettingsAPICommon::ReadFileIntoString(void *,ushort * *)
0x1800a9f31  mov     edi, eax
0x1800a9f33  test    eax, eax
0x1800a9f35  jns     short loc_1800A9F76
0x1800a9f37  mov     rcx, [rbp+218h]; this
0x1800a9f3e  mov     r9d, eax; char *
0x1800a9f41  lea     r8, aOnecoreBaseFli_78; "onecore\\base\\flighting\\flightsetting"...
0x1800a9f48  mov     edx, 96h; void *
0x1800a9f4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a9f52  mov     [rsp+310h+var_2D0], edi
0x1800a9f56  mov     rcx, [rbp+218h]; this
0x1800a9f5d  mov     r9d, edi; char *
0x1800a9f60  lea     r8, aOnecoreBaseFli_78; "onecore\\base\\flighting\\flightsetting"...
0x1800a9f67  mov     edx, 6Bh ; 'k'; void *
0x1800a9f6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a9f71  jmp     loc_1800AA084
0x1800a9f76  mov     [rsp+310h+var_2D0], edi
0x1800a9f7a  mov     [rsp+310h+var_2B8], r12
0x1800a9f7f  mov     rax, [r14+90h]
0x1800a9f86  mov     [rsp+310h+var_2A8], rax
0x1800a9f8b  lea     rcx, [rsp+310h+var_2A8]
0x1800a9f90  call    ?InternalAddRef@?$ComPtr@VCFlightStore@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<CFlightStore>::InternalAddRef(void)
0x1800a9f95  lea     rax, [rsp+310h+var_2A8]
0x1800a9f9a  mov     [rbp+210h+var_288], rax
0x1800a9f9e  lea     rcx, [rsp+310h+var_2B8]
0x1800a9fa3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a9fa8  nop
0x1800a9fa9  mov     rax, [rsp+310h+var_2A8]
0x1800a9fae  mov     [rsp+310h+var_2B0], rax
0x1800a9fb3  lea     rcx, [rsp+310h+var_2B0]
0x1800a9fb8  call    ?InternalAddRef@?$ComPtr@VCFlightStore@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<CFlightStore>::InternalAddRef(void)
0x1800a9fbd  lea     r9, [rsp+310h+var_2B0]
0x1800a9fc2  mov     r8, [rsp+310h+var_2A0]
0x1800a9fc7  lea     rdx, [rsp+310h+var_2B8]
0x1800a9fcc  call    ?s_CreateInstance@FSPrivilegedActionsJsonDescriptor@@SAJAEBU_GUID@@PEAPEAXPEBGV?$ComPtr@VFSActionContext@@@WRL@Microsoft@@@Z; FSPrivilegedActionsJsonDescriptor::s_CreateInstance(_GUID const &,void * *,ushort const *,Microsoft::WRL::ComPtr<FSActionContext>)
0x1800a9fd1  mov     edi, eax
0x1800a9fd3  test    eax, eax
0x1800a9fd5  jns     short loc_1800A9FF3
0x1800a9fd7  mov     rcx, [rbp+218h]; this
0x1800a9fde  mov     r9d, eax; char *
0x1800a9fe1  lea     r8, aOnecoreBaseFli; "onecore\\base\\flighting\\flightsetting"...
0x1800a9fe8  mov     edx, 37h ; '7'; void *
0x1800a9fed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a9ff2  nop
0x1800a9ff3  lea     rcx, [rsp+310h+var_2A8]
0x1800a9ff8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a9ffd  mov     [rsp+310h+var_2D0], edi
0x1800aa001  test    edi, edi
0x1800aa003  jns     short loc_1800AA00C
0x1800aa005  mov     edx, 6Fh ; 'o'
0x1800aa00a  jmp     short loc_1800AA062
0x1800aa00c  mov     rdi, [rsp+310h+var_2B8]
0x1800aa011  mov     rax, [rdi]
0x1800aa014  mov     rbx, [rax+18h]
0x1800aa018  lea     rcx, [r14+98h]
0x1800aa01f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800aa024  lea     rdx, [r14+98h]
0x1800aa02b  mov     rcx, rdi
0x1800aa02e  mov     rax, rbx
0x1800aa031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa036  mov     edi, eax
0x1800aa038  mov     [rsp+310h+var_2D0], eax
0x1800aa03c  test    eax, eax
0x1800aa03e  jns     short loc_1800AA047
0x1800aa040  mov     edx, 71h ; 'q'
0x1800aa045  jmp     short loc_1800AA062
0x1800aa047  mov     rdx, [r14+98h]; struct IObjectArray *
0x1800aa04e  call    ?RunAllServiceDrivenActions@FSPrivilegedAction@@AEAAJPEAUIObjectArray@@@Z; FSPrivilegedAction::RunAllServiceDrivenActions(IObjectArray *)
0x1800aa053  mov     edi, eax
0x1800aa055  mov     [rsp+310h+var_2D0], eax
0x1800aa059  test    eax, eax
0x1800aa05b  jns     short loc_1800AA079
0x1800aa05d  mov     edx, 73h ; 's'; void *
0x1800aa062  mov     r9d, edi; char *
0x1800aa065  lea     r8, aOnecoreBaseFli_78; "onecore\\base\\flighting\\flightsetting"...
0x1800aa06c  mov     rcx, [rbp+218h]; this
0x1800aa073  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aa078  nop
0x1800aa079  lea     rcx, [rsp+310h+var_2B8]
0x1800aa07e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800aa083  nop
0x1800aa084  lea     rcx, [rsp+310h+var_2A0]
0x1800aa089  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800aa08e  nop
0x1800aa08f  lea     rcx, [rsp+310h+var_2C8]
0x1800aa094  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800aa099  nop
0x1800aa09a  lea     rcx, [rsp+310h+var_2C0]
0x1800aa09f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800aa0a4  nop
0x1800aa0a5  lea     rbx, LocaleName
0x1800aa0ac  mov     rcx, rbx
0x1800aa0af  cmp     [rsi+60h], r12
0x1800aa0b3  cmovnz  rcx, [rsi+60h]; lpFileName
0x1800aa0b8  call    cs:__imp_GetFileAttributesW
0x1800aa0be  cmp     eax, 0FFFFFFFFh
0x1800aa0c1  jz      short loc_1800AA0DA
0x1800aa0c3  cmp     [rsi+60h], r12
0x1800aa0c7  cmovnz  rbx, [rsi+60h]
0x1800aa0cc  mov     r8, r13
0x1800aa0cf  xor     edx, edx
0x1800aa0d1  mov     rcx, rbx
0x1800aa0d4  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x1800aa0d9  nop
0x1800aa0da  cmp     [rsp+310h+var_2D0], r12d
0x1800aa0df  jge     short loc_1800AA102
0x1800aa0e1  call    ?IsEnabled@FlightSettingsAPITelemetryClass@@SA_NE_K@Z; FlightSettingsAPITelemetryClass::IsEnabled(uchar,unsigned __int64)
0x1800aa0e6  test    al, al
0x1800aa0e8  jz      short loc_1800AA102
0x1800aa0ea  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_144f2b6777ef104894e0ad961c1a2ea1_@@CA@XZ; _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_(void)
0x1800aa0f1  call    ?get@?$static_lazy@VFlightSettingsAPITelemetryClass@@@details@wil@@QEAAPEAVFlightSettingsAPITelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(void (*)(void))
0x1800aa0f6  mov     edx, [rsp+310h+var_2D0]; int
0x1800aa0fa  mov     rcx, rax; this
0x1800aa0fd  call    ?PrivilegedActionFailed_@FlightSettingsAPITelemetryClass@@QEAAXJ@Z; FlightSettingsAPITelemetryClass::PrivilegedActionFailed_(long)
0x1800aa102  mov     eax, edi
0x1800aa104  mov     rcx, [rbp+210h+var_50]
0x1800aa10b  xor     rcx, rsp; StackCookie
0x1800aa10e  call    __security_check_cookie
0x1800aa113  add     rsp, 2D8h
0x1800aa11a  pop     r15
0x1800aa11c  pop     r14
0x1800aa11e  pop     r13
0x1800aa120  pop     r12
0x1800aa122  pop     rdi
0x1800aa123  pop     rsi
0x1800aa124  pop     rbx
0x1800aa125  pop     rbp
0x1800aa126  retn
```
