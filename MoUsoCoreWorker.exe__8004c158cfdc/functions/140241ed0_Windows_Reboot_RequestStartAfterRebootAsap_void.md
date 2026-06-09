# Windows::Reboot::RequestStartAfterRebootAsap(void)

- ea: `0x140241ed0`
- end: `0x140241ff6`
- name: `?RequestStartAfterRebootAsap@Reboot@Windows@@UEAAXXZ`
- size: `294`
- prototype: `void __fastcall(Windows::Reboot *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x14003c578`
- `0x140241ed0`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140241f8f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140241f9e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140241f8f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140241f9e`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140241efd`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140241efd`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140241f30`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140241f30`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x140241f68`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x140241f68`

## string_xrefs

- `0x140241fc6`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Reboot.cpp`
- `0x140241fd6`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Reboot.cpp`
- `0x140241fe5`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Reboot.cpp`

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
0x140241ed0  mov     [rsp+arg_8], rbx
0x140241ed5  mov     [rsp+arg_10], rsi
0x140241eda  push    rdi
0x140241edb  push    r14
0x140241edd  push    r15
0x140241edf  sub     rsp, 40h
0x140241ee3  mov     rax, cs:__security_cookie
0x140241eea  xor     rax, rsp
0x140241eed  mov     [rsp+58h+var_20], rax
0x140241ef2  mov     rsi, rcx
0x140241ef5  xor     edx, edx; lpDatabaseName
0x140241ef7  xor     ecx, ecx; lpMachineName
0x140241ef9  lea     r8d, [rdx+1]; dwDesiredAccess
0x140241efd  call    cs:__imp_OpenSCManagerW
0x140241f03  mov     rbx, rax
0x140241f06  mov     [rsp+58h+var_38], rax
0x140241f0b  mov     rcx, [rsp+58h]; this
0x140241f10  test    rax, rax
0x140241f13  setnz   r14b
0x140241f17  test    rax, rax
0x140241f1a  jz      loc_140241FC6
0x140241f20  mov     r8d, 2; dwDesiredAccess
0x140241f26  lea     rdx, ServiceName; "UsoSvc"
0x140241f2d  mov     rcx, rbx; hSCManager
0x140241f30  call    cs:__imp_OpenServiceW
0x140241f36  mov     rdi, rax
0x140241f39  mov     [rsp+58h+var_30], rax
0x140241f3e  mov     rcx, [rsp+58h]; this
0x140241f43  test    rax, rax
0x140241f46  setnz   r15b
0x140241f4a  test    rax, rax
0x140241f4d  jz      loc_140241FD6
0x140241f53  mov     [rsp+58h+Info], 0
0x140241f5b  lea     r8, [rsp+58h+Info]; lpInfo
0x140241f60  mov     edx, 3; dwInfoLevel
0x140241f65  mov     rcx, rdi; hService
0x140241f68  call    cs:__imp_ChangeServiceConfig2W
0x140241f6e  mov     rcx, [rsp+58h]; this
0x140241f73  test    eax, eax
0x140241f75  jz      short loc_140241FE5
0x140241f77  mov     rax, [rsi]
0x140241f7a  mov     rcx, rsi
0x140241f7d  mov     rax, [rax+10h]
0x140241f81  call    _guard_dispatch_icall
0x140241f86  nop
0x140241f87  test    r15b, r15b
0x140241f8a  jz      short loc_140241F96
0x140241f8c  mov     rcx, rdi; hSCObject
0x140241f8f  call    cs:__imp_CloseServiceHandle
0x140241f95  nop
0x140241f96  test    r14b, r14b
0x140241f99  jz      short loc_140241FA5
0x140241f9b  mov     rcx, rbx; hSCObject
0x140241f9e  call    cs:__imp_CloseServiceHandle
0x140241fa4  nop
0x140241fa5  mov     rcx, [rsp+58h+var_20]
0x140241faa  xor     rcx, rsp; StackCookie
0x140241fad  call    __security_check_cookie
0x140241fb2  mov     rbx, [rsp+58h+arg_8]
0x140241fb7  mov     rsi, [rsp+58h+arg_10]
0x140241fbc  add     rsp, 40h
0x140241fc0  pop     r15
0x140241fc2  pop     r14
0x140241fc4  pop     rdi
0x140241fc5  retn
0x140241fc6  lea     r8, aCW1SSrcOrchest_77; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140241fcd  lea     edx, [rax+27h]; void *
0x140241fd0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140241fd6  lea     r8, aCW1SSrcOrchest_77; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140241fdd  lea     edx, [rax+2Ah]; void *
0x140241fe0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140241fe5  lea     r8, aCW1SSrcOrchest_77; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140241fec  lea     edx, [rax+30h]; void *
0x140241fef  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
