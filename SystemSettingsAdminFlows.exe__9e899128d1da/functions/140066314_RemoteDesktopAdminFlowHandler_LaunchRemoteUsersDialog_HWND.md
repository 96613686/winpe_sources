# RemoteDesktopAdminFlowHandler::LaunchRemoteUsersDialog(HWND__ *)

- ea: `0x140066314`
- end: `0x14006641e`
- name: `?LaunchRemoteUsersDialog@RemoteDesktopAdminFlowHandler@@SAJPEAUHWND__@@@Z`
- size: `266`
- prototype: `__int64 __fastcall(HWND)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x140020120`

## callees

- `0x140005f30`
- `0x14001f3d4`
- `0x1400660ec`
- `0x14006624c`
- `0x140066314`
- `0x140066624`
- `0x1400666bc`
- `0x14007d010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1400663aa`
- `KERNEL32!GetProcAddress` at `0x1400663aa`
- `KERNEL32!LoadLibraryA` at `0x14006636f`
- `KERNEL32!LoadLibraryA` at `0x14006636f`
- `KERNEL32!FreeLibrary` at `0x1400663df`
- `KERNEL32!FreeLibrary` at `0x1400663df`

## string_xrefs

- `0x140066368`: `remotepg.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RemoteDesktopAdminFlowHandler::LaunchRemoteUsersDialog(HWND a1)
{
  unsigned int v2; // ebx
  __int64 v3; // rdx
  HMODULE LibraryA; // rax
  HMODULE v5; // rdi
  unsigned __int64 v6; // r9
  FARPROC ProcAddress; // rax
  int v8; // eax
  int v10[84]; // [rsp+20h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  wil::ActivityBase<RemoteDesktopAdminFlowTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<RemoteDesktopAdminFlowTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v10);
  *(_QWORD *)v10 = &RemoteDesktopAdminFlowTelemetryProvider::LaunchUsersActivity::`vftable';
  RemoteDesktopAdminFlowTelemetryProvider::LaunchUsersActivity::StartActivity((RemoteDesktopAdminFlowTelemetryProvider::LaunchUsersActivity *)v10);
  if ( !a1 )
  {
    v2 = -2147024809;
    v3 = 140;
LABEL_5:
    v6 = v2;
    goto LABEL_6;
  }
  LibraryA = LoadLibraryA("remotepg.dll");
  v5 = LibraryA;
  if ( !LibraryA )
  {
    v2 = -2147312566;
    v3 = 144;
    goto LABEL_5;
  }
  ProcAddress = GetProcAddress(LibraryA, "LaunchRemoteUsersDialog");
  if ( !ProcAddress )
  {
    v2 = -2147417849;
    v3 = 147;
    goto LABEL_5;
  }
  v8 = ((__int64 (__fastcall *)(HWND, HMODULE))ProcAddress)(a1, v5);
  v2 = v8;
  if ( v8 >= 0 )
  {
    FreeLibrary(v5);
    wil::ActivityBase<RemoteDesktopAdminFlowTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v10);
    v2 = 0;
    goto LABEL_12;
  }
  v6 = (unsigned int)v8;
  v3 = 149;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v3,
    (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\remotedesktop\\remotedesktopadminflowhandler.cpp",
    (const char *)v6,
    v10[0]);
LABEL_12:
  RemoteDesktopAdminFlowTelemetryProvider::LaunchUsersActivity::~LaunchUsersActivity((RemoteDesktopAdminFlowTelemetryProvider::LaunchUsersActivity *)v10);
  return v2;
}

```

## disassembly

```asm
0x140066314  mov     [rsp+arg_8], rbx
0x140066319  push    rdi
0x14006631a  sub     rsp, 180h
0x140066321  mov     rax, cs:__security_cookie
0x140066328  xor     rax, rsp
0x14006632b  mov     [rsp+188h+var_18], rax
0x140066333  mov     rbx, rcx
0x140066336  lea     rcx, [rsp+188h+var_168]; struct wil::details::IFailureCallback *
0x14006633b  call    ??0?$ActivityBase@VRemoteDesktopAdminFlowTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<RemoteDesktopAdminFlowTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<RemoteDesktopAdminFlowTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140066340  lea     rax, ??_7LaunchUsersActivity@RemoteDesktopAdminFlowTelemetryProvider@@6B@; const RemoteDesktopAdminFlowTelemetryProvider::LaunchUsersActivity::`vftable'
0x140066347  mov     qword ptr [rsp+188h+var_168], rax; int
0x14006634c  lea     rcx, [rsp+188h+var_168]; this
0x140066351  call    ?StartActivity@LaunchUsersActivity@RemoteDesktopAdminFlowTelemetryProvider@@QEAAXXZ; RemoteDesktopAdminFlowTelemetryProvider::LaunchUsersActivity::StartActivity(void)
0x140066356  nop
0x140066357  test    rbx, rbx
0x14006635a  jnz     short loc_140066368
0x14006635c  mov     ebx, 80070057h
0x140066361  mov     edx, 8Ch
0x140066366  jmp     short loc_140066387
0x140066368  lea     rcx, aRemotepgDll; "remotepg.dll"
0x14006636f  call    cs:__imp_LoadLibraryA
0x140066375  mov     rdi, rax
0x140066378  test    rax, rax
0x14006637b  jnz     short loc_1400663A0
0x14006637d  mov     ebx, 80029C4Ah
0x140066382  mov     edx, 90h; void *
0x140066387  mov     r9d, ebx; char *
0x14006638a  lea     r8, aPcshellShellSy_12; "pcshell\\shell\\systemsettings\\adminfl"...
0x140066391  mov     rcx, [rsp+188h]; this
0x140066399  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006639e  jmp     short loc_1400663F1
0x1400663a0  lea     rdx, aLaunchremoteus; "LaunchRemoteUsersDialog"
0x1400663a7  mov     rcx, rdi; hModule
0x1400663aa  call    cs:__imp_GetProcAddress
0x1400663b0  test    rax, rax
0x1400663b3  jnz     short loc_1400663C1
0x1400663b5  mov     ebx, 80010107h
0x1400663ba  mov     edx, 93h
0x1400663bf  jmp     short loc_140066387
0x1400663c1  mov     rdx, rdi
0x1400663c4  mov     rcx, rbx
0x1400663c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400663cc  mov     ebx, eax
0x1400663ce  test    eax, eax
0x1400663d0  jns     short loc_1400663DC
0x1400663d2  mov     r9d, eax
0x1400663d5  mov     edx, 95h
0x1400663da  jmp     short loc_14006638A
0x1400663dc  mov     rcx, rdi; hLibModule
0x1400663df  call    cs:__imp_FreeLibrary
0x1400663e5  lea     rcx, [rsp+188h+var_168]
0x1400663ea  call    ?Stop@?$ActivityBase@VRemoteDesktopAdminFlowTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<RemoteDesktopAdminFlowTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400663ef  xor     ebx, ebx
0x1400663f1  lea     rcx, [rsp+188h+var_168]; this
0x1400663f6  call    ??1LaunchUsersActivity@RemoteDesktopAdminFlowTelemetryProvider@@QEAA@XZ; RemoteDesktopAdminFlowTelemetryProvider::LaunchUsersActivity::~LaunchUsersActivity(void)
0x1400663fb  mov     eax, ebx
0x1400663fd  mov     rcx, [rsp+188h+var_18]
0x140066405  xor     rcx, rsp; StackCookie
0x140066408  call    __security_check_cookie
0x14006640d  mov     rbx, [rsp+188h+arg_8]
0x140066415  add     rsp, 180h
0x14006641c  pop     rdi
0x14006641d  retn
```
