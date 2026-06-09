# Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::SearchForUpdatesWithUpdateOptionsAsync(HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::IAppUpdateOptions *,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> * *)

- ea: `0x1800c0d00`
- end: `0x1800c0f7d`
- name: `?SearchForUpdatesWithUpdateOptionsAsync@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@UEAAJPEAUHSTRING__@@000PEAUIAppUpdateOptions@23456@PEAPEAU?$IAsyncOperation@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@6@@Z`
- size: `637`
- prototype: `__int64 __fastcall(int, int, int, int, HSTRING, __int64, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, installer_update`

## callees

- `0x180010b74`
- `0x18002ec2c`
- `0x18003b08c`
- `0x1800c0d00`
- `0x1800ccc08`
- `0x18012efec`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0db1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0e72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0ebe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0ed2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0f47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0f5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0db1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0e72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0ebe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0ed2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0f47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0f5b`

## string_xrefs

- `0x1800c0d3d`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c0d94`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c0de1`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c0e3d`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c0ea7`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c0f30`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c0e82`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::SearchForUpdatesWithUpdateOptionsAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::SearchForUpdatesWithUpdateOptionsAsync(
        UserHelpers *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        HSTRING a5,
        __int64 a6,
        _QWORD *a7)
{
  int v10; // eax
  int v11; // eax
  __int64 (__fastcall *v12)(__int64, HSTRING *); // rbx
  int v13; // eax
  int v14; // eax
  __int64 v15; // rcx
  int CallingProcessAndFunction; // eax
  unsigned int v17; // ebx
  const char *v18; // r9
  __int64 result; // rax
  int v20; // eax
  int v21; // [rsp+20h] [rbp-88h]
  int v22; // [rsp+20h] [rbp-88h]
  char v23[8]; // [rsp+50h] [rbp-58h] BYREF
  HSTRING v24; // [rsp+58h] [rbp-50h] BYREF
  HSTRING string; // [rsp+60h] [rbp-48h] BYREF
  _QWORD v26[8]; // [rsp+68h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  *a7 = 0;
  try
  {
    v10 = UserHelpers::ValidateSingleUserApiCall(a1);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x73B,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
        (const char *)(unsigned int)v10,
        v21);
    v23[0] = 1;
    LOBYTE(a7) = 1;
    string = 0;
    if ( a6 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)a6 + 64LL))(a6, v23);
      if ( v11 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x742,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
          (const char *)(unsigned int)v11,
          v21);
      v12 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a6 + 48LL);
      WindowsDeleteString(string);
      string = 0;
      v13 = v12(a6, &string);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x743,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
          (const char *)(unsigned int)v13,
          v21);
      v26[0] = 0;
      if ( (**(int (__fastcall ***)(__int64, GUID *, _QWORD *))a6)(a6, &GUID_f4646e08_ed26_4bf9_9679_48f628e53df8, v26) >= 0 )
      {
        v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD **))(*(_QWORD *)v26[0] + 48LL))(v26[0], &a7);
        if ( v14 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x748,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
            (const char *)(unsigned int)v14,
            v21);
      }
      v15 = v26[0];
      if ( v26[0] )
      {
        v26[0] = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
    }
    v24 = 0;
    WindowsDeleteString(0);
    v24 = 0;
    CallingProcessAndFunction = GetCallingProcessAndFunction(
                                  a5,
                                  L"Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::Sear"
                                   "chForUpdatesWithUpdateOptionsAsync",
                                  &v24);
    v17 = CallingProcessAndFunction;
    if ( CallingProcessAndFunction >= 0 )
    {
      v22 = (int)string;
      v20 = Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_SearchForUpdatesForUserAsync(
              (char *)a1 - 40,
              0,
              a2,
              a3);
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x758,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
          (const char *)(unsigned int)v20,
          v22);
      WindowsDeleteString(v24);
      v24 = 0;
      WindowsDeleteString(string);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x74D,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
        (const char *)(unsigned int)CallingProcessAndFunction,
        v21);
      WindowsDeleteString(v24);
      v24 = 0;
      WindowsDeleteString(string);
      result = v17;
    }
  }
  catch ( ... )
  {
    LODWORD(a7) = wil::details::in1diag3::Return_CaughtException(
                    retaddr,
                    (void *)0x75B,
                    (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
                    v18);
    return (unsigned int)a7;
  }
  return result;
}

```

## disassembly

```asm
0x1800c0d00  push    rbx
0x1800c0d02  push    rsi
0x1800c0d03  push    rdi
0x1800c0d04  push    r12
0x1800c0d06  push    r13
0x1800c0d08  push    r14
0x1800c0d0a  push    r15
0x1800c0d0c  sub     rsp, 70h
0x1800c0d10  mov     r14, r9
0x1800c0d13  mov     r15, r8
0x1800c0d16  mov     r12, rdx
0x1800c0d19  mov     r13, rcx
0x1800c0d1c  xor     ebx, ebx
0x1800c0d1e  mov     rsi, [rsp+0A8h+arg_30]
0x1800c0d26  mov     [rsi], rbx
0x1800c0d29  call    ?ValidateSingleUserApiCall@UserHelpers@@YAJXZ; UserHelpers::ValidateSingleUserApiCall(void)
0x1800c0d2e  mov     rcx, [rsp+0A8h]; this
0x1800c0d36  test    eax, eax
0x1800c0d38  jns     short loc_1800C0D4E
0x1800c0d3a  mov     r9d, eax; char *
0x1800c0d3d  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c0d44  mov     edx, 73Bh; void *
0x1800c0d49  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c0d4e  mov     [rsp+0A8h+var_58], 1
0x1800c0d53  mov     byte ptr [rsp+0A8h+arg_30], 1
0x1800c0d5b  mov     [rsp+0A8h+string], rbx
0x1800c0d60  mov     rdi, [rsp+0A8h+arg_28]
0x1800c0d68  test    rdi, rdi
0x1800c0d6b  jz      loc_1800C0E6B
0x1800c0d71  mov     rax, [rdi]
0x1800c0d74  lea     rdx, [rsp+0A8h+var_58]
0x1800c0d79  mov     rcx, rdi
0x1800c0d7c  mov     rax, [rax+40h]
0x1800c0d80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0d85  mov     rcx, [rsp+0A8h]; this
0x1800c0d8d  test    eax, eax
0x1800c0d8f  jns     short loc_1800C0DA5
0x1800c0d91  mov     r9d, eax; char *
0x1800c0d94  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c0d9b  mov     edx, 742h; void *
0x1800c0da0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c0da5  mov     rax, [rdi]
0x1800c0da8  mov     rbx, [rax+30h]
0x1800c0dac  mov     rcx, [rsp+0A8h+string]; string
0x1800c0db1  call    cs:__imp_WindowsDeleteString
0x1800c0db7  mov     [rsp+0A8h+string], 0
0x1800c0dc0  lea     rdx, [rsp+0A8h+string]
0x1800c0dc5  mov     rcx, rdi
0x1800c0dc8  mov     rax, rbx
0x1800c0dcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0dd0  mov     rcx, [rsp+0A8h]; this
0x1800c0dd8  xor     ebx, ebx
0x1800c0dda  test    eax, eax
0x1800c0ddc  jns     short loc_1800C0DF2
0x1800c0dde  mov     r9d, eax; char *
0x1800c0de1  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c0de8  mov     edx, 743h; void *
0x1800c0ded  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c0df2  mov     [rsp+0A8h+var_40], rbx
0x1800c0df7  mov     rax, [rdi]
0x1800c0dfa  lea     r8, [rsp+0A8h+var_40]
0x1800c0dff  lea     rdx, _GUID_f4646e08_ed26_4bf9_9679_48f628e53df8
0x1800c0e06  mov     rcx, rdi
0x1800c0e09  mov     rax, [rax]
0x1800c0e0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0e11  test    eax, eax
0x1800c0e13  js      short loc_1800C0E4F
0x1800c0e15  mov     rcx, [rsp+0A8h+var_40]
0x1800c0e1a  mov     rax, [rcx]
0x1800c0e1d  lea     rdx, [rsp+0A8h+arg_30]
0x1800c0e25  mov     rax, [rax+30h]
0x1800c0e29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0e2e  mov     rcx, [rsp+0A8h]; this
0x1800c0e36  test    eax, eax
0x1800c0e38  jns     short loc_1800C0E4F
0x1800c0e3a  mov     r9d, eax; char *
0x1800c0e3d  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c0e44  mov     edx, 748h; void *
0x1800c0e49  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c0e4f  mov     rcx, [rsp+0A8h+var_40]
0x1800c0e54  test    rcx, rcx
0x1800c0e57  jz      short loc_1800C0E6B
0x1800c0e59  mov     [rsp+0A8h+var_40], rbx
0x1800c0e5e  mov     rax, [rcx]
0x1800c0e61  mov     rax, [rax+10h]
0x1800c0e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0e6a  nop
0x1800c0e6b  mov     [rsp+0A8h+var_50], rbx
0x1800c0e70  xor     ecx, ecx; string
0x1800c0e72  call    cs:__imp_WindowsDeleteString
0x1800c0e78  mov     [rsp+0A8h+var_50], rbx
0x1800c0e7d  lea     r8, [rsp+0A8h+var_50]; HSTRING *
0x1800c0e82  lea     rdx, aWindowsApplica_62; "Windows::ApplicationModel::Store::Previ"...
0x1800c0e89  mov     rcx, [rsp+0A8h+arg_20]; HSTRING
0x1800c0e91  call    ?GetCallingProcessAndFunction@@YAJPEAUHSTRING__@@PEBGPEAPEAU1@@Z; GetCallingProcessAndFunction(HSTRING__ *,ushort const *,HSTRING__ * *)
0x1800c0e96  mov     ebx, eax
0x1800c0e98  test    eax, eax
0x1800c0e9a  jns     short loc_1800C0EDF
0x1800c0e9c  mov     rcx, [rsp+0A8h]; this
0x1800c0ea4  mov     r9d, eax; char *
0x1800c0ea7  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c0eae  mov     edx, 74Dh; void *
0x1800c0eb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c0eb8  nop
0x1800c0eb9  mov     rcx, [rsp+0A8h+var_50]; string
0x1800c0ebe  call    cs:__imp_WindowsDeleteString
0x1800c0ec4  mov     [rsp+0A8h+var_50], 0
0x1800c0ecd  mov     rcx, [rsp+0A8h+string]; string
0x1800c0ed2  call    cs:__imp_WindowsDeleteString
0x1800c0ed8  mov     eax, ebx
0x1800c0eda  jmp     loc_1800C0F6C
0x1800c0edf  mov     al, byte ptr [rsp+0A8h+arg_30]
0x1800c0ee6  mov     dl, [rsp+0A8h+var_58]
0x1800c0eea  mov     r8, [rsp+0A8h+var_50]
0x1800c0eef  mov     r9, [rsp+0A8h+string]
0x1800c0ef4  lea     rcx, [r13-28h]
0x1800c0ef8  mov     [rsp+0A8h+var_60], rsi
0x1800c0efd  mov     [rsp+0A8h+var_68], al
0x1800c0f01  mov     [rsp+0A8h+var_70], dl
0x1800c0f05  mov     [rsp+0A8h+var_78], r8
0x1800c0f0a  mov     [rsp+0A8h+var_80], r14
0x1800c0f0f  mov     qword ptr [rsp+0A8h+var_88], r9; int
0x1800c0f14  mov     r9, r15
0x1800c0f17  mov     r8, r12
0x1800c0f1a  xor     edx, edx
0x1800c0f1c  call    ?_SearchForUpdatesForUserAsync@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAAJPEAUIUser@System@6@PEAUHSTRING__@@1111EEPEAPEAU?$IAsyncOperation@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@6@@Z; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_SearchForUpdatesForUserAsync(Windows::System::IUser *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,uchar,uchar,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> * *)
0x1800c0f21  mov     rcx, [rsp+0A8h]; this
0x1800c0f29  test    eax, eax
0x1800c0f2b  jns     short loc_1800C0F42
0x1800c0f2d  mov     r9d, eax; char *
0x1800c0f30  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c0f37  mov     edx, 758h; void *
0x1800c0f3c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c0f42  mov     rcx, [rsp+0A8h+var_50]; string
0x1800c0f47  call    cs:__imp_WindowsDeleteString
0x1800c0f4d  mov     [rsp+0A8h+var_50], 0
0x1800c0f56  mov     rcx, [rsp+0A8h+string]; string
0x1800c0f5b  call    cs:__imp_WindowsDeleteString
0x1800c0f61  xor     eax, eax
0x1800c0f63  jmp     short loc_1800C0F6C
0x1800c0f65  mov     eax, dword ptr [rsp+0A8h+arg_30]
0x1800c0f6c  add     rsp, 70h
0x1800c0f70  pop     r15
0x1800c0f72  pop     r14
0x1800c0f74  pop     r13
0x1800c0f76  pop     r12
0x1800c0f78  pop     rdi
0x1800c0f79  pop     rsi
0x1800c0f7a  pop     rbx
0x1800c0f7b  retn
```
