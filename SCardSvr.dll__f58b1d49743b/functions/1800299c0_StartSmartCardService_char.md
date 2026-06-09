# StartSmartCardService(char *)

- ea: `0x1800299c0`
- end: `0x180029b72`
- name: `?StartSmartCardService@@YAKPEAD@Z`
- size: `434`
- prototype: `__int64 __fastcall(LPCSTR lpServiceName)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180025a20`

## callees

- `0x1800299c0`
- `0x18003261b`
- `0x1800326d0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180029aad`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180029aad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029a14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029a4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029a7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029a81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029aec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029afb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029b23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029b3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029a14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029a4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029a7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029a81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029aec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029afb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029b23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029b3f`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180029abb`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180029abb`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x180029a3b`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x180029a3b`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180029a01`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180029a01`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180029b19`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180029b35`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180029b19`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180029b35`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180029a71`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180029a71`

## pseudocode

```c
__int64 __fastcall StartSmartCardService(LPCSTR lpServiceName)
{
  unsigned int v2; // ebx
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // r14
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rdi
  DWORD v7; // eax
  int v8; // esi
  DWORD dwCurrentState; // eax
  ulong pExceptionObject; // [rsp+28h] [rbp-80h] BYREF
  ulong LastError; // [rsp+2Ch] [rbp-7Ch] BYREF
  ulong v13; // [rsp+30h] [rbp-78h] BYREF
  ulong v14; // [rsp+34h] [rbp-74h] BYREF
  ulong v15; // [rsp+38h] [rbp-70h] BYREF
  SC_HANDLE v16; // [rsp+40h] [rbp-68h]
  ulong v17; // [rsp+48h] [rbp-60h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+50h] [rbp-58h] BYREF

  v2 = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v3 = OpenSCManagerW(0, 0, 0x80000000);
  try
  {
    v4 = v3;
    v16 = v3;
    if ( !v3 )
    {
      pExceptionObject = GetLastError();
      throw &pExceptionObject;
    }
    v5 = OpenServiceA(v3, lpServiceName, 0x14u);
    v6 = v5;
    if ( !v5 )
    {
      LastError = GetLastError();
      throw &LastError;
    }
    if ( !StartServiceW(v5, 0, 0) )
    {
      GetLastError();
      v7 = GetLastError();
      if ( v7 != 1056 )
      {
        v13 = v7;
        throw &v13;
      }
    }
    v8 = 60;
    while ( 1 )
    {
      Sleep(0x3E8u);
      if ( !QueryServiceStatus(v6, &ServiceStatus) )
        break;
      dwCurrentState = ServiceStatus.dwCurrentState;
      if ( ServiceStatus.dwCurrentState != 2 )
        goto LABEL_15;
      if ( !--v8 )
      {
        v14 = -2146435043;
        throw &v14;
      }
    }
    GetLastError();
    dwCurrentState = ServiceStatus.dwCurrentState;
LABEL_15:
    if ( dwCurrentState != 4 )
    {
      v15 = GetLastError();
      throw &v15;
    }
    if ( !CloseServiceHandle(v6) )
      GetLastError();
    if ( !CloseServiceHandle(v4) )
      GetLastError();
    v16 = 0;
  }
  catch ( ulong v17 )
  {
    return v17;
  }
  catch ( ... )
  {
    return 87;
  }
  return v2;
}

```

## disassembly

```asm
0x1800299c0  push    rbx
0x1800299c2  push    rsi
0x1800299c3  push    rdi
0x1800299c4  push    r14
0x1800299c6  sub     rsp, 88h
0x1800299cd  mov     rax, cs:__security_cookie
0x1800299d4  xor     rax, rsp
0x1800299d7  mov     [rsp+0A8h+var_38], rax
0x1800299dc  mov     rdi, rcx
0x1800299df  mov     [rsp+0A8h+var_88], 0
0x1800299e8  xor     ebx, ebx
0x1800299ea  xorps   xmm0, xmm0
0x1800299ed  movups  xmmword ptr [rsp+0A8h+ServiceStatus.dwServiceType], xmm0
0x1800299f2  movups  xmmword ptr [rsp+0A8h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800299f7  xor     edx, edx; lpDatabaseName
0x1800299f9  xor     ecx, ecx; lpMachineName
0x1800299fb  mov     r8d, 80000000h; dwDesiredAccess
0x180029a01  call    cs:__imp_OpenSCManagerW
0x180029a07  mov     r14, rax
0x180029a0a  mov     [rsp+0A8h+var_68], rax
0x180029a0f  test    rax, rax
0x180029a12  jnz     short loc_180029A2F
0x180029a14  call    cs:__imp_GetLastError
0x180029a1a  mov     [rsp+0A8h+pExceptionObject], eax
0x180029a1e  lea     rdx, _TI1K; pThrowInfo
0x180029a25  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x180029a2a  call    _CxxThrowException_0
0x180029a2f  mov     r8d, 14h; dwDesiredAccess
0x180029a35  mov     rdx, rdi; lpServiceName
0x180029a38  mov     rcx, r14; hSCManager
0x180029a3b  call    cs:__imp_OpenServiceA
0x180029a41  mov     rdi, rax
0x180029a44  mov     [rsp+0A8h+var_88], rax
0x180029a49  test    rax, rax
0x180029a4c  jnz     short loc_180029A69
0x180029a4e  call    cs:__imp_GetLastError
0x180029a54  mov     [rsp+0A8h+var_7C], eax
0x180029a58  lea     rdx, _TI1K; pThrowInfo
0x180029a5f  lea     rcx, [rsp+0A8h+var_7C]; pExceptionObject
0x180029a64  call    _CxxThrowException_0
0x180029a69  xor     r8d, r8d; lpServiceArgVectors
0x180029a6c  xor     edx, edx; dwNumServiceArgs
0x180029a6e  mov     rcx, rdi; hService
0x180029a71  call    cs:__imp_StartServiceW
0x180029a77  test    eax, eax
0x180029a79  jnz     short loc_180029AA3
0x180029a7b  call    cs:__imp_GetLastError
0x180029a81  call    cs:__imp_GetLastError
0x180029a87  cmp     eax, 420h
0x180029a8c  jz      short loc_180029AA3
0x180029a8e  mov     [rsp+0A8h+var_78], eax
0x180029a92  lea     rdx, _TI1K; pThrowInfo
0x180029a99  lea     rcx, [rsp+0A8h+var_78]; pExceptionObject
0x180029a9e  call    _CxxThrowException_0
0x180029aa3  mov     esi, 3Ch ; '<'
0x180029aa8  mov     ecx, 3E8h; dwMilliseconds
0x180029aad  call    cs:__imp_Sleep
0x180029ab3  lea     rdx, [rsp+0A8h+ServiceStatus]; lpServiceStatus
0x180029ab8  mov     rcx, rdi; hService
0x180029abb  call    cs:__imp_QueryServiceStatus
0x180029ac1  test    eax, eax
0x180029ac3  jz      short loc_180029AEC
0x180029ac5  mov     eax, [rsp+0A8h+ServiceStatus.dwCurrentState]
0x180029ac9  cmp     eax, 2
0x180029acc  jnz     short loc_180029AF6
0x180029ace  add     esi, 0FFFFFFFFh
0x180029ad1  jnz     short loc_180029AA8
0x180029ad3  mov     [rsp+0A8h+var_74], 8010001Dh
0x180029adb  lea     rdx, _TI1K; pThrowInfo
0x180029ae2  lea     rcx, [rsp+0A8h+var_74]; pExceptionObject
0x180029ae7  call    _CxxThrowException_0
0x180029aec  call    cs:__imp_GetLastError
0x180029af2  mov     eax, [rsp+0A8h+ServiceStatus.dwCurrentState]
0x180029af6  cmp     eax, 4
0x180029af9  jz      short loc_180029B16
0x180029afb  call    cs:__imp_GetLastError
0x180029b01  mov     [rsp+0A8h+var_70], eax
0x180029b05  lea     rdx, _TI1K; pThrowInfo
0x180029b0c  lea     rcx, [rsp+0A8h+var_70]; pExceptionObject
0x180029b11  call    _CxxThrowException_0
0x180029b16  mov     rcx, rdi; hSCObject
0x180029b19  call    cs:__imp_CloseServiceHandle
0x180029b1f  test    eax, eax
0x180029b21  jnz     short loc_180029B29
0x180029b23  call    cs:__imp_GetLastError
0x180029b29  mov     [rsp+0A8h+var_88], 0
0x180029b32  mov     rcx, r14; hSCObject
0x180029b35  call    cs:__imp_CloseServiceHandle
0x180029b3b  test    eax, eax
0x180029b3d  jnz     short loc_180029B45
0x180029b3f  call    cs:__imp_GetLastError
0x180029b45  mov     [rsp+0A8h+var_68], 0
0x180029b4e  jmp     short loc_180029B56
0x180029b50  jmp     short $+2
0x180029b52  mov     ebx, dword ptr [rsp+0A8h+var_88]
0x180029b56  mov     eax, ebx
0x180029b58  mov     rcx, [rsp+0A8h+var_38]
0x180029b5d  xor     rcx, rsp; StackCookie
0x180029b60  call    __security_check_cookie
0x180029b65  add     rsp, 88h
0x180029b6c  pop     r14
0x180029b6e  pop     rdi
0x180029b6f  pop     rsi
0x180029b70  pop     rbx
0x180029b71  retn
```
