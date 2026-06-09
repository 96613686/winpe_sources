# CServiceMonitor::AttachToService(void)

- ea: `0x18002a374`
- end: `0x18002a47d`
- name: `?AttachToService@CServiceMonitor@@IEAAJXZ`
- size: `265`
- prototype: `__int64 __fastcall(CServiceMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180030fbc`

## callees

- `0x180002520`
- `0x18002a374`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a3b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a3e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a43b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a3b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a3e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a43b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002a400`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002a400`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002a3d6`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002a3d6`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002a3a4`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002a3a4`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002a42d`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002a42d`

## string_xrefs

- `0x18002a395`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall CServiceMonitor::AttachToService(const WCHAR *this)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rbp
  signed int v4; // eax
  signed int v5; // ebx
  SC_HANDLE v6; // rax
  signed int LastError; // eax
  SC_HANDLE v8; // rcx
  signed int v9; // eax
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  v2 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v3 = v2;
  if ( v2 )
  {
    v5 = 0;
    v6 = OpenServiceW(v2, this + 4, 4u);
    *((_QWORD *)this + 67) = v6;
    if ( !v6 )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
    CloseServiceHandle(v3);
  }
  else
  {
    v4 = GetLastError();
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
  }
  if ( v5 >= 0 )
  {
    v8 = (SC_HANDLE)*((_QWORD *)this + 67);
    v5 = -2147467259;
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( v8 )
    {
      if ( QueryServiceStatus(v8, &ServiceStatus) )
      {
        v5 = 0;
LABEL_15:
        *((_DWORD *)this + 131) = ServiceStatus.dwCurrentState;
        return (unsigned int)v5;
      }
      v9 = GetLastError();
      v5 = v9;
      if ( v9 > 0 )
        v5 = (unsigned __int16)v9 | 0x80070000;
    }
    if ( v5 >= 0 )
      goto LABEL_15;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002a374  mov     [rsp+arg_8], rbx
0x18002a379  mov     [rsp+arg_10], rbp
0x18002a37e  push    rsi
0x18002a37f  sub     rsp, 50h
0x18002a383  mov     rax, cs:__security_cookie
0x18002a38a  xor     rax, rsp
0x18002a38d  mov     [rsp+58h+var_18], rax
0x18002a392  mov     rsi, rcx
0x18002a395  lea     rdx, DatabaseName; "ServicesActive"
0x18002a39c  xor     ecx, ecx; lpMachineName
0x18002a39e  mov     r8d, 1; dwDesiredAccess
0x18002a3a4  call    cs:__imp_OpenSCManagerW
0x18002a3aa  mov     rbp, rax
0x18002a3ad  test    rax, rax
0x18002a3b0  jnz     short loc_18002A3C9
0x18002a3b2  call    cs:__imp_GetLastError
0x18002a3b8  mov     ebx, eax
0x18002a3ba  test    eax, eax
0x18002a3bc  jle     short loc_18002A406
0x18002a3be  movzx   ebx, ax
0x18002a3c1  or      ebx, 80070000h
0x18002a3c7  jmp     short loc_18002A406
0x18002a3c9  xor     ebx, ebx
0x18002a3cb  lea     rdx, [rsi+8]; lpServiceName
0x18002a3cf  mov     rcx, rbp; hSCManager
0x18002a3d2  lea     r8d, [rbx+4]; dwDesiredAccess
0x18002a3d6  call    cs:__imp_OpenServiceW
0x18002a3dc  mov     [rsi+218h], rax
0x18002a3e3  test    rax, rax
0x18002a3e6  jnz     short loc_18002A3FD
0x18002a3e8  call    cs:__imp_GetLastError
0x18002a3ee  mov     ebx, eax
0x18002a3f0  test    eax, eax
0x18002a3f2  jle     short loc_18002A3FD
0x18002a3f4  movzx   ebx, ax
0x18002a3f7  or      ebx, 80070000h
0x18002a3fd  mov     rcx, rbp; hSCObject
0x18002a400  call    cs:__imp_CloseServiceHandle
0x18002a406  test    ebx, ebx
0x18002a408  js      short loc_18002A45E
0x18002a40a  mov     rcx, [rsi+218h]; hService
0x18002a411  xorps   xmm0, xmm0
0x18002a414  mov     ebx, 80004005h
0x18002a419  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x18002a41e  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x18002a423  test    rcx, rcx
0x18002a426  jz      short loc_18002A450
0x18002a428  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18002a42d  call    cs:__imp_QueryServiceStatus
0x18002a433  test    eax, eax
0x18002a435  jz      short loc_18002A43B
0x18002a437  xor     ebx, ebx
0x18002a439  jmp     short loc_18002A454
0x18002a43b  call    cs:__imp_GetLastError
0x18002a441  mov     ebx, eax
0x18002a443  test    eax, eax
0x18002a445  jle     short loc_18002A450
0x18002a447  movzx   ebx, ax
0x18002a44a  or      ebx, 80070000h
0x18002a450  test    ebx, ebx
0x18002a452  js      short loc_18002A45E
0x18002a454  mov     eax, [rsp+58h+ServiceStatus.dwCurrentState]
0x18002a458  mov     [rsi+20Ch], eax
0x18002a45e  mov     eax, ebx
0x18002a460  mov     rcx, [rsp+58h+var_18]
0x18002a465  xor     rcx, rsp; StackCookie
0x18002a468  call    __security_check_cookie
0x18002a46d  mov     rbx, [rsp+58h+arg_8]
0x18002a472  mov     rbp, [rsp+58h+arg_10]
0x18002a477  add     rsp, 50h
0x18002a47b  pop     rsi
0x18002a47c  retn
```
