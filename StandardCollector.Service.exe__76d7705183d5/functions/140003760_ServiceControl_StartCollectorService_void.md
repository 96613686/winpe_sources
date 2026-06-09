# ServiceControl::StartCollectorService(void)

- ea: `0x140003760`
- end: `0x140003859`
- name: `?StartCollectorService@ServiceControl@@CAJXZ`
- size: `249`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14000356c`

## callees

- `0x1400023e4`
- `0x140003760`
- `0x1400137e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140003794`
- `KERNEL32!GetLastError` at `0x1400037f6`
- `KERNEL32!GetLastError` at `0x140003794`
- `KERNEL32!GetLastError` at `0x1400037f6`
- `ADVAPI32!StartServiceW` at `0x1400037ec`
- `ADVAPI32!StartServiceW` at `0x1400037ec`
- `ADVAPI32!QueryServiceStatus` at `0x1400037d3`
- `ADVAPI32!QueryServiceStatus` at `0x1400037d3`
- `ADVAPI32!OpenServiceW` at `0x1400037bd`
- `ADVAPI32!OpenServiceW` at `0x1400037bd`
- `ADVAPI32!OpenSCManagerW` at `0x140003786`
- `ADVAPI32!OpenSCManagerW` at `0x140003786`
- `ADVAPI32!CloseServiceHandle` at `0x14000382b`
- `ADVAPI32!CloseServiceHandle` at `0x140003834`
- `ADVAPI32!CloseServiceHandle` at `0x14000382b`
- `ADVAPI32!CloseServiceHandle` at `0x140003834`

## string_xrefs

- `0x140003811`: `SUCCESS: The service was started successfully\n`
- `0x14000381a`: `WARNING: The service is already started\n`
- `0x1400037b3`: `VsStandardCollectorService170`

## pseudocode

```c
__int64 ServiceControl::StartCollectorService(void)
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rdi
  signed int v2; // eax
  unsigned int v3; // esi
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rbx
  signed int LastError; // eax
  _SERVICE_STATUS ServiceStatus; // [rsp+28h] [rbp-30h] BYREF

  v0 = OpenSCManagerW(0, 0, 1u);
  v1 = v0;
  if ( v0 )
  {
    v4 = OpenServiceW(v0, L"VsStandardCollectorService170", 0x14u);
    v5 = v4;
    if ( v4 && QueryServiceStatus(v4, &ServiceStatus) )
    {
      if ( ServiceStatus.dwCurrentState == 1 )
      {
        if ( !StartServiceW(v5, 0, 0) )
          goto LABEL_9;
        wprintf(L"SUCCESS: The service was started successfully\n");
      }
      else
      {
        wprintf(L"WARNING: The service is already started\n");
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
0x140003760  mov     [rsp+arg_0], rbx
0x140003765  mov     [rsp+arg_8], rsi
0x14000376a  push    rdi
0x14000376b  sub     rsp, 50h
0x14000376f  mov     rax, cs:__security_cookie
0x140003776  xor     rax, rsp
0x140003779  mov     [rsp+58h+var_10], rax
0x14000377e  xor     edx, edx; lpDatabaseName
0x140003780  xor     ecx, ecx; lpMachineName
0x140003782  lea     r8d, [rdx+1]; dwDesiredAccess
0x140003786  call    cs:__imp_OpenSCManagerW
0x14000378c  mov     rdi, rax
0x14000378f  test    rax, rax
0x140003792  jnz     short loc_1400037AD
0x140003794  call    cs:__imp_GetLastError
0x14000379a  movzx   esi, ax
0x14000379d  or      esi, 80070000h
0x1400037a3  test    eax, eax
0x1400037a5  cmovle  esi, eax
0x1400037a8  jmp     loc_14000383A
0x1400037ad  mov     r8d, 14h; dwDesiredAccess
0x1400037b3  lea     rdx, ?WZ_SERVICENAME@@3QBGB; "VsStandardCollectorService170"
0x1400037ba  mov     rcx, rdi; hSCManager
0x1400037bd  call    cs:__imp_OpenServiceW
0x1400037c3  mov     rbx, rax
0x1400037c6  test    rax, rax
0x1400037c9  jz      short loc_1400037F6
0x1400037cb  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x1400037d0  mov     rcx, rax; hService
0x1400037d3  call    cs:__imp_QueryServiceStatus
0x1400037d9  test    eax, eax
0x1400037db  jz      short loc_1400037F6
0x1400037dd  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 1
0x1400037e2  jnz     short loc_14000381A
0x1400037e4  xor     r8d, r8d; lpServiceArgVectors
0x1400037e7  xor     edx, edx; dwNumServiceArgs
0x1400037e9  mov     rcx, rbx; hService
0x1400037ec  call    cs:__imp_StartServiceW
0x1400037f2  test    eax, eax
0x1400037f4  jnz     short loc_140003811
0x1400037f6  call    cs:__imp_GetLastError
0x1400037fc  movzx   esi, ax
0x1400037ff  or      esi, 80070000h
0x140003805  test    eax, eax
0x140003807  cmovle  esi, eax
0x14000380a  test    rbx, rbx
0x14000380d  jz      short loc_140003831
0x14000380f  jmp     short loc_140003828
0x140003811  lea     rcx, aSuccessTheServ_0; "SUCCESS: The service was started succes"...
0x140003818  jmp     short loc_140003821
0x14000381a  lea     rcx, aWarningTheServ; "WARNING: The service is already started"...
0x140003821  call    wprintf
0x140003826  xor     esi, esi
0x140003828  mov     rcx, rbx; hSCObject
0x14000382b  call    cs:__imp_CloseServiceHandle
0x140003831  mov     rcx, rdi; hSCObject
0x140003834  call    cs:__imp_CloseServiceHandle
0x14000383a  mov     eax, esi
0x14000383c  mov     rcx, [rsp+58h+var_10]
0x140003841  xor     rcx, rsp; StackCookie
0x140003844  call    __security_check_cookie
0x140003849  mov     rbx, [rsp+58h+arg_0]
0x14000384e  mov     rsi, [rsp+58h+arg_8]
0x140003853  add     rsp, 50h
0x140003857  pop     rdi
0x140003858  retn
```
