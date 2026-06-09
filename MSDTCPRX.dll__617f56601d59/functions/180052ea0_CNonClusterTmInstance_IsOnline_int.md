# CNonClusterTmInstance::IsOnline(int *)

- ea: `0x180052ea0`
- end: `0x180052fa5`
- name: `?IsOnline@CNonClusterTmInstance@@UEAAJPEAH@Z`
- size: `261`
- prototype: `__int64 __fastcall(CNonClusterTmInstance *__hidden this, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180052ea0`
- `0x180081dd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052f1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052f50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052f70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052f1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052f50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052f70`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180052f48`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180052f68`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180052f48`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180052f68`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180052ef1`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180052ef1`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180052ecf`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180052ecf`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180052f14`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180052f14`

## pseudocode

```c
__int64 __fastcall CNonClusterTmInstance::IsOnline(LPCWSTR *this, int *a2)
{
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rsi
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rdi
  signed int LastError; // eax
  unsigned int v8; // ebx
  signed int v9; // eax
  signed int v10; // eax
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-48h] BYREF

  *a2 = 0;
  v3 = OpenSCManagerW(this[4], 0, 1u);
  v4 = v3;
  if ( v3 )
  {
    v5 = OpenServiceW(v3, L"MSDTC", 4u);
    v6 = v5;
    if ( v5 )
    {
      memset(&ServiceStatus, 0, sizeof(ServiceStatus));
      if ( QueryServiceStatus(v5, &ServiceStatus) )
      {
        v8 = 0;
        if ( ServiceStatus.dwCurrentState == 4 )
          *a2 = 1;
      }
      else
      {
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
      }
      CloseServiceHandle(v6);
    }
    else
    {
      v9 = GetLastError();
      v8 = v9;
      if ( v9 > 0 )
        v8 = (unsigned __int16)v9 | 0x80070000;
    }
    CloseServiceHandle(v4);
  }
  else
  {
    v10 = GetLastError();
    v8 = v10;
    if ( v10 > 0 )
      return (unsigned __int16)v10 | 0x80070000;
  }
  return v8;
}

```

## disassembly

```asm
0x180052ea0  mov     [rsp+arg_10], rbx
0x180052ea5  push    rsi
0x180052ea6  push    rdi
0x180052ea7  push    r14
0x180052ea9  sub     rsp, 50h
0x180052ead  mov     rax, cs:__security_cookie
0x180052eb4  xor     rax, rsp
0x180052eb7  mov     [rsp+68h+var_28], rax
0x180052ebc  mov     dword ptr [rdx], 0
0x180052ec2  mov     r14, rdx
0x180052ec5  mov     rcx, [rcx+20h]; lpMachineName
0x180052ec9  xor     edx, edx; lpDatabaseName
0x180052ecb  lea     r8d, [rdx+1]; dwDesiredAccess
0x180052ecf  call    cs:__imp_OpenSCManagerW
0x180052ed5  mov     rsi, rax
0x180052ed8  test    rax, rax
0x180052edb  jz      loc_180052F70
0x180052ee1  mov     r8d, 4; dwDesiredAccess
0x180052ee7  lea     rdx, aMsdtc; "MSDTC"
0x180052eee  mov     rcx, rax; hSCManager
0x180052ef1  call    cs:__imp_OpenServiceW
0x180052ef7  mov     rdi, rax
0x180052efa  test    rax, rax
0x180052efd  jz      short loc_180052F50
0x180052eff  xorps   xmm0, xmm0
0x180052f02  lea     rdx, [rsp+68h+ServiceStatus]; lpServiceStatus
0x180052f07  movups  xmmword ptr [rsp+68h+ServiceStatus.dwServiceType], xmm0
0x180052f0c  mov     rcx, rax; hService
0x180052f0f  movups  xmmword ptr [rsp+68h+ServiceStatus.dwWin32ExitCode], xmm0
0x180052f14  call    cs:__imp_QueryServiceStatus
0x180052f1a  test    eax, eax
0x180052f1c  jnz     short loc_180052F35
0x180052f1e  call    cs:__imp_GetLastError
0x180052f24  mov     ebx, eax
0x180052f26  test    eax, eax
0x180052f28  jle     short loc_180052F45
0x180052f2a  movzx   ebx, ax
0x180052f2d  or      ebx, 80070000h
0x180052f33  jmp     short loc_180052F45
0x180052f35  xor     ebx, ebx
0x180052f37  cmp     [rsp+68h+ServiceStatus.dwCurrentState], 4
0x180052f3c  jnz     short loc_180052F45
0x180052f3e  mov     dword ptr [r14], 1
0x180052f45  mov     rcx, rdi; hSCObject
0x180052f48  call    cs:__imp_CloseServiceHandle
0x180052f4e  jmp     short loc_180052F65
0x180052f50  call    cs:__imp_GetLastError
0x180052f56  mov     ebx, eax
0x180052f58  test    eax, eax
0x180052f5a  jle     short loc_180052F65
0x180052f5c  movzx   ebx, ax
0x180052f5f  or      ebx, 80070000h
0x180052f65  mov     rcx, rsi; hSCObject
0x180052f68  call    cs:__imp_CloseServiceHandle
0x180052f6e  jmp     short loc_180052F85
0x180052f70  call    cs:__imp_GetLastError
0x180052f76  mov     ebx, eax
0x180052f78  test    eax, eax
0x180052f7a  jle     short loc_180052F85
0x180052f7c  movzx   ebx, ax
0x180052f7f  or      ebx, 80070000h
0x180052f85  mov     eax, ebx
0x180052f87  mov     rcx, [rsp+68h+var_28]
0x180052f8c  xor     rcx, rsp; StackCookie
0x180052f8f  call    __security_check_cookie
0x180052f94  mov     rbx, [rsp+68h+arg_10]
0x180052f9c  add     rsp, 50h
0x180052fa0  pop     r14
0x180052fa2  pop     rdi
0x180052fa3  pop     rsi
0x180052fa4  retn
```
