# WaitForCryptService

- ea: `0x18000e340`
- end: `0x18000e637`
- name: `WaitForCryptService`
- size: `759`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18000e1a4`

## callees

- `0x18000e340`
- `0x180044c8c`
- `0x180053744`
- `0x18013a898`
- `0x18013aa3c`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e547`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e591`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e59e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e5fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e547`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e591`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e59e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e5fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e561`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e5da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e561`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e5da`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000e57a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000e5ea`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000e5f3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000e57a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000e5ea`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000e5f3`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18000e557`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18000e557`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000e37f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000e37f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000e3b6`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000e3d6`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000e516`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000e3b6`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000e3d6`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000e516`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000e416`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000e416`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18000e53a`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18000e53a`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x18000e4d0`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x18000e4d0`

## pseudocode

```c
SC_HANDLE WaitForCryptService()
{
  SC_HANDLE result; // rax
  SC_HANDLE v1; // rbx
  int v2; // esi
  SC_HANDLE v3; // rdi
  DWORD LastError; // r14d
  int CryptSvcForceStartPolicy; // eax
  const WCHAR *v6; // rcx
  DWORD v7; // edx
  unsigned int v8; // esi
  int v9; // eax
  int v10; // ebp
  DWORD v11; // r8d
  SC_HANDLE v12; // rax
  SC_HANDLE v13; // r15
  BOOL started; // eax
  DWORD v15; // ebp
  DWORD v16; // esi
  DWORD pcbBytesNeeded; // [rsp+20h] [rbp-458h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+28h] [rbp-450h] BYREF
  _QUERY_SERVICE_CONFIGW ServiceConfig; // [rsp+50h] [rbp-428h] BYREF

  if ( dword_1801AF304 )
    return (SC_HANDLE)(unsigned int)dword_1801AF308;
  result = OpenSCManagerW(0, 0, 1u);
  v1 = result;
  if ( result )
  {
    v2 = 1;
    v3 = OpenServiceW(result, L"CryptSvc", 5u);
    if ( v3 || (v2 = 0, (v3 = OpenServiceW(v1, L"CryptSvc", 4u)) != 0) )
    {
      LastError = 0;
      if ( !v2 )
        goto LABEL_16;
      pcbBytesNeeded = 1024;
      if ( QueryServiceConfigW(v3, &ServiceConfig, 0x400u, &pcbBytesNeeded) )
      {
        if ( ServiceConfig.dwStartType != 4 )
          goto LABEL_16;
        if ( wcsicmp(L"CryptSvc", L"cryptsvc") || (CryptSvcForceStartPolicy = GetCryptSvcForceStartPolicy()) == 0 )
        {
          if ( wcsicmp(L"CryptSvc", L"ProtectedStorage") )
          {
            SetLastError(0x422u);
            goto LABEL_36;
          }
          v7 = 3;
          v6 = L"ProtectedStorage";
        }
        else
        {
          v6 = L"cryptsvc";
          v7 = (CryptSvcForceStartPolicy != 2) + 2;
        }
        if ( (unsigned int)ForceCryptServiceToStart(v6, v7) )
        {
          LastError = 1;
LABEL_16:
          v8 = 1000 * GetServiceWaitTimeout();
          while ( 1 )
          {
            v9 = WaitServiceState(v3, 73, v8, 0);
            v10 = v9;
            if ( !v9 )
              break;
            if ( v9 == 4 )
            {
              dword_1801AF308 = 1;
              dword_1801AF304 = 1;
              break;
            }
            if ( LastError )
            {
              SetLastError(0x5B4u);
              break;
            }
            v11 = 64;
            *(_OWORD *)&ServiceStatus.dwServiceType = 0;
            if ( v9 != 7 )
              v11 = 16;
            *(_OWORD *)&ServiceStatus.dwWin32ExitCode = 0;
            v12 = OpenServiceW(v1, L"CryptSvc", v11);
            v13 = v12;
            if ( !v12 )
              break;
            if ( v10 == 7 )
              started = ControlService(v12, 3u, &ServiceStatus);
            else
              started = StartServiceW(v12, 0, 0);
            if ( !started )
              LastError = GetLastError();
            v15 = 0;
            if ( LastError != 1056 )
              v15 = LastError;
            CloseServiceHandle(v13);
            if ( v15 )
            {
              SetLastError(v15);
              break;
            }
            LastError = 1;
          }
        }
      }
    }
LABEL_36:
    v16 = GetLastError();
    if ( v3 )
      CloseServiceHandle(v3);
    CloseServiceHandle(v1);
    SetLastError(v16);
    return (SC_HANDLE)(unsigned int)dword_1801AF308;
  }
  return result;
}

```

## disassembly

```asm
0x18000e340  sub     rsp, 478h
0x18000e347  mov     rax, cs:__security_cookie
0x18000e34e  xor     rax, rsp
0x18000e351  mov     [rsp+478h+var_28], rax
0x18000e359  cmp     cs:dword_1801AF304, 0
0x18000e360  jz      short loc_18000E36D
0x18000e362  mov     eax, cs:dword_1801AF308
0x18000e368  jmp     loc_18000E61F
0x18000e36d  xor     edx, edx; lpDatabaseName
0x18000e36f  mov     [rsp+478h+arg_0], rbx
0x18000e377  xor     ecx, ecx; lpMachineName
0x18000e379  mov     r8d, 1; dwDesiredAccess
0x18000e37f  call    cs:__imp_OpenSCManagerW
0x18000e385  mov     rbx, rax
0x18000e388  test    rax, rax
0x18000e38b  jz      loc_18000E617
0x18000e391  mov     [rsp+478h+arg_10], rsi
0x18000e399  lea     rdx, aCryptsvc; "CryptSvc"
0x18000e3a0  mov     r8d, 5; dwDesiredAccess
0x18000e3a6  mov     [rsp+478h+arg_18], rdi
0x18000e3ae  mov     rcx, rbx; hSCManager
0x18000e3b1  mov     esi, 1
0x18000e3b6  call    cs:__imp_OpenServiceW
0x18000e3bc  mov     rdi, rax
0x18000e3bf  test    rax, rax
0x18000e3c2  jnz     short loc_18000E3E8
0x18000e3c4  mov     r8d, 4; dwDesiredAccess
0x18000e3ca  lea     rdx, aCryptsvc; "CryptSvc"
0x18000e3d1  mov     rcx, rbx; hSCManager
0x18000e3d4  xor     esi, esi
0x18000e3d6  call    cs:__imp_OpenServiceW
0x18000e3dc  mov     rdi, rax
0x18000e3df  test    rax, rax
0x18000e3e2  jz      loc_18000E5DA
0x18000e3e8  mov     [rsp+478h+var_10], r14
0x18000e3f0  xor     r14d, r14d
0x18000e3f3  test    esi, esi
0x18000e3f5  jz      loc_18000E499
0x18000e3fb  lea     r9, [rsp+478h+pcbBytesNeeded]; pcbBytesNeeded
0x18000e400  mov     [rsp+478h+pcbBytesNeeded], 400h
0x18000e408  mov     r8d, 400h; cbBufSize
0x18000e40e  lea     rdx, [rsp+478h+ServiceConfig]; lpServiceConfig
0x18000e413  mov     rcx, rdi; hService
0x18000e416  call    cs:__imp_QueryServiceConfigW
0x18000e41c  test    eax, eax
0x18000e41e  jz      loc_18000E5D2
0x18000e424  cmp     [rsp+478h+ServiceConfig.dwStartType], 4
0x18000e429  jnz     short loc_18000E499
0x18000e42b  lea     rdx, aCryptsvc_0; "cryptsvc"
0x18000e432  lea     rcx, aCryptsvc; "CryptSvc"
0x18000e439  call    _wcsicmp
0x18000e43e  test    eax, eax
0x18000e440  jnz     short loc_18000E45F
0x18000e442  call    GetCryptSvcForceStartPolicy
0x18000e447  test    eax, eax
0x18000e449  jz      short loc_18000E45F
0x18000e44b  xor     edx, edx
0x18000e44d  lea     rcx, aCryptsvc_0; "cryptsvc"
0x18000e454  cmp     eax, 2
0x18000e457  setnz   dl
0x18000e45a  add     edx, 2
0x18000e45d  jmp     short loc_18000E486
0x18000e45f  lea     rdx, aProtectedstora; "ProtectedStorage"
0x18000e466  lea     rcx, aCryptsvc; "CryptSvc"
0x18000e46d  call    _wcsicmp
0x18000e472  test    eax, eax
0x18000e474  jnz     loc_18000E542
0x18000e47a  mov     edx, 3; dwStartType
0x18000e47f  lea     rcx, aProtectedstora; "ProtectedStorage"
0x18000e486  call    ForceCryptServiceToStart
0x18000e48b  test    eax, eax
0x18000e48d  jz      loc_18000E5D2
0x18000e493  mov     r14d, 1
0x18000e499  mov     [rsp+478h+arg_8], rbp
0x18000e4a1  mov     [rsp+478h+var_8], r12
0x18000e4a9  call    GetServiceWaitTimeout
0x18000e4ae  imul    esi, eax, 3E8h
0x18000e4b4  mov     r12d, 10h
0x18000e4ba  mov     [rsp+478h+var_18], r15
0x18000e4c2  xor     r9d, r9d
0x18000e4c5  mov     r8d, esi
0x18000e4c8  mov     edx, 49h ; 'I'
0x18000e4cd  mov     rcx, rdi
0x18000e4d0  call    cs:__imp_WaitServiceState
0x18000e4d6  mov     ebp, eax
0x18000e4d8  test    eax, eax
0x18000e4da  jz      loc_18000E5BA
0x18000e4e0  cmp     eax, 4
0x18000e4e3  jz      loc_18000E5A6
0x18000e4e9  test    r14d, r14d
0x18000e4ec  jnz     loc_18000E599
0x18000e4f2  xorps   xmm0, xmm0
0x18000e4f5  lea     rdx, aCryptsvc; "CryptSvc"
0x18000e4fc  cmp     eax, 7
0x18000e4ff  mov     r8d, 40h ; '@'
0x18000e505  movups  xmmword ptr [rsp+478h+ServiceStatus.dwServiceType], xmm0
0x18000e50a  cmovnz  r8d, r12d; dwDesiredAccess
0x18000e50e  mov     rcx, rbx; hSCManager
0x18000e511  movups  xmmword ptr [rsp+478h+ServiceStatus.dwWin32ExitCode], xmm0
0x18000e516  call    cs:__imp_OpenServiceW
0x18000e51c  mov     r15, rax
0x18000e51f  test    rax, rax
0x18000e522  jz      loc_18000E5BA
0x18000e528  mov     rcx, rax; hService
0x18000e52b  cmp     ebp, 7
0x18000e52e  jnz     short loc_18000E552
0x18000e530  lea     r8, [rsp+478h+ServiceStatus]; lpServiceStatus
0x18000e535  mov     edx, 3; dwControl
0x18000e53a  call    cs:__imp_ControlService
0x18000e540  jmp     short loc_18000E55D
0x18000e542  mov     ecx, 422h; dwErrCode
0x18000e547  call    cs:__imp_SetLastError
0x18000e54d  jmp     loc_18000E5D2
0x18000e552  xor     r8d, r8d; lpServiceArgVectors
0x18000e555  xor     edx, edx; dwNumServiceArgs
0x18000e557  call    cs:__imp_StartServiceW
0x18000e55d  test    eax, eax
0x18000e55f  jnz     short loc_18000E56A
0x18000e561  call    cs:__imp_GetLastError
0x18000e567  mov     r14d, eax
0x18000e56a  xor     ebp, ebp
0x18000e56c  mov     rcx, r15; hSCObject
0x18000e56f  cmp     r14d, 420h
0x18000e576  cmovnz  ebp, r14d
0x18000e57a  call    cs:__imp_CloseServiceHandle
0x18000e580  test    ebp, ebp
0x18000e582  jnz     short loc_18000E58F
0x18000e584  mov     r14d, 1
0x18000e58a  jmp     loc_18000E4C2
0x18000e58f  mov     ecx, ebp; dwErrCode
0x18000e591  call    cs:__imp_SetLastError
0x18000e597  jmp     short loc_18000E5BA
0x18000e599  mov     ecx, 5B4h; dwErrCode
0x18000e59e  call    cs:__imp_SetLastError
0x18000e5a4  jmp     short loc_18000E5BA
0x18000e5a6  mov     cs:dword_1801AF308, 1
0x18000e5b0  mov     cs:dword_1801AF304, 1
0x18000e5ba  mov     r15, [rsp+478h+var_18]
0x18000e5c2  mov     r12, [rsp+478h+var_8]
0x18000e5ca  mov     rbp, [rsp+478h+arg_8]
0x18000e5d2  mov     r14, [rsp+478h+var_10]
0x18000e5da  call    cs:__imp_GetLastError
0x18000e5e0  mov     esi, eax
0x18000e5e2  test    rdi, rdi
0x18000e5e5  jz      short loc_18000E5F0
0x18000e5e7  mov     rcx, rdi; hSCObject
0x18000e5ea  call    cs:__imp_CloseServiceHandle
0x18000e5f0  mov     rcx, rbx; hSCObject
0x18000e5f3  call    cs:__imp_CloseServiceHandle
0x18000e5f9  mov     ecx, esi; dwErrCode
0x18000e5fb  call    cs:__imp_SetLastError
0x18000e601  mov     eax, cs:dword_1801AF308
0x18000e607  mov     rdi, [rsp+478h+arg_18]
0x18000e60f  mov     rsi, [rsp+478h+arg_10]
0x18000e617  mov     rbx, [rsp+478h+arg_0]
0x18000e61f  mov     rcx, [rsp+478h+var_28]
0x18000e627  xor     rcx, rsp; StackCookie
0x18000e62a  call    __security_check_cookie
0x18000e62f  add     rsp, 478h
0x18000e636  retn
```
