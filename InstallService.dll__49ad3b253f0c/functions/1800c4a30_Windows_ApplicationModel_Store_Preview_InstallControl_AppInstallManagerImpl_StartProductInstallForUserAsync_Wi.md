# Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartProductInstallForUserAsync(Windows::System::IUser *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,uchar,uchar,uchar,uchar,HSTRING__ *,Windows::Management::Deployment::IPackageVolume *,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> * *)

- ea: `0x1800c4a30`
- end: `0x1800c4c66`
- name: `?StartProductInstallForUserAsync@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@UEAAJPEAUIUser@System@6@PEAUHSTRING__@@111EEEE1PEAUIPackageVolume@Deployment@Management@6@PEAPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@6@@Z`
- size: `566`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180010b74`
- `0x18003b08c`
- `0x18006e510`
- `0x180084280`
- `0x1800c4a30`
- `0x1800cd04c`
- `0x180105afc`
- `0x18012efb0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4a71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4a7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4a8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4ac7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4b1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4b2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4b3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4b52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4c1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4c30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4c3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4c4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4a71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4a7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4a8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4ac7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4b1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4b2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4b3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4b52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4c1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4c30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4c3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4c4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c4b71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c4b71`

## string_xrefs

- `0x1800c4b02`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c4add`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartProductInstallForUserAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartProductInstallForUserAsync(
        __int64 a1,
        UserHelpers *a2,
        HSTRING a3,
        HSTRING a4,
        HSTRING a5,
        HSTRING a6,
        char a7,
        __int64 a8,
        char a9,
        char a10,
        WindowsUpdate::CommonTelemetry *a11,
        __int64 a12,
        HSTRING string)
{
  HSTRING v17; // r14
  int started; // ebx
  int CallingProcessAndFunction; // eax
  unsigned int v20; // ebx
  wchar_t *StringRawBuffer; // rax
  const unsigned __int16 *v23; // rdx
  bool v24; // r8
  __int64 v25; // r9
  __int64 v26; // r8
  __int64 v27; // rdx
  __int64 v28; // rcx
  char StartProductInstallOptions; // al
  __int64 v30; // [rsp+20h] [rbp-A8h]
  HSTRING v31; // [rsp+70h] [rbp-58h] BYREF
  HSTRING v32; // [rsp+78h] [rbp-50h] BYREF
  HSTRING v33; // [rsp+80h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v17 = string;
  *(_QWORD *)string = 0;
  started = UserHelpers::ValidateMultiUserApiCall(a2, a2);
  if ( started >= 0 )
  {
    WindowsDeleteString(0);
    v31 = 0;
    WindowsDeleteString(0);
    v32 = 0;
    WindowsDeleteString(0);
    v33 = 0;
    started = AppId::SplitStoreId(a3, &v33, &v32, &v31);
    if ( started >= 0 )
    {
      string = 0;
      WindowsDeleteString(0);
      string = 0;
      CallingProcessAndFunction = GetCallingProcessAndFunction(
                                    a6,
                                    L"Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::St"
                                     "artProductInstallForUserAsync",
                                    &string);
      v20 = CallingProcessAndFunction;
      if ( CallingProcessAndFunction < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1123,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
          (const char *)(unsigned int)CallingProcessAndFunction,
          v30);
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v31);
        v31 = 0;
        WindowsDeleteString(v32);
        v32 = 0;
        WindowsDeleteString(v33);
        v33 = 0;
        return v20;
      }
      StringRawBuffer = (wchar_t *)WindowsGetStringRawBuffer(string, 0);
      LOBYTE(v23) = 1;
      LOBYTE(v30) = a10;
      LOBYTE(v25) = Utils::IsCallerInteractive(StringRawBuffer, v23, v24);
      LOBYTE(v26) = a7;
      LOBYTE(v27) = a9;
      LOBYTE(v28) = v25;
      StartProductInstallOptions = GetStartProductInstallOptions(v28, v27, v26, v25, v30, 0);
      started = Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_StartBundleProductInstallAsync(
                  a1 - 80,
                  (__int64)a2,
                  (char *)v33,
                  v32,
                  (__int64)v31,
                  a4,
                  a5,
                  string,
                  a11,
                  0,
                  StartProductInstallOptions,
                  0,
                  0,
                  v17);
      WindowsDeleteString(string);
    }
    WindowsDeleteString(v31);
    WindowsDeleteString(v32);
    WindowsDeleteString(v33);
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x1800c4a30  push    rbx
0x1800c4a32  push    rsi
0x1800c4a33  push    rdi
0x1800c4a34  push    r12
0x1800c4a36  push    r13
0x1800c4a38  push    r14
0x1800c4a3a  push    r15
0x1800c4a3c  sub     rsp, 90h
0x1800c4a43  mov     r15, r9
0x1800c4a46  mov     rdi, r8
0x1800c4a49  mov     rsi, rdx
0x1800c4a4c  mov     r13, rcx
0x1800c4a4f  xor     r12d, r12d
0x1800c4a52  mov     r14, [rsp+0C8h+string]
0x1800c4a5a  mov     [r14], r12
0x1800c4a5d  mov     rcx, rdx; this
0x1800c4a60  call    ?ValidateMultiUserApiCall@UserHelpers@@YAJPEAUIUser@System@Windows@@@Z; UserHelpers::ValidateMultiUserApiCall(Windows::System::IUser *)
0x1800c4a65  mov     ebx, eax
0x1800c4a67  test    eax, eax
0x1800c4a69  js      loc_1800C4C51
0x1800c4a6f  xor     ecx, ecx; string
0x1800c4a71  call    cs:__imp_WindowsDeleteString
0x1800c4a77  mov     [rsp+0C8h+var_58], r12
0x1800c4a7c  xor     ecx, ecx; string
0x1800c4a7e  call    cs:__imp_WindowsDeleteString
0x1800c4a84  mov     [rsp+0C8h+var_50], r12
0x1800c4a89  xor     ecx, ecx; string
0x1800c4a8b  call    cs:__imp_WindowsDeleteString
0x1800c4a91  mov     [rsp+0C8h+var_48], r12
0x1800c4a99  lea     r9, [rsp+0C8h+var_58]; HSTRING *
0x1800c4a9e  lea     r8, [rsp+0C8h+var_50]; HSTRING *
0x1800c4aa3  lea     rdx, [rsp+0C8h+var_48]; HSTRING *
0x1800c4aab  mov     rcx, rdi; HSTRING
0x1800c4aae  call    ?SplitStoreId@AppId@@SAJPEAUHSTRING__@@PEAPEAU2@11@Z; AppId::SplitStoreId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *)
0x1800c4ab3  mov     ebx, eax
0x1800c4ab5  test    eax, eax
0x1800c4ab7  js      loc_1800C4C2B
0x1800c4abd  mov     [rsp+0C8h+string], r12
0x1800c4ac5  xor     ecx, ecx; string
0x1800c4ac7  call    cs:__imp_WindowsDeleteString
0x1800c4acd  mov     [rsp+0C8h+string], r12
0x1800c4ad5  lea     r8, [rsp+0C8h+string]; HSTRING *
0x1800c4add  lea     rdx, aWindowsApplica_95; "Windows::ApplicationModel::Store::Previ"...
0x1800c4ae4  mov     rcx, [rsp+0C8h+arg_28]; HSTRING
0x1800c4aec  call    ?GetCallingProcessAndFunction@@YAJPEAUHSTRING__@@PEBGPEAPEAU1@@Z; GetCallingProcessAndFunction(HSTRING__ *,ushort const *,HSTRING__ * *)
0x1800c4af1  mov     ebx, eax
0x1800c4af3  test    eax, eax
0x1800c4af5  jns     short loc_1800C4B67
0x1800c4af7  mov     rcx, [rsp+0C8h]; this
0x1800c4aff  mov     r9d, eax; char *
0x1800c4b02  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c4b09  mov     edx, 1123h; void *
0x1800c4b0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c4b13  nop
0x1800c4b14  mov     rcx, [rsp+0C8h+string]; string
0x1800c4b1c  call    cs:__imp_WindowsDeleteString
0x1800c4b22  mov     [rsp+0C8h+string], r12
0x1800c4b2a  mov     rcx, [rsp+0C8h+var_58]; string
0x1800c4b2f  call    cs:__imp_WindowsDeleteString
0x1800c4b35  mov     [rsp+0C8h+var_58], r12
0x1800c4b3a  mov     rcx, [rsp+0C8h+var_50]; string
0x1800c4b3f  call    cs:__imp_WindowsDeleteString
0x1800c4b45  mov     [rsp+0C8h+var_50], r12
0x1800c4b4a  mov     rcx, [rsp+0C8h+var_48]; string
0x1800c4b52  call    cs:__imp_WindowsDeleteString
0x1800c4b58  mov     [rsp+0C8h+var_48], r12
0x1800c4b60  mov     eax, ebx
0x1800c4b62  jmp     loc_1800C4C53
0x1800c4b67  xor     edx, edx; length
0x1800c4b69  mov     rcx, [rsp+0C8h+string]; string
0x1800c4b71  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c4b77  mov     rcx, rax; Str
0x1800c4b7a  mov     dl, 1; unsigned __int16 *
0x1800c4b7c  call    ?IsCallerInteractive@Utils@@YA_NPEBG_N@Z; Utils::IsCallerInteractive(ushort const *,bool)
0x1800c4b81  mov     [rsp+0C8h+var_A0], r12
0x1800c4b86  mov     cl, [rsp+0C8h+arg_48]
0x1800c4b8d  mov     byte ptr [rsp+0C8h+var_A8], cl
0x1800c4b91  mov     r9b, al
0x1800c4b94  mov     r8b, [rsp+0C8h+arg_30]
0x1800c4b9c  mov     dl, [rsp+0C8h+arg_40]
0x1800c4ba3  mov     cl, al
0x1800c4ba5  call    ?GetStartProductInstallOptions@@YA?AW4StartProductInstallOptions@@EEEEEPEAUIAppInstallOptions@InstallControl@Preview@Store@ApplicationModel@Windows@@@Z; GetStartProductInstallOptions(uchar,uchar,uchar,uchar,uchar,Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallOptions *)
0x1800c4baa  mov     rdx, [rsp+0C8h+string]
0x1800c4bb2  lea     rcx, [r13-50h]
0x1800c4bb6  mov     [rsp+0C8h+var_60], r14
0x1800c4bbb  mov     [rsp+0C8h+var_68], r12d
0x1800c4bc0  mov     [rsp+0C8h+var_70], r12d
0x1800c4bc5  mov     [rsp+0C8h+var_78], eax
0x1800c4bc9  mov     [rsp+0C8h+var_80], r12
0x1800c4bce  mov     rax, [rsp+0C8h+arg_50]
0x1800c4bd6  mov     [rsp+0C8h+var_88], rax
0x1800c4bdb  mov     [rsp+0C8h+var_90], rdx
0x1800c4be0  mov     rax, [rsp+0C8h+arg_20]
0x1800c4be8  mov     [rsp+0C8h+var_98], rax
0x1800c4bed  mov     [rsp+0C8h+var_A0], r15
0x1800c4bf2  mov     rax, [rsp+0C8h+var_58]
0x1800c4bf7  mov     [rsp+0C8h+var_A8], rax
0x1800c4bfc  mov     r9, [rsp+0C8h+var_50]
0x1800c4c01  mov     r8, [rsp+0C8h+var_48]
0x1800c4c09  mov     rdx, rsi
0x1800c4c0c  call    ?_StartBundleProductInstallAsync@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAAJPEAUIUser@System@6@PEAUHSTRING__@@111111PEAUIPackageVolume@Deployment@Management@6@W4StartProductInstallOptions@@W4AppInstallationToastNotificationMode@23456@4PEAPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@6@@Z; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_StartBundleProductInstallAsync(Windows::System::IUser *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,Windows::Management::Deployment::IPackageVolume *,StartProductInstallOptions,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallationToastNotificationMode,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallationToastNotificationMode,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> * *)
0x1800c4c11  mov     ebx, eax
0x1800c4c13  mov     rcx, [rsp+0C8h+string]; string
0x1800c4c1b  call    cs:__imp_WindowsDeleteString
0x1800c4c21  nop
0x1800c4c22  jmp     short loc_1800C4C2B
0x1800c4c24  mov     ebx, dword ptr [rsp+0C8h+string]
0x1800c4c2b  mov     rcx, [rsp+0C8h+var_58]; string
0x1800c4c30  call    cs:__imp_WindowsDeleteString
0x1800c4c36  nop
0x1800c4c37  mov     rcx, [rsp+0C8h+var_50]; string
0x1800c4c3c  call    cs:__imp_WindowsDeleteString
0x1800c4c42  nop
0x1800c4c43  mov     rcx, [rsp+0C8h+var_48]; string
0x1800c4c4b  call    cs:__imp_WindowsDeleteString
0x1800c4c51  mov     eax, ebx
0x1800c4c53  add     rsp, 90h
0x1800c4c5a  pop     r15
0x1800c4c5c  pop     r14
0x1800c4c5e  pop     r13
0x1800c4c60  pop     r12
0x1800c4c62  pop     rdi
0x1800c4c63  pop     rsi
0x1800c4c64  pop     rbx
0x1800c4c65  retn
```
