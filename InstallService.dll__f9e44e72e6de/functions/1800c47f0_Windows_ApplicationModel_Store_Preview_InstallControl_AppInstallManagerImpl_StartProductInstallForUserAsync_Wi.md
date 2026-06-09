# Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartProductInstallForUserAsync(Windows::System::IUser *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,uchar,uchar,HSTRING__ *,Windows::Management::Deployment::IPackageVolume *,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> * *)

- ea: `0x1800c47f0`
- end: `0x1800c4a29`
- name: `?StartProductInstallForUserAsync@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@UEAAJPEAUIUser@System@6@PEAUHSTRING__@@111EE1PEAUIPackageVolume@Deployment@Management@6@PEAPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@6@@Z`
- size: `569`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, installer_update`

## callees

- `0x180010b74`
- `0x18003b08c`
- `0x18006e510`
- `0x180084280`
- `0x1800c47f0`
- `0x1800cd04c`
- `0x180105afc`
- `0x18012efb0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4831`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c483e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c484b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4887`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c48dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c48ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c48ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4912`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c49de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c49f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c49ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4a0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4831`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c483e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c484b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4887`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c48dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c48ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c48ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4912`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c49de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c49f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c49ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4a0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c4931`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c4931`

## string_xrefs

- `0x1800c48c2`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c489d`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartProductInstallForUserAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartProductInstallForUserAsync(
        __int64 a1,
        UserHelpers *a2,
        HSTRING a3,
        __int64 a4,
        __int64 a5,
        HSTRING a6,
        char a7,
        char a8,
        __int64 a9,
        __int64 a10,
        HSTRING string)
{
  HSTRING v15; // r14
  int started; // ebx
  int CallingProcessAndFunction; // eax
  unsigned int v18; // ebx
  wchar_t *StringRawBuffer; // rax
  const unsigned __int16 *v21; // rdx
  bool v22; // r8
  bool IsCallerInteractive; // al
  __int64 v24; // r9
  __int64 v25; // r8
  __int64 v26; // rcx
  int StartProductInstallOptions; // eax
  __int64 v28; // [rsp+20h] [rbp-A8h]
  HSTRING v29; // [rsp+70h] [rbp-58h] BYREF
  HSTRING v30; // [rsp+78h] [rbp-50h] BYREF
  HSTRING v31; // [rsp+80h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v15 = string;
  *(_QWORD *)string = 0;
  started = UserHelpers::ValidateMultiUserApiCall(a2, a2);
  if ( started >= 0 )
  {
    WindowsDeleteString(0);
    v29 = 0;
    WindowsDeleteString(0);
    v30 = 0;
    WindowsDeleteString(0);
    v31 = 0;
    started = AppId::SplitStoreId(a3, &v31, &v30, &v29);
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
      v18 = CallingProcessAndFunction;
      if ( CallingProcessAndFunction < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x915,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
          (const char *)(unsigned int)CallingProcessAndFunction,
          v28);
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v29);
        v29 = 0;
        WindowsDeleteString(v30);
        v30 = 0;
        WindowsDeleteString(v31);
        v31 = 0;
        return v18;
      }
      StringRawBuffer = (wchar_t *)WindowsGetStringRawBuffer(string, 0);
      LOBYTE(v21) = 1;
      IsCallerInteractive = Utils::IsCallerInteractive(StringRawBuffer, v21, v22);
      LOBYTE(v28) = a8;
      LOBYTE(v24) = 1;
      LOBYTE(v25) = a7;
      LOBYTE(v26) = IsCallerInteractive;
      StartProductInstallOptions = GetStartProductInstallOptions(v26, 0, v25, v24, v28, 0);
      started = Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_StartBundleProductInstallAsync(
                  a1 - 16,
                  a2,
                  v31,
                  v30,
                  v29,
                  a4,
                  a5,
                  string,
                  a9,
                  a10,
                  StartProductInstallOptions,
                  0,
                  0,
                  v15);
      WindowsDeleteString(string);
    }
    WindowsDeleteString(v29);
    WindowsDeleteString(v30);
    WindowsDeleteString(v31);
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x1800c47f0  push    rbx
0x1800c47f2  push    rsi
0x1800c47f3  push    rdi
0x1800c47f4  push    r12
0x1800c47f6  push    r13
0x1800c47f8  push    r14
0x1800c47fa  push    r15
0x1800c47fc  sub     rsp, 90h
0x1800c4803  mov     r15, r9
0x1800c4806  mov     rdi, r8
0x1800c4809  mov     rsi, rdx
0x1800c480c  mov     r13, rcx
0x1800c480f  xor     r12d, r12d
0x1800c4812  mov     r14, [rsp+0C8h+string]
0x1800c481a  mov     [r14], r12
0x1800c481d  mov     rcx, rdx; this
0x1800c4820  call    ?ValidateMultiUserApiCall@UserHelpers@@YAJPEAUIUser@System@Windows@@@Z; UserHelpers::ValidateMultiUserApiCall(Windows::System::IUser *)
0x1800c4825  mov     ebx, eax
0x1800c4827  test    eax, eax
0x1800c4829  js      loc_1800C4A14
0x1800c482f  xor     ecx, ecx; string
0x1800c4831  call    cs:__imp_WindowsDeleteString
0x1800c4837  mov     [rsp+0C8h+var_58], r12
0x1800c483c  xor     ecx, ecx; string
0x1800c483e  call    cs:__imp_WindowsDeleteString
0x1800c4844  mov     [rsp+0C8h+var_50], r12
0x1800c4849  xor     ecx, ecx; string
0x1800c484b  call    cs:__imp_WindowsDeleteString
0x1800c4851  mov     [rsp+0C8h+var_48], r12
0x1800c4859  lea     r9, [rsp+0C8h+var_58]; HSTRING *
0x1800c485e  lea     r8, [rsp+0C8h+var_50]; HSTRING *
0x1800c4863  lea     rdx, [rsp+0C8h+var_48]; HSTRING *
0x1800c486b  mov     rcx, rdi; HSTRING
0x1800c486e  call    ?SplitStoreId@AppId@@SAJPEAUHSTRING__@@PEAPEAU2@11@Z; AppId::SplitStoreId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *)
0x1800c4873  mov     ebx, eax
0x1800c4875  test    eax, eax
0x1800c4877  js      loc_1800C49EE
0x1800c487d  mov     [rsp+0C8h+string], r12
0x1800c4885  xor     ecx, ecx; string
0x1800c4887  call    cs:__imp_WindowsDeleteString
0x1800c488d  mov     [rsp+0C8h+string], r12
0x1800c4895  lea     r8, [rsp+0C8h+string]; HSTRING *
0x1800c489d  lea     rdx, aWindowsApplica_95; "Windows::ApplicationModel::Store::Previ"...
0x1800c48a4  mov     rcx, [rsp+0C8h+arg_28]; HSTRING
0x1800c48ac  call    ?GetCallingProcessAndFunction@@YAJPEAUHSTRING__@@PEBGPEAPEAU1@@Z; GetCallingProcessAndFunction(HSTRING__ *,ushort const *,HSTRING__ * *)
0x1800c48b1  mov     ebx, eax
0x1800c48b3  test    eax, eax
0x1800c48b5  jns     short loc_1800C4927
0x1800c48b7  mov     rcx, [rsp+0C8h]; this
0x1800c48bf  mov     r9d, eax; char *
0x1800c48c2  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c48c9  mov     edx, 915h; void *
0x1800c48ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c48d3  nop
0x1800c48d4  mov     rcx, [rsp+0C8h+string]; string
0x1800c48dc  call    cs:__imp_WindowsDeleteString
0x1800c48e2  mov     [rsp+0C8h+string], r12
0x1800c48ea  mov     rcx, [rsp+0C8h+var_58]; string
0x1800c48ef  call    cs:__imp_WindowsDeleteString
0x1800c48f5  mov     [rsp+0C8h+var_58], r12
0x1800c48fa  mov     rcx, [rsp+0C8h+var_50]; string
0x1800c48ff  call    cs:__imp_WindowsDeleteString
0x1800c4905  mov     [rsp+0C8h+var_50], r12
0x1800c490a  mov     rcx, [rsp+0C8h+var_48]; string
0x1800c4912  call    cs:__imp_WindowsDeleteString
0x1800c4918  mov     [rsp+0C8h+var_48], r12
0x1800c4920  mov     eax, ebx
0x1800c4922  jmp     loc_1800C4A16
0x1800c4927  xor     edx, edx; length
0x1800c4929  mov     rcx, [rsp+0C8h+string]; string
0x1800c4931  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c4937  mov     rcx, rax; Str
0x1800c493a  mov     dl, 1; unsigned __int16 *
0x1800c493c  call    ?IsCallerInteractive@Utils@@YA_NPEBG_N@Z; Utils::IsCallerInteractive(ushort const *,bool)
0x1800c4941  mov     [rsp+0C8h+var_A0], r12
0x1800c4946  mov     cl, [rsp+0C8h+arg_38]
0x1800c494d  mov     byte ptr [rsp+0C8h+var_A8], cl
0x1800c4951  mov     r9b, 1
0x1800c4954  mov     r8b, [rsp+0C8h+arg_30]
0x1800c495c  xor     edx, edx
0x1800c495e  mov     cl, al
0x1800c4960  call    ?GetStartProductInstallOptions@@YA?AW4StartProductInstallOptions@@EEEEEPEAUIAppInstallOptions@InstallControl@Preview@Store@ApplicationModel@Windows@@@Z; GetStartProductInstallOptions(uchar,uchar,uchar,uchar,uchar,Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallOptions *)
0x1800c4965  mov     rdx, [rsp+0C8h+string]
0x1800c496d  lea     rcx, [r13-10h]
0x1800c4971  mov     [rsp+0C8h+var_60], r14
0x1800c4976  mov     [rsp+0C8h+var_68], r12d
0x1800c497b  mov     [rsp+0C8h+var_70], r12d
0x1800c4980  mov     [rsp+0C8h+var_78], eax
0x1800c4984  mov     rax, [rsp+0C8h+arg_48]
0x1800c498c  mov     [rsp+0C8h+var_80], rax
0x1800c4991  mov     rax, [rsp+0C8h+arg_40]
0x1800c4999  mov     [rsp+0C8h+var_88], rax
0x1800c499e  mov     [rsp+0C8h+var_90], rdx
0x1800c49a3  mov     rax, [rsp+0C8h+arg_20]
0x1800c49ab  mov     [rsp+0C8h+var_98], rax
0x1800c49b0  mov     [rsp+0C8h+var_A0], r15
0x1800c49b5  mov     rax, [rsp+0C8h+var_58]
0x1800c49ba  mov     [rsp+0C8h+var_A8], rax
0x1800c49bf  mov     r9, [rsp+0C8h+var_50]
0x1800c49c4  mov     r8, [rsp+0C8h+var_48]
0x1800c49cc  mov     rdx, rsi
0x1800c49cf  call    ?_StartBundleProductInstallAsync@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAAJPEAUIUser@System@6@PEAUHSTRING__@@111111PEAUIPackageVolume@Deployment@Management@6@W4StartProductInstallOptions@@W4AppInstallationToastNotificationMode@23456@4PEAPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@6@@Z; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_StartBundleProductInstallAsync(Windows::System::IUser *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,Windows::Management::Deployment::IPackageVolume *,StartProductInstallOptions,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallationToastNotificationMode,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallationToastNotificationMode,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> * *)
0x1800c49d4  mov     ebx, eax
0x1800c49d6  mov     rcx, [rsp+0C8h+string]; string
0x1800c49de  call    cs:__imp_WindowsDeleteString
0x1800c49e4  nop
0x1800c49e5  jmp     short loc_1800C49EE
0x1800c49e7  mov     ebx, dword ptr [rsp+0C8h+string]
0x1800c49ee  mov     rcx, [rsp+0C8h+var_58]; string
0x1800c49f3  call    cs:__imp_WindowsDeleteString
0x1800c49f9  nop
0x1800c49fa  mov     rcx, [rsp+0C8h+var_50]; string
0x1800c49ff  call    cs:__imp_WindowsDeleteString
0x1800c4a05  nop
0x1800c4a06  mov     rcx, [rsp+0C8h+var_48]; string
0x1800c4a0e  call    cs:__imp_WindowsDeleteString
0x1800c4a14  mov     eax, ebx
0x1800c4a16  add     rsp, 90h
0x1800c4a1d  pop     r15
0x1800c4a1f  pop     r14
0x1800c4a21  pop     r13
0x1800c4a23  pop     r12
0x1800c4a25  pop     rdi
0x1800c4a26  pop     rsi
0x1800c4a27  pop     rbx
0x1800c4a28  retn
```
