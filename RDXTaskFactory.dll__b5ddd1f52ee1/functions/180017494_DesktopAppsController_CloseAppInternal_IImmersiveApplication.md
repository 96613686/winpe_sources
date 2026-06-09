# DesktopAppsController::CloseAppInternal(IImmersiveApplication *)

- ea: `0x180017494`
- end: `0x180017574`
- name: `?CloseAppInternal@DesktopAppsController@@AEAAJPEAUIImmersiveApplication@@@Z`
- size: `224`
- prototype: `__int64 __fastcall(DesktopAppsController *__hidden this, struct IImmersiveApplication *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800172c0`

## callees

- `0x180008bbc`
- `0x18000aa7c`
- `0x180017494`
- `0x180017608`
- `0x180050010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x1800174fc`
- `SHCORE!IUnknown_QueryService` at `0x1800174fc`

## string_xrefs

- `0x1800174bc`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktopappscontroller.cpp`
- `0x180017540`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktopappscontroller.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DesktopAppsController::CloseAppInternal(IUnknown **this, struct IImmersiveApplication *a2)
{
  int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  unsigned int v7; // ebx
  HRESULT v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // r8
  int v13; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  void *ppvOut; // [rsp+50h] [rbp+18h] BYREF

  v4 = DesktopAppsController::EnsureImmersiveShellInitialized((DesktopAppsController *)this);
  v7 = v4;
  if ( v4 >= 0 )
  {
    ppvOut = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvOut, v5, v6);
    v8 = IUnknown_QueryService(this[6], &guidService, &GUID_103231ae_04cb_4e5e_b63d_e3ce47cd0f0a, &ppvOut);
    v7 = v8;
    if ( v8 >= 0 )
    {
      v13 = 6;
      v8 = (*(__int64 (__fastcall **)(void *, struct IImmersiveApplication *, __int64))(*(_QWORD *)ppvOut + 32LL))(
             ppvOut,
             a2,
             10);
      v7 = v8;
      if ( v8 >= 0 )
      {
        v7 = 0;
        goto LABEL_9;
      }
      v9 = 228;
    }
    else
    {
      v9 = 227;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktopappscontroller.cpp",
      (const char *)(unsigned int)v8,
      v13);
LABEL_9:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvOut, v10, v11);
    return v7;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xE1,
    (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktopappscontroller.cpp",
    (const char *)(unsigned int)v4,
    v13);
  return v7;
}

```

## disassembly

```asm
0x180017494  mov     [rsp+arg_0], rbx
0x180017499  mov     [rsp+arg_8], rsi
0x18001749e  push    rdi
0x18001749f  sub     rsp, 30h
0x1800174a3  mov     rsi, rdx
0x1800174a6  mov     rdi, rcx
0x1800174a9  call    ?EnsureImmersiveShellInitialized@DesktopAppsController@@AEAAJXZ; DesktopAppsController::EnsureImmersiveShellInitialized(void)
0x1800174ae  mov     ebx, eax
0x1800174b0  test    eax, eax
0x1800174b2  jns     short loc_1800174D2
0x1800174b4  mov     rcx, [rsp+38h]; this
0x1800174b9  mov     r9d, eax; char *
0x1800174bc  lea     r8, aPcshellShellRe_9; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800174c3  mov     edx, 0E1h; void *
0x1800174c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800174cd  jmp     loc_180017562
0x1800174d2  mov     [rsp+38h+ppvOut], 0
0x1800174db  lea     rcx, [rsp+38h+ppvOut]
0x1800174e0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800174e5  lea     r9, [rsp+38h+ppvOut]; ppvOut
0x1800174ea  lea     r8, _GUID_103231ae_04cb_4e5e_b63d_e3ce47cd0f0a; riid
0x1800174f1  lea     rdx, guidService; guidService
0x1800174f8  mov     rcx, [rdi+30h]; punk
0x1800174fc  call    cs:__imp_IUnknown_QueryService
0x180017502  mov     ebx, eax
0x180017504  test    eax, eax
0x180017506  jns     short loc_18001750F
0x180017508  mov     edx, 0E3h
0x18001750d  jmp     short loc_180017540
0x18001750f  mov     rcx, [rsp+38h+ppvOut]
0x180017514  mov     rax, [rcx]
0x180017517  mov     [rsp+38h+var_18], 6; int
0x18001751f  mov     r9d, 2
0x180017525  lea     r8d, [r9+8]
0x180017529  mov     rdx, rsi
0x18001752c  mov     rax, [rax+20h]
0x180017530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017535  mov     ebx, eax
0x180017537  test    eax, eax
0x180017539  jns     short loc_180017556
0x18001753b  mov     edx, 0E4h; void *
0x180017540  lea     r8, aPcshellShellRe_9; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180017547  mov     r9d, eax; char *
0x18001754a  mov     rcx, [rsp+38h]; this
0x18001754f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017554  jmp     short loc_180017558
0x180017556  xor     ebx, ebx
0x180017558  lea     rcx, [rsp+38h+ppvOut]
0x18001755d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017562  mov     eax, ebx
0x180017564  mov     rbx, [rsp+38h+arg_0]
0x180017569  mov     rsi, [rsp+38h+arg_8]
0x18001756e  add     rsp, 30h
0x180017572  pop     rdi
0x180017573  retn
```
