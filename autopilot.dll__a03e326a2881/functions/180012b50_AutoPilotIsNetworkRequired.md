# AutoPilotIsNetworkRequired

- ea: `0x180012b50`
- end: `0x180012df4`
- name: `AutoPilotIsNetworkRequired`
- size: `676`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800045b0`
- `0x180009963`
- `0x18000a614`
- `0x18000ec40`
- `0x1800105f4`
- `0x180012b50`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180012b9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180012b9b`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180012bb9`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180012bb9`

## string_xrefs

- `0x180012c46`: `onecoreuap\admin\moderndeployment\autopilot\dll\dllmain.cpp`
- `0x180012ccb`: `onecoreuap\admin\moderndeployment\autopilot\dll\dllmain.cpp`
- `0x180012d03`: `onecoreuap\admin\moderndeployment\autopilot\dll\dllmain.cpp`
- `0x180012d16`: `onecoreuap\admin\moderndeployment\autopilot\dll\dllmain.cpp`
- `0x180012da1`: `onecoreuap\admin\moderndeployment\autopilot\dll\dllmain.cpp`
- `0x180012b94`: `EnterpriseDeviceManagement.Service.AutoPilot.AutoPilotServer`

## pseudocode

```c
__int64 __fastcall AutoPilotIsNetworkRequired(_DWORD *a1)
{
  HRESULT v2; // eax
  int v3; // edx
  unsigned int v4; // r8d
  int v5; // ebx
  int v6; // eax
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rdi
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v17; // [rsp+20h] [rbp-50h] BYREF
  __int64 v18; // [rsp+28h] [rbp-48h] BYREF
  __int64 v19; // [rsp+30h] [rbp-40h] BYREF
  __int64 v20; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  HSTRING string; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  *a1 = 0;
  BYTE1(v17) = 0;
  v19 = 0;
  string = 0;
  v2 = WindowsCreateStringReference(
         L"EnterpriseDeviceManagement.Service.AutoPilot.AutoPilotServer",
         0x3Cu,
         &hstringHeader,
         &string);
  if ( v2 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v2, v3, v4);
    JUMPOUT(0x180012DF3LL);
  }
  v19 = 0;
  v20 = 0;
  v5 = RoActivateInstance(string, &v20);
  if ( v5 < 0 )
    goto LABEL_30;
  v6 = memcmp_0(&GUID_b7e853b5_72ab_46cc_9056_2ead33d1a74d, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u);
  v7 = v20;
  if ( !v6 )
  {
    v19 = v20;
    goto LABEL_7;
  }
  v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v20)(
         v20,
         &GUID_b7e853b5_72ab_46cc_9056_2ead33d1a74d,
         &v19);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  if ( v5 < 0 )
  {
LABEL_30:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD1,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\dll\\dllmain.cpp",
      (const char *)(unsigned int)v5,
      v17);
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    return (unsigned int)v5;
  }
  v7 = v19;
LABEL_7:
  v18 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 168LL))(v7, &v18);
  v5 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD4,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\dll\\dllmain.cpp",
      (const char *)(unsigned int)v8,
      v17);
    v10 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    return (unsigned int)v5;
  }
  v11 = v18;
  LOBYTE(v17) = 0;
  v5 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(v18, v9, 60000, &v17);
  if ( v5 < 0 )
  {
    v12 = 101;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\dll\\dllmain.cpp",
      (const char *)(unsigned int)v5,
      v17);
    v13 = 110;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\dll\\dllmain.cpp",
      (const char *)(unsigned int)v5,
      v17);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD5,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\dll\\dllmain.cpp",
      (const char *)(unsigned int)v5,
      v17);
    v14 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    return (unsigned int)v5;
  }
  if ( (_BYTE)v17 )
  {
    v5 = -2147023436;
    v12 = 102;
    goto LABEL_17;
  }
  v5 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v11 + 64LL))(v11, (char *)&v17 + 1);
  if ( v5 < 0 )
  {
    v13 = 111;
    goto LABEL_20;
  }
  *a1 = BYTE1(v17) != 0;
  v15 = v18;
  if ( v18 )
  {
    v18 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  return 0;
}

```

## disassembly

```asm
0x180012b50  mov     [rsp-18h+arg_8], rbx
0x180012b55  mov     [rsp-18h+arg_10], rsi
0x180012b5a  push    rbp
0x180012b5b  push    rdi
0x180012b5c  push    r14
0x180012b5e  mov     rbp, rsp
0x180012b61  sub     rsp, 70h
0x180012b65  mov     rax, cs:__security_cookie
0x180012b6c  xor     rax, rsp
0x180012b6f  mov     [rbp+var_10], rax
0x180012b73  mov     rsi, rcx
0x180012b76  xor     r14d, r14d
0x180012b79  mov     [rcx], r14d
0x180012b7c  mov     [rbp+var_4F], r14b
0x180012b80  mov     [rbp+var_40], r14
0x180012b84  mov     [rbp+string], r14
0x180012b88  lea     r9, [rbp+string]; string
0x180012b8c  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180012b90  lea     edx, [r14+3Ch]; length
0x180012b94  lea     rcx, ?RuntimeClass_EnterpriseDeviceManagement_Service_AutoPilot_AutoPilotServer@@3QBGB; "EnterpriseDeviceManagement.Service.Auto"...
0x180012b9b  call    cs:__imp_WindowsCreateStringReference
0x180012ba1  test    eax, eax
0x180012ba3  js      loc_180012DEC
0x180012ba9  mov     [rbp+var_40], r14
0x180012bad  mov     [rbp+var_38], r14
0x180012bb1  lea     rdx, [rbp+var_38]
0x180012bb5  mov     rcx, [rbp+string]
0x180012bb9  call    cs:__imp_RoActivateInstance
0x180012bbf  mov     ebx, eax
0x180012bc1  test    eax, eax
0x180012bc3  js      loc_180012D9A
0x180012bc9  lea     r8d, [r14+10h]; Size
0x180012bcd  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180012bd4  lea     rcx, _GUID_b7e853b5_72ab_46cc_9056_2ead33d1a74d; Buf1
0x180012bdb  call    memcmp_0
0x180012be0  mov     rcx, [rbp+var_38]
0x180012be4  test    eax, eax
0x180012be6  jnz     short loc_180012BEE
0x180012be8  mov     [rbp+var_40], rcx
0x180012bec  jmp     short loc_180012C22
0x180012bee  mov     rax, [rcx]
0x180012bf1  lea     r8, [rbp+var_40]
0x180012bf5  lea     rdx, _GUID_b7e853b5_72ab_46cc_9056_2ead33d1a74d
0x180012bfc  mov     rax, [rax]
0x180012bff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c04  mov     ebx, eax
0x180012c06  mov     rcx, [rbp+var_38]
0x180012c0a  mov     rax, [rcx]
0x180012c0d  mov     rax, [rax+10h]
0x180012c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c16  test    ebx, ebx
0x180012c18  js      loc_180012D9A
0x180012c1e  mov     rcx, [rbp+var_40]
0x180012c22  mov     [rbp+var_48], r14
0x180012c26  mov     rax, [rcx]
0x180012c29  lea     rdx, [rbp+var_48]
0x180012c2d  mov     rax, [rax+0A8h]
0x180012c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c39  mov     ebx, eax
0x180012c3b  test    eax, eax
0x180012c3d  jns     short loc_180012C8D
0x180012c3f  mov     rcx, [rbp+18h]; this
0x180012c43  mov     r9d, eax; char *
0x180012c46  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\moderndeployment\\au"...
0x180012c4d  mov     edx, 0D4h; void *
0x180012c52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012c57  nop
0x180012c58  mov     rcx, [rbp+var_48]
0x180012c5c  test    rcx, rcx
0x180012c5f  jz      short loc_180012C72
0x180012c61  mov     [rbp+var_48], r14
0x180012c65  mov     rax, [rcx]
0x180012c68  mov     rax, [rax+10h]
0x180012c6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c71  nop
0x180012c72  mov     rcx, [rbp+var_40]
0x180012c76  test    rcx, rcx
0x180012c79  jz      short loc_180012C88
0x180012c7b  mov     rax, [rcx]
0x180012c7e  mov     rax, [rax+10h]
0x180012c82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c87  nop
0x180012c88  jmp     loc_180012DC9
0x180012c8d  mov     rdi, [rbp+var_48]
0x180012c91  mov     [rbp+var_50], r14b
0x180012c95  lea     r9, [rbp+var_50]
0x180012c99  mov     r8d, 0EA60h
0x180012c9f  mov     rcx, rdi
0x180012ca2  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@_N@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,ulong,bool *)
0x180012ca7  mov     ebx, eax
0x180012ca9  test    eax, eax
0x180012cab  jns     short loc_180012CB4
0x180012cad  mov     edx, 65h ; 'e'
0x180012cb2  jmp     short loc_180012CC4
0x180012cb4  cmp     [rbp+var_50], r14b
0x180012cb8  jz      short loc_180012CDE
0x180012cba  mov     ebx, 800705B4h
0x180012cbf  mov     edx, 66h ; 'f'; void *
0x180012cc4  mov     r9d, ebx; char *
0x180012cc7  mov     rcx, [rbp+18h]; this
0x180012ccb  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\moderndeployment\\au"...
0x180012cd2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012cd7  mov     edx, 6Eh ; 'n'
0x180012cdc  jmp     short loc_180012CFC
0x180012cde  mov     rax, [rdi]
0x180012ce1  lea     rdx, [rbp+var_4F]
0x180012ce5  mov     rcx, rdi
0x180012ce8  mov     rax, [rax+40h]
0x180012cec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012cf1  mov     ebx, eax
0x180012cf3  test    eax, eax
0x180012cf5  jns     short loc_180012D5A
0x180012cf7  mov     edx, 6Fh ; 'o'; void *
0x180012cfc  mov     r9d, ebx; char *
0x180012cff  mov     rcx, [rbp+18h]; this
0x180012d03  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\moderndeployment\\au"...
0x180012d0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012d0f  mov     rcx, [rbp+18h]; this
0x180012d13  mov     r9d, ebx; char *
0x180012d16  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\moderndeployment\\au"...
0x180012d1d  mov     edx, 0D5h; void *
0x180012d22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012d27  nop
0x180012d28  mov     rcx, [rbp+var_48]
0x180012d2c  test    rcx, rcx
0x180012d2f  jz      short loc_180012D42
0x180012d31  mov     [rbp+var_48], r14
0x180012d35  mov     rax, [rcx]
0x180012d38  mov     rax, [rax+10h]
0x180012d3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d41  nop
0x180012d42  mov     rcx, [rbp+var_40]
0x180012d46  test    rcx, rcx
0x180012d49  jz      short loc_180012D58
0x180012d4b  mov     rdx, [rcx]
0x180012d4e  mov     rax, [rdx+10h]
0x180012d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d57  nop
0x180012d58  jmp     short loc_180012DC9
0x180012d5a  mov     eax, r14d
0x180012d5d  cmp     [rbp+var_4F], r14b
0x180012d61  setnz   al
0x180012d64  mov     [rsi], eax
0x180012d66  mov     rcx, [rbp+var_48]
0x180012d6a  test    rcx, rcx
0x180012d6d  jz      short loc_180012D80
0x180012d6f  mov     [rbp+var_48], r14
0x180012d73  mov     rax, [rcx]
0x180012d76  mov     rax, [rax+10h]
0x180012d7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d7f  nop
0x180012d80  mov     rcx, [rbp+var_40]
0x180012d84  test    rcx, rcx
0x180012d87  jz      short loc_180012D96
0x180012d89  mov     rax, [rcx]
0x180012d8c  mov     rax, [rax+10h]
0x180012d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d95  nop
0x180012d96  xor     eax, eax
0x180012d98  jmp     short loc_180012DCB
0x180012d9a  mov     rcx, [rbp+18h]; this
0x180012d9e  mov     r9d, ebx; char *
0x180012da1  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\moderndeployment\\au"...
0x180012da8  mov     edx, 0D1h; void *
0x180012dad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012db2  nop
0x180012db3  mov     rcx, [rbp+var_40]
0x180012db7  test    rcx, rcx
0x180012dba  jz      short loc_180012DC9
0x180012dbc  mov     rax, [rcx]
0x180012dbf  mov     rax, [rax+10h]
0x180012dc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012dc8  nop
0x180012dc9  mov     eax, ebx
0x180012dcb  mov     rcx, [rbp+var_10]
0x180012dcf  xor     rcx, rsp; StackCookie
0x180012dd2  call    __security_check_cookie
0x180012dd7  lea     r11, [rsp+70h+var_s0]
0x180012ddc  mov     rbx, [r11+28h]
0x180012de0  mov     rsi, [r11+30h]
0x180012de4  mov     rsp, r11
0x180012de7  pop     r14
0x180012de9  pop     rdi
0x180012dea  pop     rbp
0x180012deb  retn
0x180012dec  mov     ecx, eax; this
0x180012dee  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
