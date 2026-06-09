# AicpStartAIS(ulong)

- ea: `0x180013e1c`
- end: `0x180013f20`
- name: `?AicpStartAIS@@YAKK@Z`
- size: `260`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800138f0`

## callees

- `0x180001720`
- `0x18000228f`
- `0x180013e1c`

## import_xrefs

- `ADVAPI32!OpenSCManagerW` at `0x180013e49`
- `ADVAPI32!OpenSCManagerW` at `0x180013e49`
- `ADVAPI32!OpenServiceW` at `0x180013e73`
- `ADVAPI32!OpenServiceW` at `0x180013e73`
- `ADVAPI32!CloseServiceHandle` at `0x180013ef9`
- `ADVAPI32!CloseServiceHandle` at `0x180013f02`
- `ADVAPI32!CloseServiceHandle` at `0x180013ef9`
- `ADVAPI32!CloseServiceHandle` at `0x180013f02`
- `ADVAPI32!QueryServiceStatus` at `0x180013eb9`
- `ADVAPI32!QueryServiceStatus` at `0x180013eb9`
- `ADVAPI32!StartServiceW` at `0x180013e92`
- `ADVAPI32!StartServiceW` at `0x180013e92`
- `KERNEL32!Sleep` at `0x180013ed6`
- `KERNEL32!Sleep` at `0x180013ed6`

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
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-58h] BYREF

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
0x180013e1c  push    rbx
0x180013e1e  push    rbp
0x180013e1f  push    rsi
0x180013e20  push    rdi
0x180013e21  sub     rsp, 58h
0x180013e25  mov     rax, cs:__security_cookie
0x180013e2c  xor     rax, rsp
0x180013e2f  mov     [rsp+78h+var_38], rax
0x180013e34  xorps   xmm0, xmm0
0x180013e37  xor     edx, edx; lpDatabaseName
0x180013e39  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x180013e3e  xor     ecx, ecx; lpMachineName
0x180013e40  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x180013e45  lea     r8d, [rdx+1]; dwDesiredAccess
0x180013e49  call    cs:__imp_OpenSCManagerW
0x180013e4f  mov     rbp, rax
0x180013e52  test    rax, rax
0x180013e55  jnz     short loc_180013E63
0x180013e57  call    GetLastError_0
0x180013e5c  mov     ebx, eax
0x180013e5e  jmp     loc_180013F08
0x180013e63  mov     r8d, 14h; dwDesiredAccess
0x180013e69  lea     rdx, aAppinfo; "AppInfo"
0x180013e70  mov     rcx, rbp; hSCManager
0x180013e73  call    cs:__imp_OpenServiceW
0x180013e79  mov     rsi, rax
0x180013e7c  test    rax, rax
0x180013e7f  jnz     short loc_180013E8A
0x180013e81  call    GetLastError_0
0x180013e86  mov     ebx, eax
0x180013e88  jmp     short loc_180013EFF
0x180013e8a  xor     r8d, r8d; lpServiceArgVectors
0x180013e8d  xor     edx, edx; dwNumServiceArgs
0x180013e8f  mov     rcx, rsi; hService
0x180013e92  call    cs:__imp_StartServiceW
0x180013e98  test    eax, eax
0x180013e9a  jnz     short loc_180013EAA
0x180013e9c  call    GetLastError_0
0x180013ea1  mov     ebx, eax
0x180013ea3  cmp     eax, 420h
0x180013ea8  jnz     short loc_180013EF6
0x180013eaa  xor     edi, edi
0x180013eac  mov     ebx, 5B4h
0x180013eb1  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x180013eb6  mov     rcx, rsi; hService
0x180013eb9  call    cs:__imp_QueryServiceStatus
0x180013ebf  test    eax, eax
0x180013ec1  jz      short loc_180013EEF
0x180013ec3  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 4
0x180013ec8  jz      short loc_180013EEB
0x180013eca  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 1
0x180013ecf  jz      short loc_180013EE5
0x180013ed1  mov     ecx, 1F4h; dwMilliseconds
0x180013ed6  call    cs:__imp_Sleep
0x180013edc  inc     edi
0x180013ede  cmp     edi, 0Ah
0x180013ee1  jbe     short loc_180013EB1
0x180013ee3  jmp     short loc_180013EF6
0x180013ee5  mov     ebx, [rsp+78h+ServiceStatus.dwWin32ExitCode]
0x180013ee9  jmp     short loc_180013EF6
0x180013eeb  xor     ebx, ebx
0x180013eed  jmp     short loc_180013EF6
0x180013eef  call    GetLastError_0
0x180013ef4  mov     ebx, eax
0x180013ef6  mov     rcx, rsi; hSCObject
0x180013ef9  call    cs:__imp_CloseServiceHandle
0x180013eff  mov     rcx, rbp; hSCObject
0x180013f02  call    cs:__imp_CloseServiceHandle
0x180013f08  mov     eax, ebx
0x180013f0a  mov     rcx, [rsp+78h+var_38]
0x180013f0f  xor     rcx, rsp; StackCookie
0x180013f12  call    __security_check_cookie
0x180013f17  add     rsp, 58h
0x180013f1b  pop     rdi
0x180013f1c  pop     rsi
0x180013f1d  pop     rbp
0x180013f1e  pop     rbx
0x180013f1f  retn
```
