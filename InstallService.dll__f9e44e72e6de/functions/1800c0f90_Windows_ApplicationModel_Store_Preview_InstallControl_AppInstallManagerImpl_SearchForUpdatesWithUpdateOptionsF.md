# Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::SearchForUpdatesWithUpdateOptionsForUserAsync(Windows::System::IUser *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::IAppUpdateOptions *,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> * *)

- ea: `0x1800c0f90`
- end: `0x1800c1219`
- name: `?SearchForUpdatesWithUpdateOptionsForUserAsync@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@UEAAJPEAUIUser@System@6@PEAUHSTRING__@@111PEAUIAppUpdateOptions@23456@PEAPEAU?$IAsyncOperation@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@6@@Z`
- size: `649`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, HSTRING, __int64, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, installer_update`

## callees

- `0x180010b74`
- `0x18002ec2c`
- `0x18003b08c`
- `0x1800c0f90`
- `0x1800ccc08`
- `0x18012efb0`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1044`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1105`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1151`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1165`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c11e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c11f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1044`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1105`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1151`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1165`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c11e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c11f7`

## string_xrefs

- `0x1800c0fd0`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c1027`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c1074`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c10d0`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c113a`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c11cc`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c1115`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::SearchForUpdatesWithUpdateOptionsForUserAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::SearchForUpdatesWithUpdateOptionsForUserAsync(
        __int64 a1,
        UserHelpers *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        HSTRING a6,
        __int64 a7,
        _QWORD *a8)
{
  int v12; // eax
  int v13; // eax
  __int64 (__fastcall *v14)(__int64, HSTRING *); // rbx
  int v15; // eax
  int v16; // eax
  __int64 v17; // rcx
  int CallingProcessAndFunction; // eax
  unsigned int v19; // ebx
  const char *v20; // r9
  __int64 result; // rax
  int v22; // eax
  int v23; // [rsp+20h] [rbp-88h]
  int v24; // [rsp+20h] [rbp-88h]
  char v25[8]; // [rsp+50h] [rbp-58h] BYREF
  HSTRING v26; // [rsp+58h] [rbp-50h] BYREF
  HSTRING string; // [rsp+60h] [rbp-48h] BYREF
  _QWORD v28[8]; // [rsp+68h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  *a8 = 0;
  try
  {
    v12 = UserHelpers::ValidateMultiUserApiCall(a2, a2);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x767,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
        (const char *)(unsigned int)v12,
        v23);
    v25[0] = 1;
    LOBYTE(a8) = 1;
    string = 0;
    if ( a7 )
    {
      v13 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)a7 + 64LL))(a7, v25);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x76E,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
          (const char *)(unsigned int)v13,
          v23);
      v14 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a7 + 48LL);
      WindowsDeleteString(string);
      string = 0;
      v15 = v14(a7, &string);
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x76F,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
          (const char *)(unsigned int)v15,
          v23);
      v28[0] = 0;
      if ( (**(int (__fastcall ***)(__int64, GUID *, _QWORD *))a7)(a7, &GUID_f4646e08_ed26_4bf9_9679_48f628e53df8, v28) >= 0 )
      {
        v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD **))(*(_QWORD *)v28[0] + 48LL))(v28[0], &a8);
        if ( v16 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x774,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
            (const char *)(unsigned int)v16,
            v23);
      }
      v17 = v28[0];
      if ( v28[0] )
      {
        v28[0] = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
    }
    v26 = 0;
    WindowsDeleteString(0);
    v26 = 0;
    CallingProcessAndFunction = GetCallingProcessAndFunction(
                                  a6,
                                  L"Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::Sear"
                                   "chForUpdatesWithUpdateOptionsForUserAsync",
                                  &v26);
    v19 = CallingProcessAndFunction;
    if ( CallingProcessAndFunction >= 0 )
    {
      v24 = (int)string;
      v22 = Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_SearchForUpdatesForUserAsync(
              a1 - 40,
              a2,
              a3,
              a4);
      if ( v22 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x784,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
          (const char *)(unsigned int)v22,
          v24);
      WindowsDeleteString(v26);
      v26 = 0;
      WindowsDeleteString(string);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x779,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
        (const char *)(unsigned int)CallingProcessAndFunction,
        v23);
      WindowsDeleteString(v26);
      v26 = 0;
      WindowsDeleteString(string);
      result = v19;
    }
  }
  catch ( ... )
  {
    LODWORD(a8) = wil::details::in1diag3::Return_CaughtException(
                    retaddr,
                    (void *)0x787,
                    (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
                    v20);
    return (unsigned int)a8;
  }
  return result;
}

```

## disassembly

```asm
0x1800c0f90  push    rbx
0x1800c0f92  push    rsi
0x1800c0f93  push    rdi
0x1800c0f94  push    r12
0x1800c0f96  push    r13
0x1800c0f98  push    r14
0x1800c0f9a  push    r15
0x1800c0f9c  sub     rsp, 70h
0x1800c0fa0  mov     r15, r9
0x1800c0fa3  mov     r12, r8
0x1800c0fa6  mov     rsi, rdx
0x1800c0fa9  mov     r13, rcx
0x1800c0fac  xor     ebx, ebx
0x1800c0fae  mov     r14, [rsp+0A8h+arg_38]
0x1800c0fb6  mov     [r14], rbx
0x1800c0fb9  mov     rcx, rdx; this
0x1800c0fbc  call    ?ValidateMultiUserApiCall@UserHelpers@@YAJPEAUIUser@System@Windows@@@Z; UserHelpers::ValidateMultiUserApiCall(Windows::System::IUser *)
0x1800c0fc1  mov     rcx, [rsp+0A8h]; this
0x1800c0fc9  test    eax, eax
0x1800c0fcb  jns     short loc_1800C0FE1
0x1800c0fcd  mov     r9d, eax; char *
0x1800c0fd0  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c0fd7  mov     edx, 767h; void *
0x1800c0fdc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c0fe1  mov     [rsp+0A8h+var_58], 1
0x1800c0fe6  mov     byte ptr [rsp+0A8h+arg_38], 1
0x1800c0fee  mov     [rsp+0A8h+string], rbx
0x1800c0ff3  mov     rdi, [rsp+0A8h+arg_30]
0x1800c0ffb  test    rdi, rdi
0x1800c0ffe  jz      loc_1800C10FE
0x1800c1004  mov     rax, [rdi]
0x1800c1007  lea     rdx, [rsp+0A8h+var_58]
0x1800c100c  mov     rcx, rdi
0x1800c100f  mov     rax, [rax+40h]
0x1800c1013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1018  mov     rcx, [rsp+0A8h]; this
0x1800c1020  test    eax, eax
0x1800c1022  jns     short loc_1800C1038
0x1800c1024  mov     r9d, eax; char *
0x1800c1027  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c102e  mov     edx, 76Eh; void *
0x1800c1033  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c1038  mov     rax, [rdi]
0x1800c103b  mov     rbx, [rax+30h]
0x1800c103f  mov     rcx, [rsp+0A8h+string]; string
0x1800c1044  call    cs:__imp_WindowsDeleteString
0x1800c104a  mov     [rsp+0A8h+string], 0
0x1800c1053  lea     rdx, [rsp+0A8h+string]
0x1800c1058  mov     rcx, rdi
0x1800c105b  mov     rax, rbx
0x1800c105e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1063  mov     rcx, [rsp+0A8h]; this
0x1800c106b  xor     ebx, ebx
0x1800c106d  test    eax, eax
0x1800c106f  jns     short loc_1800C1085
0x1800c1071  mov     r9d, eax; char *
0x1800c1074  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c107b  mov     edx, 76Fh; void *
0x1800c1080  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c1085  mov     [rsp+0A8h+var_40], rbx
0x1800c108a  mov     rax, [rdi]
0x1800c108d  lea     r8, [rsp+0A8h+var_40]
0x1800c1092  lea     rdx, _GUID_f4646e08_ed26_4bf9_9679_48f628e53df8
0x1800c1099  mov     rcx, rdi
0x1800c109c  mov     rax, [rax]
0x1800c109f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c10a4  test    eax, eax
0x1800c10a6  js      short loc_1800C10E2
0x1800c10a8  mov     rcx, [rsp+0A8h+var_40]
0x1800c10ad  mov     rax, [rcx]
0x1800c10b0  lea     rdx, [rsp+0A8h+arg_38]
0x1800c10b8  mov     rax, [rax+30h]
0x1800c10bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c10c1  mov     rcx, [rsp+0A8h]; this
0x1800c10c9  test    eax, eax
0x1800c10cb  jns     short loc_1800C10E2
0x1800c10cd  mov     r9d, eax; char *
0x1800c10d0  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c10d7  mov     edx, 774h; void *
0x1800c10dc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c10e2  mov     rcx, [rsp+0A8h+var_40]
0x1800c10e7  test    rcx, rcx
0x1800c10ea  jz      short loc_1800C10FE
0x1800c10ec  mov     [rsp+0A8h+var_40], rbx
0x1800c10f1  mov     rax, [rcx]
0x1800c10f4  mov     rax, [rax+10h]
0x1800c10f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c10fd  nop
0x1800c10fe  mov     [rsp+0A8h+var_50], rbx
0x1800c1103  xor     ecx, ecx; string
0x1800c1105  call    cs:__imp_WindowsDeleteString
0x1800c110b  mov     [rsp+0A8h+var_50], rbx
0x1800c1110  lea     r8, [rsp+0A8h+var_50]; HSTRING *
0x1800c1115  lea     rdx, aWindowsApplica_40; "Windows::ApplicationModel::Store::Previ"...
0x1800c111c  mov     rcx, [rsp+0A8h+arg_28]; HSTRING
0x1800c1124  call    ?GetCallingProcessAndFunction@@YAJPEAUHSTRING__@@PEBGPEAPEAU1@@Z; GetCallingProcessAndFunction(HSTRING__ *,ushort const *,HSTRING__ * *)
0x1800c1129  mov     ebx, eax
0x1800c112b  test    eax, eax
0x1800c112d  jns     short loc_1800C1172
0x1800c112f  mov     rcx, [rsp+0A8h]; this
0x1800c1137  mov     r9d, eax; char *
0x1800c113a  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c1141  mov     edx, 779h; void *
0x1800c1146  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c114b  nop
0x1800c114c  mov     rcx, [rsp+0A8h+var_50]; string
0x1800c1151  call    cs:__imp_WindowsDeleteString
0x1800c1157  mov     [rsp+0A8h+var_50], 0
0x1800c1160  mov     rcx, [rsp+0A8h+string]; string
0x1800c1165  call    cs:__imp_WindowsDeleteString
0x1800c116b  mov     eax, ebx
0x1800c116d  jmp     loc_1800C1208
0x1800c1172  mov     al, byte ptr [rsp+0A8h+arg_38]
0x1800c1179  mov     dl, [rsp+0A8h+var_58]
0x1800c117d  mov     r8, [rsp+0A8h+var_50]
0x1800c1182  mov     r9, [rsp+0A8h+string]
0x1800c1187  lea     rcx, [r13-28h]
0x1800c118b  mov     [rsp+0A8h+var_60], r14
0x1800c1190  mov     [rsp+0A8h+var_68], al
0x1800c1194  mov     [rsp+0A8h+var_70], dl
0x1800c1198  mov     [rsp+0A8h+var_78], r8
0x1800c119d  mov     rax, [rsp+0A8h+arg_20]
0x1800c11a5  mov     [rsp+0A8h+var_80], rax
0x1800c11aa  mov     qword ptr [rsp+0A8h+var_88], r9; int
0x1800c11af  mov     r9, r15
0x1800c11b2  mov     r8, r12
0x1800c11b5  mov     rdx, rsi
0x1800c11b8  call    ?_SearchForUpdatesForUserAsync@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAAJPEAUIUser@System@6@PEAUHSTRING__@@1111EEPEAPEAU?$IAsyncOperation@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@6@@Z; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_SearchForUpdatesForUserAsync(Windows::System::IUser *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,uchar,uchar,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> * *)
0x1800c11bd  mov     rcx, [rsp+0A8h]; this
0x1800c11c5  test    eax, eax
0x1800c11c7  jns     short loc_1800C11DE
0x1800c11c9  mov     r9d, eax; char *
0x1800c11cc  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c11d3  mov     edx, 784h; void *
0x1800c11d8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c11de  mov     rcx, [rsp+0A8h+var_50]; string
0x1800c11e3  call    cs:__imp_WindowsDeleteString
0x1800c11e9  mov     [rsp+0A8h+var_50], 0
0x1800c11f2  mov     rcx, [rsp+0A8h+string]; string
0x1800c11f7  call    cs:__imp_WindowsDeleteString
0x1800c11fd  xor     eax, eax
0x1800c11ff  jmp     short loc_1800C1208
0x1800c1201  mov     eax, dword ptr [rsp+0A8h+arg_38]
0x1800c1208  add     rsp, 70h
0x1800c120c  pop     r15
0x1800c120e  pop     r14
0x1800c1210  pop     r13
0x1800c1212  pop     r12
0x1800c1214  pop     rdi
0x1800c1215  pop     rsi
0x1800c1216  pop     rbx
0x1800c1217  retn
```
