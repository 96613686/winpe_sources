# ServiceControl::StopCollectorService(void)

- ea: `0x14000385c`
- end: `0x14000395a`
- name: `?StopCollectorService@ServiceControl@@CAJXZ`
- size: `254`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14000356c`

## callees

- `0x1400023e4`
- `0x14000385c`
- `0x1400137e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140003894`
- `KERNEL32!GetLastError` at `0x1400038f7`
- `KERNEL32!GetLastError` at `0x140003894`
- `KERNEL32!GetLastError` at `0x1400038f7`
- `ADVAPI32!ControlService` at `0x1400038ed`
- `ADVAPI32!ControlService` at `0x1400038ed`
- `ADVAPI32!QueryServiceStatus` at `0x1400038d3`
- `ADVAPI32!QueryServiceStatus` at `0x1400038d3`
- `ADVAPI32!OpenServiceW` at `0x1400038bd`
- `ADVAPI32!OpenServiceW` at `0x1400038bd`
- `ADVAPI32!OpenSCManagerW` at `0x140003886`
- `ADVAPI32!OpenSCManagerW` at `0x140003886`
- `ADVAPI32!CloseServiceHandle` at `0x14000392c`
- `ADVAPI32!CloseServiceHandle` at `0x140003935`
- `ADVAPI32!CloseServiceHandle` at `0x14000392c`
- `ADVAPI32!CloseServiceHandle` at `0x140003935`

## string_xrefs

- `0x140003912`: `SUCCESS: The service was stopped successfully\n`
- `0x14000391b`: `WARNING: The service is already stopped\n`
- `0x1400038b3`: `VsStandardCollectorService170`

## pseudocode

```c
__int64 ServiceControl::StopCollectorService(void)
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rdi
  signed int v2; // eax
  unsigned int v3; // esi
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rbx
  signed int LastError; // eax
  struct _SERVICE_STATUS ServiceStatus; // [rsp+28h] [rbp-30h] BYREF

  v0 = OpenSCManagerW(0, 0, 1u);
  v1 = v0;
  if ( v0 )
  {
    v4 = OpenServiceW(v0, L"VsStandardCollectorService170", 0x24u);
    v5 = v4;
    if ( v4 && QueryServiceStatus(v4, &ServiceStatus) )
    {
      if ( ServiceStatus.dwCurrentState == 1 )
      {
        wprintf(L"WARNING: The service is already stopped\n");
      }
      else
      {
        if ( !ControlService(v5, 1u, &ServiceStatus) )
          goto LABEL_9;
        wprintf(L"SUCCESS: The service was stopped successfully\n");
      }
      v3 = 0;
LABEL_16:
      CloseServiceHandle(v5);
LABEL_17:
      CloseServiceHandle(v1);
      return v3;
    }
LABEL_9:
    LastError = GetLastError();
    v3 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v3 = LastError;
    if ( !v5 )
      goto LABEL_17;
    goto LABEL_16;
  }
  v2 = GetLastError();
  v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v2 <= 0 )
    return (unsigned int)v2;
  return v3;
}

```

## disassembly

```asm
0x14000385c  mov     [rsp+arg_0], rbx
0x140003861  mov     [rsp+arg_8], rsi
0x140003866  push    rdi
0x140003867  sub     rsp, 50h
0x14000386b  mov     rax, cs:__security_cookie
0x140003872  xor     rax, rsp
0x140003875  mov     [rsp+58h+var_10], rax
0x14000387a  mov     esi, 1
0x14000387f  xor     edx, edx; lpDatabaseName
0x140003881  mov     r8d, esi; dwDesiredAccess
0x140003884  xor     ecx, ecx; lpMachineName
0x140003886  call    cs:__imp_OpenSCManagerW
0x14000388c  mov     rdi, rax
0x14000388f  test    rax, rax
0x140003892  jnz     short loc_1400038AD
0x140003894  call    cs:__imp_GetLastError
0x14000389a  movzx   esi, ax
0x14000389d  or      esi, 80070000h
0x1400038a3  test    eax, eax
0x1400038a5  cmovle  esi, eax
0x1400038a8  jmp     loc_14000393B
0x1400038ad  mov     r8d, 24h ; '$'; dwDesiredAccess
0x1400038b3  lea     rdx, ?WZ_SERVICENAME@@3QBGB; "VsStandardCollectorService170"
0x1400038ba  mov     rcx, rdi; hSCManager
0x1400038bd  call    cs:__imp_OpenServiceW
0x1400038c3  mov     rbx, rax
0x1400038c6  test    rax, rax
0x1400038c9  jz      short loc_1400038F7
0x1400038cb  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x1400038d0  mov     rcx, rax; hService
0x1400038d3  call    cs:__imp_QueryServiceStatus
0x1400038d9  test    eax, eax
0x1400038db  jz      short loc_1400038F7
0x1400038dd  cmp     [rsp+58h+ServiceStatus.dwCurrentState], esi
0x1400038e1  jz      short loc_14000391B
0x1400038e3  lea     r8, [rsp+58h+ServiceStatus]; lpServiceStatus
0x1400038e8  mov     edx, esi; dwControl
0x1400038ea  mov     rcx, rbx; hService
0x1400038ed  call    cs:__imp_ControlService
0x1400038f3  test    eax, eax
0x1400038f5  jnz     short loc_140003912
0x1400038f7  call    cs:__imp_GetLastError
0x1400038fd  movzx   esi, ax
0x140003900  or      esi, 80070000h
0x140003906  test    eax, eax
0x140003908  cmovle  esi, eax
0x14000390b  test    rbx, rbx
0x14000390e  jz      short loc_140003932
0x140003910  jmp     short loc_140003929
0x140003912  lea     rcx, aSuccessTheServ; "SUCCESS: The service was stopped succes"...
0x140003919  jmp     short loc_140003922
0x14000391b  lea     rcx, aWarningTheServ_0; "WARNING: The service is already stopped"...
0x140003922  call    wprintf
0x140003927  xor     esi, esi
0x140003929  mov     rcx, rbx; hSCObject
0x14000392c  call    cs:__imp_CloseServiceHandle
0x140003932  mov     rcx, rdi; hSCObject
0x140003935  call    cs:__imp_CloseServiceHandle
0x14000393b  mov     eax, esi
0x14000393d  mov     rcx, [rsp+58h+var_10]
0x140003942  xor     rcx, rsp; StackCookie
0x140003945  call    __security_check_cookie
0x14000394a  mov     rbx, [rsp+58h+arg_0]
0x14000394f  mov     rsi, [rsp+58h+arg_8]
0x140003954  add     rsp, 50h
0x140003958  pop     rdi
0x140003959  retn
```
