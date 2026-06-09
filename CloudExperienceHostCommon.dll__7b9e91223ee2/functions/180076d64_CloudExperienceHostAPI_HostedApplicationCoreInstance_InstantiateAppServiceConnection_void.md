# CloudExperienceHostAPI::HostedApplicationCoreInstance::InstantiateAppServiceConnection(void)

- ea: `0x180076d64`
- end: `0x180077322`
- name: `?InstantiateAppServiceConnection@HostedApplicationCoreInstance@CloudExperienceHostAPI@@AEAAXXZ`
- size: `1470`
- prototype: `void __fastcall(CloudExperienceHostAPI::HostedApplicationCoreInstance *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180079bd0`

## callees

- `0x180003a70`
- `0x180005174`
- `0x18000fd28`
- `0x180010810`
- `0x180010c8c`
- `0x180016b04`
- `0x180016fd8`
- `0x180017b88`
- `0x18001a540`
- `0x18001cdeb`
- `0x180072a1c`
- `0x180075a9c`
- `0x1800762dc`
- `0x1800763c4`
- `0x180076d34`
- `0x180076d64`
- `0x180079194`
- `0x18007978c`
- `0x1800798e8`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076eb8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800771db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800771f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076eb8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800771db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800771f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076e68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076e88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076ee2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076e68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076e88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076ee2`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180076de2`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180076de2`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x180076f02`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x180076f02`

## string_xrefs

- `0x180077292`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x1800772e6`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180076dc0`: `Windows.ApplicationModel.AppService.AppServiceConnection`
- `0x180077175`: `AppServiceConnectionStatus: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
void __fastcall CloudExperienceHostAPI::HostedApplicationCoreInstance::InstantiateAppServiceConnection(
        CloudExperienceHostAPI::HostedApplicationCoreInstance *this)
{
  HSTRING *v2; // rsi
  __int64 v3; // rcx
  int v4; // ebx
  PCWSTR StringRawBuffer; // rbx
  CoreShellUtils *v6; // rcx
  PCWSTR v7; // rax
  int v8; // eax
  __int64 v9; // rdx
  const WCHAR *v10; // rax
  unsigned int v11; // eax
  __int64 v12; // rdx
  char v13; // r8
  __int64 (__fastcall **v14)(_QWORD *, GUID *, HSTRING *); // rax
  int v15; // eax
  __int64 v16; // rbx
  int v17; // eax
  __int64 v18; // rax
  char v19; // r8
  int v20; // eax
  HSTRING v21; // rbx
  __int64 (__fastcall *v22)(HSTRING, __int64 *); // rdi
  __int64 v23; // rcx
  int v24; // eax
  HSTRING v25; // rdi
  __int64 (__fastcall *v26)(HSTRING, PVOID); // rbx
  HSTRING_HEADER *v27; // rax
  int v28; // eax
  HSTRING v29; // rdi
  __int64 (__fastcall *v30)(HSTRING, _QWORD); // rbx
  __int64 v31; // rax
  int v32; // eax
  __int64 (__fastcall ***v33)(_QWORD, GUID *, _QWORD *); // rcx
  int v34; // eax
  int v35; // eax
  HSTRING v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  __int64 v39; // rbx
  int v40; // eax
  int packageRelativeApplicationId; // [rsp+20h] [rbp-E0h]
  unsigned int packageRelativeApplicationIda; // [rsp+20h] [rbp-E0h]
  char *v43; // [rsp+30h] [rbp-D0h]
  HSTRING v44; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v45; // [rsp+48h] [rbp-B8h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v47; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v48; // [rsp+60h] [rbp-A0h] BYREF
  UINT32 packageRelativeApplicationIdLength; // [rsp+68h] [rbp-98h] BYREF
  __int64 v50; // [rsp+70h] [rbp-90h] BYREF
  __int64 *v51; // [rsp+78h] [rbp-88h] BYREF
  _QWORD *v52; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v53; // [rsp+88h] [rbp-78h] BYREF
  HSTRING string; // [rsp+90h] [rbp-70h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp-68h] BYREF
  __int64 v56; // [rsp+B0h] [rbp-50h]
  HSTRING_HEADER v57; // [rsp+B8h] [rbp-48h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR v59[72]; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+148h]

  v2 = (HSTRING *)((char *)this + 128);
  v3 = *((_QWORD *)this + 16);
  *v2 = 0;
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v56 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.ApplicationModel.AppService.AppServiceConnection",
    0x39u,
    0x38u);
  *v2 = 0;
  v44 = 0;
  v4 = RoActivateInstance(v56, &v44);
  if ( v4 >= 0 )
  {
    if ( !memcmp_0(&GUID_9dd474a2_871f_4d52_89a9_9e090531bd27, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      *v2 = v44;
    }
    else
    {
      v4 = (**(__int64 (__fastcall ***)(HSTRING, GUID *, HSTRING *))v44)(
             v44,
             &GUID_9dd474a2_871f_4d52_89a9_9e090531bd27,
             v2);
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v44 + 16LL))(v44);
    }
  }
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5B,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\hostedapplicationcore.cpp",
      (const char *)(unsigned int)v4,
      packageRelativeApplicationId);
  CoreShellUtils::GetDefaultComposerClassId(&string);
  memset(&hstringHeader, 0, sizeof(hstringHeader));
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  CoreShellUtils::EnsureRegistryIsPopulated(v6);
  CoreShellUtils::GetComposerRegistryRootPathWithoutChecks(&v44);
  v7 = WindowsGetStringRawBuffer(v44, 0);
  v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
         &hstringHeader,
         L"%s\\%s",
         v7,
         StringRawBuffer);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x60,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\hostedapplicationcore.cpp",
      (const char *)(unsigned int)v8,
      packageRelativeApplicationId);
  WindowsDeleteString(v44);
  CoreShellUtils::GetComposerClassActivationValue(&v53, v9, hstringHeader.Reserved.Reserved1);
  packageFamilyNameLength = 65;
  packageRelativeApplicationIdLength = 66;
  v10 = WindowsGetStringRawBuffer(v53, 0);
  v11 = ParseApplicationUserModelId(
          v10,
          &packageFamilyNameLength,
          packageFamilyName,
          &packageRelativeApplicationIdLength,
          v59);
  if ( v11 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x69,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\hostedapplicationcore.cpp",
      (const char *)v11,
      packageRelativeApplicationIda);
  wil::GetActivationFactory<Windows::System::IUserStatics>((const WCHAR *)&v52, v12, v13);
  v48 = 0;
  v14 = (__int64 (__fastcall **)(_QWORD *, GUID *, HSTRING *))*v52;
  v48 = 0;
  v15 = ((__int64 (__fastcall *)(_QWORD *, __int64 *))v14[7])(v52, &v48);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6D,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\hostedapplicationcore.cpp",
      (const char *)(unsigned int)v15,
      packageRelativeApplicationIda);
  v51 = 0;
  v16 = v48;
  v17 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>>(v48);
  if ( v17 >= 0 )
    v17 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v16 + 64LL))(v16, &v51);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6F,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\hostedapplicationcore.cpp",
      (const char *)(unsigned int)v17,
      packageRelativeApplicationIda);
  v45 = 0;
  v18 = *v51;
  v45 = 0;
  if ( (*(int (__fastcall **)(__int64 *, _QWORD, __int64 *))(v18 + 48))(v51, 0, &v45) < 0 )
  {
    v44 = 0;
    v20 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, HSTRING *))*v52)(
            v52,
            &GUID_74a37e11_2eb5_4487_b0d5_2c6790e013e9,
            &v44);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v20,
        packageRelativeApplicationIda);
    v21 = v44;
    v22 = *(__int64 (__fastcall **)(HSTRING, __int64 *))(*(_QWORD *)v44 + 48LL);
    v23 = v45;
    v45 = 0;
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v24 = v22(v21, &v45);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x78,
        (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\hostedapplicationcore.cpp",
        (const char *)(unsigned int)v24,
        packageRelativeApplicationIda);
    wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v44);
  }
  v25 = *v2;
  v26 = *(__int64 (__fastcall **)(HSTRING, PVOID))(*(_QWORD *)*v2 + 56LL);
  v27 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v57, (const WCHAR **)off_1800F5148, v19);
  v28 = v26(v25, v27[1].Reserved.Reserved1);
  if ( v28 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7B,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\hostedapplicationcore.cpp",
      (const char *)(unsigned int)v28,
      packageRelativeApplicationIda);
  v29 = *v2;
  v30 = *(__int64 (__fastcall **)(HSTRING, _QWORD))(*(_QWORD *)*v2 + 72LL);
  v31 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v57, packageFamilyName);
  v32 = v30(v29, *(_QWORD *)(v31 + 24));
  if ( v32 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7C,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\hostedapplicationcore.cpp",
      (const char *)(unsigned int)v32,
      packageRelativeApplicationIda);
  v33 = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *))*v2;
  v50 = 0;
  v34 = (**v33)(v33, &GUID_8bdfcd5f_2302_4fbd_8061_52511c2f8bf9, &v50);
  if ( v34 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v34,
      packageRelativeApplicationIda);
  v35 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v50 + 64LL))(v50, v45);
  if ( v35 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7F,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\hostedapplicationcore.cpp",
      (const char *)(unsigned int)v35,
      packageRelativeApplicationIda);
  v47 = 0;
  v36 = *v2;
  v37 = *(_QWORD *)*v2;
  v47 = 0;
  v38 = (*(__int64 (__fastcall **)(HSTRING, __int64 *))(v37 + 80))(v36, &v47);
  if ( v38 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x82,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\hostedapplicationcore.cpp",
      (const char *)(unsigned int)v38,
      packageRelativeApplicationIda);
  v39 = v47;
  v40 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus>,Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>(v47);
  if ( v40 >= 0 )
    v40 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v39 + 64LL))(v39, (char *)this + 136);
  if ( v40 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x83,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\hostedapplicationcore.cpp",
      (const char *)(unsigned int)v40,
      packageRelativeApplicationIda);
  LODWORD(v43) = *((_DWORD *)this + 34);
  wil::details::in1diag3::Throw_HrIfFalseMsg(
    retaddr,
    (void *)0x85,
    (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\hostedapplicationcore.cpp",
    (const char *)0x80000013LL,
    (_DWORD)v43 == 0,
    (bool)"AppServiceConnectionStatus: %d",
    v43);
  wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v47);
  wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v50);
  wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v45);
  wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v51);
  wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v48);
  wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v52);
  WindowsDeleteString(v53);
  v53 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
  WindowsDeleteString(string);
}

```

## disassembly

```asm
0x180076d64  push    rbp
0x180076d66  push    rbx
0x180076d67  push    rsi
0x180076d68  push    rdi
0x180076d69  push    r14
0x180076d6b  push    r15
0x180076d6d  lea     rbp, [rsp-118h]
0x180076d75  sub     rsp, 218h
0x180076d7c  mov     rax, cs:__security_cookie
0x180076d83  xor     rax, rsp
0x180076d86  mov     [rbp+140h+var_40], rax
0x180076d8d  mov     r14, rcx
0x180076d90  xor     r15d, r15d
0x180076d93  lea     rsi, [rcx+80h]
0x180076d9a  mov     rcx, [rsi]
0x180076d9d  mov     [rsi], r15
0x180076da0  test    rcx, rcx
0x180076da3  jz      short loc_180076DB2
0x180076da5  mov     rax, [rcx]
0x180076da8  mov     rax, [rax+10h]
0x180076dac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076db1  nop
0x180076db2  mov     [rbp+140h+var_190], r15
0x180076db6  mov     r9d, 38h ; '8'; unsigned int
0x180076dbc  lea     r8d, [r9+1]; unsigned int
0x180076dc0  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_AppService_AppServiceConnection@@3QBGB; "Windows.ApplicationModel.AppService.App"...
0x180076dc7  lea     rcx, [rbp+140h+hstringHeader]; hstringHeader
0x180076dcb  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180076dd0  nop
0x180076dd1  mov     [rsi], r15
0x180076dd4  mov     [rsp+240h+var_200], r15
0x180076dd9  lea     rdx, [rsp+240h+var_200]
0x180076dde  mov     rcx, [rbp+140h+var_190]
0x180076de2  call    cs:__imp_RoActivateInstance
0x180076de8  mov     ebx, eax
0x180076dea  test    eax, eax
0x180076dec  js      short loc_180076E3D
0x180076dee  mov     r8d, 10h; Size
0x180076df4  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180076dfb  lea     rcx, _GUID_9dd474a2_871f_4d52_89a9_9e090531bd27; Buf1
0x180076e02  call    memcmp_0
0x180076e07  mov     rcx, [rsp+240h+var_200]
0x180076e0c  test    eax, eax
0x180076e0e  jnz     short loc_180076E15
0x180076e10  mov     [rsi], rcx
0x180076e13  jmp     short loc_180076E3D
0x180076e15  mov     rax, [rcx]
0x180076e18  mov     r8, rsi
0x180076e1b  lea     rdx, _GUID_9dd474a2_871f_4d52_89a9_9e090531bd27
0x180076e22  mov     rax, [rax]
0x180076e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076e2a  mov     ebx, eax
0x180076e2c  mov     rcx, [rsp+240h+var_200]
0x180076e31  mov     rax, [rcx]
0x180076e34  mov     rax, [rax+10h]
0x180076e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076e3d  mov     rcx, [rbp+148h]; this
0x180076e44  test    ebx, ebx
0x180076e46  js      loc_180077226
0x180076e4c  lea     rcx, [rbp+140h+string]
0x180076e50  call    ?GetDefaultComposerClassId@CoreShellUtils@@YA?AVHString@Wrappers@WRL@Microsoft@@XZ; CoreShellUtils::GetDefaultComposerClassId(void)
0x180076e55  nop
0x180076e56  mov     qword ptr [rbp+140h+hstringHeader.Reserved], r15
0x180076e5a  mov     qword ptr [rbp+140h+hstringHeader.Reserved+8], r15
0x180076e5e  mov     qword ptr [rbp+140h+hstringHeader.Reserved+10h], r15
0x180076e62  xor     edx, edx; length
0x180076e64  mov     rcx, [rbp+140h+string]; string
0x180076e68  call    cs:__imp_WindowsGetStringRawBuffer
0x180076e6e  mov     rbx, rax
0x180076e71  call    ?EnsureRegistryIsPopulated@CoreShellUtils@@YAXXZ; CoreShellUtils::EnsureRegistryIsPopulated(void)
0x180076e76  lea     rcx, [rsp+240h+var_200]
0x180076e7b  call    ?GetComposerRegistryRootPathWithoutChecks@CoreShellUtils@@YA?AVHString@Wrappers@WRL@Microsoft@@XZ; CoreShellUtils::GetComposerRegistryRootPathWithoutChecks(void)
0x180076e80  nop
0x180076e81  xor     edx, edx; length
0x180076e83  mov     rcx, [rsp+240h+var_200]; string
0x180076e88  call    cs:__imp_WindowsGetStringRawBuffer
0x180076e8e  mov     r9, rbx
0x180076e91  mov     r8, rax
0x180076e94  lea     rdx, aSS; "%s\\%s"
0x180076e9b  lea     rcx, [rbp+140h+hstringHeader]
0x180076e9f  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180076ea4  mov     rcx, [rbp+148h]; this
0x180076eab  test    eax, eax
0x180076ead  js      loc_18007723B
0x180076eb3  mov     rcx, [rsp+240h+var_200]; string
0x180076eb8  call    cs:__imp_WindowsDeleteString
0x180076ebe  mov     r8, qword ptr [rbp+140h+hstringHeader.Reserved]
0x180076ec2  lea     rcx, [rbp+140h+var_1B8]
0x180076ec6  call    ?GetComposerClassActivationValue@CoreShellUtils@@YA?AVHString@Wrappers@WRL@Microsoft@@PEAUHKEY__@@PEBG@Z; CoreShellUtils::GetComposerClassActivationValue(HKEY__ *,ushort const *)
0x180076ecb  nop
0x180076ecc  mov     [rsp+240h+packageFamilyNameLength], 41h ; 'A'
0x180076ed4  mov     [rsp+240h+packageRelativeApplicationIdLength], 42h ; 'B'
0x180076edc  xor     edx, edx; length
0x180076ede  mov     rcx, [rbp+140h+var_1B8]; string
0x180076ee2  call    cs:__imp_WindowsGetStringRawBuffer
0x180076ee8  mov     rcx, rax; applicationUserModelId
0x180076eeb  lea     rax, [rbp+140h+var_D0]
0x180076eef  mov     [rsp+240h+packageRelativeApplicationId], rax; int
0x180076ef4  lea     r9, [rsp+240h+packageRelativeApplicationIdLength]; packageRelativeApplicationIdLength
0x180076ef9  lea     r8, [rbp+140h+packageFamilyName]; packageFamilyName
0x180076efd  lea     rdx, [rsp+240h+packageFamilyNameLength]; packageFamilyNameLength
0x180076f02  call    cs:__imp_ParseApplicationUserModelId
0x180076f08  mov     rcx, [rbp+148h]; this
0x180076f0f  test    eax, eax
0x180076f11  jnz     loc_180077250
0x180076f17  lea     rcx, [rbp+140h+var_1C0]
0x180076f1b  call    ??$GetActivationFactory@UIUserStatics@System@Windows@@@wil@@YA?AV?$com_ptr_t@UIUserStatics@System@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::System::IUserStatics>(ushort const *)
0x180076f20  nop
0x180076f21  mov     [rsp+240h+var_1E0], r15
0x180076f26  mov     rcx, [rbp+140h+var_1C0]
0x180076f2a  mov     rax, [rcx]
0x180076f2d  mov     [rsp+240h+var_1E0], r15
0x180076f32  lea     rdx, [rsp+240h+var_1E0]
0x180076f37  mov     rax, [rax+38h]
0x180076f3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076f40  mov     rcx, [rbp+148h]; this
0x180076f47  test    eax, eax
0x180076f49  js      loc_180077265
0x180076f4f  mov     [rsp+240h+var_1C8], r15
0x180076f54  mov     rbx, [rsp+240h+var_1E0]
0x180076f59  mov     rcx, rbx
0x180076f5c  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *,tagCOWAIT_FLAGS,void *)
0x180076f61  test    eax, eax
0x180076f63  js      short loc_180076F79
0x180076f65  mov     rax, [rbx]
0x180076f68  lea     rdx, [rsp+240h+var_1C8]
0x180076f6d  mov     rcx, rbx
0x180076f70  mov     rax, [rax+40h]
0x180076f74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076f79  mov     rcx, [rbp+148h]; this
0x180076f80  test    eax, eax
0x180076f82  js      loc_18007727A
0x180076f88  mov     [rsp+240h+var_1F8], r15
0x180076f8d  mov     rcx, [rsp+240h+var_1C8]
0x180076f92  mov     rax, [rcx]
0x180076f95  mov     [rsp+240h+var_1F8], r15
0x180076f9a  lea     r8, [rsp+240h+var_1F8]
0x180076f9f  xor     edx, edx
0x180076fa1  mov     rax, [rax+30h]
0x180076fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076faa  test    eax, eax
0x180076fac  jns     loc_180077032
0x180076fb2  mov     rcx, [rbp+140h+var_1C0]
0x180076fb6  mov     [rsp+240h+var_200], r15
0x180076fbb  mov     rax, [rcx]
0x180076fbe  lea     r8, [rsp+240h+var_200]
0x180076fc3  lea     rdx, _GUID_74a37e11_2eb5_4487_b0d5_2c6790e013e9
0x180076fca  mov     rax, [rax]
0x180076fcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076fd2  mov     rcx, [rbp+148h]; this
0x180076fd9  test    eax, eax
0x180076fdb  js      loc_18007728F
0x180076fe1  mov     rbx, [rsp+240h+var_200]
0x180076fe6  mov     rax, [rbx]
0x180076fe9  mov     rdi, [rax+30h]
0x180076fed  mov     rcx, [rsp+240h+var_1F8]
0x180076ff2  mov     [rsp+240h+var_1F8], r15
0x180076ff7  test    rcx, rcx
0x180076ffa  jz      short loc_180077009
0x180076ffc  mov     rdx, [rcx]
0x180076fff  mov     rax, [rdx+10h]
0x180077003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077008  nop
0x180077009  lea     rdx, [rsp+240h+var_1F8]
0x18007700e  mov     rcx, rbx
0x180077011  mov     rax, rdi
0x180077014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077019  mov     rcx, [rbp+148h]; this
0x180077020  test    eax, eax
0x180077022  js      loc_1800772A4
0x180077028  lea     rcx, [rsp+240h+var_200]
0x18007702d  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x180077032  mov     rdi, [rsi]
0x180077035  mov     rax, [rdi]
0x180077038  mov     rbx, [rax+38h]
0x18007703c  lea     rdx, off_1800F5148; "com.microsoft.launchoobeapp"
0x180077043  lea     rcx, [rbp+140h+var_188]
0x180077047  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18007704c  nop
0x18007704d  mov     rdx, [rax+18h]
0x180077051  mov     rcx, rdi
0x180077054  mov     rax, rbx
0x180077057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007705c  mov     rcx, [rbp+148h]; this
0x180077063  test    eax, eax
0x180077065  js      loc_1800772B9
0x18007706b  mov     rdi, [rsi]
0x18007706e  mov     rax, [rdi]
0x180077071  mov     rbx, [rax+48h]
0x180077075  lea     rdx, [rbp+140h+packageFamilyName]; sourceString
0x180077079  lea     rcx, [rbp+140h+var_188]; hstringHeader
0x18007707d  call    ??$?0$0EB@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0EB@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[65])
0x180077082  nop
0x180077083  mov     rdx, [rax+18h]
0x180077087  mov     rcx, rdi
0x18007708a  mov     rax, rbx
0x18007708d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077092  mov     rcx, [rbp+148h]; this
0x180077099  test    eax, eax
0x18007709b  js      loc_1800772CE
0x1800770a1  mov     rcx, [rsi]
0x1800770a4  mov     [rsp+240h+var_1D0], r15
0x1800770a9  mov     rax, [rcx]
0x1800770ac  lea     r8, [rsp+240h+var_1D0]
0x1800770b1  lea     rdx, _GUID_8bdfcd5f_2302_4fbd_8061_52511c2f8bf9
0x1800770b8  mov     rax, [rax]
0x1800770bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800770c0  mov     rcx, [rbp+148h]; this
0x1800770c7  test    eax, eax
0x1800770c9  js      loc_1800772E3
0x1800770cf  mov     rcx, [rsp+240h+var_1D0]
0x1800770d4  mov     rax, [rcx]
0x1800770d7  mov     rdx, [rsp+240h+var_1F8]
0x1800770dc  mov     rax, [rax+40h]
0x1800770e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800770e5  mov     rcx, [rbp+148h]; this
0x1800770ec  test    eax, eax
0x1800770ee  js      loc_1800772F8
0x1800770f4  mov     [rsp+240h+var_1E8], r15
0x1800770f9  mov     rcx, [rsi]
0x1800770fc  mov     rax, [rcx]
0x1800770ff  mov     [rsp+240h+var_1E8], r15
0x180077104  lea     rdx, [rsp+240h+var_1E8]
0x180077109  mov     rax, [rax+50h]
0x18007710d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077112  mov     rcx, [rbp+148h]; this
0x180077119  test    eax, eax
0x18007711b  js      loc_18007730D
0x180077121  mov     rbx, [rsp+240h+var_1E8]
0x180077126  mov     rcx, rbx
0x180077129  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *,tagCOWAIT_FLAGS,void *)
0x18007712e  test    eax, eax
0x180077130  js      short loc_180077148
0x180077132  mov     rax, [rbx]
0x180077135  lea     rdx, [r14+88h]
0x18007713c  mov     rcx, rbx
0x18007713f  mov     rax, [rax+40h]
0x180077143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077148  mov     rcx, [rbp+148h]; this
0x18007714f  lea     r8, aOnecoreuapShel_24; "onecoreuap\\shell\\cloudexperiencehost"...
0x180077156  test    eax, eax
0x180077158  js      loc_180077218
0x18007715e  mov     eax, [r14+88h]
0x180077165  test    eax, eax
0x180077167  setz    dl
0x18007716a  mov     rcx, [rbp+148h]; this
0x180077171  mov     dword ptr [rsp+240h+var_210], eax; char *
0x180077175  lea     rax, aAppserviceconn; "AppServiceConnectionStatus: %d"
0x18007717c  mov     qword ptr [rsp+240h+var_218], rax; bool
0x180077181  mov     byte ptr [rsp+240h+packageRelativeApplicationId], dl; char
0x180077185  mov     r9d, 80000013h; char *
0x18007718b  mov     edx, 85h; void *
0x180077190  call    ?Throw_HrIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfFalseMsg(void *,uint,char const *,long,bool,char const *,...)
0x180077195  nop
0x180077196  lea     rcx, [rsp+240h+var_1E8]
0x18007719b  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x1800771a0  nop
0x1800771a1  lea     rcx, [rsp+240h+var_1D0]
0x1800771a6  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x1800771ab  nop
0x1800771ac  lea     rcx, [rsp+240h+var_1F8]
0x1800771b1  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x1800771b6  nop
0x1800771b7  lea     rcx, [rsp+240h+var_1C8]
0x1800771bc  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x1800771c1  nop
0x1800771c2  lea     rcx, [rsp+240h+var_1E0]
0x1800771c7  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x1800771cc  nop
0x1800771cd  lea     rcx, [rbp+140h+var_1C0]
0x1800771d1  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x1800771d6  nop
0x1800771d7  mov     rcx, [rbp+140h+var_1B8]; string
0x1800771db  call    cs:__imp_WindowsDeleteString
0x1800771e1  mov     [rbp+140h+var_1B8], r15
0x1800771e5  lea     rcx, [rbp+140h+hstringHeader]
0x1800771e9  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800771ee  nop
0x1800771ef  mov     rcx, [rbp+140h+string]; string
0x1800771f3  call    cs:__imp_WindowsDeleteString
0x1800771f9  mov     rcx, [rbp+140h+var_40]
0x180077200  xor     rcx, rsp; StackCookie
0x180077203  call    __security_check_cookie
0x180077208  add     rsp, 218h
0x18007720f  pop     r15
0x180077211  pop     r14
0x180077213  pop     rdi
0x180077214  pop     rsi
0x180077215  pop     rbx
0x180077216  pop     rbp
0x180077217  retn
0x180077218  mov     r9d, eax; char *
0x18007721b  mov     edx, 83h; void *
0x180077220  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180077226  mov     r9d, ebx; char *
0x180077229  lea     r8, aOnecoreuapShel_24; "onecoreuap\\shell\\cloudexperiencehost"...
0x180077230  mov     edx, 5Bh ; '['; void *
0x180077235  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007723b  mov     r9d, eax; char *
0x18007723e  lea     r8, aOnecoreuapShel_24; "onecoreuap\\shell\\cloudexperiencehost"...
  ... truncated ...
```
