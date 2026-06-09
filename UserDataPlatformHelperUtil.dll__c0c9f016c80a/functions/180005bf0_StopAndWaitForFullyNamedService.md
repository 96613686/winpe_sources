# StopAndWaitForFullyNamedService

- ea: `0x180005bf0`
- end: `0x180005d7f`
- name: `StopAndWaitForFullyNamedService`
- size: `399`
- prototype: `signed int __fastcall(LPCWSTR lpServiceName, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180005d90`

## callees

- `0x180005bf0`
- `0x18000a190`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005cbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ccc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005cbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ccc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d46`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180005c57`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180005ce1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180005c57`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180005ce1`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180005c81`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180005c81`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180005c29`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180005c29`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005d02`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005d0d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005d1a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005d3c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005d02`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005d0d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005d1a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005d3c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180005c45`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180005c45`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x180005ca9`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x180005ca9`

## pseudocode

```c
signed int __fastcall StopAndWaitForFullyNamedService(LPCWSTR lpServiceName, unsigned int a2)
{
  __int64 v2; // r14
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rdi
  SC_HANDLE v6; // rbx
  int v7; // r12d
  ULONGLONG v8; // r15
  int v9; // eax
  unsigned int v10; // esi
  signed int LastError; // eax
  ULONGLONG TickCount64; // rax
  signed int v13; // eax
  signed int result; // eax
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-58h] BYREF

  v2 = a2;
  v4 = OpenSCManagerW(0, 0, 1u);
  v5 = v4;
  if ( v4 )
  {
    v6 = OpenServiceW(v4, lpServiceName, 0x24u);
    if ( v6 )
    {
      v7 = 1;
      v8 = GetTickCount64() + v2;
      while ( 1 )
      {
        memset(&ServiceStatus, 0, sizeof(ServiceStatus));
        if ( !ControlService(v6, 1u, &ServiceStatus) )
          break;
        if ( ServiceStatus.dwCurrentState == 1 )
          goto LABEL_18;
        if ( (unsigned int)v2 <= 0x64 )
          LODWORD(v2) = 100;
        v9 = WaitServiceState(v6, 1, (unsigned int)v2);
        if ( v9 == 1 )
        {
          CloseServiceHandle(v6);
          v10 = 0;
          goto LABEL_22;
        }
        v10 = -2147467259;
        if ( !v9 )
          goto LABEL_12;
LABEL_14:
        TickCount64 = GetTickCount64();
        if ( v8 > TickCount64 )
        {
          ++v7;
          LODWORD(v2) = v8 - TickCount64;
          if ( v7 <= 3 )
            continue;
        }
        CloseServiceHandle(v6);
        goto LABEL_22;
      }
      if ( GetLastError() == 1062 )
      {
LABEL_18:
        CloseServiceHandle(v6);
        v10 = 1;
        goto LABEL_22;
      }
LABEL_12:
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_14;
    }
    v13 = GetLastError();
    if ( v13 > 0 )
      v13 = (unsigned __int16)v13 | 0x80070000;
    v10 = v13;
LABEL_22:
    CloseServiceHandle(v5);
    return v10;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180005bf0  mov     [rsp+arg_10], rbx
0x180005bf5  mov     [rsp+arg_18], rsi
0x180005bfa  push    rdi
0x180005bfb  push    r12
0x180005bfd  push    r13
0x180005bff  push    r14
0x180005c01  push    r15
0x180005c03  sub     rsp, 50h
0x180005c07  mov     rax, cs:__security_cookie
0x180005c0e  xor     rax, rsp
0x180005c11  mov     [rsp+78h+var_38], rax
0x180005c16  mov     r14d, edx
0x180005c19  mov     rbx, rcx
0x180005c1c  mov     r13d, 1
0x180005c22  xor     edx, edx; lpDatabaseName
0x180005c24  mov     r8d, r13d; dwDesiredAccess
0x180005c27  xor     ecx, ecx; lpMachineName
0x180005c29  call    cs:__imp_OpenSCManagerW
0x180005c2f  mov     rdi, rax
0x180005c32  test    rax, rax
0x180005c35  jz      loc_180005D46
0x180005c3b  lea     r8d, [r13+23h]; dwDesiredAccess
0x180005c3f  mov     rdx, rbx; lpServiceName
0x180005c42  mov     rcx, rax; hSCManager
0x180005c45  call    cs:__imp_OpenServiceW
0x180005c4b  mov     rbx, rax
0x180005c4e  test    rax, rax
0x180005c51  jz      loc_180005D25
0x180005c57  call    cs:__imp_GetTickCount64
0x180005c5d  mov     r12d, r13d
0x180005c60  lea     r15, [rax+r14]
0x180005c64  xorps   xmm0, xmm0
0x180005c67  lea     r8, [rsp+78h+ServiceStatus]; lpServiceStatus
0x180005c6c  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x180005c71  mov     edx, r13d; dwControl
0x180005c74  mov     rcx, rbx; hService
0x180005c77  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x180005c7c  mov     esi, 64h ; 'd'
0x180005c81  call    cs:__imp_ControlService
0x180005c87  test    eax, eax
0x180005c89  jz      short loc_180005CBF
0x180005c8b  cmp     [rsp+78h+ServiceStatus.dwCurrentState], r13d
0x180005c90  jz      loc_180005D17
0x180005c96  cmp     r14d, esi
0x180005c99  mov     edx, r13d
0x180005c9c  mov     rcx, rbx
0x180005c9f  cmovbe  r14d, esi
0x180005ca3  xor     r9d, r9d
0x180005ca6  mov     r8d, r14d
0x180005ca9  call    cs:__imp_WaitServiceState
0x180005caf  cmp     eax, r13d
0x180005cb2  jz      short loc_180005D0A
0x180005cb4  mov     esi, 80004005h
0x180005cb9  test    eax, eax
0x180005cbb  jnz     short loc_180005CE1
0x180005cbd  jmp     short loc_180005CCC
0x180005cbf  call    cs:__imp_GetLastError
0x180005cc5  cmp     eax, 426h
0x180005cca  jz      short loc_180005D17
0x180005ccc  call    cs:__imp_GetLastError
0x180005cd2  mov     esi, eax
0x180005cd4  test    eax, eax
0x180005cd6  jle     short loc_180005CE1
0x180005cd8  movzx   esi, ax
0x180005cdb  or      esi, 80070000h
0x180005ce1  call    cs:__imp_GetTickCount64
0x180005ce7  cmp     r15, rax
0x180005cea  jbe     short loc_180005CFF
0x180005cec  mov     r14d, r15d
0x180005cef  add     r12d, r13d
0x180005cf2  sub     r14d, eax
0x180005cf5  cmp     r12d, 3
0x180005cf9  jle     loc_180005C64
0x180005cff  mov     rcx, rbx; hSCObject
0x180005d02  call    cs:__imp_CloseServiceHandle
0x180005d08  jmp     short loc_180005D39
0x180005d0a  mov     rcx, rbx; hSCObject
0x180005d0d  call    cs:__imp_CloseServiceHandle
0x180005d13  xor     esi, esi
0x180005d15  jmp     short loc_180005D39
0x180005d17  mov     rcx, rbx; hSCObject
0x180005d1a  call    cs:__imp_CloseServiceHandle
0x180005d20  mov     esi, r13d
0x180005d23  jmp     short loc_180005D39
0x180005d25  call    cs:__imp_GetLastError
0x180005d2b  test    eax, eax
0x180005d2d  jle     short loc_180005D37
0x180005d2f  movzx   eax, ax
0x180005d32  or      eax, 80070000h
0x180005d37  mov     esi, eax
0x180005d39  mov     rcx, rdi; hSCObject
0x180005d3c  call    cs:__imp_CloseServiceHandle
0x180005d42  mov     eax, esi
0x180005d44  jmp     short loc_180005D58
0x180005d46  call    cs:__imp_GetLastError
0x180005d4c  test    eax, eax
0x180005d4e  jle     short loc_180005D58
0x180005d50  movzx   eax, ax
0x180005d53  or      eax, 80070000h
0x180005d58  mov     rcx, [rsp+78h+var_38]
0x180005d5d  xor     rcx, rsp; StackCookie
0x180005d60  call    __security_check_cookie
0x180005d65  lea     r11, [rsp+78h+var_28]
0x180005d6a  mov     rbx, [r11+40h]
0x180005d6e  mov     rsi, [r11+48h]
0x180005d72  mov     rsp, r11
0x180005d75  pop     r15
0x180005d77  pop     r14
0x180005d79  pop     r13
0x180005d7b  pop     r12
0x180005d7d  pop     rdi
0x180005d7e  retn
```
