# Microsoft::Windows::Autopilot::ServiceControlManagerHelper::GetServiceHandle(ushort const *,ulong,Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits> &)

- ea: `0x180028470`
- end: `0x18002861d`
- name: `?GetServiceHandle@ServiceControlManagerHelper@Autopilot@Windows@Microsoft@@SAJPEBGKAEAV?$HandleT@UServiceHandleTraits@Autopilot@Windows@Microsoft@@@Wrappers@WRL@4@@Z`
- size: `429`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800286f4`

## callees

- `0x18000ed44`
- `0x180010744`
- `0x180028470`
- `0x1800286d0`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002859d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800285bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800285dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800285fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002859d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800285bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800285dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800285fd`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002848a`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002848a`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800284f8`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800284f8`

## string_xrefs

- `0x1800284b1`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\scmhelper.cpp`
- `0x18002853e`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\scmhelper.cpp`

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
      JUMPOUT(0x18002861CLL);
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
0x180028470  mov     [rsp+arg_0], rbx
0x180028475  mov     [rsp+arg_8], rbp
0x18002847a  push    rdi
0x18002847b  sub     rsp, 30h
0x18002847f  xor     edx, edx; lpDatabaseName
0x180028481  mov     rdi, r8
0x180028484  xor     ecx, ecx; lpMachineName
0x180028486  lea     r8d, [rdx+1]; dwDesiredAccess
0x18002848a  call    cs:__imp_OpenSCManagerW
0x180028491  nop     dword ptr [rax+rax+00h]
0x180028496  mov     [rsp+38h+var_10], rax
0x18002849b  lea     rbp, ??_7?$HandleT@UServiceHandleTraits@Autopilot@Windows@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::`vftable'
0x1800284a2  mov     [rsp+38h+var_18], rbp
0x1800284a7  test    rax, rax
0x1800284aa  jnz     short loc_1800284E8
0x1800284ac  mov     rcx, [rsp+38h]; this
0x1800284b1  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800284b8  lea     edx, [rax+0Eh]; void *
0x1800284bb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800284c0  cmp     [rsp+38h+var_10], 0
0x1800284c6  mov     ebx, eax
0x1800284c8  mov     [rsp+38h+var_18], rbp
0x1800284cd  jz      short loc_1800284E1
0x1800284cf  lea     rcx, [rsp+38h+var_18]
0x1800284d4  call    ?InternalClose@?$HandleT@UServiceHandleTraits@Autopilot@Windows@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::InternalClose(void)
0x1800284d9  test    al, al
0x1800284db  jz      loc_1800285DD
0x1800284e1  mov     eax, ebx
0x1800284e3  jmp     loc_18002858C
0x1800284e8  mov     r8d, 0F01FFh; dwDesiredAccess
0x1800284ee  lea     rdx, ServiceName; "w32time"
0x1800284f5  mov     rcx, rax; hSCManager
0x1800284f8  call    cs:__imp_OpenServiceW
0x1800284ff  nop     dword ptr [rax+rax+00h]
0x180028504  mov     rbx, rax
0x180028507  mov     rax, [rdi+8]
0x18002850b  cmp     rbx, rax
0x18002850e  jz      short loc_180028531
0x180028510  test    rax, rax
0x180028513  jz      short loc_18002852B
0x180028515  mov     rcx, [rdi]
0x180028518  mov     rax, [rcx]
0x18002851b  mov     rcx, rdi
0x18002851e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028523  test    al, al
0x180028525  jz      loc_1800285FD
0x18002852b  mov     [rdi+8], rbx
0x18002852f  jmp     short loc_180028534
0x180028531  mov     rbx, rax
0x180028534  test    rbx, rbx
0x180028537  jnz     short loc_18002856F
0x180028539  mov     rcx, [rsp+38h]; this
0x18002853e  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\moderndeployment\\au"...
0x180028545  lea     edx, [rbx+11h]; void *
0x180028548  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002854d  cmp     [rsp+38h+var_10], 0
0x180028553  mov     ebx, eax
0x180028555  mov     [rsp+38h+var_18], rbp
0x18002855a  jz      short loc_1800284E1
0x18002855c  lea     rcx, [rsp+38h+var_18]
0x180028561  call    ?InternalClose@?$HandleT@UServiceHandleTraits@Autopilot@Windows@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::InternalClose(void)
0x180028566  test    al, al
0x180028568  jz      short loc_1800285BD
0x18002856a  jmp     loc_1800284E1
0x18002856f  cmp     [rsp+38h+var_10], 0
0x180028575  mov     [rsp+38h+var_18], rbp
0x18002857a  jz      short loc_18002858A
0x18002857c  lea     rcx, [rsp+38h+var_18]
0x180028581  call    ?InternalClose@?$HandleT@UServiceHandleTraits@Autopilot@Windows@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::InternalClose(void)
0x180028586  test    al, al
0x180028588  jz      short loc_18002859D
0x18002858a  xor     eax, eax
0x18002858c  mov     rbx, [rsp+38h+arg_0]
0x180028591  mov     rbp, [rsp+38h+arg_8]
0x180028596  add     rsp, 30h
0x18002859a  pop     rdi
0x18002859b  retn
0x18002859d  call    cs:__imp_GetLastError
0x1800285a4  nop     dword ptr [rax+rax+00h]
0x1800285a9  test    eax, eax
0x1800285ab  jle     short loc_1800285B5
0x1800285ad  movzx   eax, ax
0x1800285b0  or      eax, 80070000h
0x1800285b5  mov     ecx, eax; this
0x1800285b7  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800285bc  int     3; Trap to Debugger
0x1800285bd  call    cs:__imp_GetLastError
0x1800285c4  nop     dword ptr [rax+rax+00h]
0x1800285c9  test    eax, eax
0x1800285cb  jle     short loc_1800285D5
0x1800285cd  movzx   eax, ax
0x1800285d0  or      eax, 80070000h
0x1800285d5  mov     ecx, eax; this
0x1800285d7  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800285dc  int     3; Trap to Debugger
0x1800285dd  call    cs:__imp_GetLastError
0x1800285e4  nop     dword ptr [rax+rax+00h]
0x1800285e9  test    eax, eax
0x1800285eb  jle     short loc_1800285F5
0x1800285ed  movzx   eax, ax
0x1800285f0  or      eax, 80070000h
0x1800285f5  mov     ecx, eax; this
0x1800285f7  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800285fc  int     3; Trap to Debugger
0x1800285fd  call    cs:__imp_GetLastError
0x180028604  nop     dword ptr [rax+rax+00h]
0x180028609  test    eax, eax
0x18002860b  jle     short loc_180028615
0x18002860d  movzx   eax, ax
0x180028610  or      eax, 80070000h
0x180028615  mov     ecx, eax; this
0x180028617  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
