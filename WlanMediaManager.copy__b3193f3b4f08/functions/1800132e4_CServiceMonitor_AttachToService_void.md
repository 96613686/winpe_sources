# CServiceMonitor::AttachToService(void)

- ea: `0x1800132e4`
- end: `0x1800133ed`
- name: `?AttachToService@CServiceMonitor@@IEAAJXZ`
- size: `265`
- prototype: `__int64 __fastcall(CServiceMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180016b04`

## callees

- `0x180003ed0`
- `0x1800132e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013322`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013358`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800133ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013322`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013358`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800133ab`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180013346`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180013346`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180013370`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180013370`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180013314`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180013314`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18001339d`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18001339d`

## string_xrefs

- `0x180013305`: `ServicesActive`

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
0x1800132e4  mov     [rsp+arg_8], rbx
0x1800132e9  mov     [rsp+arg_10], rbp
0x1800132ee  push    rsi
0x1800132ef  sub     rsp, 50h
0x1800132f3  mov     rax, cs:__security_cookie
0x1800132fa  xor     rax, rsp
0x1800132fd  mov     [rsp+58h+var_18], rax
0x180013302  mov     rsi, rcx
0x180013305  lea     rdx, DatabaseName; "ServicesActive"
0x18001330c  xor     ecx, ecx; lpMachineName
0x18001330e  mov     r8d, 1; dwDesiredAccess
0x180013314  call    cs:__imp_OpenSCManagerW
0x18001331a  mov     rbp, rax
0x18001331d  test    rax, rax
0x180013320  jnz     short loc_180013339
0x180013322  call    cs:__imp_GetLastError
0x180013328  mov     ebx, eax
0x18001332a  test    eax, eax
0x18001332c  jle     short loc_180013376
0x18001332e  movzx   ebx, ax
0x180013331  or      ebx, 80070000h
0x180013337  jmp     short loc_180013376
0x180013339  xor     ebx, ebx
0x18001333b  lea     rdx, [rsi+8]; lpServiceName
0x18001333f  mov     rcx, rbp; hSCManager
0x180013342  lea     r8d, [rbx+4]; dwDesiredAccess
0x180013346  call    cs:__imp_OpenServiceW
0x18001334c  mov     [rsi+218h], rax
0x180013353  test    rax, rax
0x180013356  jnz     short loc_18001336D
0x180013358  call    cs:__imp_GetLastError
0x18001335e  mov     ebx, eax
0x180013360  test    eax, eax
0x180013362  jle     short loc_18001336D
0x180013364  movzx   ebx, ax
0x180013367  or      ebx, 80070000h
0x18001336d  mov     rcx, rbp; hSCObject
0x180013370  call    cs:__imp_CloseServiceHandle
0x180013376  test    ebx, ebx
0x180013378  js      short loc_1800133CE
0x18001337a  mov     rcx, [rsi+218h]; hService
0x180013381  xorps   xmm0, xmm0
0x180013384  mov     ebx, 80004005h
0x180013389  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x18001338e  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x180013393  test    rcx, rcx
0x180013396  jz      short loc_1800133C0
0x180013398  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18001339d  call    cs:__imp_QueryServiceStatus
0x1800133a3  test    eax, eax
0x1800133a5  jz      short loc_1800133AB
0x1800133a7  xor     ebx, ebx
0x1800133a9  jmp     short loc_1800133C4
0x1800133ab  call    cs:__imp_GetLastError
0x1800133b1  mov     ebx, eax
0x1800133b3  test    eax, eax
0x1800133b5  jle     short loc_1800133C0
0x1800133b7  movzx   ebx, ax
0x1800133ba  or      ebx, 80070000h
0x1800133c0  test    ebx, ebx
0x1800133c2  js      short loc_1800133CE
0x1800133c4  mov     eax, [rsp+58h+ServiceStatus.dwCurrentState]
0x1800133c8  mov     [rsi+20Ch], eax
0x1800133ce  mov     eax, ebx
0x1800133d0  mov     rcx, [rsp+58h+var_18]
0x1800133d5  xor     rcx, rsp; StackCookie
0x1800133d8  call    __security_check_cookie
0x1800133dd  mov     rbx, [rsp+58h+arg_8]
0x1800133e2  mov     rbp, [rsp+58h+arg_10]
0x1800133e7  add     rsp, 50h
0x1800133eb  pop     rsi
0x1800133ec  retn
```
