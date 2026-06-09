# Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartProductInstallAsync(HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,uchar,uchar,HSTRING__ *,Windows::Management::Deployment::IPackageVolume *,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> * *)

- ea: `0x1800c4380`
- end: `0x1800c45ad`
- name: `?StartProductInstallAsync@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@UEAAJPEAUHSTRING__@@000EE0PEAUIPackageVolume@Deployment@Management@6@PEAPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@6@@Z`
- size: `557`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180010b74`
- `0x18003b08c`
- `0x18006e510`
- `0x180084280`
- `0x1800c4380`
- `0x1800cd04c`
- `0x180105afc`
- `0x18012efec`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c43be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c43cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c43d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4414`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4469`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c447c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c448c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c449f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4562`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4577`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4583`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4592`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c43be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c43cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c43d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4414`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4469`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c447c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c448c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c449f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4562`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4577`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4583`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4592`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c44be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c44be`

## string_xrefs

- `0x1800c444f`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c442a`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartProductInstallAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartProductInstallAsync(
        UserHelpers *a1,
        HSTRING a2,
        HSTRING a3,
        HSTRING a4,
        HSTRING a5,
        char a6,
        char a7,
        WindowsUpdate::CommonTelemetry *a8,
        __int64 a9,
        HSTRING string)
{
  HSTRING v14; // rsi
  int started; // ebx
  int CallingProcessAndFunction; // eax
  unsigned int v17; // ebx
  wchar_t *StringRawBuffer; // rax
  const unsigned __int16 *v20; // rdx
  bool v21; // r8
  bool IsCallerInteractive; // al
  __int64 v23; // r9
  __int64 v24; // r8
  __int64 v25; // rcx
  char StartProductInstallOptions; // al
  __int64 v27; // [rsp+20h] [rbp-A8h]
  HSTRING v28; // [rsp+70h] [rbp-58h] BYREF
  HSTRING v29; // [rsp+78h] [rbp-50h] BYREF
  HSTRING v30; // [rsp+80h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v14 = string;
  *(_QWORD *)string = 0;
  started = UserHelpers::ValidateSingleUserApiCall(a1);
  if ( started >= 0 )
  {
    WindowsDeleteString(0);
    v28 = 0;
    WindowsDeleteString(0);
    v29 = 0;
    WindowsDeleteString(0);
    v30 = 0;
    started = AppId::SplitStoreId(a2, &v30, &v29, &v28);
    if ( started >= 0 )
    {
      string = 0;
      WindowsDeleteString(0);
      string = 0;
      CallingProcessAndFunction = GetCallingProcessAndFunction(
                                    a5,
                                    L"Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::St"
                                     "artProductInstallAsync",
                                    &string);
      v17 = CallingProcessAndFunction;
      if ( CallingProcessAndFunction < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8DE,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
          (const char *)(unsigned int)CallingProcessAndFunction,
          v27);
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v28);
        v28 = 0;
        WindowsDeleteString(v29);
        v29 = 0;
        WindowsDeleteString(v30);
        v30 = 0;
        return v17;
      }
      StringRawBuffer = (wchar_t *)WindowsGetStringRawBuffer(string, 0);
      LOBYTE(v20) = 1;
      IsCallerInteractive = Utils::IsCallerInteractive(StringRawBuffer, v20, v21);
      LOBYTE(v27) = a7;
      LOBYTE(v23) = 1;
      LOBYTE(v24) = a6;
      LOBYTE(v25) = IsCallerInteractive;
      StartProductInstallOptions = GetStartProductInstallOptions(v25, 0, v24, v23, v27, 0);
      started = Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_StartBundleProductInstallAsync(
                  (__int64)a1 - 16,
                  0,
                  (char *)v30,
                  v29,
                  (__int64)v28,
                  a3,
                  a4,
                  string,
                  a8,
                  a9,
                  StartProductInstallOptions,
                  0,
                  0,
                  v14);
      WindowsDeleteString(string);
    }
    WindowsDeleteString(v28);
    WindowsDeleteString(v29);
    WindowsDeleteString(v30);
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x1800c4380  push    rbx
0x1800c4382  push    rsi
0x1800c4383  push    rdi
0x1800c4384  push    r12
0x1800c4386  push    r13
0x1800c4388  push    r14
0x1800c438a  push    r15
0x1800c438c  sub     rsp, 90h
0x1800c4393  mov     r14, r9
0x1800c4396  mov     r15, r8
0x1800c4399  mov     rdi, rdx
0x1800c439c  mov     r13, rcx
0x1800c439f  xor     r12d, r12d
0x1800c43a2  mov     rsi, [rsp+0C8h+string]
0x1800c43aa  mov     [rsi], r12
0x1800c43ad  call    ?ValidateSingleUserApiCall@UserHelpers@@YAJXZ; UserHelpers::ValidateSingleUserApiCall(void)
0x1800c43b2  mov     ebx, eax
0x1800c43b4  test    eax, eax
0x1800c43b6  js      loc_1800C4598
0x1800c43bc  xor     ecx, ecx; string
0x1800c43be  call    cs:__imp_WindowsDeleteString
0x1800c43c4  mov     [rsp+0C8h+var_58], r12
0x1800c43c9  xor     ecx, ecx; string
0x1800c43cb  call    cs:__imp_WindowsDeleteString
0x1800c43d1  mov     [rsp+0C8h+var_50], r12
0x1800c43d6  xor     ecx, ecx; string
0x1800c43d8  call    cs:__imp_WindowsDeleteString
0x1800c43de  mov     [rsp+0C8h+var_48], r12
0x1800c43e6  lea     r9, [rsp+0C8h+var_58]; HSTRING *
0x1800c43eb  lea     r8, [rsp+0C8h+var_50]; HSTRING *
0x1800c43f0  lea     rdx, [rsp+0C8h+var_48]; HSTRING *
0x1800c43f8  mov     rcx, rdi; HSTRING
0x1800c43fb  call    ?SplitStoreId@AppId@@SAJPEAUHSTRING__@@PEAPEAU2@11@Z; AppId::SplitStoreId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *)
0x1800c4400  mov     ebx, eax
0x1800c4402  test    eax, eax
0x1800c4404  js      loc_1800C4572
0x1800c440a  mov     [rsp+0C8h+string], r12
0x1800c4412  xor     ecx, ecx; string
0x1800c4414  call    cs:__imp_WindowsDeleteString
0x1800c441a  mov     [rsp+0C8h+string], r12
0x1800c4422  lea     r8, [rsp+0C8h+string]; HSTRING *
0x1800c442a  lea     rdx, aWindowsApplica_142; "Windows::ApplicationModel::Store::Previ"...
0x1800c4431  mov     rcx, [rsp+0C8h+arg_20]; HSTRING
0x1800c4439  call    ?GetCallingProcessAndFunction@@YAJPEAUHSTRING__@@PEBGPEAPEAU1@@Z; GetCallingProcessAndFunction(HSTRING__ *,ushort const *,HSTRING__ * *)
0x1800c443e  mov     ebx, eax
0x1800c4440  test    eax, eax
0x1800c4442  jns     short loc_1800C44B4
0x1800c4444  mov     rcx, [rsp+0C8h]; this
0x1800c444c  mov     r9d, eax; char *
0x1800c444f  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c4456  mov     edx, 8DEh; void *
0x1800c445b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c4460  nop
0x1800c4461  mov     rcx, [rsp+0C8h+string]; string
0x1800c4469  call    cs:__imp_WindowsDeleteString
0x1800c446f  mov     [rsp+0C8h+string], r12
0x1800c4477  mov     rcx, [rsp+0C8h+var_58]; string
0x1800c447c  call    cs:__imp_WindowsDeleteString
0x1800c4482  mov     [rsp+0C8h+var_58], r12
0x1800c4487  mov     rcx, [rsp+0C8h+var_50]; string
0x1800c448c  call    cs:__imp_WindowsDeleteString
0x1800c4492  mov     [rsp+0C8h+var_50], r12
0x1800c4497  mov     rcx, [rsp+0C8h+var_48]; string
0x1800c449f  call    cs:__imp_WindowsDeleteString
0x1800c44a5  mov     [rsp+0C8h+var_48], r12
0x1800c44ad  mov     eax, ebx
0x1800c44af  jmp     loc_1800C459A
0x1800c44b4  xor     edx, edx; length
0x1800c44b6  mov     rcx, [rsp+0C8h+string]; string
0x1800c44be  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c44c4  mov     rcx, rax; Str
0x1800c44c7  mov     dl, 1; unsigned __int16 *
0x1800c44c9  call    ?IsCallerInteractive@Utils@@YA_NPEBG_N@Z; Utils::IsCallerInteractive(ushort const *,bool)
0x1800c44ce  mov     [rsp+0C8h+var_A0], r12
0x1800c44d3  mov     cl, [rsp+0C8h+arg_30]
0x1800c44da  mov     byte ptr [rsp+0C8h+var_A8], cl
0x1800c44de  mov     r9b, 1
0x1800c44e1  mov     r8b, [rsp+0C8h+arg_28]
0x1800c44e9  xor     edx, edx
0x1800c44eb  mov     cl, al
0x1800c44ed  call    ?GetStartProductInstallOptions@@YA?AW4StartProductInstallOptions@@EEEEEPEAUIAppInstallOptions@InstallControl@Preview@Store@ApplicationModel@Windows@@@Z; GetStartProductInstallOptions(uchar,uchar,uchar,uchar,uchar,Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallOptions *)
0x1800c44f2  mov     rdx, [rsp+0C8h+string]
0x1800c44fa  lea     rcx, [r13-10h]
0x1800c44fe  mov     [rsp+0C8h+var_60], rsi
0x1800c4503  mov     [rsp+0C8h+var_68], r12d
0x1800c4508  mov     [rsp+0C8h+var_70], r12d
0x1800c450d  mov     [rsp+0C8h+var_78], eax
0x1800c4511  mov     rax, [rsp+0C8h+arg_40]
0x1800c4519  mov     [rsp+0C8h+var_80], rax
0x1800c451e  mov     rax, [rsp+0C8h+arg_38]
0x1800c4526  mov     [rsp+0C8h+var_88], rax
0x1800c452b  mov     [rsp+0C8h+var_90], rdx
0x1800c4530  mov     [rsp+0C8h+var_98], r14
0x1800c4535  mov     [rsp+0C8h+var_A0], r15
0x1800c453a  mov     rax, [rsp+0C8h+var_58]
0x1800c453f  mov     [rsp+0C8h+var_A8], rax
0x1800c4544  mov     r9, [rsp+0C8h+var_50]
0x1800c4549  mov     r8, [rsp+0C8h+var_48]
0x1800c4551  xor     edx, edx
0x1800c4553  call    ?_StartBundleProductInstallAsync@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAAJPEAUIUser@System@6@PEAUHSTRING__@@111111PEAUIPackageVolume@Deployment@Management@6@W4StartProductInstallOptions@@W4AppInstallationToastNotificationMode@23456@4PEAPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@6@@Z; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_StartBundleProductInstallAsync(Windows::System::IUser *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,Windows::Management::Deployment::IPackageVolume *,StartProductInstallOptions,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallationToastNotificationMode,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallationToastNotificationMode,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> * *)
0x1800c4558  mov     ebx, eax
0x1800c455a  mov     rcx, [rsp+0C8h+string]; string
0x1800c4562  call    cs:__imp_WindowsDeleteString
0x1800c4568  nop
0x1800c4569  jmp     short loc_1800C4572
0x1800c456b  mov     ebx, dword ptr [rsp+0C8h+string]
0x1800c4572  mov     rcx, [rsp+0C8h+var_58]; string
0x1800c4577  call    cs:__imp_WindowsDeleteString
0x1800c457d  nop
0x1800c457e  mov     rcx, [rsp+0C8h+var_50]; string
0x1800c4583  call    cs:__imp_WindowsDeleteString
0x1800c4589  nop
0x1800c458a  mov     rcx, [rsp+0C8h+var_48]; string
0x1800c4592  call    cs:__imp_WindowsDeleteString
0x1800c4598  mov     eax, ebx
0x1800c459a  add     rsp, 90h
0x1800c45a1  pop     r15
0x1800c45a3  pop     r14
0x1800c45a5  pop     r13
0x1800c45a7  pop     r12
0x1800c45a9  pop     rdi
0x1800c45aa  pop     rsi
0x1800c45ab  pop     rbx
0x1800c45ac  retn
```
