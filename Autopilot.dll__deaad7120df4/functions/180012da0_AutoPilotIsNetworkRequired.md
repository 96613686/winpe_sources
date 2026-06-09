# AutoPilotIsNetworkRequired

- ea: `0x180012da0`
- end: `0x180013051`
- name: `AutoPilotIsNetworkRequired`
- size: `689`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800045d0`
- `0x1800098f3`
- `0x18000a608`
- `0x18000ed44`
- `0x180010764`
- `0x180012da0`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180012deb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180012deb`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180012e0f`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180012e0f`

## string_xrefs

- `0x180012ea2`: `onecoreuap\admin\moderndeployment\autopilot\dll\dllmain.cpp`
- `0x180012f27`: `onecoreuap\admin\moderndeployment\autopilot\dll\dllmain.cpp`
- `0x180012f5f`: `onecoreuap\admin\moderndeployment\autopilot\dll\dllmain.cpp`
- `0x180012f72`: `onecoreuap\admin\moderndeployment\autopilot\dll\dllmain.cpp`
- `0x180012ffd`: `onecoreuap\admin\moderndeployment\autopilot\dll\dllmain.cpp`
- `0x180012de4`: `EnterpriseDeviceManagement.Service.AutoPilot.AutoPilotServer`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AutoPilotIsNetworkRequired(_DWORD *a1)
{
  HRESULT v2; // eax
  int v3; // ebx
  int v4; // eax
  __int64 v5; // rcx
  int v6; // eax
  int v7; // edx
  __int64 (__fastcall ***v8)(_QWORD, GUID *, __int64 *); // rcx
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 (__fastcall ***v12)(_QWORD, GUID *, __int64 *); // rcx
  __int64 (__fastcall ***v13)(_QWORD, GUID *, __int64 *); // rcx
  char v15; // [rsp+20h] [rbp-50h] BYREF
  _BYTE v16[7]; // [rsp+21h] [rbp-4Fh] BYREF
  __int64 (__fastcall ***v17)(_QWORD, GUID *, __int64 *); // [rsp+28h] [rbp-48h] BYREF
  __int64 v18; // [rsp+30h] [rbp-40h] BYREF
  __int64 v19; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  HSTRING string; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  *a1 = 0;
  v16[0] = 0;
  v18 = 0;
  string = 0;
  v2 = WindowsCreateStringReference(
         L"EnterpriseDeviceManagement.Service.AutoPilot.AutoPilotServer",
         0x3Cu,
         &hstringHeader,
         &string);
  if ( v2 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v2);
    JUMPOUT(0x180013050LL);
  }
  v18 = 0;
  v19 = 0;
  v3 = RoActivateInstance(string, &v19);
  if ( v3 < 0 )
    goto LABEL_30;
  v4 = memcmp_0(&GUID_b7e853b5_72ab_46cc_9056_2ead33d1a74d, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u);
  v5 = v19;
  if ( !v4 )
  {
    v18 = v19;
    goto LABEL_7;
  }
  v3 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v19)(
         v19,
         &GUID_b7e853b5_72ab_46cc_9056_2ead33d1a74d,
         &v18);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  if ( v3 < 0 )
  {
LABEL_30:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD1,
      (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\dll\\dllmain.cpp",
      (const char *)(unsigned int)v3);
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    return (unsigned int)v3;
  }
  v5 = v18;
LABEL_7:
  v17 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v5 + 168LL))(
         v5,
         &v17);
  v3 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD4,
      (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\dll\\dllmain.cpp",
      (const char *)(unsigned int)v6);
    v8 = v17;
    if ( v17 )
    {
      v17 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v8)[2])(v8);
    }
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    return (unsigned int)v3;
  }
  v9 = v17;
  v15 = 0;
  v3 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(v17, v7, 0xEA60u, &v15);
  if ( v3 < 0 )
  {
    v10 = 101;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\dll\\dllmain.cpp",
      (const char *)(unsigned int)v3);
    v11 = 110;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\dll\\dllmain.cpp",
      (const char *)(unsigned int)v3);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD5,
      (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\dll\\dllmain.cpp",
      (const char *)(unsigned int)v3);
    v12 = v17;
    if ( v17 )
    {
      v17 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v12)[2])(v12);
    }
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    return (unsigned int)v3;
  }
  if ( v15 )
  {
    v3 = -2147023436;
    v10 = 102;
    goto LABEL_17;
  }
  v3 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), _BYTE *))(*v9)[8])(v9, v16);
  if ( v3 < 0 )
  {
    v11 = 111;
    goto LABEL_20;
  }
  *a1 = v16[0] != 0;
  v13 = v17;
  if ( v17 )
  {
    v17 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v13)[2])(v13);
  }
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  return 0;
}

```

## disassembly

```asm
0x180012da0  mov     [rsp-18h+arg_8], rbx
0x180012da5  mov     [rsp-18h+arg_10], rsi
0x180012daa  push    rbp
0x180012dab  push    rdi
0x180012dac  push    r14
0x180012dae  mov     rbp, rsp
0x180012db1  sub     rsp, 70h
0x180012db5  mov     rax, cs:__security_cookie
0x180012dbc  xor     rax, rsp
0x180012dbf  mov     [rbp+var_10], rax
0x180012dc3  mov     rsi, rcx
0x180012dc6  xor     r14d, r14d
0x180012dc9  mov     [rcx], r14d
0x180012dcc  mov     [rbp+var_4F], r14b
0x180012dd0  mov     [rbp+var_40], r14
0x180012dd4  mov     [rbp+string], r14
0x180012dd8  lea     r9, [rbp+string]; string
0x180012ddc  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180012de0  lea     edx, [r14+3Ch]; length
0x180012de4  lea     rcx, ?RuntimeClass_EnterpriseDeviceManagement_Service_AutoPilot_AutoPilotServer@@3QBGB; "EnterpriseDeviceManagement.Service.Auto"...
0x180012deb  call    cs:__imp_WindowsCreateStringReference
0x180012df2  nop     dword ptr [rax+rax+00h]
0x180012df7  test    eax, eax
0x180012df9  js      loc_180013049
0x180012dff  mov     [rbp+var_40], r14
0x180012e03  mov     [rbp+var_38], r14
0x180012e07  lea     rdx, [rbp+var_38]
0x180012e0b  mov     rcx, [rbp+string]
0x180012e0f  call    cs:__imp_RoActivateInstance
0x180012e16  nop     dword ptr [rax+rax+00h]
0x180012e1b  mov     ebx, eax
0x180012e1d  test    eax, eax
0x180012e1f  js      loc_180012FF6
0x180012e25  lea     r8d, [r14+10h]; Size
0x180012e29  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180012e30  lea     rcx, _GUID_b7e853b5_72ab_46cc_9056_2ead33d1a74d; Buf1
0x180012e37  call    memcmp_0
0x180012e3c  mov     rcx, [rbp+var_38]
0x180012e40  test    eax, eax
0x180012e42  jnz     short loc_180012E4A
0x180012e44  mov     [rbp+var_40], rcx
0x180012e48  jmp     short loc_180012E7E
0x180012e4a  mov     rax, [rcx]
0x180012e4d  lea     r8, [rbp+var_40]
0x180012e51  lea     rdx, _GUID_b7e853b5_72ab_46cc_9056_2ead33d1a74d
0x180012e58  mov     rax, [rax]
0x180012e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e60  mov     ebx, eax
0x180012e62  mov     rcx, [rbp+var_38]
0x180012e66  mov     rax, [rcx]
0x180012e69  mov     rax, [rax+10h]
0x180012e6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e72  test    ebx, ebx
0x180012e74  js      loc_180012FF6
0x180012e7a  mov     rcx, [rbp+var_40]
0x180012e7e  mov     [rbp+var_48], r14
0x180012e82  mov     rax, [rcx]
0x180012e85  lea     rdx, [rbp+var_48]
0x180012e89  mov     rax, [rax+0A8h]
0x180012e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e95  mov     ebx, eax
0x180012e97  test    eax, eax
0x180012e99  jns     short loc_180012EE9
0x180012e9b  mov     rcx, [rbp+18h]; this
0x180012e9f  mov     r9d, eax; char *
0x180012ea2  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\moderndeployment\\au"...
0x180012ea9  mov     edx, 0D4h; void *
0x180012eae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012eb3  nop
0x180012eb4  mov     rcx, [rbp+var_48]
0x180012eb8  test    rcx, rcx
0x180012ebb  jz      short loc_180012ECE
0x180012ebd  mov     [rbp+var_48], r14
0x180012ec1  mov     rax, [rcx]
0x180012ec4  mov     rax, [rax+10h]
0x180012ec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ecd  nop
0x180012ece  mov     rcx, [rbp+var_40]
0x180012ed2  test    rcx, rcx
0x180012ed5  jz      short loc_180012EE4
0x180012ed7  mov     rax, [rcx]
0x180012eda  mov     rax, [rax+10h]
0x180012ede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ee3  nop
0x180012ee4  jmp     loc_180013025
0x180012ee9  mov     rdi, [rbp+var_48]
0x180012eed  mov     [rbp+var_50], r14b
0x180012ef1  lea     r9, [rbp+var_50]
0x180012ef5  mov     r8d, 0EA60h
0x180012efb  mov     rcx, rdi
0x180012efe  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@_N@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,ulong,bool *)
0x180012f03  mov     ebx, eax
0x180012f05  test    eax, eax
0x180012f07  jns     short loc_180012F10
0x180012f09  mov     edx, 65h ; 'e'
0x180012f0e  jmp     short loc_180012F20
0x180012f10  cmp     [rbp+var_50], r14b
0x180012f14  jz      short loc_180012F3A
0x180012f16  mov     ebx, 800705B4h
0x180012f1b  mov     edx, 66h ; 'f'; void *
0x180012f20  mov     r9d, ebx; char *
0x180012f23  mov     rcx, [rbp+18h]; this
0x180012f27  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\moderndeployment\\au"...
0x180012f2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012f33  mov     edx, 6Eh ; 'n'
0x180012f38  jmp     short loc_180012F58
0x180012f3a  mov     rax, [rdi]
0x180012f3d  lea     rdx, [rbp+var_4F]
0x180012f41  mov     rcx, rdi
0x180012f44  mov     rax, [rax+40h]
0x180012f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f4d  mov     ebx, eax
0x180012f4f  test    eax, eax
0x180012f51  jns     short loc_180012FB6
0x180012f53  mov     edx, 6Fh ; 'o'; void *
0x180012f58  mov     r9d, ebx; char *
0x180012f5b  mov     rcx, [rbp+18h]; this
0x180012f5f  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\moderndeployment\\au"...
0x180012f66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012f6b  mov     rcx, [rbp+18h]; this
0x180012f6f  mov     r9d, ebx; char *
0x180012f72  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\moderndeployment\\au"...
0x180012f79  mov     edx, 0D5h; void *
0x180012f7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012f83  nop
0x180012f84  mov     rcx, [rbp+var_48]
0x180012f88  test    rcx, rcx
0x180012f8b  jz      short loc_180012F9E
0x180012f8d  mov     [rbp+var_48], r14
0x180012f91  mov     rax, [rcx]
0x180012f94  mov     rax, [rax+10h]
0x180012f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f9d  nop
0x180012f9e  mov     rcx, [rbp+var_40]
0x180012fa2  test    rcx, rcx
0x180012fa5  jz      short loc_180012FB4
0x180012fa7  mov     rdx, [rcx]
0x180012faa  mov     rax, [rdx+10h]
0x180012fae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012fb3  nop
0x180012fb4  jmp     short loc_180013025
0x180012fb6  mov     eax, r14d
0x180012fb9  cmp     [rbp+var_4F], r14b
0x180012fbd  setnz   al
0x180012fc0  mov     [rsi], eax
0x180012fc2  mov     rcx, [rbp+var_48]
0x180012fc6  test    rcx, rcx
0x180012fc9  jz      short loc_180012FDC
0x180012fcb  mov     [rbp+var_48], r14
0x180012fcf  mov     rax, [rcx]
0x180012fd2  mov     rax, [rax+10h]
0x180012fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012fdb  nop
0x180012fdc  mov     rcx, [rbp+var_40]
0x180012fe0  test    rcx, rcx
0x180012fe3  jz      short loc_180012FF2
0x180012fe5  mov     rax, [rcx]
0x180012fe8  mov     rax, [rax+10h]
0x180012fec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ff1  nop
0x180012ff2  xor     eax, eax
0x180012ff4  jmp     short loc_180013027
0x180012ff6  mov     rcx, [rbp+18h]; this
0x180012ffa  mov     r9d, ebx; char *
0x180012ffd  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\moderndeployment\\au"...
0x180013004  mov     edx, 0D1h; void *
0x180013009  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001300e  nop
0x18001300f  mov     rcx, [rbp+var_40]
0x180013013  test    rcx, rcx
0x180013016  jz      short loc_180013025
0x180013018  mov     rax, [rcx]
0x18001301b  mov     rax, [rax+10h]
0x18001301f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013024  nop
0x180013025  mov     eax, ebx
0x180013027  mov     rcx, [rbp+var_10]
0x18001302b  xor     rcx, rsp; StackCookie
0x18001302e  call    __security_check_cookie
0x180013033  lea     r11, [rsp+70h+var_s0]
0x180013038  mov     rbx, [r11+28h]
0x18001303c  mov     rsi, [r11+30h]
0x180013040  mov     rsp, r11
0x180013043  pop     r14
0x180013045  pop     rdi
0x180013046  pop     rbp
0x180013047  retn
0x180013049  mov     ecx, eax; this
0x18001304b  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
