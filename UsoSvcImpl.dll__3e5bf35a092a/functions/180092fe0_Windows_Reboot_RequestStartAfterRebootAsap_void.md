# Windows::Reboot::RequestStartAfterRebootAsap(void)

- ea: `0x180092fe0`
- end: `0x180093106`
- name: `?RequestStartAfterRebootAsap@Reboot@Windows@@UEAAXXZ`
- size: `294`
- prototype: `void __fastcall(Windows::Reboot *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x180010f24`
- `0x180092fe0`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180093040`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180093040`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18009300d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18009300d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18009309f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800930ae`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18009309f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800930ae`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x180093078`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x180093078`

## string_xrefs

- `0x1800930d6`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Reboot.cpp`
- `0x1800930e6`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Reboot.cpp`
- `0x1800930f5`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Reboot.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Windows::Reboot::RequestStartAfterRebootAsap(Windows::Reboot *this)
{
  SC_HANDLE v2; // rax
  const char *v3; // r9
  SC_HANDLE v4; // rbx
  bool v5; // r14
  SC_HANDLE v6; // rax
  const char *v7; // r9
  SC_HANDLE v8; // rdi
  bool v9; // r15
  const char *v10; // r9
  const char *v11; // r9
  int Info; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = OpenSCManagerW(0, 0, 1u);
  try
  {
    v4 = v2;
    v5 = v2 != 0;
    if ( !v2 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x27,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Reboot.cpp",
        v3);
    v6 = OpenServiceW(v2, L"UsoSvc", 2u);
    v8 = v6;
    v9 = v6 != 0;
    if ( !v6 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x2A,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Reboot.cpp",
        v7);
    Info = 0;
    if ( !ChangeServiceConfig2W(v6, 3u, &Info) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x30,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Reboot.cpp",
        v10);
    (*(void (__fastcall **)(Windows::Reboot *))(*(_QWORD *)this + 16LL))(this);
    if ( v9 )
      CloseServiceHandle(v8);
    if ( v5 )
      CloseServiceHandle(v4);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x35,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Reboot.cpp",
      v11);
  }
}

```

## disassembly

```asm
0x180092fe0  mov     [rsp+arg_8], rbx
0x180092fe5  mov     [rsp+arg_10], rsi
0x180092fea  push    rdi
0x180092feb  push    r14
0x180092fed  push    r15
0x180092fef  sub     rsp, 40h
0x180092ff3  mov     rax, cs:__security_cookie
0x180092ffa  xor     rax, rsp
0x180092ffd  mov     [rsp+58h+var_20], rax
0x180093002  mov     rsi, rcx
0x180093005  xor     edx, edx; lpDatabaseName
0x180093007  xor     ecx, ecx; lpMachineName
0x180093009  lea     r8d, [rdx+1]; dwDesiredAccess
0x18009300d  call    cs:__imp_OpenSCManagerW
0x180093013  mov     rbx, rax
0x180093016  mov     [rsp+58h+var_38], rax
0x18009301b  mov     rcx, [rsp+58h]; this
0x180093020  test    rax, rax
0x180093023  setnz   r14b
0x180093027  test    rax, rax
0x18009302a  jz      loc_1800930D6
0x180093030  mov     r8d, 2; dwDesiredAccess
0x180093036  lea     rdx, aUsosvc; "UsoSvc"
0x18009303d  mov     rcx, rbx; hSCManager
0x180093040  call    cs:__imp_OpenServiceW
0x180093046  mov     rdi, rax
0x180093049  mov     [rsp+58h+var_30], rax
0x18009304e  mov     rcx, [rsp+58h]; this
0x180093053  test    rax, rax
0x180093056  setnz   r15b
0x18009305a  test    rax, rax
0x18009305d  jz      loc_1800930E6
0x180093063  mov     [rsp+58h+Info], 0
0x18009306b  lea     r8, [rsp+58h+Info]; lpInfo
0x180093070  mov     edx, 3; dwInfoLevel
0x180093075  mov     rcx, rdi; hService
0x180093078  call    cs:__imp_ChangeServiceConfig2W
0x18009307e  mov     rcx, [rsp+58h]; this
0x180093083  test    eax, eax
0x180093085  jz      short loc_1800930F5
0x180093087  mov     rax, [rsi]
0x18009308a  mov     rcx, rsi
0x18009308d  mov     rax, [rax+10h]
0x180093091  call    _guard_dispatch_icall
0x180093096  nop
0x180093097  test    r15b, r15b
0x18009309a  jz      short loc_1800930A6
0x18009309c  mov     rcx, rdi; hSCObject
0x18009309f  call    cs:__imp_CloseServiceHandle
0x1800930a5  nop
0x1800930a6  test    r14b, r14b
0x1800930a9  jz      short loc_1800930B5
0x1800930ab  mov     rcx, rbx; hSCObject
0x1800930ae  call    cs:__imp_CloseServiceHandle
0x1800930b4  nop
0x1800930b5  mov     rcx, [rsp+58h+var_20]
0x1800930ba  xor     rcx, rsp; StackCookie
0x1800930bd  call    __security_check_cookie
0x1800930c2  mov     rbx, [rsp+58h+arg_8]
0x1800930c7  mov     rsi, [rsp+58h+arg_10]
0x1800930cc  add     rsp, 40h
0x1800930d0  pop     r15
0x1800930d2  pop     r14
0x1800930d4  pop     rdi
0x1800930d5  retn
0x1800930d6  lea     r8, aCW1SSrcOrchest_27; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800930dd  lea     edx, [rax+27h]; void *
0x1800930e0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800930e6  lea     r8, aCW1SSrcOrchest_27; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800930ed  lea     edx, [rax+2Ah]; void *
0x1800930f0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800930f5  lea     r8, aCW1SSrcOrchest_27; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800930fc  lea     edx, [rax+30h]; void *
0x1800930ff  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
