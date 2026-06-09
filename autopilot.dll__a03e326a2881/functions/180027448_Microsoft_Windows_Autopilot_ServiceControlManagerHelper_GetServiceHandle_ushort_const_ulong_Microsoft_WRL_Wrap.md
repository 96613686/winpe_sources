# Microsoft::Windows::Autopilot::ServiceControlManagerHelper::GetServiceHandle(ushort const *,ulong,Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits> &)

- ea: `0x180027448`
- end: `0x1800275d0`
- name: `?GetServiceHandle@ServiceControlManagerHelper@Autopilot@Windows@Microsoft@@SAJPEBGKAEAV?$HandleT@UServiceHandleTraits@Autopilot@Windows@Microsoft@@@Wrappers@WRL@4@@Z`
- size: `392`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002769c`

## callees

- `0x18000ec40`
- `0x1800105d4`
- `0x180027448`
- `0x180027680`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027568`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027582`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002759c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800275b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027568`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027582`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002759c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800275b6`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180027462`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180027462`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800274ca`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800274ca`

## string_xrefs

- `0x180027483`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\scmhelper.cpp`
- `0x18002750a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\scmhelper.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::ServiceControlManagerHelper::GetServiceHandle(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  SC_HANDLE v4; // rax
  const char *v5; // r9
  unsigned int LastError; // ebx
  SC_HANDLE v8; // rbx
  const char *v9; // r9
  SC_HANDLE v10; // rax
  signed int v11; // eax
  int v12; // edx
  unsigned int v13; // r8d
  signed int v14; // eax
  int v15; // edx
  unsigned int v16; // r8d
  signed int v17; // eax
  int v18; // edx
  unsigned int v19; // r8d
  void **v20; // [rsp+20h] [rbp-18h] BYREF
  SC_HANDLE v21; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v4 = OpenSCManagerW(0, 0, 1u);
  v21 = v4;
  v20 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::`vftable';
  if ( !v4 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xE,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\scmhelper.cpp",
                  v5);
    v20 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::`vftable';
    return LastError;
  }
  v8 = OpenServiceW(v4, L"w32time", 0xF01FFu);
  v10 = *(SC_HANDLE *)(a3 + 8);
  if ( v8 == v10 )
  {
    v8 = *(SC_HANDLE *)(a3 + 8);
  }
  else
  {
    if ( v10 && !(**(unsigned __int8 (__fastcall ***)(__int64))a3)(a3) )
    {
      v17 = GetLastError();
      if ( v17 > 0 )
        v17 = (unsigned __int16)v17 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v17, v18, v19);
      JUMPOUT(0x1800275CFLL);
    }
    *(_QWORD *)(a3 + 8) = v8;
  }
  if ( !v8 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x11,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\scmhelper.cpp",
                  v9);
    v20 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::`vftable';
    if ( v21
      && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::InternalClose(&v20) )
    {
      v14 = GetLastError();
      if ( v14 > 0 )
        v14 = (unsigned __int16)v14 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v14, v15, v16);
      __debugbreak();
    }
    return LastError;
  }
  v20 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::`vftable';
  if ( v21
    && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::InternalClose(&v20) )
  {
    v11 = GetLastError();
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v11, v12, v13);
    __debugbreak();
  }
  return 0;
}

```

## disassembly

```asm
0x180027448  mov     [rsp+arg_0], rbx
0x18002744d  mov     [rsp+arg_8], rbp
0x180027452  push    rdi
0x180027453  sub     rsp, 30h
0x180027457  xor     edx, edx; lpDatabaseName
0x180027459  mov     rdi, r8
0x18002745c  xor     ecx, ecx; lpMachineName
0x18002745e  lea     r8d, [rdx+1]; dwDesiredAccess
0x180027462  call    cs:__imp_OpenSCManagerW
0x180027468  mov     [rsp+38h+var_10], rax
0x18002746d  lea     rbp, ??_7?$HandleT@UServiceHandleTraits@Autopilot@Windows@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::`vftable'
0x180027474  mov     [rsp+38h+var_18], rbp
0x180027479  test    rax, rax
0x18002747c  jnz     short loc_1800274BA
0x18002747e  mov     rcx, [rsp+38h]; this
0x180027483  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002748a  lea     edx, [rax+0Eh]; void *
0x18002748d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180027492  cmp     [rsp+38h+var_10], 0
0x180027498  mov     ebx, eax
0x18002749a  mov     [rsp+38h+var_18], rbp
0x18002749f  jz      short loc_1800274B3
0x1800274a1  lea     rcx, [rsp+38h+var_18]
0x1800274a6  call    ?InternalClose@?$HandleT@UServiceHandleTraits@Autopilot@Windows@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::InternalClose(void)
0x1800274ab  test    al, al
0x1800274ad  jz      loc_18002759C
0x1800274b3  mov     eax, ebx
0x1800274b5  jmp     loc_180027558
0x1800274ba  mov     r8d, 0F01FFh; dwDesiredAccess
0x1800274c0  lea     rdx, ServiceName; "w32time"
0x1800274c7  mov     rcx, rax; hSCManager
0x1800274ca  call    cs:__imp_OpenServiceW
0x1800274d0  mov     rbx, rax
0x1800274d3  mov     rax, [rdi+8]
0x1800274d7  cmp     rbx, rax
0x1800274da  jz      short loc_1800274FD
0x1800274dc  test    rax, rax
0x1800274df  jz      short loc_1800274F7
0x1800274e1  mov     rcx, [rdi]
0x1800274e4  mov     rax, [rcx]
0x1800274e7  mov     rcx, rdi
0x1800274ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800274ef  test    al, al
0x1800274f1  jz      loc_1800275B6
0x1800274f7  mov     [rdi+8], rbx
0x1800274fb  jmp     short loc_180027500
0x1800274fd  mov     rbx, rax
0x180027500  test    rbx, rbx
0x180027503  jnz     short loc_18002753B
0x180027505  mov     rcx, [rsp+38h]; this
0x18002750a  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\moderndeployment\\au"...
0x180027511  lea     edx, [rbx+11h]; void *
0x180027514  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180027519  cmp     [rsp+38h+var_10], 0
0x18002751f  mov     ebx, eax
0x180027521  mov     [rsp+38h+var_18], rbp
0x180027526  jz      short loc_1800274B3
0x180027528  lea     rcx, [rsp+38h+var_18]
0x18002752d  call    ?InternalClose@?$HandleT@UServiceHandleTraits@Autopilot@Windows@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::InternalClose(void)
0x180027532  test    al, al
0x180027534  jz      short loc_180027582
0x180027536  jmp     loc_1800274B3
0x18002753b  cmp     [rsp+38h+var_10], 0
0x180027541  mov     [rsp+38h+var_18], rbp
0x180027546  jz      short loc_180027556
0x180027548  lea     rcx, [rsp+38h+var_18]
0x18002754d  call    ?InternalClose@?$HandleT@UServiceHandleTraits@Autopilot@Windows@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::InternalClose(void)
0x180027552  test    al, al
0x180027554  jz      short loc_180027568
0x180027556  xor     eax, eax
0x180027558  mov     rbx, [rsp+38h+arg_0]
0x18002755d  mov     rbp, [rsp+38h+arg_8]
0x180027562  add     rsp, 30h
0x180027566  pop     rdi
0x180027567  retn
0x180027568  call    cs:__imp_GetLastError
0x18002756e  test    eax, eax
0x180027570  jle     short loc_18002757A
0x180027572  movzx   eax, ax
0x180027575  or      eax, 80070000h
0x18002757a  mov     ecx, eax; this
0x18002757c  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180027581  int     3; Trap to Debugger
0x180027582  call    cs:__imp_GetLastError
0x180027588  test    eax, eax
0x18002758a  jle     short loc_180027594
0x18002758c  movzx   eax, ax
0x18002758f  or      eax, 80070000h
0x180027594  mov     ecx, eax; this
0x180027596  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18002759b  int     3; Trap to Debugger
0x18002759c  call    cs:__imp_GetLastError
0x1800275a2  test    eax, eax
0x1800275a4  jle     short loc_1800275AE
0x1800275a6  movzx   eax, ax
0x1800275a9  or      eax, 80070000h
0x1800275ae  mov     ecx, eax; this
0x1800275b0  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800275b5  int     3; Trap to Debugger
0x1800275b6  call    cs:__imp_GetLastError
0x1800275bc  test    eax, eax
0x1800275be  jle     short loc_1800275C8
0x1800275c0  movzx   eax, ax
0x1800275c3  or      eax, 80070000h
0x1800275c8  mov     ecx, eax; this
0x1800275ca  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
