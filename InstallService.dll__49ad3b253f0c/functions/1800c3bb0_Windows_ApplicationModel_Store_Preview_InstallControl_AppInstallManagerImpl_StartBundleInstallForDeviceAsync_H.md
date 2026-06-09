# Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartBundleInstallForDeviceAsync(HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,uchar,uchar,uchar,uchar,HSTRING__ *,Windows::Management::Deployment::IPackageVolume *,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> * *)

- ea: `0x1800c3bb0`
- end: `0x1800c4177`
- name: `?StartBundleInstallForDeviceAsync@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@UEAAJPEAUHSTRING__@@000EEEE0PEAUIPackageVolume@Deployment@Management@6@PEAPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@6@@Z`
- size: `1479`
- prototype: `__int64 __fastcall(__int64, HSTRING, HSTRING, HSTRING, HSTRING, char, __int64, char, char, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x180010b74`
- `0x18001c414`
- `0x1800252e8`
- `0x18002ec2c`
- `0x18003b08c`
- `0x18006e510`
- `0x180084280`
- `0x180086888`
- `0x1800c3bb0`
- `0x1800cd634`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3c2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3c7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3d9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3dad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3dbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4061`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4070`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c407f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c408e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3c2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3c7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3d9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3dad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3dbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4061`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4070`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c407f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c408e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c3c95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c3cb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c3cbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c3cd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c3ce0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c3c95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c3cb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c3cbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c3cd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c3ce0`

## string_xrefs

- `0x1800c3e15`: `Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallOptions`
- `0x1800c3c61`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c3d88`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c3c41`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartBundleInstallForDeviceAsync`
- `0x1800c3d7b`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartBundleInstallForDeviceAsync`
- `0x1800c3d67`: `request: storeId = %s, catalogId = %s, flightId = %s, clientId = %s, repair = %s, userInteractive = %s, allowDownloadOnAnyNetwork  =%s, forceUseOfNonRemovableStorage = %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartBundleInstallForDeviceAsync(
        __int64 a1,
        HSTRING a2,
        HSTRING a3,
        HSTRING a4,
        HSTRING a5,
        char a6,
        __int64 a7,
        char a8,
        char a9,
        __int64 a10,
        __int64 a11,
        _QWORD *a12)
{
  int CallingProcessAndFunction; // eax
  unsigned int v15; // ebx
  const char *v16; // r9
  __int64 result; // rax
  HSTRING v18; // r14
  wchar_t *StringRawBuffer; // rax
  const unsigned __int16 *v20; // rdx
  bool v21; // r8
  PCWSTR v22; // rsi
  PCWSTR v23; // rdi
  PCWSTR v24; // rbx
  PCWSTR v25; // r9
  const unsigned __int16 *v26; // r8
  const unsigned __int16 *v27; // rdx
  const unsigned __int16 *v28; // rcx
  const unsigned __int16 *v29; // rax
  int v30; // eax
  int v31; // eax
  __int64 v32; // rdx
  int v33; // eax
  int v34; // eax
  __int64 v35; // rdx
  int v36; // eax
  int v37; // eax
  int v38; // eax
  _QWORD **v39; // rbx
  __int64 (__fastcall *v40)(_QWORD **, GUID *, __int64 *); // rdi
  int v41; // eax
  int v42; // eax
  __int64 v43; // rdx
  int v44; // eax
  HSTRING v45; // rbx
  int started; // eax
  int v47; // [rsp+20h] [rbp-118h]
  int v48; // [rsp+20h] [rbp-118h]
  int v49; // [rsp+20h] [rbp-118h]
  char IsCallerInteractive; // [rsp+80h] [rbp-B8h]
  _QWORD **v51; // [rsp+88h] [rbp-B0h] BYREF
  __int64 v52; // [rsp+90h] [rbp-A8h] BYREF
  HSTRING string; // [rsp+98h] [rbp-A0h] BYREF
  HSTRING v54; // [rsp+A0h] [rbp-98h] BYREF
  HSTRING v55; // [rsp+A8h] [rbp-90h] BYREF
  HSTRING v56; // [rsp+B0h] [rbp-88h] BYREF
  __int64 v57; // [rsp+B8h] [rbp-80h]
  __int64 v58; // [rsp+C0h] [rbp-78h]
  HSTRING v59; // [rsp+C8h] [rbp-70h]
  HSTRING_HEADER hstringHeader; // [rsp+D0h] [rbp-68h] BYREF
  __int64 v61; // [rsp+E8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v59 = a4;
  v54 = a3;
  v57 = a1;
  v58 = a10;
  *a12 = 0;
  WindowsDeleteString(0);
  string = 0;
  try
  {
    CallingProcessAndFunction = GetCallingProcessAndFunction(
                                  a5,
                                  L"Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::Star"
                                   "tBundleInstallForDeviceAsync",
                                  &string);
    v15 = CallingProcessAndFunction;
    if ( CallingProcessAndFunction >= 0 )
    {
      v18 = string;
      StringRawBuffer = (wchar_t *)WindowsGetStringRawBuffer(string, 0);
      LOBYTE(v20) = 1;
      IsCallerInteractive = Utils::IsCallerInteractive(StringRawBuffer, v20, v21);
      v22 = WindowsGetStringRawBuffer(v18, 0);
      v23 = WindowsGetStringRawBuffer(a4, 0);
      v24 = WindowsGetStringRawBuffer(v54, 0);
      v25 = WindowsGetStringRawBuffer(a2, 0);
      v26 = L"true";
      v27 = L"true";
      if ( !a9 )
        v27 = L"false";
      v28 = L"true";
      if ( !a8 )
        v28 = L"false";
      v29 = L"true";
      if ( !IsCallerInteractive )
        v29 = L"false";
      if ( !a6 )
        v26 = L"false";
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
        0x1B68u,
        "Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartBundleInstallForDeviceAsync",
        -1,
        L"request: storeId = %s, catalogId = %s, flightId = %s, clientId = %s, repair = %s, userInteractive = %s, allowDow"
         "nloadOnAnyNetwork  =%s, forceUseOfNonRemovableStorage = %s",
        0,
        0,
        v25,
        v24,
        v23,
        v22,
        v26,
        v29,
        v28,
        v27);
      WindowsDeleteString(0);
      v54 = 0;
      WindowsDeleteString(0);
      v55 = 0;
      WindowsDeleteString(0);
      v56 = 0;
      v30 = AppId::SplitStoreId(a2, &v56, &v55, &v54);
      if ( v30 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1B6E,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
          (const char *)(unsigned int)v30,
          v48);
      v51 = 0;
      v61 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallOptions",
        0x48u,
        0x47u);
      v31 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallOptions>>(
              v61,
              &v51);
      if ( v31 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1B71,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
          (const char *)(unsigned int)v31,
          v48);
      LOBYTE(v32) = a6;
      v33 = ((__int64 (__fastcall *)(_QWORD **, __int64))(*v51)[13])(v51, v32);
      if ( v33 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1B73,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
          (const char *)(unsigned int)v33,
          v48);
      v34 = ((__int64 (__fastcall *)(_QWORD **, __int64))(*v51)[15])(v51, a11);
      if ( v34 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1B74,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
          (const char *)(unsigned int)v34,
          v48);
      LOBYTE(v35) = a9;
      v36 = ((__int64 (__fastcall *)(_QWORD **, __int64))(*v51)[9])(v51, v35);
      if ( v36 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1B75,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
          (const char *)(unsigned int)v36,
          v48);
      v37 = ((__int64 (__fastcall *)(_QWORD **, _QWORD))(*v51)[11])(v51, 0);
      if ( v37 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1B76,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
          (const char *)(unsigned int)v37,
          v48);
      v38 = ((__int64 (__fastcall *)(_QWORD **, _QWORD))(*v51)[17])(v51, 0);
      if ( v38 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1B77,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
          (const char *)(unsigned int)v38,
          v48);
      v52 = 0;
      v39 = v51;
      v40 = (__int64 (__fastcall *)(_QWORD **, GUID *, __int64 *))**v51;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v52);
      v41 = v40(v39, &GUID_8a04c0d7_c94b_425e_95b4_bf27faeaee89, &v52);
      if ( v41 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1B7A,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
          (const char *)(unsigned int)v41,
          v48);
      v42 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v52 + 152LL))(v52, 0);
      if ( v42 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1B7C,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
          (const char *)(unsigned int)v42,
          v48);
      LOBYTE(v43) = 1;
      v44 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v52 + 136LL))(v52, v43);
      if ( v44 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1B7D,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
          (const char *)(unsigned int)v44,
          v48);
      v45 = v54;
      started = Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_StartBundleProductInstallWithOptionsAsync(
                  (int)v57 - 112,
                  0,
                  (_DWORD)v56,
                  (_DWORD)v55,
                  (__int64)v54,
                  (__int64)v59,
                  (__int64)v18,
                  IsCallerInteractive,
                  a8,
                  v58,
                  (__int64)v51,
                  (__int64)a12);
      if ( started < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1B8A,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
          (const char *)(unsigned int)started,
          v49);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v52);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v51);
      WindowsDeleteString(v45);
      WindowsDeleteString(v55);
      WindowsDeleteString(v56);
      WindowsDeleteString(string);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B5A,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
        (const char *)(unsigned int)CallingProcessAndFunction,
        v47);
      WindowsDeleteString(string);
      result = v15;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1B8D,
                           (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
                           v16);
  }
  return result;
}

```

## disassembly

```asm
0x1800c3bb0  push    rbx
0x1800c3bb2  push    rsi
0x1800c3bb3  push    rdi
0x1800c3bb4  push    r12
0x1800c3bb6  push    r13
0x1800c3bb8  push    r14
0x1800c3bba  push    r15
0x1800c3bbc  sub     rsp, 100h
0x1800c3bc3  mov     rax, cs:__security_cookie
0x1800c3bca  xor     rax, rsp
0x1800c3bcd  mov     [rsp+138h+var_48], rax
0x1800c3bd5  mov     rdi, r9
0x1800c3bd8  mov     [rsp+138h+var_70], r9
0x1800c3be0  mov     [rsp+138h+var_98], r8
0x1800c3be8  mov     r15, rdx
0x1800c3beb  mov     [rsp+138h+var_80], rcx
0x1800c3bf3  mov     rbx, [rsp+138h+arg_20]
0x1800c3bfb  mov     rax, [rsp+138h+arg_48]
0x1800c3c03  mov     [rsp+138h+var_78], rax
0x1800c3c0b  mov     r13, [rsp+138h+arg_50]
0x1800c3c13  mov     r12, [rsp+138h+arg_58]
0x1800c3c1b  xor     esi, esi
0x1800c3c1d  mov     [r12], rsi
0x1800c3c21  mov     [rsp+138h+string], rsi
0x1800c3c29  xor     ecx, ecx; string
0x1800c3c2b  call    cs:__imp_WindowsDeleteString
0x1800c3c31  mov     [rsp+138h+string], rsi
0x1800c3c39  lea     r8, [rsp+138h+string]; HSTRING *
0x1800c3c41  lea     rdx, aWindowsApplica_26; "Windows::ApplicationModel::Store::Previ"...
0x1800c3c48  mov     rcx, rbx; HSTRING
0x1800c3c4b  call    ?GetCallingProcessAndFunction@@YAJPEAUHSTRING__@@PEBGPEAPEAU1@@Z; GetCallingProcessAndFunction(HSTRING__ *,ushort const *,HSTRING__ * *)
0x1800c3c50  mov     ebx, eax
0x1800c3c52  test    eax, eax
0x1800c3c54  jns     short loc_1800C3C88
0x1800c3c56  mov     rcx, [rsp+138h]; this
0x1800c3c5e  mov     r9d, eax; char *
0x1800c3c61  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c3c68  mov     edx, 1B5Ah; void *
0x1800c3c6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c3c72  nop
0x1800c3c73  mov     rcx, [rsp+138h+string]; string
0x1800c3c7b  call    cs:__imp_WindowsDeleteString
0x1800c3c81  mov     eax, ebx
0x1800c3c83  jmp     loc_1800C409F
0x1800c3c88  mov     r14, [rsp+138h+string]
0x1800c3c90  xor     edx, edx; length
0x1800c3c92  mov     rcx, r14; string
0x1800c3c95  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c3c9b  mov     rcx, rax; Str
0x1800c3c9e  mov     dl, 1; unsigned __int16 *
0x1800c3ca0  call    ?IsCallerInteractive@Utils@@YA_NPEBG_N@Z; Utils::IsCallerInteractive(ushort const *,bool)
0x1800c3ca5  mov     [rsp+138h+var_B8], al
0x1800c3cac  xor     edx, edx; length
0x1800c3cae  mov     rcx, r14; string
0x1800c3cb1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c3cb7  mov     rsi, rax
0x1800c3cba  xor     edx, edx; length
0x1800c3cbc  mov     rcx, rdi; string
0x1800c3cbf  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c3cc5  mov     rdi, rax
0x1800c3cc8  xor     edx, edx; length
0x1800c3cca  mov     rcx, [rsp+138h+var_98]; string
0x1800c3cd2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c3cd8  mov     rbx, rax
0x1800c3cdb  xor     edx, edx; length
0x1800c3cdd  mov     rcx, r15; string
0x1800c3ce0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c3ce6  mov     r9, rax
0x1800c3ce9  lea     r10, aFalse_0; "false"
0x1800c3cf0  lea     r8, aTrue; "true"
0x1800c3cf7  mov     rdx, r8
0x1800c3cfa  xor     r11d, r11d
0x1800c3cfd  cmp     [rsp+138h+arg_40], r11b
0x1800c3d05  cmovz   rdx, r10
0x1800c3d09  mov     rcx, r8
0x1800c3d0c  cmp     [rsp+138h+arg_38], r11b
0x1800c3d14  cmovz   rcx, r10
0x1800c3d18  mov     rax, r8
0x1800c3d1b  cmp     [rsp+138h+var_B8], r11b
0x1800c3d23  cmovz   rax, r10
0x1800c3d27  cmp     [rsp+138h+arg_28], r11b
0x1800c3d2f  cmovz   r8, r10
0x1800c3d33  mov     [rsp+138h+var_C0], rdx
0x1800c3d38  mov     [rsp+138h+var_C8], rcx
0x1800c3d3d  mov     [rsp+138h+var_D0], rax
0x1800c3d42  mov     [rsp+138h+var_D8], r8
0x1800c3d47  mov     [rsp+138h+var_E0], rsi
0x1800c3d4c  mov     [rsp+138h+var_E8], rdi
0x1800c3d51  mov     [rsp+138h+var_F0], rbx
0x1800c3d56  mov     [rsp+138h+var_F8], r9
0x1800c3d5b  xor     ebx, ebx
0x1800c3d5d  mov     [rsp+138h+var_100], rbx; unsigned __int16 *
0x1800c3d62  mov     [rsp+138h+var_108], rbx; char *
0x1800c3d67  lea     rax, aRequestStoreid_0; "request: storeId = %s, catalogId = %s, "...
0x1800c3d6e  mov     [rsp+138h+var_110], rax; unsigned __int16 *
0x1800c3d73  mov     [rsp+138h+var_118], 0FFFFFFFFh; int
0x1800c3d7b  lea     r9, aWindowsApplica_52; "Windows::ApplicationModel::Store::Previ"...
0x1800c3d82  mov     r8d, 1B68h; unsigned int
0x1800c3d88  lea     rsi, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c3d8f  mov     rdx, rsi; char *
0x1800c3d92  lea     ecx, [rbx+3]; unsigned int
0x1800c3d95  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800c3d9a  nop
0x1800c3d9b  xor     ecx, ecx; string
0x1800c3d9d  call    cs:__imp_WindowsDeleteString
0x1800c3da3  mov     [rsp+138h+var_98], rbx
0x1800c3dab  xor     ecx, ecx; string
0x1800c3dad  call    cs:__imp_WindowsDeleteString
0x1800c3db3  mov     [rsp+138h+var_90], rbx
0x1800c3dbb  xor     ecx, ecx; string
0x1800c3dbd  call    cs:__imp_WindowsDeleteString
0x1800c3dc3  mov     [rsp+138h+var_88], rbx
0x1800c3dcb  lea     r9, [rsp+138h+var_98]; HSTRING *
0x1800c3dd3  lea     r8, [rsp+138h+var_90]; HSTRING *
0x1800c3ddb  lea     rdx, [rsp+138h+var_88]; HSTRING *
0x1800c3de3  mov     rcx, r15; HSTRING
0x1800c3de6  call    ?SplitStoreId@AppId@@SAJPEAUHSTRING__@@PEAPEAU2@11@Z; AppId::SplitStoreId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *)
0x1800c3deb  mov     rcx, [rsp+138h]; this
0x1800c3df3  test    eax, eax
0x1800c3df5  js      loc_1800C40C2
0x1800c3dfb  mov     [rsp+138h+var_B0], rbx
0x1800c3e03  mov     [rsp+138h+var_50], rbx
0x1800c3e0b  mov     r9d, 47h ; 'G'; unsigned int
0x1800c3e11  lea     r8d, [r9+1]; unsigned int
0x1800c3e15  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_Store_Preview_InstallControl_AppInstallOptions@@3QBGB; "Windows.ApplicationModel.Store.Preview."...
0x1800c3e1c  lea     rcx, [rsp+138h+hstringHeader]; hstringHeader
0x1800c3e24  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800c3e29  nop
0x1800c3e2a  lea     rdx, [rsp+138h+var_B0]
0x1800c3e32  mov     rcx, [rsp+138h+var_50]
0x1800c3e3a  call    ??$ActivateInstance@V?$ComPtr@UIAppInstallOptions@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIAppInstallOptions@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallOptions>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallOptions>>)
0x1800c3e3f  mov     rcx, [rsp+138h]; this
0x1800c3e47  test    eax, eax
0x1800c3e49  js      loc_1800C40D3
0x1800c3e4f  mov     rcx, [rsp+138h+var_B0]
0x1800c3e57  mov     rax, [rcx]
0x1800c3e5a  mov     dl, [rsp+138h+arg_28]
0x1800c3e61  mov     rax, [rax+68h]
0x1800c3e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3e6a  mov     rcx, [rsp+138h]; this
0x1800c3e72  test    eax, eax
0x1800c3e74  js      loc_1800C40E4
0x1800c3e7a  mov     rcx, [rsp+138h+var_B0]
0x1800c3e82  mov     rax, [rcx]
0x1800c3e85  mov     rdx, r13
0x1800c3e88  mov     rax, [rax+78h]
0x1800c3e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3e91  mov     rcx, [rsp+138h]; this
0x1800c3e99  test    eax, eax
0x1800c3e9b  js      loc_1800C40F4
0x1800c3ea1  mov     rcx, [rsp+138h+var_B0]
0x1800c3ea9  mov     rax, [rcx]
0x1800c3eac  mov     dl, [rsp+138h+arg_40]
0x1800c3eb3  mov     rax, [rax+48h]
0x1800c3eb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3ebc  mov     rcx, [rsp+138h]; this
0x1800c3ec4  test    eax, eax
0x1800c3ec6  js      loc_1800C4104
0x1800c3ecc  mov     rcx, [rsp+138h+var_B0]
0x1800c3ed4  mov     rax, [rcx]
0x1800c3ed7  xor     edx, edx
0x1800c3ed9  mov     rax, [rax+58h]
0x1800c3edd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3ee2  mov     rcx, [rsp+138h]; this
0x1800c3eea  test    eax, eax
0x1800c3eec  js      loc_1800C4114
0x1800c3ef2  mov     rcx, [rsp+138h+var_B0]
0x1800c3efa  mov     rax, [rcx]
0x1800c3efd  xor     edx, edx
0x1800c3eff  mov     rax, [rax+88h]
0x1800c3f06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3f0b  mov     rcx, [rsp+138h]; this
0x1800c3f13  test    eax, eax
0x1800c3f15  js      loc_1800C4124
0x1800c3f1b  mov     [rsp+138h+var_A8], rbx
0x1800c3f23  mov     rbx, [rsp+138h+var_B0]
0x1800c3f2b  mov     rax, [rbx]
0x1800c3f2e  mov     rdi, [rax]
0x1800c3f31  lea     rcx, [rsp+138h+var_A8]
0x1800c3f39  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800c3f3e  lea     r8, [rsp+138h+var_A8]
0x1800c3f46  lea     rdx, _GUID_8a04c0d7_c94b_425e_95b4_bf27faeaee89
0x1800c3f4d  mov     rcx, rbx
0x1800c3f50  mov     rax, rdi
0x1800c3f53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3f58  nop
0x1800c3f59  mov     rcx, [rsp+138h]; this
0x1800c3f61  test    eax, eax
0x1800c3f63  js      loc_1800C4135
0x1800c3f69  mov     rcx, [rsp+138h+var_A8]
0x1800c3f71  mov     rax, [rcx]
0x1800c3f74  xor     edx, edx
0x1800c3f76  mov     rax, [rax+98h]
0x1800c3f7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3f82  mov     rcx, [rsp+138h]; this
0x1800c3f8a  test    eax, eax
0x1800c3f8c  js      loc_1800C4145
0x1800c3f92  mov     rcx, [rsp+138h+var_A8]
0x1800c3f9a  mov     rax, [rcx]
0x1800c3f9d  mov     dl, 1
0x1800c3f9f  mov     rax, [rax+88h]
0x1800c3fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3fab  mov     rcx, [rsp+138h]; this
0x1800c3fb3  test    eax, eax
0x1800c3fb5  js      loc_1800C4155
0x1800c3fbb  mov     rax, [rsp+138h+var_B0]
0x1800c3fc3  mov     rcx, [rsp+138h+var_80]
0x1800c3fcb  add     rcx, 0FFFFFFFFFFFFFF90h
0x1800c3fcf  mov     [rsp+138h+var_E0], r12
0x1800c3fd4  mov     [rsp+138h+var_E8], rax
0x1800c3fd9  mov     rax, [rsp+138h+var_78]
0x1800c3fe1  mov     [rsp+138h+var_F0], rax
0x1800c3fe6  mov     al, [rsp+138h+arg_38]
0x1800c3fed  mov     byte ptr [rsp+138h+var_F8], al
0x1800c3ff1  mov     al, [rsp+138h+var_B8]
0x1800c3ff8  mov     byte ptr [rsp+138h+var_100], al
0x1800c3ffc  mov     [rsp+138h+var_108], r14
0x1800c4001  mov     rax, [rsp+138h+var_70]
0x1800c4009  mov     [rsp+138h+var_110], rax
0x1800c400e  mov     rbx, [rsp+138h+var_98]
0x1800c4016  mov     qword ptr [rsp+138h+var_118], rbx; int
0x1800c401b  mov     r9, [rsp+138h+var_90]
0x1800c4023  mov     r8, [rsp+138h+var_88]
0x1800c402b  xor     edx, edx
0x1800c402d  call    ?_StartBundleProductInstallWithOptionsAsync@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAAJPEAUIUser@System@6@PEAUHSTRING__@@1111EE1PEAUIAppInstallOptions@23456@PEAPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@6@@Z; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_StartBundleProductInstallWithOptionsAsync(Windows::System::IUser *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,uchar,uchar,HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallOptions *,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> * *)
0x1800c4032  mov     rcx, [rsp+138h]; this
0x1800c403a  test    eax, eax
0x1800c403c  js      loc_1800C4165
0x1800c4042  lea     rcx, [rsp+138h+var_A8]
0x1800c404a  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800c404f  nop
0x1800c4050  lea     rcx, [rsp+138h+var_B0]
0x1800c4058  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800c405d  nop
0x1800c405e  mov     rcx, rbx; string
0x1800c4061  call    cs:__imp_WindowsDeleteString
0x1800c4067  nop
0x1800c4068  mov     rcx, [rsp+138h+var_90]; string
0x1800c4070  call    cs:__imp_WindowsDeleteString
0x1800c4076  nop
0x1800c4077  mov     rcx, [rsp+138h+var_88]; string
0x1800c407f  call    cs:__imp_WindowsDeleteString
0x1800c4085  nop
0x1800c4086  mov     rcx, [rsp+138h+string]; string
0x1800c408e  call    cs:__imp_WindowsDeleteString
0x1800c4094  xor     eax, eax
0x1800c4096  jmp     short loc_1800C409F
0x1800c4098  mov     eax, dword ptr [rsp+138h+var_B0]
0x1800c409f  mov     rcx, [rsp+138h+var_48]
0x1800c40a7  xor     rcx, rsp; StackCookie
0x1800c40aa  call    __security_check_cookie
0x1800c40af  add     rsp, 100h
0x1800c40b6  pop     r15
0x1800c40b8  pop     r14
0x1800c40ba  pop     r13
0x1800c40bc  pop     r12
0x1800c40be  pop     rdi
0x1800c40bf  pop     rsi
0x1800c40c0  pop     rbx
0x1800c40c1  retn
0x1800c40c2  mov     r9d, eax; char *
0x1800c40c5  mov     r8, rsi; unsigned int
0x1800c40c8  mov     edx, 1B6Eh; void *
0x1800c40cd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c40d3  mov     r9d, eax; char *
0x1800c40d6  mov     r8, rsi; unsigned int
0x1800c40d9  mov     edx, 1B71h; void *
0x1800c40de  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c40e4  mov     r9d, eax; char *
0x1800c40e7  mov     r8, rsi; unsigned int
0x1800c40ea  mov     edx, 1B73h; void *
0x1800c40ef  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c40f4  mov     r9d, eax; char *
0x1800c40f7  mov     r8, rsi; unsigned int
0x1800c40fa  mov     edx, 1B74h; void *
0x1800c40ff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c4104  mov     r9d, eax; char *
0x1800c4107  mov     r8, rsi; unsigned int
0x1800c410a  mov     edx, 1B75h; void *
0x1800c410f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c4114  mov     r9d, eax; char *
0x1800c4117  mov     r8, rsi; unsigned int
0x1800c411a  mov     edx, 1B76h; void *
0x1800c411f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c4124  mov     r9d, eax; char *
0x1800c4127  mov     r8, rsi; unsigned int
0x1800c412a  mov     edx, 1B77h; void *
0x1800c412f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c4135  mov     r9d, eax; char *
0x1800c4138  mov     r8, rsi; unsigned int
0x1800c413b  mov     edx, 1B7Ah; void *
0x1800c4140  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c4145  mov     r9d, eax; char *
0x1800c4148  mov     r8, rsi; unsigned int
0x1800c414b  mov     edx, 1B7Ch; void *
0x1800c4150  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c4155  mov     r9d, eax; char *
0x1800c4158  mov     r8, rsi; unsigned int
0x1800c415b  mov     edx, 1B7Dh; void *
0x1800c4160  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
  ... truncated ...
```
