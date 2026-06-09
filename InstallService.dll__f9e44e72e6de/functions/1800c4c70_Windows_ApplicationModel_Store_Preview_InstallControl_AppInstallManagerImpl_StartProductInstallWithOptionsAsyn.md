# Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartProductInstallWithOptionsAsync(HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallOptions *,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> * *)

- ea: `0x1800c4c70`
- end: `0x1800c4ebb`
- name: `?StartProductInstallWithOptionsAsync@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@UEAAJPEAUHSTRING__@@000PEAUIAppInstallOptions@23456@PEAPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@6@@Z`
- size: `587`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, installer_update`

## callees

- `0x180010b74`
- `0x18002ec2c`
- `0x18003b08c`
- `0x18006e510`
- `0x180084280`
- `0x1800c4c70`
- `0x1800cd634`
- `0x18012efec`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4cb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4cc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4cd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4d17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4d6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4d82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4d8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4d9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4e2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4e43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4e4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4e5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4cb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4cc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4cd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4d17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4d6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4d82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4d8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4d9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4e2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4e43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4e4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4e5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c4db1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c4db1`

## string_xrefs

- `0x1800c4d51`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c4e7e`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c4e93`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c4ea8`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c4d31`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartProductInstallWithOptionsAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartProductInstallWithOptionsAsync(
        UserHelpers *a1,
        HSTRING a2,
        __int64 a3,
        HSTRING a4,
        __int64 a5,
        __int64 a6,
        HSTRING string)
{
  int v10; // r15d
  HSTRING v11; // rdi
  int v12; // eax
  int v13; // eax
  int CallingProcessAndFunction; // eax
  unsigned int v15; // ebx
  const char *v16; // r9
  __int64 result; // rax
  wchar_t *StringRawBuffer; // rax
  const unsigned __int16 *v19; // rdx
  bool v20; // r8
  char IsCallerInteractive; // al
  HSTRING v22; // rbx
  int started; // eax
  int v24; // [rsp+20h] [rbp-88h]
  int v25; // [rsp+20h] [rbp-88h]
  HSTRING v26; // [rsp+60h] [rbp-48h] BYREF
  HSTRING v27; // [rsp+68h] [rbp-40h] BYREF
  HSTRING v28; // [rsp+70h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v10 = (int)a1;
  v11 = string;
  *(_QWORD *)string = 0;
  try
  {
    v12 = UserHelpers::ValidateSingleUserApiCall(a1);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x792,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
        (const char *)(unsigned int)v12,
        v24);
    WindowsDeleteString(0);
    v28 = 0;
    WindowsDeleteString(0);
    v26 = 0;
    WindowsDeleteString(0);
    v27 = 0;
    v13 = AppId::SplitStoreId(a2, &v27, &v26, &v28);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x794,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
        (const char *)(unsigned int)v13,
        v24);
    string = 0;
    WindowsDeleteString(0);
    string = 0;
    CallingProcessAndFunction = GetCallingProcessAndFunction(
                                  a4,
                                  L"Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::Star"
                                   "tProductInstallWithOptionsAsync",
                                  &string);
    v15 = CallingProcessAndFunction;
    if ( CallingProcessAndFunction >= 0 )
    {
      StringRawBuffer = (wchar_t *)WindowsGetStringRawBuffer(string, 0);
      LOBYTE(v19) = 1;
      IsCallerInteractive = Utils::IsCallerInteractive(StringRawBuffer, v19, v20);
      v22 = v28;
      started = Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_StartBundleProductInstallWithOptionsAsync(
                  v10 - 40,
                  0,
                  (_DWORD)v27,
                  (_DWORD)v26,
                  (__int64)v28,
                  a3,
                  (__int64)string,
                  IsCallerInteractive,
                  0,
                  a5,
                  a6,
                  (__int64)v11);
      if ( started < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x7A6,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
          (const char *)(unsigned int)started,
          v25);
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v22);
      WindowsDeleteString(v26);
      WindowsDeleteString(v27);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x797,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
        (const char *)(unsigned int)CallingProcessAndFunction,
        v24);
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v28);
      WindowsDeleteString(v26);
      WindowsDeleteString(v27);
      result = v15;
    }
  }
  catch ( ... )
  {
    LODWORD(string) = wil::details::in1diag3::Return_CaughtException(
                        retaddr,
                        (void *)0x7A9,
                        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
                        v16);
    return (unsigned int)string;
  }
  return result;
}

```

## disassembly

```asm
0x1800c4c70  push    rbx
0x1800c4c72  push    rsi
0x1800c4c73  push    rdi
0x1800c4c74  push    r14
0x1800c4c76  push    r15
0x1800c4c78  sub     rsp, 80h
0x1800c4c7f  mov     rbx, r9
0x1800c4c82  mov     r14, r8
0x1800c4c85  mov     rsi, rdx
0x1800c4c88  mov     r15, rcx
0x1800c4c8b  mov     rdi, [rsp+0A8h+string]
0x1800c4c93  mov     qword ptr [rdi], 0
0x1800c4c9a  call    ?ValidateSingleUserApiCall@UserHelpers@@YAJXZ; UserHelpers::ValidateSingleUserApiCall(void)
0x1800c4c9f  mov     rcx, [rsp+0A8h]; this
0x1800c4ca7  test    eax, eax
0x1800c4ca9  js      loc_1800C4E7B
0x1800c4caf  xor     ecx, ecx; string
0x1800c4cb1  call    cs:__imp_WindowsDeleteString
0x1800c4cb7  mov     [rsp+0A8h+var_38], 0
0x1800c4cc0  xor     ecx, ecx; string
0x1800c4cc2  call    cs:__imp_WindowsDeleteString
0x1800c4cc8  mov     [rsp+0A8h+var_48], 0
0x1800c4cd1  xor     ecx, ecx; string
0x1800c4cd3  call    cs:__imp_WindowsDeleteString
0x1800c4cd9  mov     [rsp+0A8h+var_40], 0
0x1800c4ce2  lea     r9, [rsp+0A8h+var_38]; HSTRING *
0x1800c4ce7  lea     r8, [rsp+0A8h+var_48]; HSTRING *
0x1800c4cec  lea     rdx, [rsp+0A8h+var_40]; HSTRING *
0x1800c4cf1  mov     rcx, rsi; HSTRING
0x1800c4cf4  call    ?SplitStoreId@AppId@@SAJPEAUHSTRING__@@PEAPEAU2@11@Z; AppId::SplitStoreId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *)
0x1800c4cf9  mov     rcx, [rsp+0A8h]; this
0x1800c4d01  test    eax, eax
0x1800c4d03  js      loc_1800C4E90
0x1800c4d09  mov     [rsp+0A8h+string], 0
0x1800c4d15  xor     ecx, ecx; string
0x1800c4d17  call    cs:__imp_WindowsDeleteString
0x1800c4d1d  mov     [rsp+0A8h+string], 0
0x1800c4d29  lea     r8, [rsp+0A8h+string]; HSTRING *
0x1800c4d31  lea     rdx, aWindowsApplica_89; "Windows::ApplicationModel::Store::Previ"...
0x1800c4d38  mov     rcx, rbx; HSTRING
0x1800c4d3b  call    ?GetCallingProcessAndFunction@@YAJPEAUHSTRING__@@PEBGPEAPEAU1@@Z; GetCallingProcessAndFunction(HSTRING__ *,ushort const *,HSTRING__ * *)
0x1800c4d40  mov     ebx, eax
0x1800c4d42  test    eax, eax
0x1800c4d44  jns     short loc_1800C4DA7
0x1800c4d46  mov     rcx, [rsp+0A8h]; this
0x1800c4d4e  mov     r9d, eax; char *
0x1800c4d51  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c4d58  mov     edx, 797h; void *
0x1800c4d5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c4d62  nop
0x1800c4d63  mov     rcx, [rsp+0A8h+string]; string
0x1800c4d6b  call    cs:__imp_WindowsDeleteString
0x1800c4d71  mov     [rsp+0A8h+string], 0
0x1800c4d7d  mov     rcx, [rsp+0A8h+var_38]; string
0x1800c4d82  call    cs:__imp_WindowsDeleteString
0x1800c4d88  nop
0x1800c4d89  mov     rcx, [rsp+0A8h+var_48]; string
0x1800c4d8e  call    cs:__imp_WindowsDeleteString
0x1800c4d94  nop
0x1800c4d95  mov     rcx, [rsp+0A8h+var_40]; string
0x1800c4d9a  call    cs:__imp_WindowsDeleteString
0x1800c4da0  mov     eax, ebx
0x1800c4da2  jmp     loc_1800C4E6C
0x1800c4da7  xor     edx, edx; length
0x1800c4da9  mov     rcx, [rsp+0A8h+string]; string
0x1800c4db1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c4db7  mov     rcx, rax; Str
0x1800c4dba  mov     dl, 1; unsigned __int16 *
0x1800c4dbc  call    ?IsCallerInteractive@Utils@@YA_NPEBG_N@Z; Utils::IsCallerInteractive(ushort const *,bool)
0x1800c4dc1  mov     r8, [rsp+0A8h+string]
0x1800c4dc9  lea     rcx, [r15-28h]
0x1800c4dcd  mov     [rsp+0A8h+var_50], rdi
0x1800c4dd2  mov     rdx, [rsp+0A8h+arg_28]
0x1800c4dda  mov     [rsp+0A8h+var_58], rdx
0x1800c4ddf  mov     rdx, [rsp+0A8h+arg_20]
0x1800c4de7  mov     [rsp+0A8h+var_60], rdx
0x1800c4dec  mov     [rsp+0A8h+var_68], 0
0x1800c4df1  mov     [rsp+0A8h+var_70], al
0x1800c4df5  mov     [rsp+0A8h+var_78], r8
0x1800c4dfa  mov     [rsp+0A8h+var_80], r14
0x1800c4dff  mov     rbx, [rsp+0A8h+var_38]
0x1800c4e04  mov     qword ptr [rsp+0A8h+var_88], rbx; int
0x1800c4e09  mov     r9, [rsp+0A8h+var_48]
0x1800c4e0e  mov     r8, [rsp+0A8h+var_40]
0x1800c4e13  xor     edx, edx
0x1800c4e15  call    ?_StartBundleProductInstallWithOptionsAsync@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAAJPEAUIUser@System@6@PEAUHSTRING__@@1111EE1PEAUIAppInstallOptions@23456@PEAPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@6@@Z; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_StartBundleProductInstallWithOptionsAsync(Windows::System::IUser *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,uchar,uchar,HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallOptions *,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> * *)
0x1800c4e1a  mov     rcx, [rsp+0A8h]; this
0x1800c4e22  test    eax, eax
0x1800c4e24  js      short loc_1800C4EA5
0x1800c4e26  mov     rcx, [rsp+0A8h+string]; string
0x1800c4e2e  call    cs:__imp_WindowsDeleteString
0x1800c4e34  mov     [rsp+0A8h+string], 0
0x1800c4e40  mov     rcx, rbx; string
0x1800c4e43  call    cs:__imp_WindowsDeleteString
0x1800c4e49  nop
0x1800c4e4a  mov     rcx, [rsp+0A8h+var_48]; string
0x1800c4e4f  call    cs:__imp_WindowsDeleteString
0x1800c4e55  nop
0x1800c4e56  mov     rcx, [rsp+0A8h+var_40]; string
0x1800c4e5b  call    cs:__imp_WindowsDeleteString
0x1800c4e61  xor     eax, eax
0x1800c4e63  jmp     short loc_1800C4E6C
0x1800c4e65  mov     eax, dword ptr [rsp+0A8h+string]
0x1800c4e6c  add     rsp, 80h
0x1800c4e73  pop     r15
0x1800c4e75  pop     r14
0x1800c4e77  pop     rdi
0x1800c4e78  pop     rsi
0x1800c4e79  pop     rbx
0x1800c4e7a  retn
0x1800c4e7b  mov     r9d, eax; char *
0x1800c4e7e  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c4e85  mov     edx, 792h; void *
0x1800c4e8a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c4e90  mov     r9d, eax; char *
0x1800c4e93  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c4e9a  mov     edx, 794h; void *
0x1800c4e9f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c4ea5  mov     r9d, eax; char *
0x1800c4ea8  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c4eaf  mov     edx, 7A6h; void *
0x1800c4eb4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
