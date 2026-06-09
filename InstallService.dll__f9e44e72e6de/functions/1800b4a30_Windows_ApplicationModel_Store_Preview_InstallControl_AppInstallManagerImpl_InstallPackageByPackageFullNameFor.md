# Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::InstallPackageByPackageFullNameForUserAsync(Windows::System::IUser *,HSTRING__ *,HSTRING__ *,HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallOptions *,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> * *)

- ea: `0x1800b4a30`
- end: `0x1800b5057`
- name: `?InstallPackageByPackageFullNameForUserAsync@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@UEAAJPEAUIUser@System@6@PEAUHSTRING__@@11PEAUIAppInstallOptions@23456@PEAPEAU?$IAsyncOperation@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@6@@Z`
- size: `1575`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x180010b74`
- `0x18001c414`
- `0x180023a9c`
- `0x18002548c`
- `0x180028cd4`
- `0x18002c310`
- `0x18003b08c`
- `0x18006d484`
- `0x18006e510`
- `0x180072420`
- `0x18007bff0`
- `0x18008f620`
- `0x180091ed4`
- `0x180095cc8`
- `0x1800b4a30`
- `0x1800c83a8`
- `0x1801473f4`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b4b7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b4bb4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b4fb8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b4fce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b5007`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b501a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b4b7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b4bb4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b4fb8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b4fce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b5007`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b501a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b4c44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b4c57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b4d89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b4f38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b4f4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b4c44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b4c57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b4d89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b4f38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b4f4b`

## string_xrefs

- `0x1800b4bea`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800b4cae`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800b4f9f`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800b4c8d`: `request: packageFullName = %s, clientId = %s, allowForcedAppRestart = %s, forceUseOfNonRemovableStorage = %s, repair = %s, CV = %hs`
- `0x1800b4ca1`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::InstallPackageByPackageFullNameForUserAsync`
- `0x1800b4f92`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::InstallPackageByPackageFullNameForUserAsync`
- `0x1800b4bca`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::InstallPackageByPackageFullNameForUserAsync`
- `0x1800b4f81`: `initialization failed:: packageFullName = %s, clientId = %s, allowForcedAppRestart = %s, forceUseOfNonRemovableStorage = %s, repair = %s, CV = %hs`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::InstallPackageByPackageFullNameForUserAsync(
        __int64 a1,
        __int64 a2,
        char *a3,
        HSTRING a4,
        WindowsUpdate::CommonTelemetry *a5,
        Utils *a6,
        _QWORD *a7)
{
  int v9; // r12d
  __int64 (__fastcall *v10)(Utils *, __int64 *); // rbx
  __int64 v11; // rbx
  __int64 (__fastcall *v12)(__int64, HSTRING *); // rdi
  int CallingProcessAndFunction; // eax
  unsigned int v14; // ebx
  const unsigned __int16 *v15; // r14
  const unsigned __int16 *v16; // rsi
  const unsigned __int16 *v17; // rdi
  PCWSTR StringRawBuffer; // rbx
  PCWSTR v19; // rax
  Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl *v20; // rcx
  HSTRING v21; // rdi
  void *CurrentActiveUserAccessToken; // rax
  HSTRING v23; // rax
  struct Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallOptions *v24; // rdx
  unsigned __int8 v25; // r9
  wchar_t *v26; // rax
  const unsigned __int16 *v27; // rdx
  bool v28; // r8
  int v29; // ebx
  __int64 v30; // rax
  __int64 v31; // r8
  const char *v32; // r9
  const unsigned __int16 *v33; // r14
  HSTRING v34; // rcx
  const unsigned __int16 *v35; // rsi
  const unsigned __int16 *v36; // rdi
  PCWSTR v37; // rbx
  PCWSTR v38; // rax
  unsigned int v39; // edx
  int v40; // [rsp+20h] [rbp-1F8h]
  char v41; // [rsp+70h] [rbp-1A8h] BYREF
  char v42; // [rsp+71h] [rbp-1A7h] BYREF
  char v43; // [rsp+72h] [rbp-1A6h] BYREF
  bool v44[5]; // [rsp+73h] [rbp-1A5h] BYREF
  HSTRING string; // [rsp+78h] [rbp-1A0h] BYREF
  HSTRING v46; // [rsp+80h] [rbp-198h] BYREF
  HSTRING newString; // [rsp+88h] [rbp-190h] BYREF
  HSTRING v48; // [rsp+90h] [rbp-188h] BYREF
  HSTRING v49; // [rsp+98h] [rbp-180h] BYREF
  HSTRING v50; // [rsp+A0h] [rbp-178h] BYREF
  __int64 v51; // [rsp+A8h] [rbp-170h] BYREF
  __int64 v52; // [rsp+B0h] [rbp-168h] BYREF
  HSTRING v53; // [rsp+B8h] [rbp-160h] BYREF
  __int64 v54; // [rsp+C0h] [rbp-158h] BYREF
  _QWORD v55[2]; // [rsp+C8h] [rbp-150h] BYREF
  _QWORD *v56; // [rsp+D8h] [rbp-140h]
  _BYTE v57[96]; // [rsp+E0h] [rbp-138h] BYREF
  HSTRING__ v58; // [rsp+140h] [rbp-D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+0h]

  v53 = (HSTRING)a3;
  v51 = a2;
  v55[0] = a1;
  v49 = (HSTRING)a3;
  v56 = a7;
  *a7 = 0;
  if ( !a3 )
    return 2147942487LL;
  v43 = 1;
  v42 = 0;
  v41 = 0;
  v52 = 0;
  string = 0;
  v9 = 0;
  if ( a6 )
  {
    v9 = (*(__int64 (__fastcall **)(Utils *, char *))(*(_QWORD *)a6 + 80LL))(a6, &v43);
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(Utils *, char *))(*(_QWORD *)a6 + 64LL))(a6, &v42);
      if ( v9 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(Utils *, char *))(*(_QWORD *)a6 + 96LL))(a6, &v41);
        if ( v9 >= 0 )
        {
          v10 = *(__int64 (__fastcall **)(Utils *, __int64 *))(*(_QWORD *)a6 + 112LL);
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v52);
          v9 = v10(a6, &v52);
          if ( v9 >= 0 )
          {
            v11 = v52;
            if ( v52 )
            {
              v12 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v52 + 72LL);
              WindowsDeleteString(string);
              string = 0;
              v9 = v12(v11, &string);
            }
          }
        }
      }
    }
  }
  WindowsUpdate::CommonTelemetry::GenerateIfMissingCorrelationVector(a5, &v58, a3);
  v48 = 0;
  WindowsDeleteString(0);
  v48 = 0;
  CallingProcessAndFunction = GetCallingProcessAndFunction(
                                a4,
                                L"Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::Instal"
                                 "lPackageByPackageFullNameForUserAsync",
                                &v48);
  v14 = CallingProcessAndFunction;
  if ( CallingProcessAndFunction >= 0 )
  {
    v50 = v48;
    v15 = L"true";
    if ( !v41 )
      v15 = L"false";
    v16 = L"true";
    if ( !v42 )
      v16 = L"false";
    v17 = L"true";
    if ( !v43 )
      v17 = L"false";
    StringRawBuffer = WindowsGetStringRawBuffer(v48, 0);
    v19 = WindowsGetStringRawBuffer(v53, 0);
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      0x1A33u,
      "Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::InstallPackageByPackageFullNameForUserAsync",
      -1,
      L"request: packageFullName = %s, clientId = %s, allowForcedAppRestart = %s, forceUseOfNonRemovableStorage = %s, repa"
       "ir = %s, CV = %hs",
      0,
      0,
      v19,
      StringRawBuffer,
      v17,
      v16,
      v15,
      &v58);
    v54 = 0;
    v21 = (HSTRING)v51;
    if ( !v51 )
    {
      CurrentActiveUserAccessToken = Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetCurrentActiveUserAccessToken(v20);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &v54,
        CurrentActiveUserAccessToken);
    }
    v23 = (HSTRING)TraceLoggingCorrelationVector::Extend((const char *)&v58, 0);
    v53 = v23;
    if ( v9 >= 0 )
      v9 = v23 == 0 ? 0x8007000E : 0;
    newString = 0;
    if ( v9 >= 0 )
      v9 = Microsoft::WRL::Wrappers::HString::Set(&newString, &v50);
    v46 = 0;
    if ( v9 < 0 || (v9 = Microsoft::WRL::Wrappers::HString::Set(&v46, &v49), v9 < 0) )
    {
      v33 = L"true";
    }
    else
    {
      try
      {
        LOBYTE(v24) = 1;
        LODWORD(v49) = Utils::GetInstallFlags(a6, v24, 0, v25);
        v26 = (wchar_t *)WindowsGetStringRawBuffer(v48, 0);
        LOBYTE(v27) = 1;
        v44[0] = Utils::IsCallerInteractive(v26, v27, v28);
        v29 = LODWORD(v55[0]) - 104;
        v51 = v55[0] - 104LL;
        Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(&v51);
        v50 = v21;
        Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(&v50);
        v30 = lambda_31d51c1d296f7628d8b1582d7f634666_::_lambda_31d51c1d296f7628d8b1582d7f634666_(
                (unsigned int)v57,
                v29,
                (unsigned int)&v51,
                (unsigned int)&v50,
                (__int64)&v41,
                (__int64)&v42,
                (__int64)v44,
                (__int64)&v54,
                (__int64)&v43,
                (__int64)string,
                (__int64)newString,
                (__int64)v46,
                (__int64)&v53,
                (__int64)&v49);
        LODWORD(v55[0]) = 0;
        *(_QWORD *)((char *)v55 + 4) = 128;
        v9 = Windows::Internal::MakeAsyncOperation_Windows::Internal::CMarshaledInterfaceResult_Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem__Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem___Windows::Internal::ComTaskPoolHandler__lambda_31d51c1d296f7628d8b1582d7f634666___(
               v55,
               v56,
               v31,
               v30);
        lambda_31d51c1d296f7628d8b1582d7f634666_::__lambda_31d51c1d296f7628d8b1582d7f634666_(v57);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v50);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v51);
      }
      catch ( ... )
      {
        LODWORD(v49) = wil::details::in1diag3::Log_CaughtException(
                         retaddr,
                         (void *)0x1AD9,
                         (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
                         v32);
        v9 = (int)v49;
      }
      v33 = L"true";
      if ( v9 >= 0 )
      {
        newString = 0;
        v34 = 0;
        v46 = 0;
        string = 0;
LABEL_37:
        WindowsDeleteString(v34);
        v46 = 0;
        WindowsDeleteString(newString);
        newString = 0;
        if ( v53 )
          TraceLoggingCorrelationVector::`scalar deleting destructor'((TraceLoggingCorrelationVector *)v53, v39);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v54);
        v14 = v9;
        goto LABEL_40;
      }
    }
    v35 = L"true";
    if ( !v41 )
      v35 = L"false";
    v36 = L"true";
    if ( !v42 )
      v36 = L"false";
    if ( !v43 )
      v33 = L"false";
    v37 = WindowsGetStringRawBuffer(newString, 0);
    v38 = WindowsGetStringRawBuffer(v46, 0);
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      0x1AEBu,
      "Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::InstallPackageByPackageFullNameForUserAsync",
      v9,
      L"initialization failed:: packageFullName = %s, clientId = %s, allowForcedAppRestart = %s, forceUseOfNonRemovableSto"
       "rage = %s, repair = %s, CV = %hs",
      0,
      0,
      v38,
      v37,
      v33,
      v36,
      v35,
      &v58);
    v34 = v46;
    goto LABEL_37;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1A29,
    (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
    (const char *)(unsigned int)CallingProcessAndFunction,
    v40);
LABEL_40:
  WindowsDeleteString(v48);
  v48 = 0;
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v52);
  return v14;
}

```

## disassembly

```asm
0x1800b4a30  push    rbx
0x1800b4a32  push    rsi
0x1800b4a33  push    rdi
0x1800b4a34  push    r12
0x1800b4a36  push    r13
0x1800b4a38  push    r14
0x1800b4a3a  push    r15
0x1800b4a3c  sub     rsp, 1E0h
0x1800b4a43  mov     rax, cs:__security_cookie
0x1800b4a4a  xor     rax, rsp
0x1800b4a4d  mov     [rsp+218h+var_48], rax
0x1800b4a55  mov     rsi, r9
0x1800b4a58  mov     rax, r8
0x1800b4a5b  mov     [rsp+218h+var_160], rax
0x1800b4a63  mov     [rsp+218h+var_170], rdx
0x1800b4a6b  mov     qword ptr [rsp+218h+var_150], rcx
0x1800b4a73  mov     [rsp+218h+var_180], rax
0x1800b4a7b  mov     r14, [rsp+218h+arg_20]
0x1800b4a83  mov     r13, [rsp+218h+arg_28]
0x1800b4a8b  mov     rcx, [rsp+218h+arg_30]
0x1800b4a93  mov     [rsp+218h+var_140], rcx
0x1800b4a9b  xor     r15d, r15d
0x1800b4a9e  mov     [rcx], r15
0x1800b4aa1  test    r8, r8
0x1800b4aa4  jnz     short loc_1800B4AB0
0x1800b4aa6  mov     eax, 80070057h
0x1800b4aab  jmp     loc_1800B5034
0x1800b4ab0  mov     [rsp+218h+var_1A6], 1
0x1800b4ab5  mov     [rsp+218h+var_1A7], r15b
0x1800b4aba  mov     [rsp+218h+var_1A8], r15b
0x1800b4abf  mov     [rsp+218h+var_168], r15
0x1800b4ac7  mov     [rsp+218h+string], r15
0x1800b4acc  mov     r12d, r15d
0x1800b4acf  test    r13, r13
0x1800b4ad2  jz      loc_1800B4B9A
0x1800b4ad8  mov     rax, [r13+0]
0x1800b4adc  lea     rdx, [rsp+218h+var_1A6]
0x1800b4ae1  mov     rcx, r13
0x1800b4ae4  mov     rax, [rax+50h]
0x1800b4ae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4aed  mov     r12d, eax
0x1800b4af0  test    eax, eax
0x1800b4af2  js      loc_1800B4B9A
0x1800b4af8  mov     rax, [r13+0]
0x1800b4afc  lea     rdx, [rsp+218h+var_1A7]
0x1800b4b01  mov     rcx, r13
0x1800b4b04  mov     rax, [rax+40h]
0x1800b4b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4b0d  mov     r12d, eax
0x1800b4b10  test    eax, eax
0x1800b4b12  js      loc_1800B4B9A
0x1800b4b18  mov     rax, [r13+0]
0x1800b4b1c  lea     rdx, [rsp+218h+var_1A8]
0x1800b4b21  mov     rcx, r13
0x1800b4b24  mov     rax, [rax+60h]
0x1800b4b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4b2d  mov     r12d, eax
0x1800b4b30  test    eax, eax
0x1800b4b32  js      short loc_1800B4B9A
0x1800b4b34  mov     rax, [r13+0]
0x1800b4b38  mov     rbx, [rax+70h]
0x1800b4b3c  lea     rcx, [rsp+218h+var_168]
0x1800b4b44  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800b4b49  lea     rdx, [rsp+218h+var_168]
0x1800b4b51  mov     rcx, r13
0x1800b4b54  mov     rax, rbx
0x1800b4b57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4b5c  mov     r12d, eax
0x1800b4b5f  test    eax, eax
0x1800b4b61  js      short loc_1800B4B9A
0x1800b4b63  mov     rbx, [rsp+218h+var_168]
0x1800b4b6b  test    rbx, rbx
0x1800b4b6e  jz      short loc_1800B4B9A
0x1800b4b70  mov     rax, [rbx]
0x1800b4b73  mov     rdi, [rax+48h]
0x1800b4b77  mov     rcx, [rsp+218h+string]; string
0x1800b4b7c  call    cs:__imp_WindowsDeleteString
0x1800b4b82  mov     [rsp+218h+string], r15
0x1800b4b87  lea     rdx, [rsp+218h+string]
0x1800b4b8c  mov     rcx, rbx
0x1800b4b8f  mov     rax, rdi
0x1800b4b92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4b97  mov     r12d, eax
0x1800b4b9a  lea     rdx, [rsp+218h+var_D8]; HSTRING
0x1800b4ba2  mov     rcx, r14; this
0x1800b4ba5  call    ?GenerateIfMissingCorrelationVector@CommonTelemetry@WindowsUpdate@@YAXPEAUHSTRING__@@QEAD@Z; WindowsUpdate::CommonTelemetry::GenerateIfMissingCorrelationVector(HSTRING__ *,char * const)
0x1800b4baa  mov     [rsp+218h+var_188], r15
0x1800b4bb2  xor     ecx, ecx; string
0x1800b4bb4  call    cs:__imp_WindowsDeleteString
0x1800b4bba  mov     [rsp+218h+var_188], r15
0x1800b4bc2  lea     r8, [rsp+218h+var_188]; HSTRING *
0x1800b4bca  lea     rdx, aWindowsApplica_78; "Windows::ApplicationModel::Store::Previ"...
0x1800b4bd1  mov     rcx, rsi; HSTRING
0x1800b4bd4  call    ?GetCallingProcessAndFunction@@YAJPEAUHSTRING__@@PEBGPEAPEAU1@@Z; GetCallingProcessAndFunction(HSTRING__ *,ushort const *,HSTRING__ * *)
0x1800b4bd9  mov     ebx, eax
0x1800b4bdb  test    eax, eax
0x1800b4bdd  jns     short loc_1800B4C00
0x1800b4bdf  mov     rcx, [rsp+218h]; this
0x1800b4be7  mov     r9d, eax; char *
0x1800b4bea  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800b4bf1  mov     edx, 1A29h; void *
0x1800b4bf6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4bfb  jmp     loc_1800B4FFF
0x1800b4c00  mov     rcx, [rsp+218h+var_188]; string
0x1800b4c08  mov     [rsp+218h+var_178], rcx
0x1800b4c10  lea     rax, aTrue; "true"
0x1800b4c17  mov     r14, rax
0x1800b4c1a  lea     rdx, aFalse_0; "false"
0x1800b4c21  cmp     [rsp+218h+var_1A8], r15b
0x1800b4c26  cmovz   r14, rdx
0x1800b4c2a  mov     rsi, rax
0x1800b4c2d  cmp     [rsp+218h+var_1A7], r15b
0x1800b4c32  cmovz   rsi, rdx
0x1800b4c36  mov     rdi, rax
0x1800b4c39  cmp     [rsp+218h+var_1A6], r15b
0x1800b4c3e  cmovz   rdi, rdx
0x1800b4c42  xor     edx, edx; length
0x1800b4c44  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b4c4a  mov     rbx, rax
0x1800b4c4d  xor     edx, edx; length
0x1800b4c4f  mov     rcx, [rsp+218h+var_160]; string
0x1800b4c57  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b4c5d  lea     rcx, [rsp+218h+var_D8]
0x1800b4c65  mov     [rsp+218h+var_1B0], rcx
0x1800b4c6a  mov     [rsp+218h+var_1B8], r14
0x1800b4c6f  mov     [rsp+218h+var_1C0], rsi
0x1800b4c74  mov     [rsp+218h+var_1C8], rdi
0x1800b4c79  mov     [rsp+218h+var_1D0], rbx
0x1800b4c7e  mov     [rsp+218h+var_1D8], rax
0x1800b4c83  mov     [rsp+218h+var_1E0], r15; unsigned __int16 *
0x1800b4c88  mov     [rsp+218h+var_1E8], r15; char *
0x1800b4c8d  lea     rax, aRequestPackage; "request: packageFullName = %s, clientId"...
0x1800b4c94  mov     [rsp+218h+var_1F0], rax; unsigned __int16 *
0x1800b4c99  mov     [rsp+218h+var_1F8], 0FFFFFFFFh; int
0x1800b4ca1  lea     r9, aWindowsApplica_57; "Windows::ApplicationModel::Store::Previ"...
0x1800b4ca8  mov     r8d, 1A33h; unsigned int
0x1800b4cae  lea     rdx, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800b4cb5  mov     ecx, 3; unsigned int
0x1800b4cba  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800b4cbf  mov     [rsp+218h+var_158], r15
0x1800b4cc7  mov     rdi, [rsp+218h+var_170]
0x1800b4ccf  test    rdi, rdi
0x1800b4cd2  jnz     short loc_1800B4CE9
0x1800b4cd4  call    ?_GetCurrentActiveUserAccessToken@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAAPEAXXZ; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetCurrentActiveUserAccessToken(void)
0x1800b4cd9  mov     rdx, rax
0x1800b4cdc  lea     rcx, [rsp+218h+var_158]
0x1800b4ce4  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800b4ce9  xor     edx, edx; bool
0x1800b4ceb  lea     rcx, [rsp+218h+var_D8]; char *
0x1800b4cf3  call    ?Extend@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Extend(char const *,bool)
0x1800b4cf8  mov     [rsp+218h+var_160], rax
0x1800b4d00  test    r12d, r12d
0x1800b4d03  js      short loc_1800B4D15
0x1800b4d05  neg     rax
0x1800b4d08  sbb     r12d, r12d
0x1800b4d0b  not     r12d
0x1800b4d0e  and     r12d, 8007000Eh
0x1800b4d15  mov     [rsp+218h+newString], r15
0x1800b4d1d  test    r12d, r12d
0x1800b4d20  js      short loc_1800B4D3A
0x1800b4d22  lea     rdx, [rsp+218h+var_178]; HSTRING *
0x1800b4d2a  lea     rcx, [rsp+218h+newString]; newString
0x1800b4d32  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800b4d37  mov     r12d, eax
0x1800b4d3a  mov     [rsp+218h+var_198], r15
0x1800b4d42  test    r12d, r12d
0x1800b4d45  js      loc_1800B4EFF
0x1800b4d4b  lea     rdx, [rsp+218h+var_180]; HSTRING *
0x1800b4d53  lea     rcx, [rsp+218h+var_198]; newString
0x1800b4d5b  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800b4d60  mov     r12d, eax
0x1800b4d63  test    eax, eax
0x1800b4d65  js      loc_1800B4EFF
0x1800b4d6b  xor     r8d, r8d; unsigned __int8
0x1800b4d6e  mov     dl, 1; struct Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallOptions *
0x1800b4d70  mov     rcx, r13; this
0x1800b4d73  call    ?GetInstallFlags@Utils@@YAKPEAUIAppInstallOptions@InstallControl@Preview@Store@ApplicationModel@Windows@@EE@Z; Utils::GetInstallFlags(Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallOptions *,uchar,uchar)
0x1800b4d78  mov     dword ptr [rsp+218h+var_180], eax
0x1800b4d7f  xor     edx, edx; length
0x1800b4d81  mov     rcx, [rsp+218h+var_188]; string
0x1800b4d89  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b4d8f  mov     rcx, rax; Str
0x1800b4d92  mov     dl, 1; unsigned __int16 *
0x1800b4d94  call    ?IsCallerInteractive@Utils@@YA_NPEBG_N@Z; Utils::IsCallerInteractive(ushort const *,bool)
0x1800b4d99  mov     [rsp+218h+var_1A5], al
0x1800b4d9d  mov     rbx, qword ptr [rsp+218h+var_150]
0x1800b4da5  add     rbx, 0FFFFFFFFFFFFFF98h
0x1800b4da9  mov     [rsp+218h+var_170], rbx
0x1800b4db1  lea     rcx, [rsp+218h+var_170]
0x1800b4db9  call    ?InternalAddRef@?$ComPtr@VAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(void)
0x1800b4dbe  nop
0x1800b4dbf  mov     [rsp+218h+var_178], rdi
0x1800b4dc7  lea     rcx, [rsp+218h+var_178]
0x1800b4dcf  call    ?InternalAddRef@?$ComPtr@VAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(void)
0x1800b4dd4  nop
0x1800b4dd5  mov     r8, [rsp+218h+string]
0x1800b4dda  mov     rcx, [rsp+218h+newString]
0x1800b4de2  mov     rax, [rsp+218h+var_198]
0x1800b4dea  lea     rdx, [rsp+218h+var_180]
0x1800b4df2  mov     [rsp+218h+var_1B0], rdx
0x1800b4df7  lea     rdx, [rsp+218h+var_160]
0x1800b4dff  mov     [rsp+218h+var_1B8], rdx
0x1800b4e04  mov     [rsp+218h+var_1C0], rax
0x1800b4e09  mov     [rsp+218h+var_1C8], rcx
0x1800b4e0e  mov     [rsp+218h+var_1D0], r8
0x1800b4e13  lea     rax, [rsp+218h+var_1A6]
0x1800b4e18  mov     [rsp+218h+var_1D8], rax
0x1800b4e1d  lea     rax, [rsp+218h+var_158]
0x1800b4e25  mov     [rsp+218h+var_1E0], rax
0x1800b4e2a  lea     rax, [rsp+218h+var_1A5]
0x1800b4e2f  mov     [rsp+218h+var_1E8], rax
0x1800b4e34  lea     rax, [rsp+218h+var_1A7]
0x1800b4e39  mov     [rsp+218h+var_1F0], rax
0x1800b4e3e  lea     rax, [rsp+218h+var_1A8]
0x1800b4e43  mov     qword ptr [rsp+218h+var_1F8], rax
0x1800b4e48  lea     r9, [rsp+218h+var_178]
0x1800b4e50  lea     r8, [rsp+218h+var_170]
0x1800b4e58  mov     rdx, rbx
0x1800b4e5b  lea     rcx, [rsp+218h+var_138]
0x1800b4e63  call    _lambda_31d51c1d296f7628d8b1582d7f634666____lambda_31d51c1d296f7628d8b1582d7f634666_
0x1800b4e68  nop
0x1800b4e69  mov     dword ptr [rsp+218h+var_150], r15d
0x1800b4e71  mov     qword ptr [rsp+218h+var_150+4], 80h
0x1800b4e7d  mov     r9, rax
0x1800b4e80  mov     rdx, [rsp+218h+var_140]
0x1800b4e88  lea     rcx, [rsp+218h+var_150]
0x1800b4e90  call    Windows__Internal__MakeAsyncOperation_Windows__Internal__CMarshaledInterfaceResult_Windows__ApplicationModel__Store__Preview__InstallControl__IAppInstallItem__Windows__ApplicationModel__Store__Preview__InstallControl__AppInstallItem___Windows__Internal__ComTaskPoolHandler__lambda_31d51c1d296f7628d8b1582d7f634666___
0x1800b4e95  mov     r12d, eax
0x1800b4e98  lea     rcx, [rsp+218h+var_138]
0x1800b4ea0  call    _lambda_31d51c1d296f7628d8b1582d7f634666_____lambda_31d51c1d296f7628d8b1582d7f634666_
0x1800b4ea5  nop
0x1800b4ea6  lea     rcx, [rsp+218h+var_178]
0x1800b4eae  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800b4eb3  nop
0x1800b4eb4  lea     rcx, [rsp+218h+var_170]
0x1800b4ebc  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800b4ec1  nop
0x1800b4ec2  jmp     short loc_1800B4ECF
0x1800b4ec4  xor     r15d, r15d
0x1800b4ec7  mov     r12d, dword ptr [rsp+218h+var_180]
0x1800b4ecf  lea     rax, aFalse_0; "false"
0x1800b4ed6  lea     r14, aTrue; "true"
0x1800b4edd  test    r12d, r12d
0x1800b4ee0  js      short loc_1800B4F0D
0x1800b4ee2  mov     [rsp+218h+newString], r15
0x1800b4eea  mov     rcx, r15
0x1800b4eed  mov     [rsp+218h+var_198], rcx
0x1800b4ef5  mov     [rsp+218h+string], r15
0x1800b4efa  jmp     loc_1800B4FB8
0x1800b4eff  lea     rax, aFalse_0; "false"
0x1800b4f06  lea     r14, aTrue; "true"
0x1800b4f0d  mov     rsi, r14
0x1800b4f10  cmp     [rsp+218h+var_1A8], r15b
0x1800b4f15  cmovz   rsi, rax
0x1800b4f19  mov     rdi, r14
0x1800b4f1c  cmp     [rsp+218h+var_1A7], r15b
0x1800b4f21  cmovz   rdi, rax
0x1800b4f25  cmp     [rsp+218h+var_1A6], r15b
0x1800b4f2a  cmovz   r14, rax
0x1800b4f2e  xor     edx, edx; length
0x1800b4f30  mov     rcx, [rsp+218h+newString]; string
0x1800b4f38  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b4f3e  mov     rbx, rax
0x1800b4f41  xor     edx, edx; length
0x1800b4f43  mov     rcx, [rsp+218h+var_198]; string
0x1800b4f4b  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b4f51  lea     rcx, [rsp+218h+var_D8]
0x1800b4f59  mov     [rsp+218h+var_1B0], rcx
0x1800b4f5e  mov     [rsp+218h+var_1B8], rsi
0x1800b4f63  mov     [rsp+218h+var_1C0], rdi
0x1800b4f68  mov     [rsp+218h+var_1C8], r14
0x1800b4f6d  mov     [rsp+218h+var_1D0], rbx
0x1800b4f72  mov     [rsp+218h+var_1D8], rax
0x1800b4f77  mov     [rsp+218h+var_1E0], r15; unsigned __int16 *
0x1800b4f7c  mov     [rsp+218h+var_1E8], r15; char *
0x1800b4f81  lea     rax, aInitialization_9; "initialization failed:: packageFullName"...
0x1800b4f88  mov     [rsp+218h+var_1F0], rax; unsigned __int16 *
0x1800b4f8d  mov     [rsp+218h+var_1F8], r12d; int
0x1800b4f92  lea     r9, aWindowsApplica_57; "Windows::ApplicationModel::Store::Previ"...
0x1800b4f99  mov     r8d, 1AEBh; unsigned int
0x1800b4f9f  lea     rdx, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800b4fa6  mov     ecx, 3; unsigned int
0x1800b4fab  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800b4fb0  mov     rcx, [rsp+218h+var_198]; string
0x1800b4fb8  call    cs:__imp_WindowsDeleteString
0x1800b4fbe  mov     [rsp+218h+var_198], r15
0x1800b4fc6  mov     rcx, [rsp+218h+newString]; string
0x1800b4fce  call    cs:__imp_WindowsDeleteString
0x1800b4fd4  mov     [rsp+218h+newString], r15
0x1800b4fdc  mov     rcx, [rsp+218h+var_160]; this
0x1800b4fe4  test    rcx, rcx
0x1800b4fe7  jz      short loc_1800B4FEF
0x1800b4fe9  call    ??_GTraceLoggingCorrelationVector@@QEAAPEAXI@Z; TraceLoggingCorrelationVector::`scalar deleting destructor'(uint)
0x1800b4fee  nop
0x1800b4fef  lea     rcx, [rsp+218h+var_158]
0x1800b4ff7  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800b4ffc  mov     ebx, r12d
0x1800b4fff  mov     rcx, [rsp+218h+var_188]; string
0x1800b5007  call    cs:__imp_WindowsDeleteString
0x1800b500d  mov     [rsp+218h+var_188], r15
  ... truncated ...
```
