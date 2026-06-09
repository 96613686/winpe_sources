# Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartProductInstallWithOptionsForUserAsync(Windows::System::IUser *,HSTRING__ *,HSTRING__ *,HSTRING__ *,uchar,uchar,HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallOptions *,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> * *)

- ea: `0x1800c5180`
- end: `0x1800c53ad`
- name: `?StartProductInstallWithOptionsForUserAsync@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@UEAAJPEAUIUser@System@6@PEAUHSTRING__@@11EE1PEAUIAppInstallOptions@23456@PEAPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@6@@Z`
- size: `557`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, installer_update`

## callees

- `0x180010b74`
- `0x18002ec2c`
- `0x18003b08c`
- `0x18006e510`
- `0x180084280`
- `0x1800c5180`
- `0x1800cd634`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c51ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c51bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c51ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c5212`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c526b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c5282`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c528e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c529a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c5335`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c534a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c5356`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c5362`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c51ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c51bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c51ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c5212`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c526b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c5282`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c528e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c529a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c5335`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c534a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c5356`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c5362`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c52b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c52b1`

## string_xrefs

- `0x1800c5251`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c5385`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c539a`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c522c`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartProductInstallWithOptionsForUserAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartProductInstallWithOptionsForUserAsync(
        __int64 a1,
        __int64 a2,
        HSTRING a3,
        __int64 a4,
        HSTRING a5,
        __int64 a6,
        char a7,
        __int64 a8,
        int (__fastcall ***a9)(_QWORD, GUID *, __int64 *),
        HSTRING string)
{
  HSTRING v14; // rdi
  int v15; // eax
  int CallingProcessAndFunction; // eax
  unsigned int v17; // ebx
  const char *v18; // r9
  __int64 result; // rax
  wchar_t *StringRawBuffer; // rax
  const unsigned __int16 *v21; // rdx
  bool v22; // r8
  char IsCallerInteractive; // al
  HSTRING v24; // rbx
  int started; // eax
  int v26; // [rsp+20h] [rbp-88h]
  int v27; // [rsp+20h] [rbp-88h]
  HSTRING v28; // [rsp+60h] [rbp-48h] BYREF
  HSTRING v29; // [rsp+68h] [rbp-40h] BYREF
  HSTRING v30; // [rsp+70h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v14 = string;
  *(_QWORD *)string = 0;
  WindowsDeleteString(0);
  v30 = 0;
  WindowsDeleteString(0);
  v28 = 0;
  WindowsDeleteString(0);
  v29 = 0;
  v15 = AppId::SplitStoreId(a3, &v29, &v28, &v30);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B01,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      (const char *)(unsigned int)v15,
      v26);
  string = 0;
  WindowsDeleteString(0);
  try
  {
    string = 0;
    CallingProcessAndFunction = GetCallingProcessAndFunction(
                                  a5,
                                  L"Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::Star"
                                   "tProductInstallWithOptionsForUserAsync",
                                  &string);
    v17 = CallingProcessAndFunction;
    if ( CallingProcessAndFunction >= 0 )
    {
      StringRawBuffer = (wchar_t *)WindowsGetStringRawBuffer(string, 0);
      LOBYTE(v21) = 1;
      IsCallerInteractive = Utils::IsCallerInteractive(StringRawBuffer, v21, v22);
      v24 = v30;
      started = Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_StartBundleProductInstallWithOptionsAsync(
                  (RTL_SRWLOCK *)(a1 - 104),
                  a2,
                  (__int64)v29,
                  (__int64)v28,
                  (__int64)v30,
                  a4,
                  (__int64)string,
                  IsCallerInteractive,
                  a7,
                  a8,
                  a9,
                  (__int64)v14);
      if ( started < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1B14,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
          (const char *)(unsigned int)started,
          v27);
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v24);
      WindowsDeleteString(v28);
      WindowsDeleteString(v29);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B04,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
        (const char *)(unsigned int)CallingProcessAndFunction,
        v26);
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v30);
      WindowsDeleteString(v28);
      WindowsDeleteString(v29);
      result = v17;
    }
  }
  catch ( ... )
  {
    LODWORD(string) = wil::details::in1diag3::Return_CaughtException(
                        retaddr,
                        (void *)0x1B17,
                        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
                        v18);
    return (unsigned int)string;
  }
  return result;
}

```

## disassembly

```asm
0x1800c5180  push    rbx
0x1800c5182  push    rsi
0x1800c5183  push    rdi
0x1800c5184  push    r14
0x1800c5186  push    r15
0x1800c5188  sub     rsp, 80h
0x1800c518f  mov     rsi, r9
0x1800c5192  mov     rbx, r8
0x1800c5195  mov     r14, rdx
0x1800c5198  mov     r15, rcx
0x1800c519b  mov     rdi, [rsp+0A8h+string]
0x1800c51a3  mov     qword ptr [rdi], 0
0x1800c51aa  xor     ecx, ecx; string
0x1800c51ac  call    cs:__imp_WindowsDeleteString
0x1800c51b2  mov     [rsp+0A8h+var_38], 0
0x1800c51bb  xor     ecx, ecx; string
0x1800c51bd  call    cs:__imp_WindowsDeleteString
0x1800c51c3  mov     [rsp+0A8h+var_48], 0
0x1800c51cc  xor     ecx, ecx; string
0x1800c51ce  call    cs:__imp_WindowsDeleteString
0x1800c51d4  mov     [rsp+0A8h+var_40], 0
0x1800c51dd  lea     r9, [rsp+0A8h+var_38]; HSTRING *
0x1800c51e2  lea     r8, [rsp+0A8h+var_48]; HSTRING *
0x1800c51e7  lea     rdx, [rsp+0A8h+var_40]; HSTRING *
0x1800c51ec  mov     rcx, rbx; HSTRING
0x1800c51ef  call    ?SplitStoreId@AppId@@SAJPEAUHSTRING__@@PEAPEAU2@11@Z; AppId::SplitStoreId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *)
0x1800c51f4  mov     rcx, [rsp+0A8h]; this
0x1800c51fc  test    eax, eax
0x1800c51fe  js      loc_1800C5382
0x1800c5204  mov     [rsp+0A8h+string], 0
0x1800c5210  xor     ecx, ecx; string
0x1800c5212  call    cs:__imp_WindowsDeleteString
0x1800c5218  mov     [rsp+0A8h+string], 0
0x1800c5224  lea     r8, [rsp+0A8h+string]; HSTRING *
0x1800c522c  lea     rdx, aWindowsApplica_34; "Windows::ApplicationModel::Store::Previ"...
0x1800c5233  mov     rcx, [rsp+0A8h+arg_20]; HSTRING
0x1800c523b  call    ?GetCallingProcessAndFunction@@YAJPEAUHSTRING__@@PEBGPEAPEAU1@@Z; GetCallingProcessAndFunction(HSTRING__ *,ushort const *,HSTRING__ * *)
0x1800c5240  mov     ebx, eax
0x1800c5242  test    eax, eax
0x1800c5244  jns     short loc_1800C52A7
0x1800c5246  mov     rcx, [rsp+0A8h]; this
0x1800c524e  mov     r9d, eax; char *
0x1800c5251  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c5258  mov     edx, 1B04h; void *
0x1800c525d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c5262  nop
0x1800c5263  mov     rcx, [rsp+0A8h+string]; string
0x1800c526b  call    cs:__imp_WindowsDeleteString
0x1800c5271  mov     [rsp+0A8h+string], 0
0x1800c527d  mov     rcx, [rsp+0A8h+var_38]; string
0x1800c5282  call    cs:__imp_WindowsDeleteString
0x1800c5288  nop
0x1800c5289  mov     rcx, [rsp+0A8h+var_48]; string
0x1800c528e  call    cs:__imp_WindowsDeleteString
0x1800c5294  nop
0x1800c5295  mov     rcx, [rsp+0A8h+var_40]; string
0x1800c529a  call    cs:__imp_WindowsDeleteString
0x1800c52a0  mov     eax, ebx
0x1800c52a2  jmp     loc_1800C5373
0x1800c52a7  xor     edx, edx; length
0x1800c52a9  mov     rcx, [rsp+0A8h+string]; string
0x1800c52b1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c52b7  mov     rcx, rax; Str
0x1800c52ba  mov     dl, 1; unsigned __int16 *
0x1800c52bc  call    ?IsCallerInteractive@Utils@@YA_NPEBG_N@Z; Utils::IsCallerInteractive(ushort const *,bool)
0x1800c52c1  mov     r8, [rsp+0A8h+string]
0x1800c52c9  lea     rcx, [r15-68h]
0x1800c52cd  mov     [rsp+0A8h+var_50], rdi
0x1800c52d2  mov     rdx, [rsp+0A8h+arg_40]
0x1800c52da  mov     [rsp+0A8h+var_58], rdx
0x1800c52df  mov     rdx, [rsp+0A8h+arg_38]
0x1800c52e7  mov     [rsp+0A8h+var_60], rdx
0x1800c52ec  mov     dl, [rsp+0A8h+arg_30]
0x1800c52f3  mov     [rsp+0A8h+var_68], dl
0x1800c52f7  mov     [rsp+0A8h+var_70], al
0x1800c52fb  mov     [rsp+0A8h+var_78], r8
0x1800c5300  mov     [rsp+0A8h+var_80], rsi
0x1800c5305  mov     rbx, [rsp+0A8h+var_38]
0x1800c530a  mov     qword ptr [rsp+0A8h+var_88], rbx; int
0x1800c530f  mov     r9, [rsp+0A8h+var_48]
0x1800c5314  mov     r8, [rsp+0A8h+var_40]
0x1800c5319  mov     rdx, r14
0x1800c531c  call    ?_StartBundleProductInstallWithOptionsAsync@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAAJPEAUIUser@System@6@PEAUHSTRING__@@1111EE1PEAUIAppInstallOptions@23456@PEAPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@6@@Z; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_StartBundleProductInstallWithOptionsAsync(Windows::System::IUser *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,uchar,uchar,HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallOptions *,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> * *)
0x1800c5321  mov     rcx, [rsp+0A8h]; this
0x1800c5329  test    eax, eax
0x1800c532b  js      short loc_1800C5397
0x1800c532d  mov     rcx, [rsp+0A8h+string]; string
0x1800c5335  call    cs:__imp_WindowsDeleteString
0x1800c533b  mov     [rsp+0A8h+string], 0
0x1800c5347  mov     rcx, rbx; string
0x1800c534a  call    cs:__imp_WindowsDeleteString
0x1800c5350  nop
0x1800c5351  mov     rcx, [rsp+0A8h+var_48]; string
0x1800c5356  call    cs:__imp_WindowsDeleteString
0x1800c535c  nop
0x1800c535d  mov     rcx, [rsp+0A8h+var_40]; string
0x1800c5362  call    cs:__imp_WindowsDeleteString
0x1800c5368  xor     eax, eax
0x1800c536a  jmp     short loc_1800C5373
0x1800c536c  mov     eax, dword ptr [rsp+0A8h+string]
0x1800c5373  add     rsp, 80h
0x1800c537a  pop     r15
0x1800c537c  pop     r14
0x1800c537e  pop     rdi
0x1800c537f  pop     rsi
0x1800c5380  pop     rbx
0x1800c5381  retn
0x1800c5382  mov     r9d, eax; char *
0x1800c5385  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c538c  mov     edx, 1B01h; void *
0x1800c5391  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c5397  mov     r9d, eax; char *
0x1800c539a  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c53a1  mov     edx, 1B14h; void *
0x1800c53a6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
