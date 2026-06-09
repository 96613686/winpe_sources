# AicpStartAIS(ulong)

- ea: `0x180094318`
- end: `0x18009441c`
- name: `?AicpStartAIS@@YAKK@Z`
- size: `260`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18005697c`

## callees

- `0x18005ae90`
- `0x18005bb2c`
- `0x180094318`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800943d2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800943d2`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18009436f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18009436f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180094345`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180094345`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18009438e`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18009438e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800943f5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800943fe`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800943f5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800943fe`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800943b5`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800943b5`

## pseudocode

```c
__int64 __fastcall AicpStartAIS()
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rbp
  DWORD dwWin32ExitCode; // ebx
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rsi
  int v5; // edi
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-58h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v0 = OpenSCManagerW(0, 0, 1u);
  v1 = v0;
  if ( v0 )
  {
    v3 = OpenServiceW(v0, L"AppInfo", 0x14u);
    v4 = v3;
    if ( v3 )
    {
      if ( StartServiceW(v3, 0, 0) || (dwWin32ExitCode = GetLastError_0(), dwWin32ExitCode == 1056) )
      {
        v5 = 0;
        dwWin32ExitCode = 1460;
        while ( QueryServiceStatus(v4, &ServiceStatus) )
        {
          if ( ServiceStatus.dwCurrentState == 4 )
          {
            dwWin32ExitCode = 0;
            goto LABEL_16;
          }
          if ( ServiceStatus.dwCurrentState == 1 )
          {
            dwWin32ExitCode = ServiceStatus.dwWin32ExitCode;
            goto LABEL_16;
          }
          Sleep(0x1F4u);
          if ( (unsigned int)++v5 > 0xA )
            goto LABEL_16;
        }
        dwWin32ExitCode = GetLastError_0();
      }
LABEL_16:
      CloseServiceHandle(v4);
    }
    else
    {
      dwWin32ExitCode = GetLastError_0();
    }
    CloseServiceHandle(v1);
  }
  else
  {
    return GetLastError_0();
  }
  return dwWin32ExitCode;
}

```

## disassembly

```asm
0x180094318  push    rbx
0x18009431a  push    rbp
0x18009431b  push    rsi
0x18009431c  push    rdi
0x18009431d  sub     rsp, 58h
0x180094321  mov     rax, cs:__security_cookie
0x180094328  xor     rax, rsp
0x18009432b  mov     [rsp+78h+var_38], rax
0x180094330  xorps   xmm0, xmm0
0x180094333  xor     edx, edx; lpDatabaseName
0x180094335  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x18009433a  xor     ecx, ecx; lpMachineName
0x18009433c  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x180094341  lea     r8d, [rdx+1]; dwDesiredAccess
0x180094345  call    cs:__imp_OpenSCManagerW
0x18009434b  mov     rbp, rax
0x18009434e  test    rax, rax
0x180094351  jnz     short loc_18009435F
0x180094353  call    GetLastError_0
0x180094358  mov     ebx, eax
0x18009435a  jmp     loc_180094404
0x18009435f  mov     r8d, 14h; dwDesiredAccess
0x180094365  lea     rdx, ServiceName; "AppInfo"
0x18009436c  mov     rcx, rbp; hSCManager
0x18009436f  call    cs:__imp_OpenServiceW
0x180094375  mov     rsi, rax
0x180094378  test    rax, rax
0x18009437b  jnz     short loc_180094386
0x18009437d  call    GetLastError_0
0x180094382  mov     ebx, eax
0x180094384  jmp     short loc_1800943FB
0x180094386  xor     r8d, r8d; lpServiceArgVectors
0x180094389  xor     edx, edx; dwNumServiceArgs
0x18009438b  mov     rcx, rsi; hService
0x18009438e  call    cs:__imp_StartServiceW
0x180094394  test    eax, eax
0x180094396  jnz     short loc_1800943A6
0x180094398  call    GetLastError_0
0x18009439d  mov     ebx, eax
0x18009439f  cmp     eax, 420h
0x1800943a4  jnz     short loc_1800943F2
0x1800943a6  xor     edi, edi
0x1800943a8  mov     ebx, 5B4h
0x1800943ad  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x1800943b2  mov     rcx, rsi; hService
0x1800943b5  call    cs:__imp_QueryServiceStatus
0x1800943bb  test    eax, eax
0x1800943bd  jz      short loc_1800943EB
0x1800943bf  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 4
0x1800943c4  jz      short loc_1800943E7
0x1800943c6  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 1
0x1800943cb  jz      short loc_1800943E1
0x1800943cd  mov     ecx, 1F4h; dwMilliseconds
0x1800943d2  call    cs:__imp_Sleep
0x1800943d8  inc     edi
0x1800943da  cmp     edi, 0Ah
0x1800943dd  jbe     short loc_1800943AD
0x1800943df  jmp     short loc_1800943F2
0x1800943e1  mov     ebx, [rsp+78h+ServiceStatus.dwWin32ExitCode]
0x1800943e5  jmp     short loc_1800943F2
0x1800943e7  xor     ebx, ebx
0x1800943e9  jmp     short loc_1800943F2
0x1800943eb  call    GetLastError_0
0x1800943f0  mov     ebx, eax
0x1800943f2  mov     rcx, rsi; hSCObject
0x1800943f5  call    cs:__imp_CloseServiceHandle
0x1800943fb  mov     rcx, rbp; hSCObject
0x1800943fe  call    cs:__imp_CloseServiceHandle
0x180094404  mov     eax, ebx
0x180094406  mov     rcx, [rsp+78h+var_38]
0x18009440b  xor     rcx, rsp; StackCookie
0x18009440e  call    __security_check_cookie
0x180094413  add     rsp, 58h
0x180094417  pop     rdi
0x180094418  pop     rsi
0x180094419  pop     rbp
0x18009441a  pop     rbx
0x18009441b  retn
```
