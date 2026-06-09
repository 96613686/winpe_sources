# DesktopAppsController::GetApplication(ushort const *,IImmersiveApplication * *)

- ea: `0x1800177c0`
- end: `0x1800178f1`
- name: `?GetApplication@DesktopAppsController@@AEAAJPEBGPEAPEAUIImmersiveApplication@@@Z`
- size: `305`
- prototype: `int(DesktopAppsController *__hidden this, const unsigned __int16 *, struct IImmersiveApplication **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800172c0`

## callees

- `0x180008bbc`
- `0x18000aa7c`
- `0x180017608`
- `0x1800177c0`
- `0x180050010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x180017834`
- `SHCORE!IUnknown_QueryService` at `0x180017834`

## string_xrefs

- `0x1800177f7`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktopappscontroller.cpp`
- `0x180017847`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktopappscontroller.cpp`
- `0x18001789c`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktopappscontroller.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DesktopAppsController::GetApplication(
        IUnknown **this,
        const unsigned __int16 *a2,
        struct IImmersiveApplication **a3)
{
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  unsigned int v9; // ebx
  HRESULT v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // r8
  void *v15; // rdi
  __int64 (__fastcall *v16)(void *, const unsigned __int16 *, struct IImmersiveApplication **); // rbx
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // r8
  struct IImmersiveApplication *v22; // rax
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  struct IImmersiveApplication *v26; // [rsp+50h] [rbp+30h] BYREF
  void *ppvOut; // [rsp+58h] [rbp+38h] BYREF

  *a3 = 0;
  v6 = DesktopAppsController::EnsureImmersiveShellInitialized((DesktopAppsController *)this);
  v9 = v6;
  if ( v6 >= 0 )
  {
    ppvOut = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvOut, v7, v8);
    v10 = IUnknown_QueryService(
            this[6],
            (const GUID *const)&SID_ImmersiveApplicationArrayService,
            &GUID_a3c23ab7_6be2_4778_8eb0_1adb7977f76a,
            &ppvOut);
    v9 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9E,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktopappscontroller.cpp",
        (const char *)(unsigned int)v10,
        savedregs);
LABEL_10:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvOut, v13, v14);
      return v9;
    }
    v26 = 0;
    v15 = ppvOut;
    v16 = *(__int64 (__fastcall **)(void *, const unsigned __int16 *, struct IImmersiveApplication **))(*(_QWORD *)ppvOut + 32LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26, v11, v12);
    v17 = v16(v15, a2, &v26);
    v9 = v17;
    if ( v17 >= 0 )
    {
      v22 = v26;
      v26 = 0;
      *a3 = v22;
    }
    else if ( v17 != -2147319765 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA2,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktopappscontroller.cpp",
        (const char *)(unsigned int)v17,
        savedregs);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26, v20, v21);
      goto LABEL_10;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26, v18, v19);
    v9 = 0;
    goto LABEL_10;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x9C,
    (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktopappscontroller.cpp",
    (const char *)(unsigned int)v6,
    savedregs);
  return v9;
}

```

## disassembly

```asm
0x1800177c0  mov     [rsp-18h+arg_0], rbx
0x1800177c5  mov     [rsp-18h+arg_8], rsi
0x1800177ca  push    rbp
0x1800177cb  push    rdi
0x1800177cc  push    r14; int
0x1800177ce  mov     rbp, rsp
0x1800177d1  sub     rsp, 20h
0x1800177d5  mov     rsi, r8
0x1800177d8  mov     r14, rdx
0x1800177db  mov     rdi, rcx
0x1800177de  mov     qword ptr [r8], 0
0x1800177e5  call    ?EnsureImmersiveShellInitialized@DesktopAppsController@@AEAAJXZ; DesktopAppsController::EnsureImmersiveShellInitialized(void)
0x1800177ea  mov     ebx, eax
0x1800177ec  test    eax, eax
0x1800177ee  jns     short loc_18001780D
0x1800177f0  mov     rcx, [rbp+18h]; this
0x1800177f4  mov     r9d, eax; char *
0x1800177f7  lea     r8, aPcshellShellRe_9; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800177fe  mov     edx, 9Ch; void *
0x180017803  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017808  jmp     loc_1800178DC
0x18001780d  mov     [rbp+ppvOut], 0
0x180017815  lea     rcx, [rbp+ppvOut]
0x180017819  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001781e  lea     r9, [rbp+ppvOut]; ppvOut
0x180017822  lea     r8, _GUID_a3c23ab7_6be2_4778_8eb0_1adb7977f76a; riid
0x180017829  lea     rdx, SID_ImmersiveApplicationArrayService; guidService
0x180017830  mov     rcx, [rdi+30h]; punk
0x180017834  call    cs:__imp_IUnknown_QueryService
0x18001783a  mov     ebx, eax
0x18001783c  test    eax, eax
0x18001783e  jns     short loc_18001785A
0x180017840  mov     rcx, [rbp+18h]; this
0x180017844  mov     r9d, eax; char *
0x180017847  lea     r8, aPcshellShellRe_9; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18001784e  mov     edx, 9Eh; void *
0x180017853  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017858  jmp     short loc_1800178D3
0x18001785a  mov     [rbp+arg_10], 0
0x180017862  mov     rdi, [rbp+ppvOut]
0x180017866  mov     rax, [rdi]
0x180017869  mov     rbx, [rax+20h]
0x18001786d  lea     rcx, [rbp+arg_10]
0x180017871  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017876  lea     r8, [rbp+arg_10]
0x18001787a  mov     rdx, r14
0x18001787d  mov     rcx, rdi
0x180017880  mov     rax, rbx
0x180017883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017888  mov     ebx, eax
0x18001788a  test    eax, eax
0x18001788c  jns     short loc_1800178B9
0x18001788e  cmp     eax, 8002802Bh
0x180017893  jz      short loc_1800178C8
0x180017895  mov     rcx, [rbp+18h]; this
0x180017899  mov     r9d, eax; char *
0x18001789c  lea     r8, aPcshellShellRe_9; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800178a3  mov     edx, 0A2h; void *
0x1800178a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800178ad  nop
0x1800178ae  lea     rcx, [rbp+arg_10]
0x1800178b2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800178b7  jmp     short loc_1800178D3
0x1800178b9  mov     rax, [rbp+arg_10]
0x1800178bd  mov     [rbp+arg_10], 0
0x1800178c5  mov     [rsi], rax
0x1800178c8  lea     rcx, [rbp+arg_10]
0x1800178cc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800178d1  xor     ebx, ebx
0x1800178d3  lea     rcx, [rbp+ppvOut]
0x1800178d7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800178dc  mov     eax, ebx
0x1800178de  mov     rbx, [rsp+20h+arg_0]
0x1800178e3  mov     rsi, [rsp+20h+arg_8]
0x1800178e8  add     rsp, 20h
0x1800178ec  pop     r14
0x1800178ee  pop     rdi
0x1800178ef  pop     rbp
0x1800178f0  retn
```
