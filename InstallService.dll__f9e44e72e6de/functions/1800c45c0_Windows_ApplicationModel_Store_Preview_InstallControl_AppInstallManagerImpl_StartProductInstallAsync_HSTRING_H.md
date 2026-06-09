# Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartProductInstallAsync(HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,uchar,uchar,uchar,uchar,HSTRING__ *,Windows::Management::Deployment::IPackageVolume *,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> * *)

- ea: `0x1800c45c0`
- end: `0x1800c47ea`
- name: `?StartProductInstallAsync@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@UEAAJPEAUHSTRING__@@000EEEE0PEAUIPackageVolume@Deployment@Management@6@PEAPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@6@@Z`
- size: `554`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, installer_update`

## callees

- `0x180010b74`
- `0x18003b08c`
- `0x18006e510`
- `0x180084280`
- `0x1800c45c0`
- `0x1800cd04c`
- `0x180105afc`
- `0x18012efec`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c45fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c460b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4618`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4654`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c46a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c46bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c46cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c46df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c479f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c47b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c47c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c47cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c45fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c460b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4618`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4654`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c46a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c46bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c46cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c46df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c479f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c47b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c47c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c47cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c46fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c46fe`

## string_xrefs

- `0x1800c468f`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c466a`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartProductInstallAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartProductInstallAsync(
        UserHelpers *a1,
        HSTRING a2,
        __int64 a3,
        __int64 a4,
        HSTRING a5,
        char a6,
        __int64 a7,
        char a8,
        char a9,
        __int64 a10,
        __int64 a11,
        HSTRING string)
{
  HSTRING v16; // rsi
  int started; // ebx
  int CallingProcessAndFunction; // eax
  unsigned int v19; // ebx
  wchar_t *StringRawBuffer; // rax
  const unsigned __int16 *v22; // rdx
  bool v23; // r8
  __int64 v24; // r9
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // rcx
  int StartProductInstallOptions; // eax
  __int64 v29; // [rsp+20h] [rbp-A8h]
  HSTRING v30; // [rsp+70h] [rbp-58h] BYREF
  HSTRING v31; // [rsp+78h] [rbp-50h] BYREF
  HSTRING v32; // [rsp+80h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v16 = string;
  *(_QWORD *)string = 0;
  started = UserHelpers::ValidateSingleUserApiCall(a1);
  if ( started >= 0 )
  {
    WindowsDeleteString(0);
    v30 = 0;
    WindowsDeleteString(0);
    v31 = 0;
    WindowsDeleteString(0);
    v32 = 0;
    started = AppId::SplitStoreId(a2, &v32, &v31, &v30);
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
      v19 = CallingProcessAndFunction;
      if ( CallingProcessAndFunction < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x10E9,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
          (const char *)(unsigned int)CallingProcessAndFunction,
          v29);
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v30);
        v30 = 0;
        WindowsDeleteString(v31);
        v31 = 0;
        WindowsDeleteString(v32);
        v32 = 0;
        return v19;
      }
      StringRawBuffer = (wchar_t *)WindowsGetStringRawBuffer(string, 0);
      LOBYTE(v22) = 1;
      LOBYTE(v29) = a9;
      LOBYTE(v24) = Utils::IsCallerInteractive(StringRawBuffer, v22, v23);
      LOBYTE(v25) = a6;
      LOBYTE(v26) = a8;
      LOBYTE(v27) = v24;
      StartProductInstallOptions = GetStartProductInstallOptions(v27, v26, v25, v24, v29, 0);
      started = Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_StartBundleProductInstallAsync(
                  (char *)a1 - 80,
                  0,
                  v32,
                  v31,
                  v30,
                  a3,
                  a4,
                  string,
                  a10,
                  0,
                  StartProductInstallOptions,
                  0,
                  0,
                  v16);
      WindowsDeleteString(string);
    }
    WindowsDeleteString(v30);
    WindowsDeleteString(v31);
    WindowsDeleteString(v32);
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x1800c45c0  push    rbx
0x1800c45c2  push    rsi
0x1800c45c3  push    rdi
0x1800c45c4  push    r12
0x1800c45c6  push    r13
0x1800c45c8  push    r14
0x1800c45ca  push    r15
0x1800c45cc  sub     rsp, 90h
0x1800c45d3  mov     r14, r9
0x1800c45d6  mov     r15, r8
0x1800c45d9  mov     rdi, rdx
0x1800c45dc  mov     r13, rcx
0x1800c45df  xor     r12d, r12d
0x1800c45e2  mov     rsi, [rsp+0C8h+string]
0x1800c45ea  mov     [rsi], r12
0x1800c45ed  call    ?ValidateSingleUserApiCall@UserHelpers@@YAJXZ; UserHelpers::ValidateSingleUserApiCall(void)
0x1800c45f2  mov     ebx, eax
0x1800c45f4  test    eax, eax
0x1800c45f6  js      loc_1800C47D5
0x1800c45fc  xor     ecx, ecx; string
0x1800c45fe  call    cs:__imp_WindowsDeleteString
0x1800c4604  mov     [rsp+0C8h+var_58], r12
0x1800c4609  xor     ecx, ecx; string
0x1800c460b  call    cs:__imp_WindowsDeleteString
0x1800c4611  mov     [rsp+0C8h+var_50], r12
0x1800c4616  xor     ecx, ecx; string
0x1800c4618  call    cs:__imp_WindowsDeleteString
0x1800c461e  mov     [rsp+0C8h+var_48], r12
0x1800c4626  lea     r9, [rsp+0C8h+var_58]; HSTRING *
0x1800c462b  lea     r8, [rsp+0C8h+var_50]; HSTRING *
0x1800c4630  lea     rdx, [rsp+0C8h+var_48]; HSTRING *
0x1800c4638  mov     rcx, rdi; HSTRING
0x1800c463b  call    ?SplitStoreId@AppId@@SAJPEAUHSTRING__@@PEAPEAU2@11@Z; AppId::SplitStoreId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *)
0x1800c4640  mov     ebx, eax
0x1800c4642  test    eax, eax
0x1800c4644  js      loc_1800C47AF
0x1800c464a  mov     [rsp+0C8h+string], r12
0x1800c4652  xor     ecx, ecx; string
0x1800c4654  call    cs:__imp_WindowsDeleteString
0x1800c465a  mov     [rsp+0C8h+string], r12
0x1800c4662  lea     r8, [rsp+0C8h+string]; HSTRING *
0x1800c466a  lea     rdx, aWindowsApplica_142; "Windows::ApplicationModel::Store::Previ"...
0x1800c4671  mov     rcx, [rsp+0C8h+arg_20]; HSTRING
0x1800c4679  call    ?GetCallingProcessAndFunction@@YAJPEAUHSTRING__@@PEBGPEAPEAU1@@Z; GetCallingProcessAndFunction(HSTRING__ *,ushort const *,HSTRING__ * *)
0x1800c467e  mov     ebx, eax
0x1800c4680  test    eax, eax
0x1800c4682  jns     short loc_1800C46F4
0x1800c4684  mov     rcx, [rsp+0C8h]; this
0x1800c468c  mov     r9d, eax; char *
0x1800c468f  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c4696  mov     edx, 10E9h; void *
0x1800c469b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c46a0  nop
0x1800c46a1  mov     rcx, [rsp+0C8h+string]; string
0x1800c46a9  call    cs:__imp_WindowsDeleteString
0x1800c46af  mov     [rsp+0C8h+string], r12
0x1800c46b7  mov     rcx, [rsp+0C8h+var_58]; string
0x1800c46bc  call    cs:__imp_WindowsDeleteString
0x1800c46c2  mov     [rsp+0C8h+var_58], r12
0x1800c46c7  mov     rcx, [rsp+0C8h+var_50]; string
0x1800c46cc  call    cs:__imp_WindowsDeleteString
0x1800c46d2  mov     [rsp+0C8h+var_50], r12
0x1800c46d7  mov     rcx, [rsp+0C8h+var_48]; string
0x1800c46df  call    cs:__imp_WindowsDeleteString
0x1800c46e5  mov     [rsp+0C8h+var_48], r12
0x1800c46ed  mov     eax, ebx
0x1800c46ef  jmp     loc_1800C47D7
0x1800c46f4  xor     edx, edx; length
0x1800c46f6  mov     rcx, [rsp+0C8h+string]; string
0x1800c46fe  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c4704  mov     rcx, rax; Str
0x1800c4707  mov     dl, 1; unsigned __int16 *
0x1800c4709  call    ?IsCallerInteractive@Utils@@YA_NPEBG_N@Z; Utils::IsCallerInteractive(ushort const *,bool)
0x1800c470e  mov     [rsp+0C8h+var_A0], r12
0x1800c4713  mov     cl, [rsp+0C8h+arg_40]
0x1800c471a  mov     byte ptr [rsp+0C8h+var_A8], cl
0x1800c471e  mov     r9b, al
0x1800c4721  mov     r8b, [rsp+0C8h+arg_28]
0x1800c4729  mov     dl, [rsp+0C8h+arg_38]
0x1800c4730  mov     cl, al
0x1800c4732  call    ?GetStartProductInstallOptions@@YA?AW4StartProductInstallOptions@@EEEEEPEAUIAppInstallOptions@InstallControl@Preview@Store@ApplicationModel@Windows@@@Z; GetStartProductInstallOptions(uchar,uchar,uchar,uchar,uchar,Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallOptions *)
0x1800c4737  mov     rdx, [rsp+0C8h+string]
0x1800c473f  lea     rcx, [r13-50h]
0x1800c4743  mov     [rsp+0C8h+var_60], rsi
0x1800c4748  mov     [rsp+0C8h+var_68], r12d
0x1800c474d  mov     [rsp+0C8h+var_70], r12d
0x1800c4752  mov     [rsp+0C8h+var_78], eax
0x1800c4756  mov     [rsp+0C8h+var_80], r12
0x1800c475b  mov     rax, [rsp+0C8h+arg_48]
0x1800c4763  mov     [rsp+0C8h+var_88], rax
0x1800c4768  mov     [rsp+0C8h+var_90], rdx
0x1800c476d  mov     [rsp+0C8h+var_98], r14
0x1800c4772  mov     [rsp+0C8h+var_A0], r15
0x1800c4777  mov     rax, [rsp+0C8h+var_58]
0x1800c477c  mov     [rsp+0C8h+var_A8], rax
0x1800c4781  mov     r9, [rsp+0C8h+var_50]
0x1800c4786  mov     r8, [rsp+0C8h+var_48]
0x1800c478e  xor     edx, edx
0x1800c4790  call    ?_StartBundleProductInstallAsync@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAAJPEAUIUser@System@6@PEAUHSTRING__@@111111PEAUIPackageVolume@Deployment@Management@6@W4StartProductInstallOptions@@W4AppInstallationToastNotificationMode@23456@4PEAPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@6@@Z; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_StartBundleProductInstallAsync(Windows::System::IUser *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,Windows::Management::Deployment::IPackageVolume *,StartProductInstallOptions,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallationToastNotificationMode,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallationToastNotificationMode,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> * *)
0x1800c4795  mov     ebx, eax
0x1800c4797  mov     rcx, [rsp+0C8h+string]; string
0x1800c479f  call    cs:__imp_WindowsDeleteString
0x1800c47a5  nop
0x1800c47a6  jmp     short loc_1800C47AF
0x1800c47a8  mov     ebx, dword ptr [rsp+0C8h+string]
0x1800c47af  mov     rcx, [rsp+0C8h+var_58]; string
0x1800c47b4  call    cs:__imp_WindowsDeleteString
0x1800c47ba  nop
0x1800c47bb  mov     rcx, [rsp+0C8h+var_50]; string
0x1800c47c0  call    cs:__imp_WindowsDeleteString
0x1800c47c6  nop
0x1800c47c7  mov     rcx, [rsp+0C8h+var_48]; string
0x1800c47cf  call    cs:__imp_WindowsDeleteString
0x1800c47d5  mov     eax, ebx
0x1800c47d7  add     rsp, 90h
0x1800c47de  pop     r15
0x1800c47e0  pop     r14
0x1800c47e2  pop     r13
0x1800c47e4  pop     r12
0x1800c47e6  pop     rdi
0x1800c47e7  pop     rsi
0x1800c47e8  pop     rbx
0x1800c47e9  retn
```
