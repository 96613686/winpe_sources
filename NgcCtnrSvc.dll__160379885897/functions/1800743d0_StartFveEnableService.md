# StartFveEnableService

- ea: `0x1800743d0`
- end: `0x180074554`
- name: `StartFveEnableService`
- size: `388`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800742d4`

## callees

- `0x18002c640`
- `0x1800743d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074411`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074459`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074495`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074502`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074411`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074459`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074495`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074502`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800744dc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800744dc`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180074520`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007452f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180074520`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007452f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180074445`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180074445`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x1800743fd`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x1800743fd`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800744b9`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800744b9`
- `api-ms-win-service-winsvc-l1-1-0!StartServiceA` at `0x180074485`
- `api-ms-win-service-winsvc-l1-1-0!StartServiceA` at `0x180074485`

## pseudocode

```c
__int64 StartFveEnableService()
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rbp
  signed int v2; // eax
  unsigned int dwWin32ExitCode; // ebx
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rsi
  signed int LastError; // eax
  signed int v7; // eax
  int v8; // edi
  int dwWin32ExitCode_low; // ebx
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-58h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v0 = OpenSCManagerA(0, 0, 1u);
  v1 = v0;
  if ( v0 )
  {
    v4 = OpenServiceW(v0, L"FveEnableRpc", 0x14u);
    v5 = v4;
    if ( !v4 )
    {
      LastError = GetLastError();
      dwWin32ExitCode = LastError;
      if ( LastError > 0 )
        dwWin32ExitCode = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_23;
    }
    if ( StartServiceA(v4, 0, 0) || (v7 = GetLastError(), dwWin32ExitCode = v7, v7 == 1056) )
    {
      v8 = 0;
      dwWin32ExitCode = -2147467259;
      while ( 1 )
      {
        if ( !QueryServiceStatus(v5, &ServiceStatus) )
        {
          v7 = GetLastError();
          dwWin32ExitCode = v7;
          goto LABEL_19;
        }
        if ( ServiceStatus.dwCurrentState == 4 )
        {
          dwWin32ExitCode = 0;
          goto LABEL_22;
        }
        if ( ServiceStatus.dwCurrentState == 1 )
          break;
        Sleep(0x1F4u);
        if ( (unsigned int)++v8 > 0xA )
          goto LABEL_22;
      }
      dwWin32ExitCode = ServiceStatus.dwWin32ExitCode;
      if ( (int)ServiceStatus.dwWin32ExitCode <= 0 )
        goto LABEL_22;
      dwWin32ExitCode_low = LOWORD(ServiceStatus.dwWin32ExitCode);
    }
    else
    {
LABEL_19:
      if ( v7 <= 0 )
      {
LABEL_22:
        CloseServiceHandle(v5);
LABEL_23:
        CloseServiceHandle(v1);
        return dwWin32ExitCode;
      }
      dwWin32ExitCode_low = (unsigned __int16)v7;
    }
    dwWin32ExitCode = dwWin32ExitCode_low | 0x80070000;
    goto LABEL_22;
  }
  v2 = GetLastError();
  dwWin32ExitCode = v2;
  if ( v2 > 0 )
    return (unsigned __int16)v2 | 0x80070000;
  return dwWin32ExitCode;
}

```

## disassembly

```asm
0x1800743d0  push    rbx
0x1800743d2  push    rbp
0x1800743d3  push    rsi
0x1800743d4  push    rdi
0x1800743d5  sub     rsp, 58h
0x1800743d9  mov     rax, cs:__security_cookie
0x1800743e0  xor     rax, rsp
0x1800743e3  mov     [rsp+78h+var_38], rax
0x1800743e8  xorps   xmm0, xmm0
0x1800743eb  xor     edx, edx; lpDatabaseName
0x1800743ed  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x1800743f2  xor     ecx, ecx; lpMachineName
0x1800743f4  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800743f9  lea     r8d, [rdx+1]; dwDesiredAccess
0x1800743fd  call    cs:__imp_OpenSCManagerA
0x180074404  nop     dword ptr [rax+rax+00h]
0x180074409  mov     rbp, rax
0x18007440c  test    rax, rax
0x18007440f  jnz     short loc_180074435
0x180074411  call    cs:__imp_GetLastError
0x180074418  nop     dword ptr [rax+rax+00h]
0x18007441d  mov     ebx, eax
0x18007441f  test    eax, eax
0x180074421  jle     loc_18007453B
0x180074427  movzx   ebx, ax
0x18007442a  or      ebx, 80070000h
0x180074430  jmp     loc_18007453B
0x180074435  mov     r8d, 14h; dwDesiredAccess
0x18007443b  lea     rdx, aFveenablerpc; "FveEnableRpc"
0x180074442  mov     rcx, rbp; hSCManager
0x180074445  call    cs:__imp_OpenServiceW
0x18007444c  nop     dword ptr [rax+rax+00h]
0x180074451  mov     rsi, rax
0x180074454  test    rax, rax
0x180074457  jnz     short loc_18007447D
0x180074459  call    cs:__imp_GetLastError
0x180074460  nop     dword ptr [rax+rax+00h]
0x180074465  mov     ebx, eax
0x180074467  test    eax, eax
0x180074469  jle     loc_18007452C
0x18007446f  movzx   ebx, ax
0x180074472  or      ebx, 80070000h
0x180074478  jmp     loc_18007452C
0x18007447d  xor     r8d, r8d; lpServiceArgVectors
0x180074480  xor     edx, edx; dwNumServiceArgs
0x180074482  mov     rcx, rsi; hService
0x180074485  call    cs:__imp_StartServiceA
0x18007448c  nop     dword ptr [rax+rax+00h]
0x180074491  test    eax, eax
0x180074493  jnz     short loc_1800744AA
0x180074495  call    cs:__imp_GetLastError
0x18007449c  nop     dword ptr [rax+rax+00h]
0x1800744a1  mov     ebx, eax
0x1800744a3  cmp     eax, 420h
0x1800744a8  jnz     short loc_180074510
0x1800744aa  xor     edi, edi
0x1800744ac  mov     ebx, 80004005h
0x1800744b1  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x1800744b6  mov     rcx, rsi; hService
0x1800744b9  call    cs:__imp_QueryServiceStatus
0x1800744c0  nop     dword ptr [rax+rax+00h]
0x1800744c5  test    eax, eax
0x1800744c7  jz      short loc_180074502
0x1800744c9  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 4
0x1800744ce  jz      short loc_1800744FE
0x1800744d0  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 1
0x1800744d5  jz      short loc_1800744F1
0x1800744d7  mov     ecx, 1F4h; dwMilliseconds
0x1800744dc  call    cs:__imp_Sleep
0x1800744e3  nop     dword ptr [rax+rax+00h]
0x1800744e8  inc     edi
0x1800744ea  cmp     edi, 0Ah
0x1800744ed  jbe     short loc_1800744B1
0x1800744ef  jmp     short loc_18007451D
0x1800744f1  mov     ebx, [rsp+78h+ServiceStatus.dwWin32ExitCode]
0x1800744f5  test    ebx, ebx
0x1800744f7  jle     short loc_18007451D
0x1800744f9  movzx   ebx, bx
0x1800744fc  jmp     short loc_180074517
0x1800744fe  xor     ebx, ebx
0x180074500  jmp     short loc_18007451D
0x180074502  call    cs:__imp_GetLastError
0x180074509  nop     dword ptr [rax+rax+00h]
0x18007450e  mov     ebx, eax
0x180074510  test    eax, eax
0x180074512  jle     short loc_18007451D
0x180074514  movzx   ebx, ax
0x180074517  or      ebx, 80070000h
0x18007451d  mov     rcx, rsi; hSCObject
0x180074520  call    cs:__imp_CloseServiceHandle
0x180074527  nop     dword ptr [rax+rax+00h]
0x18007452c  mov     rcx, rbp; hSCObject
0x18007452f  call    cs:__imp_CloseServiceHandle
0x180074536  nop     dword ptr [rax+rax+00h]
0x18007453b  mov     eax, ebx
0x18007453d  mov     rcx, [rsp+78h+var_38]
0x180074542  xor     rcx, rsp; StackCookie
0x180074545  call    __security_check_cookie
0x18007454a  add     rsp, 58h
0x18007454e  pop     rdi
0x18007454f  pop     rsi
0x180074550  pop     rbp
0x180074551  pop     rbx
0x180074552  retn
```
