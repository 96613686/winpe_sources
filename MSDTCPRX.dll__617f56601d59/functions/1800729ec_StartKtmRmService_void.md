# StartKtmRmService(void)

- ea: `0x1800729ec`
- end: `0x180072b43`
- name: `?StartKtmRmService@@YAJXZ`
- size: `343`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18002847c`
- `0x180042f90`

## callees

- `0x1800729ec`
- `0x180081dd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072a2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072a9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072af8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072a2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072a9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072af8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180072ab9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180072ab9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180072b10`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180072b1e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180072b10`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180072b1e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180072a5b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180072a5b`
- `api-ms-win-service-winsvc-l1-1-0!StartServiceA` at `0x180072a90`
- `api-ms-win-service-winsvc-l1-1-0!StartServiceA` at `0x180072a90`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180072aee`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180072aee`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180072a75`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180072ac7`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180072a75`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180072ac7`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x180072a1f`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x180072a1f`

## pseudocode

```c
__int64 StartKtmRmService(void)
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rsi
  signed int LastError; // eax
  unsigned int v3; // ebx
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rdi
  DWORD dwCurrentState; // eax
  signed int v7; // eax
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v0 = OpenSCManagerA(0, 0, 1u);
  v1 = v0;
  if ( !v0 )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return v3;
  }
  v4 = OpenServiceW(v0, L"KtmRm", 0x114u);
  v5 = v4;
  if ( !v4 || !QueryServiceStatus(v4, &ServiceStatus) )
    goto LABEL_18;
  dwCurrentState = ServiceStatus.dwCurrentState;
  if ( ServiceStatus.dwCurrentState != 1 )
    goto LABEL_11;
  if ( StartServiceA(v5, 0, 0) || (v7 = GetLastError(), v3 = v7, v7 == 1056) )
  {
    while ( QueryServiceStatus(v5, &ServiceStatus) )
    {
      dwCurrentState = ServiceStatus.dwCurrentState;
LABEL_11:
      if ( dwCurrentState != 2 )
      {
        if ( dwCurrentState != 4 )
        {
          v3 = -2147467259;
          goto LABEL_21;
        }
        v3 = 0;
        if ( ControlService(v5, 0x80u, &ServiceStatus) )
          goto LABEL_21;
        break;
      }
      Sleep(0x3E8u);
    }
LABEL_18:
    v7 = GetLastError();
    v3 = v7;
  }
  if ( v7 > 0 )
    v3 = (unsigned __int16)v7 | 0x80070000;
LABEL_21:
  CloseServiceHandle(v1);
  if ( v5 )
    CloseServiceHandle(v5);
  return v3;
}

```

## disassembly

```asm
0x1800729ec  mov     [rsp+arg_0], rbx
0x1800729f1  mov     [rsp+arg_8], rsi
0x1800729f6  push    rdi
0x1800729f7  sub     rsp, 50h
0x1800729fb  mov     rax, cs:__security_cookie
0x180072a02  xor     rax, rsp
0x180072a05  mov     [rsp+58h+var_18], rax
0x180072a0a  xorps   xmm0, xmm0
0x180072a0d  xor     edx, edx; lpDatabaseName
0x180072a0f  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x180072a14  xor     ecx, ecx; lpMachineName
0x180072a16  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x180072a1b  lea     r8d, [rdx+1]; dwDesiredAccess
0x180072a1f  call    cs:__imp_OpenSCManagerA
0x180072a25  mov     rsi, rax
0x180072a28  test    rax, rax
0x180072a2b  jnz     short loc_180072A4B
0x180072a2d  call    cs:__imp_GetLastError
0x180072a33  mov     ebx, eax
0x180072a35  test    eax, eax
0x180072a37  jle     loc_180072B24
0x180072a3d  movzx   ebx, ax
0x180072a40  or      ebx, 80070000h
0x180072a46  jmp     loc_180072B24
0x180072a4b  mov     r8d, 114h; dwDesiredAccess
0x180072a51  lea     rdx, ServiceName; "KtmRm"
0x180072a58  mov     rcx, rsi; hSCManager
0x180072a5b  call    cs:__imp_OpenServiceW
0x180072a61  mov     rdi, rax
0x180072a64  test    rax, rax
0x180072a67  jz      loc_180072AF8
0x180072a6d  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x180072a72  mov     rcx, rax; hService
0x180072a75  call    cs:__imp_QueryServiceStatus
0x180072a7b  test    eax, eax
0x180072a7d  jz      short loc_180072AF8
0x180072a7f  mov     eax, [rsp+58h+ServiceStatus.dwCurrentState]
0x180072a83  cmp     eax, 1
0x180072a86  jnz     short loc_180072AAF
0x180072a88  xor     r8d, r8d; lpServiceArgVectors
0x180072a8b  xor     edx, edx; dwNumServiceArgs
0x180072a8d  mov     rcx, rdi; hService
0x180072a90  call    cs:__imp_StartServiceA
0x180072a96  test    eax, eax
0x180072a98  jnz     short loc_180072ABF
0x180072a9a  call    cs:__imp_GetLastError
0x180072aa0  mov     ebx, eax
0x180072aa2  cmp     eax, 420h
0x180072aa7  jnz     short loc_180072B00
0x180072aa9  jmp     short loc_180072ABF
0x180072aab  mov     eax, [rsp+58h+ServiceStatus.dwCurrentState]
0x180072aaf  cmp     eax, 2
0x180072ab2  jnz     short loc_180072AD3
0x180072ab4  mov     ecx, 3E8h; dwMilliseconds
0x180072ab9  call    cs:__imp_Sleep
0x180072abf  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x180072ac4  mov     rcx, rdi; hService
0x180072ac7  call    cs:__imp_QueryServiceStatus
0x180072acd  test    eax, eax
0x180072acf  jnz     short loc_180072AAB
0x180072ad1  jmp     short loc_180072AF8
0x180072ad3  cmp     eax, 4
0x180072ad6  jz      short loc_180072ADF
0x180072ad8  mov     ebx, 80004005h
0x180072add  jmp     short loc_180072B0D
0x180072adf  lea     r8, [rsp+58h+ServiceStatus]; lpServiceStatus
0x180072ae4  mov     edx, 80h; dwControl
0x180072ae9  mov     rcx, rdi; hService
0x180072aec  xor     ebx, ebx
0x180072aee  call    cs:__imp_ControlService
0x180072af4  test    eax, eax
0x180072af6  jnz     short loc_180072B0D
0x180072af8  call    cs:__imp_GetLastError
0x180072afe  mov     ebx, eax
0x180072b00  test    eax, eax
0x180072b02  jle     short loc_180072B0D
0x180072b04  movzx   ebx, ax
0x180072b07  or      ebx, 80070000h
0x180072b0d  mov     rcx, rsi; hSCObject
0x180072b10  call    cs:__imp_CloseServiceHandle
0x180072b16  test    rdi, rdi
0x180072b19  jz      short loc_180072B24
0x180072b1b  mov     rcx, rdi; hSCObject
0x180072b1e  call    cs:__imp_CloseServiceHandle
0x180072b24  mov     eax, ebx
0x180072b26  mov     rcx, [rsp+58h+var_18]
0x180072b2b  xor     rcx, rsp; StackCookie
0x180072b2e  call    __security_check_cookie
0x180072b33  mov     rbx, [rsp+58h+arg_0]
0x180072b38  mov     rsi, [rsp+58h+arg_8]
0x180072b3d  add     rsp, 50h
0x180072b41  pop     rdi
0x180072b42  retn
```
