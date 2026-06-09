# Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_StartBundleProductInstallAsync(Windows::System::IUser *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,Windows::Management::Deployment::IPackageVolume *,StartProductInstallOptions,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallationToastNotificationMode,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallationToastNotificationMode,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> * *)

- ea: `0x1800cd04c`
- end: `0x1800cd62e`
- name: `?_StartBundleProductInstallAsync@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAAJPEAUIUser@System@6@PEAUHSTRING__@@111111PEAUIPackageVolume@Deployment@Management@6@W4StartProductInstallOptions@@W4AppInstallationToastNotificationMode@23456@4PEAPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@6@@Z`
- size: `1506`
- prototype: `__int64 __fastcall(__int64, __int64, char *, HSTRING, __int64, HSTRING, HSTRING, HSTRING, WindowsUpdate::CommonTelemetry *, __int64, char, char, char, _QWORD *)`
- caller_count: `5`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800c4380`
- `0x1800c45c0`
- `0x1800c47f0`
- `0x1800c4a30`
- `0x1800cd634`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x1800127c8`
- `0x18001c414`
- `0x180023a9c`
- `0x18002548c`
- `0x180028cd4`
- `0x180072420`
- `0x18007bff0`
- `0x18008e1ac`
- `0x18008f294`
- `0x1800920bc`
- `0x180095da8`
- `0x1800c83a8`
- `0x1800cd04c`
- `0x18014579c`
- `0x1801467dc`
- `0x1801473f4`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd5ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd5d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd5ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd5d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800cd393`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800cd393`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd19c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd1aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd1b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd1c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd1d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd480`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd48e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd49c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd4cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd4da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd4e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd4f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd19c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd1aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd1b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd1c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd1d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd480`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd48e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd49c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd4cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd4da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd4e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd4f7`

## string_xrefs

- `0x1800cd148`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800cd2b0`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800cd5b9`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800cd13b`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_StartBundleProductInstallAsync`
- `0x1800cd2a3`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_StartBundleProductInstallAsync`
- `0x1800cd5ac`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_StartBundleProductInstallAsync`
- `0x1800cd59b`: `initialization failed: productid = %s, skuid = %s, catalogId = %s, flightId = %s, CV = %hs, repair = %s, userInteractive = %s, allowDownloadOnAnyNetwork = %s, forceUseOfNonRemovableStorage = %s, allowForcedAppRestart = %s, launchAfterInstall = %s`
- `0x1800cd28f`: `request: productId = %s, skuId = %s, catalogId = %s, flightId = %s, volumePath = %s, CV = %hs, repair = %s, userInteractive = %s, allowDownloadOnAnyNetwork = %s, forceUseOfNonRemovableStorage = %s, allowForcedAppRestart = %s, launchAfterInstall = %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_StartBundleProductInstallAsync(
        __int64 a1,
        __int64 a2,
        char *a3,
        HSTRING a4,
        __int64 a5,
        HSTRING a6,
        HSTRING a7,
        HSTRING a8,
        WindowsUpdate::CommonTelemetry *a9,
        __int64 a10,
        char a11,
        char a12,
        char a13,
        _QWORD *a14)
{
  _QWORD *v15; // r13
  HSTRING v17; // rcx
  HSTRING v18; // rsi
  HSTRING v19; // rdi
  HSTRING v20; // rbx
  Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl *v21; // rcx
  void *CurrentActiveUserAccessToken; // rax
  HRESULT v23; // r14d
  int v24; // r14d
  __int64 v25; // rax
  __int64 v26; // r8
  const unsigned __int16 *StringRawBuffer; // rdi
  const unsigned __int16 *v28; // rbx
  WindowsUpdate::CommonTelemetry *v29; // rax
  PCWSTR v30; // rsi
  PCWSTR v31; // rdi
  PCWSTR v32; // rbx
  PCWSTR v33; // r10
  const unsigned __int16 *v34; // r11
  const unsigned __int16 *v35; // r9
  const unsigned __int16 *v36; // r8
  const unsigned __int16 *v37; // rdx
  const unsigned __int16 *v38; // rcx
  const unsigned __int16 *v39; // rax
  unsigned int v40; // edx
  const unsigned __int16 *v41; // [rsp+20h] [rbp-100h]
  char *v42; // [rsp+30h] [rbp-F0h]
  char *v43; // [rsp+30h] [rbp-F0h]
  int v44; // [rsp+38h] [rbp-E8h]
  HSTRING string; // [rsp+A0h] [rbp-80h] BYREF
  const unsigned __int16 *v46; // [rsp+A8h] [rbp-78h] BYREF
  int v47; // [rsp+B0h] [rbp-70h]
  int v48; // [rsp+B4h] [rbp-6Ch]
  int v49; // [rsp+B8h] [rbp-68h]
  int v50; // [rsp+BCh] [rbp-64h]
  int v51; // [rsp+C0h] [rbp-60h]
  int v52; // [rsp+C4h] [rbp-5Ch]
  __int64 v53; // [rsp+C8h] [rbp-58h] BYREF
  __int64 v54; // [rsp+D0h] [rbp-50h] BYREF
  __int64 v55; // [rsp+D8h] [rbp-48h] BYREF
  HSTRING v56; // [rsp+E0h] [rbp-40h] BYREF
  HSTRING v57; // [rsp+E8h] [rbp-38h]
  HSTRING newString; // [rsp+F0h] [rbp-30h] BYREF
  _QWORD v59[2]; // [rsp+F8h] [rbp-28h] BYREF
  __int64 v60; // [rsp+108h] [rbp-18h]
  HSTRING v61; // [rsp+110h] [rbp-10h]
  HSTRING v62; // [rsp+118h] [rbp-8h] BYREF
  HSTRING v63; // [rsp+120h] [rbp+0h] BYREF
  HSTRING v64; // [rsp+128h] [rbp+8h] BYREF
  char *v65; // [rsp+130h] [rbp+10h] BYREF
  _BYTE v66[88]; // [rsp+138h] [rbp+18h] BYREF
  HSTRING__ v67; // [rsp+190h] [rbp+70h] BYREF

  v57 = a4;
  v60 = a2;
  v59[0] = a1;
  v65 = a3;
  v64 = a4;
  v54 = a5;
  v61 = a6;
  v63 = a6;
  v56 = a7;
  v62 = a7;
  v15 = a14;
  *a14 = 0;
  if ( !a3 )
    return 2147942487LL;
  WindowsUpdate::CommonTelemetry::GenerateIfMissingCorrelationVector(a9, &v67, a3);
  v17 = 0;
  string = 0;
  if ( a10 )
  {
    if ( (*(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a10 + 72LL))(a10, &string) >= 0 )
    {
      v17 = string;
    }
    else
    {
      LogSimpleMessage(
        2u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
        0x14E1u,
        "Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_StartBundleProductInstallAsync",
        -1,
        L"couldnt get volume name",
        0,
        0);
      v17 = 0;
      string = 0;
    }
  }
  v47 = a11 & 0x20;
  v48 = a11 & 8;
  v49 = a11 & 0x10;
  v50 = a11 & 2;
  v51 = a11 & 1;
  v52 = a11 & 4;
  WindowsGetStringRawBuffer(v17, 0);
  WindowsGetStringRawBuffer(a7, 0);
  WindowsGetStringRawBuffer(a6, 0);
  WindowsGetStringRawBuffer(v57, 0);
  WindowsGetStringRawBuffer((HSTRING)a3, 0);
  v46 = L"false";
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
    0x14F3u,
    "Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_StartBundleProductInstallAsync",
    -1,
    L"request: productId = %s, skuId = %s, catalogId = %s, flightId = %s, volumePath = %s, CV = %hs, repair = %s, userInte"
     "ractive = %s, allowDownloadOnAnyNetwork = %s, forceUseOfNonRemovableStorage = %s, allowForcedAppRestart = %s, launc"
     "hAfterInstall = %s",
    0,
    0);
  v18 = v56;
  v19 = v61;
  v20 = v57;
  WindowsUpdate::CommonTelemetry::BeginInstallOperationRequest((HSTRING)a3, v57, v61, v56, string, &v67, v42);
  v46 = 0;
  if ( !v60 )
  {
    CurrentActiveUserAccessToken = Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetCurrentActiveUserAccessToken(v21);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v46,
      CurrentActiveUserAccessToken);
  }
  v56 = (HSTRING)TraceLoggingCorrelationVector::Extend((const char *)&v67, 0);
  v23 = v56 == 0 ? 0x8007000E : 0;
  v55 = 0;
  if ( v56 )
  {
    LODWORD(v53) = 7;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v55);
    v23 = Microsoft::WRL::Details::MakeAndInitialize<AppId,AppId,HSTRING__ *,enum AppId::Type,HSTRING__ *,std::nullptr_t,std::nullptr_t,HSTRING__ *>(
            (unsigned int)&v55,
            (unsigned int)&v65,
            (unsigned int)&v53,
            (unsigned int)&v64,
            (__int64)&v63,
            (__int64)&v62,
            (__int64)&v54);
  }
  newString = 0;
  if ( v23 < 0 )
    goto LABEL_16;
  if ( a8 )
    v23 = WindowsDuplicateString(a8, &newString);
  if ( v23 < 0 )
    goto LABEL_16;
  v24 = v59[0];
  v54 = v59[0];
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(&v54);
  v53 = v60;
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(&v53);
  v25 = lambda_68d77904b0761f05ab5650e5e6678ce9_::_lambda_68d77904b0761f05ab5650e5e6678ce9_(
          (unsigned int)v66,
          v24,
          (unsigned int)&v54,
          (unsigned int)&v53,
          (__int64)&v46,
          (__int64)&v55,
          (__int64)&string,
          (__int64)&v56,
          (__int64)&newString,
          (__int64)&a11,
          (__int64)&a12,
          (__int64)&a13);
  LODWORD(v59[0]) = 0;
  *(_QWORD *)((char *)v59 + 4) = 128;
  v23 = Windows::Internal::MakeAsyncOperation_Windows::Internal::CMarshaledInterfaceResult_Windows::Foundation::Collections::IVectorView_Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem______Windows::Foundation::Collections::IVectorView_Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem______Windows::Internal::ComTaskPoolHandler__lambda_68d77904b0761f05ab5650e5e6678ce9___(
          v59,
          v15,
          v26,
          v25);
  lambda_68d77904b0761f05ab5650e5e6678ce9_::__lambda_68d77904b0761f05ab5650e5e6678ce9_(v66);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v53);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v54);
  if ( v23 < 0 )
  {
LABEL_16:
    StringRawBuffer = WindowsGetStringRawBuffer(v19, 0);
    v28 = WindowsGetStringRawBuffer(v20, 0);
    v29 = (WindowsUpdate::CommonTelemetry *)WindowsGetStringRawBuffer((HSTRING)a3, 0);
    LODWORD(v43) = v23;
    LOBYTE(v41) = 0;
    WindowsUpdate::CommonTelemetry::EndInstallOperationRequest(
      v29,
      v28,
      StringRawBuffer,
      0,
      v41,
      (unsigned __int8)&v67,
      v43,
      v44);
    v30 = WindowsGetStringRawBuffer(v18, 0);
    v31 = WindowsGetStringRawBuffer(v61, 0);
    v32 = WindowsGetStringRawBuffer(v57, 0);
    v33 = WindowsGetStringRawBuffer((HSTRING)a3, 0);
    v34 = L"true";
    v35 = L"true";
    if ( !v47 )
      v35 = L"false";
    v36 = L"true";
    if ( !v48 )
      v36 = L"false";
    v37 = L"true";
    if ( !v49 )
      v37 = L"false";
    v38 = L"true";
    if ( !v50 )
      v38 = L"false";
    v39 = L"true";
    if ( !(_BYTE)v51 )
      v39 = L"false";
    if ( !v52 )
      v34 = L"false";
    LogMessage(
      1u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      0x15B0u,
      "Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_StartBundleProductInstallAsync",
      v23,
      L"initialization failed: productid = %s, skuid = %s, catalogId = %s, flightId = %s, CV = %hs, repair = %s, userInter"
       "active = %s, allowDownloadOnAnyNetwork = %s, forceUseOfNonRemovableStorage = %s, allowForcedAppRestart = %s, laun"
       "chAfterInstall = %s",
      0,
      0,
      v33,
      v32,
      v31,
      v30,
      &v67,
      v34,
      v39,
      v38,
      v37,
      v36,
      v35);
    WindowsDeleteString(string);
    WindowsDeleteString(newString);
  }
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v55);
  if ( v56 )
    TraceLoggingCorrelationVector::`scalar deleting destructor'((TraceLoggingCorrelationVector *)v56, v40);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v46);
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x1800cd04c  mov     [rsp-8+arg_8], rbx
0x1800cd051  push    rbp
0x1800cd052  push    rsi
0x1800cd053  push    rdi
0x1800cd054  push    r12
0x1800cd056  push    r13
0x1800cd058  push    r14
0x1800cd05a  push    r15
0x1800cd05c  lea     rbp, [rsp-110h]
0x1800cd064  sub     rsp, 230h
0x1800cd06b  mov     rax, cs:__security_cookie
0x1800cd072  xor     rax, rsp
0x1800cd075  mov     [rbp+140h+var_40], rax
0x1800cd07c  mov     rax, r9
0x1800cd07f  mov     [rbp+140h+var_178], rax
0x1800cd083  mov     r15, r8
0x1800cd086  mov     [rbp+140h+var_158], rdx
0x1800cd08a  mov     qword ptr [rbp+140h+var_168], rcx
0x1800cd08e  mov     [rbp+140h+var_130], r8
0x1800cd092  mov     [rbp+140h+var_138], rax
0x1800cd096  mov     rax, [rbp+140h+arg_20]
0x1800cd09d  mov     [rbp+140h+var_190], rax
0x1800cd0a1  mov     rdi, [rbp+140h+arg_28]
0x1800cd0a8  mov     [rbp+140h+var_150], rdi
0x1800cd0ac  mov     [rbp+140h+var_140], rdi
0x1800cd0b0  mov     rsi, [rbp+140h+arg_30]
0x1800cd0b7  mov     [rbp+140h+var_180], rsi
0x1800cd0bb  mov     [rbp+140h+var_148], rsi
0x1800cd0bf  mov     r12, [rbp+140h+arg_38]
0x1800cd0c6  mov     rcx, [rbp+140h+arg_40]; this
0x1800cd0cd  mov     rbx, [rbp+140h+arg_48]
0x1800cd0d4  mov     r13, [rbp+140h+arg_68]
0x1800cd0db  xor     r14d, r14d
0x1800cd0de  mov     [r13+0], r14
0x1800cd0e2  test    r8, r8
0x1800cd0e5  jnz     short loc_1800CD0F1
0x1800cd0e7  mov     eax, 80070057h
0x1800cd0ec  jmp     loc_1800CD604
0x1800cd0f1  lea     rdx, [rbp+140h+var_D0]; HSTRING
0x1800cd0f5  call    ?GenerateIfMissingCorrelationVector@CommonTelemetry@WindowsUpdate@@YAXPEAUHSTRING__@@QEAD@Z; WindowsUpdate::CommonTelemetry::GenerateIfMissingCorrelationVector(HSTRING__ *,char * const)
0x1800cd0fa  mov     rcx, r14
0x1800cd0fd  mov     [rbp+140h+string], rcx
0x1800cd101  test    rbx, rbx
0x1800cd104  jz      short loc_1800CD166
0x1800cd106  mov     rax, [rbx]
0x1800cd109  lea     rdx, [rbp+140h+string]
0x1800cd10d  mov     rcx, rbx
0x1800cd110  mov     rax, [rax+48h]
0x1800cd114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd119  test    eax, eax
0x1800cd11b  jns     short loc_1800CD162
0x1800cd11d  mov     [rsp+260h+var_228], r14; unsigned __int16 *
0x1800cd122  mov     [rsp+260h+var_230], r14; char *
0x1800cd127  lea     rax, aCouldntGetVolu; "couldnt get volume name"
0x1800cd12e  mov     [rsp+260h+var_238], rax; unsigned __int16 *
0x1800cd133  mov     dword ptr [rsp+260h+var_240], 0FFFFFFFFh; int
0x1800cd13b  lea     r9, aWindowsApplica_33; "Windows::ApplicationModel::Store::Previ"...
0x1800cd142  mov     r8d, 14E1h; unsigned int
0x1800cd148  lea     rdx, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800cd14f  mov     ecx, 2; unsigned int
0x1800cd154  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x1800cd159  mov     rcx, r14
0x1800cd15c  mov     [rbp+140h+string], rcx
0x1800cd160  jmp     short loc_1800CD166
0x1800cd162  mov     rcx, [rbp+140h+string]; string
0x1800cd166  mov     eax, dword ptr [rbp+140h+arg_50]
0x1800cd16c  mov     edx, eax
0x1800cd16e  and     edx, 20h
0x1800cd171  mov     [rbp+140h+var_1B0], edx
0x1800cd174  mov     edx, eax
0x1800cd176  and     edx, 8
0x1800cd179  mov     [rbp+140h+var_1AC], edx
0x1800cd17c  mov     edx, eax
0x1800cd17e  and     edx, 10h
0x1800cd181  mov     [rbp+140h+var_1A8], edx
0x1800cd184  mov     edx, eax
0x1800cd186  and     edx, 2
0x1800cd189  mov     [rbp+140h+var_1A4], edx
0x1800cd18c  mov     edx, eax
0x1800cd18e  and     edx, 1
0x1800cd191  mov     [rbp+140h+var_1A0], edx
0x1800cd194  and     eax, 4
0x1800cd197  mov     [rbp+140h+var_19C], eax
0x1800cd19a  xor     edx, edx; length
0x1800cd19c  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cd1a2  mov     r14, rax
0x1800cd1a5  xor     edx, edx; length
0x1800cd1a7  mov     rcx, rsi; string
0x1800cd1aa  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cd1b0  mov     rsi, rax
0x1800cd1b3  xor     edx, edx; length
0x1800cd1b5  mov     rcx, rdi; string
0x1800cd1b8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cd1be  mov     rdi, rax
0x1800cd1c1  xor     edx, edx; length
0x1800cd1c3  mov     rcx, [rbp+140h+var_178]; string
0x1800cd1c7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cd1cd  mov     rbx, rax
0x1800cd1d0  xor     edx, edx; length
0x1800cd1d2  mov     rcx, r15; string
0x1800cd1d5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cd1db  mov     r11, rax
0x1800cd1de  lea     rdx, aFalse_0; "false"
0x1800cd1e5  mov     [rbp+140h+var_1B8], rdx
0x1800cd1e9  lea     rax, aTrue; "true"
0x1800cd1f0  mov     r10, rax
0x1800cd1f3  xor     ecx, ecx
0x1800cd1f5  cmp     [rbp+140h+var_1B0], ecx
0x1800cd1f8  cmovz   r10, rdx
0x1800cd1fc  mov     r9, rax
0x1800cd1ff  cmp     [rbp+140h+var_1AC], ecx
0x1800cd202  cmovz   r9, rdx
0x1800cd206  mov     r8, rax
0x1800cd209  cmp     [rbp+140h+var_1A8], ecx
0x1800cd20c  cmovz   r8, rdx
0x1800cd210  mov     rdx, rax
0x1800cd213  cmp     [rbp+140h+var_1A4], ecx
0x1800cd216  lea     rcx, aFalse_0; "false"
0x1800cd21d  cmovz   rdx, rcx
0x1800cd221  mov     rcx, rax
0x1800cd224  cmp     byte ptr [rbp+140h+var_1A0], 0
0x1800cd228  cmovz   rcx, [rbp+140h+var_1B8]
0x1800cd22d  cmp     [rbp+140h+var_19C], 0
0x1800cd231  cmovz   rax, [rbp+140h+var_1B8]
0x1800cd236  mov     [rsp+260h+var_1C8], r10
0x1800cd23e  mov     [rsp+260h+var_1D0], r9
0x1800cd246  mov     [rsp+260h+var_1D8], r8
0x1800cd24e  mov     [rsp+260h+var_1E0], rdx
0x1800cd256  mov     [rsp+260h+var_1E8], rcx
0x1800cd25b  mov     [rsp+260h+var_1F0], rax
0x1800cd260  lea     rax, [rbp+140h+var_D0]
0x1800cd264  mov     [rsp+260h+var_1F8], rax
0x1800cd269  mov     [rsp+260h+var_200], r14
0x1800cd26e  mov     [rsp+260h+var_208], rsi
0x1800cd273  mov     [rsp+260h+var_210], rdi
0x1800cd278  mov     [rsp+260h+var_218], rbx
0x1800cd27d  mov     [rsp+260h+var_220], r11
0x1800cd282  xor     r14d, r14d
0x1800cd285  mov     [rsp+260h+var_228], r14; int
0x1800cd28a  mov     [rsp+260h+var_230], r14; char *
0x1800cd28f  lea     rax, aRequestProduct_2; "request: productId = %s, skuId = %s, ca"...
0x1800cd296  mov     [rsp+260h+var_238], rax; unsigned __int16 *
0x1800cd29b  mov     dword ptr [rsp+260h+var_240], 0FFFFFFFFh; int
0x1800cd2a3  lea     r9, aWindowsApplica_33; "Windows::ApplicationModel::Store::Previ"...
0x1800cd2aa  mov     r8d, 14F3h; unsigned int
0x1800cd2b0  lea     rdx, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800cd2b7  lea     ecx, [r14+3]; unsigned int
0x1800cd2bb  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800cd2c0  lea     rax, [rbp+140h+var_D0]
0x1800cd2c4  mov     [rsp+260h+var_238], rax; HSTRING
0x1800cd2c9  mov     rax, [rbp+140h+string]
0x1800cd2cd  mov     [rsp+260h+var_240], rax; HSTRING
0x1800cd2d2  mov     rsi, [rbp+140h+var_180]
0x1800cd2d6  mov     r9, rsi; HSTRING
0x1800cd2d9  mov     rdi, [rbp+140h+var_150]
0x1800cd2dd  mov     r8, rdi; HSTRING
0x1800cd2e0  mov     rbx, [rbp+140h+var_178]
0x1800cd2e4  mov     rdx, rbx; HSTRING
0x1800cd2e7  mov     rcx, r15; string
0x1800cd2ea  call    ?BeginInstallOperationRequest@CommonTelemetry@WindowsUpdate@@YAXPEAUHSTRING__@@0000PEBD@Z; WindowsUpdate::CommonTelemetry::BeginInstallOperationRequest(HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,char const *)
0x1800cd2ef  mov     [rbp+140h+var_1B8], r14
0x1800cd2f3  cmp     [rbp+140h+var_158], r14
0x1800cd2f7  jnz     short loc_1800CD30A
0x1800cd2f9  call    ?_GetCurrentActiveUserAccessToken@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAAPEAXXZ; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetCurrentActiveUserAccessToken(void)
0x1800cd2fe  mov     rdx, rax
0x1800cd301  lea     rcx, [rbp+140h+var_1B8]
0x1800cd305  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800cd30a  xor     edx, edx; bool
0x1800cd30c  lea     rcx, [rbp+140h+var_D0]; char *
0x1800cd310  call    ?Extend@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Extend(char const *,bool)
0x1800cd315  mov     [rbp+140h+var_180], rax
0x1800cd319  neg     rax
0x1800cd31c  sbb     r14d, r14d
0x1800cd31f  not     r14d
0x1800cd322  and     r14d, 8007000Eh
0x1800cd329  mov     [rbp+140h+var_188], 0
0x1800cd331  jl      short loc_1800CD376
0x1800cd333  mov     dword ptr [rbp+140h+var_198], 7
0x1800cd33a  lea     rcx, [rbp+140h+var_188]
0x1800cd33e  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800cd343  lea     rax, [rbp+140h+var_190]
0x1800cd347  mov     [rsp+260h+var_230], rax
0x1800cd34c  lea     rax, [rbp+140h+var_148]
0x1800cd350  mov     [rsp+260h+var_238], rax
0x1800cd355  lea     rax, [rbp+140h+var_140]
0x1800cd359  mov     [rsp+260h+var_240], rax
0x1800cd35e  lea     r9, [rbp+140h+var_138]
0x1800cd362  lea     r8, [rbp+140h+var_198]
0x1800cd366  lea     rdx, [rbp+140h+var_130]
0x1800cd36a  lea     rcx, [rbp+140h+var_188]
0x1800cd36e  call    ??$MakeAndInitialize@VAppId@@V1@PEAUHSTRING__@@W4Type@1@PEAU2@$$T$$TPEAU2@@Details@WRL@Microsoft@@YAJPEAPEAVAppId@@$$QEAPEAUHSTRING__@@$$QEAW4Type@3@1$$QEA$$T31@Z
0x1800cd373  mov     r14d, eax
0x1800cd376  mov     [rbp+140h+newString], 0
0x1800cd37e  test    r14d, r14d
0x1800cd381  js      loc_1800CD478
0x1800cd387  test    r12, r12
0x1800cd38a  jz      short loc_1800CD39C
0x1800cd38c  lea     rdx, [rbp+140h+newString]; newString
0x1800cd390  mov     rcx, r12; string
0x1800cd393  call    cs:__imp_WindowsDuplicateString
0x1800cd399  mov     r14d, eax
0x1800cd39c  xor     r12d, r12d
0x1800cd39f  test    r14d, r14d
0x1800cd3a2  js      loc_1800CD47B
0x1800cd3a8  mov     r14, qword ptr [rbp+140h+var_168]
0x1800cd3ac  mov     [rbp+140h+var_190], r14
0x1800cd3b0  lea     rcx, [rbp+140h+var_190]
0x1800cd3b4  call    ?InternalAddRef@?$ComPtr@VAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(void)
0x1800cd3b9  nop
0x1800cd3ba  mov     rax, [rbp+140h+var_158]
0x1800cd3be  mov     [rbp+140h+var_198], rax
0x1800cd3c2  lea     rcx, [rbp+140h+var_198]
0x1800cd3c6  call    ?InternalAddRef@?$ComPtr@VAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(void)
0x1800cd3cb  nop
0x1800cd3cc  lea     rax, [rbp+140h+arg_60]
0x1800cd3d3  mov     [rsp+260h+var_208], rax
0x1800cd3d8  lea     rax, [rbp+140h+arg_58]
0x1800cd3df  mov     [rsp+260h+var_210], rax
0x1800cd3e4  lea     rax, [rbp+140h+arg_50]
0x1800cd3eb  mov     [rsp+260h+var_218], rax
0x1800cd3f0  lea     rax, [rbp+140h+newString]
0x1800cd3f4  mov     [rsp+260h+var_220], rax
0x1800cd3f9  lea     rax, [rbp+140h+var_180]
0x1800cd3fd  mov     [rsp+260h+var_228], rax
0x1800cd402  lea     rax, [rbp+140h+string]
0x1800cd406  mov     [rsp+260h+var_230], rax
0x1800cd40b  lea     rax, [rbp+140h+var_188]
0x1800cd40f  mov     [rsp+260h+var_238], rax
0x1800cd414  lea     rax, [rbp+140h+var_1B8]
0x1800cd418  mov     [rsp+260h+var_240], rax
0x1800cd41d  lea     r9, [rbp+140h+var_198]
0x1800cd421  lea     r8, [rbp+140h+var_190]
0x1800cd425  mov     rdx, r14
0x1800cd428  lea     rcx, [rbp+140h+var_128]
0x1800cd42c  call    _lambda_68d77904b0761f05ab5650e5e6678ce9____lambda_68d77904b0761f05ab5650e5e6678ce9_
0x1800cd431  nop
0x1800cd432  mov     dword ptr [rbp+140h+var_168], r12d
0x1800cd436  mov     qword ptr [rbp+140h+var_168+4], 80h
0x1800cd43e  mov     r9, rax
0x1800cd441  mov     rdx, r13
0x1800cd444  lea     rcx, [rbp+140h+var_168]
0x1800cd448  call    Windows__Internal__MakeAsyncOperation_Windows__Internal__CMarshaledInterfaceResult_Windows__Foundation__Collections__IVectorView_Windows__ApplicationModel__Store__Preview__InstallControl__AppInstallItem______Windows__Foundation__Collections__IVectorView_Windows__ApplicationModel__Store__Preview__InstallControl__AppInstallItem______Windows__Internal__ComTaskPoolHandler__lambda_68d77904b0761f05ab5650e5e6678ce9___
0x1800cd44d  mov     r14d, eax
0x1800cd450  lea     rcx, [rbp+140h+var_128]
0x1800cd454  call    _lambda_68d77904b0761f05ab5650e5e6678ce9_____lambda_68d77904b0761f05ab5650e5e6678ce9_
0x1800cd459  nop
0x1800cd45a  lea     rcx, [rbp+140h+var_198]
0x1800cd45e  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800cd463  nop
0x1800cd464  lea     rcx, [rbp+140h+var_190]
0x1800cd468  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800cd46d  test    r14d, r14d
0x1800cd470  jns     loc_1800CD5DF
0x1800cd476  jmp     short loc_1800CD47B
0x1800cd478  xor     r12d, r12d
0x1800cd47b  xor     edx, edx; length
0x1800cd47d  mov     rcx, rdi; string
0x1800cd480  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cd486  mov     rdi, rax
0x1800cd489  xor     edx, edx; length
0x1800cd48b  mov     rcx, rbx; string
0x1800cd48e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cd494  mov     rbx, rax
0x1800cd497  xor     edx, edx; length
0x1800cd499  mov     rcx, r15; string
0x1800cd49c  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cd4a2  mov     dword ptr [rsp+260h+var_230], r14d; char *
0x1800cd4a7  lea     rcx, [rbp+140h+var_D0]
0x1800cd4ab  mov     [rsp+260h+var_238], rcx; unsigned __int8
0x1800cd4b0  mov     byte ptr [rsp+260h+var_240], r12b; unsigned __int16 *
0x1800cd4b5  xor     r9d, r9d; unsigned __int16 *
0x1800cd4b8  mov     r8, rdi; unsigned __int16 *
0x1800cd4bb  mov     rdx, rbx; unsigned __int16 *
0x1800cd4be  mov     rcx, rax; this
0x1800cd4c1  call    ?EndInstallOperationRequest@CommonTelemetry@WindowsUpdate@@YAXPEBG000EPEBDJ@Z; WindowsUpdate::CommonTelemetry::EndInstallOperationRequest(ushort const *,ushort const *,ushort const *,ushort const *,uchar,char const *,long)
0x1800cd4c6  xor     edx, edx; length
0x1800cd4c8  mov     rcx, rsi; string
0x1800cd4cb  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cd4d1  mov     rsi, rax
0x1800cd4d4  xor     edx, edx; length
0x1800cd4d6  mov     rcx, [rbp+140h+var_150]; string
0x1800cd4da  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cd4e0  mov     rdi, rax
0x1800cd4e3  xor     edx, edx; length
0x1800cd4e5  mov     rcx, [rbp+140h+var_178]; string
0x1800cd4e9  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cd4ef  mov     rbx, rax
0x1800cd4f2  xor     edx, edx; length
0x1800cd4f4  mov     rcx, r15; string
0x1800cd4f7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cd4fd  mov     r10, rax
0x1800cd500  lea     r11, aTrue; "true"
0x1800cd507  mov     r9, r11
0x1800cd50a  cmp     [rbp+140h+var_1B0], r12d
0x1800cd50e  lea     r15, aFalse_0; "false"
0x1800cd515  cmovz   r9, r15
0x1800cd519  mov     r8, r11
0x1800cd51c  cmp     [rbp+140h+var_1AC], r12d
0x1800cd520  cmovz   r8, r15
0x1800cd524  mov     rdx, r11
  ... truncated ...
```
