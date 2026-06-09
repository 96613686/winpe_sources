# AicpStartAIS(ulong)

- ea: `0x180040d0c`
- end: `0x180040e0f`
- name: `?AicpStartAIS@@YAKK@Z`
- size: `259`
- prototype: `unsigned int __fastcall(unsigned int dwTimeout)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180035eb4`

## callees

- `0x180040d0c`
- `0x180052390`
- `0x180053138`
- `0x18005315c`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180040d82`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180040d82`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180040d39`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180040d39`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180040d63`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180040d63`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180040de8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180040df1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180040de8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180040df1`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180040da9`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180040da9`

## pseudocode

```c
__int64 __fastcall AicpStartAIS(unsigned int dwTimeout)
{
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rbp
  unsigned int dwWin32ExitCode; // ebx
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rsi
  int v6; // edi
  _SERVICE_STATUS ssService; // [rsp+20h] [rbp-58h] BYREF

  memset(&ssService, 0, sizeof(ssService));
  v1 = OpenSCManagerW(0, 0, 1u);
  v2 = v1;
  if ( v1 )
  {
    v4 = OpenServiceW(v1, L"AppInfo", 0x14u);
    v5 = v4;
    if ( v4 )
    {
      if ( StartServiceW(v4, 0, 0) || (dwWin32ExitCode = GetLastError_0(), dwWin32ExitCode == 1056) )
      {
        v6 = 0;
        dwWin32ExitCode = 1460;
        while ( QueryServiceStatus(v5, &ssService) )
        {
          if ( ssService.dwCurrentState == 4 )
          {
            dwWin32ExitCode = 0;
            goto $CleanExit_0;
          }
          if ( ssService.dwCurrentState == 1 )
          {
            dwWin32ExitCode = ssService.dwWin32ExitCode;
            goto $CleanExit_0;
          }
          Sleep_0(0x1F4u);
          if ( (unsigned int)++v6 > 0xA )
            goto $CleanExit_0;
        }
        dwWin32ExitCode = GetLastError_0();
      }
$CleanExit_0:
      CloseServiceHandle(v5);
    }
    else
    {
      dwWin32ExitCode = GetLastError_0();
    }
    CloseServiceHandle(v2);
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
0x180040d0c  push    rbx
0x180040d0e  push    rbp
0x180040d0f  push    rsi
0x180040d10  push    rdi
0x180040d11  sub     rsp, 58h
0x180040d15  mov     rax, cs:__security_cookie
0x180040d1c  xor     rax, rsp
0x180040d1f  mov     [rsp+78h+var_38], rax
0x180040d24  xorps   xmm0, xmm0
0x180040d27  xor     edx, edx; lpDatabaseName
0x180040d29  movups  xmmword ptr [rsp+78h+ssService.dwServiceType], xmm0
0x180040d2e  xor     ecx, ecx; lpMachineName
0x180040d30  movups  xmmword ptr [rsp+78h+ssService.dwWin32ExitCode], xmm0
0x180040d35  lea     r8d, [rdx+1]; dwDesiredAccess
0x180040d39  call    cs:__imp_OpenSCManagerW
0x180040d3f  mov     rbp, rax
0x180040d42  test    rax, rax
0x180040d45  jnz     short loc_180040D53
0x180040d47  call    GetLastError_0
0x180040d4c  mov     ebx, eax
0x180040d4e  jmp     loc_180040DF7
0x180040d53  mov     r8d, 14h; dwDesiredAccess
0x180040d59  lea     rdx, aAppinfo; "AppInfo"
0x180040d60  mov     rcx, rbp; hSCManager
0x180040d63  call    cs:__imp_OpenServiceW
0x180040d69  mov     rsi, rax
0x180040d6c  test    rax, rax
0x180040d6f  jnz     short loc_180040D7A
0x180040d71  call    GetLastError_0
0x180040d76  mov     ebx, eax
0x180040d78  jmp     short loc_180040DEE
0x180040d7a  xor     r8d, r8d; lpServiceArgVectors
0x180040d7d  xor     edx, edx; dwNumServiceArgs
0x180040d7f  mov     rcx, rsi; hService
0x180040d82  call    cs:__imp_StartServiceW
0x180040d88  test    eax, eax
0x180040d8a  jnz     short loc_180040D9A
0x180040d8c  call    GetLastError_0
0x180040d91  mov     ebx, eax
0x180040d93  cmp     eax, 420h
0x180040d98  jnz     short $CleanExit_0
0x180040d9a  xor     edi, edi
0x180040d9c  mov     ebx, 5B4h
0x180040da1  lea     rdx, [rsp+78h+ssService]; lpServiceStatus
0x180040da6  mov     rcx, rsi; hService
0x180040da9  call    cs:__imp_QueryServiceStatus
0x180040daf  test    eax, eax
0x180040db1  jz      short loc_180040DDE
0x180040db3  cmp     [rsp+78h+ssService.dwCurrentState], 4
0x180040db8  jz      short loc_180040DDA
0x180040dba  cmp     [rsp+78h+ssService.dwCurrentState], 1
0x180040dbf  jz      short loc_180040DD4
0x180040dc1  mov     ecx, 1F4h; dwMilliseconds
0x180040dc6  call    Sleep_0
0x180040dcb  inc     edi
0x180040dcd  cmp     edi, 0Ah
0x180040dd0  jbe     short loc_180040DA1
0x180040dd2  jmp     short $CleanExit_0
0x180040dd4  mov     ebx, [rsp+78h+ssService.dwWin32ExitCode]
0x180040dd8  jmp     short $CleanExit_0
0x180040dda  xor     ebx, ebx
0x180040ddc  jmp     short $CleanExit_0
0x180040dde  call    GetLastError_0
0x180040de3  mov     ebx, eax
0x180040de5  mov     rcx, rsi; hSCObject
0x180040de8  call    cs:__imp_CloseServiceHandle
0x180040dee  mov     rcx, rbp; hSCObject
0x180040df1  call    cs:__imp_CloseServiceHandle
0x180040df7  mov     eax, ebx
0x180040df9  mov     rcx, [rsp+78h+var_38]
0x180040dfe  xor     rcx, rsp; StackCookie
0x180040e01  call    __security_check_cookie
0x180040e06  add     rsp, 58h
0x180040e0a  pop     rdi
0x180040e0b  pop     rsi
0x180040e0c  pop     rbp
0x180040e0d  pop     rbx
0x180040e0e  retn
```
