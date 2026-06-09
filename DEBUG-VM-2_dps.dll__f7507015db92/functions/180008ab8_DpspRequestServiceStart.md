# DpspRequestServiceStart

- ea: `0x180008ab8`
- end: `0x180008db8`
- name: `DpspRequestServiceStart`
- size: `768`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000b484`

## callees

- `0x180008ab8`
- `0x180009090`
- `0x180009fb0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180008c81`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180008c81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008be3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008be3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d97`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008c65`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008c65`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x180008d3f`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x180008d3f`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180008cfc`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180008cfc`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180008b10`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180008b10`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180008d5a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180008d68`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180008d5a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180008d68`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180008b7a`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180008b7a`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180008bd9`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180008c8e`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180008bd9`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180008c8e`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180008c1a`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180008c1a`

## string_xrefs

- `0x180008b5d`: `clientcore\base\diagnosis\pdi\wdi\framework\dps\dpstask.cpp`
- `0x180008bc1`: `clientcore\base\diagnosis\pdi\wdi\framework\dps\dpstask.cpp`
- `0x180008b56`: `DpspRequestServiceStart`
- `0x180008bba`: `DpspRequestServiceStart`

## pseudocode

```c
__int64 __fastcall DpspRequestServiceStart(__int64 a1, const WCHAR *a2)
{
  SC_HANDLE v4; // r15
  signed int LastError; // eax
  signed int v6; // ebx
  SC_HANDLE v7; // rdi
  signed int v8; // eax
  int v9; // r8d
  signed int v10; // eax
  DWORD dwCurrentState; // eax
  signed int v12; // eax
  unsigned int v13; // esi
  unsigned int v14; // r14d
  DWORD v15; // eax
  signed int v16; // eax
  signed int v17; // eax
  signed int v19; // eax
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-39h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+38h] [rbp-31h] BYREF
  BYTE Buffer[16]; // [rsp+58h] [rbp-11h] BYREF
  __int128 v23; // [rsp+68h] [rbp-1h]
  int v24; // [rsp+78h] [rbp+Fh]

  v24 = 0;
  pcbBytesNeeded = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  *(_OWORD *)Buffer = 0;
  v23 = 0;
  v4 = OpenSCManagerW(0, 0, 1u);
  if ( (((unsigned __int64)v4 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 < 0 )
    {
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpstask.cpp",
        (int)L"DpspRequestServiceStart",
        466,
        (int)L"Error = %d",
        v6);
      goto LABEL_50;
    }
  }
  v7 = OpenServiceW(v4, a2, 0x94u);
  if ( (((unsigned __int64)v7 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    goto LABEL_16;
  v8 = GetLastError();
  v6 = v8;
  if ( v8 > 0 )
    v6 = (unsigned __int16)v8 | 0x80070000;
  if ( v6 >= 0 )
  {
LABEL_16:
    if ( QueryServiceStatus(v7, &ServiceStatus) )
      goto LABEL_18;
    v10 = GetLastError();
    v6 = v10;
    if ( v10 > 0 )
      v6 = (unsigned __int16)v10 | 0x80070000;
    if ( v6 >= 0 )
    {
LABEL_18:
      dwCurrentState = ServiceStatus.dwCurrentState;
      if ( ServiceStatus.dwCurrentState != 1 )
      {
        if ( ServiceStatus.dwCurrentState != 3 )
        {
          if ( !ControlService(v7, 1u, &ServiceStatus) )
          {
            v12 = GetLastError();
            v6 = v12;
            if ( v12 > 0 )
              v6 = (unsigned __int16)v12 | 0x80070000;
            if ( v6 < 0 )
            {
              v9 = 491;
              goto LABEL_11;
            }
          }
          dwCurrentState = ServiceStatus.dwCurrentState;
        }
        v13 = 10000;
        v14 = 1000;
        if ( dwCurrentState != 1 )
        {
          while ( WaitForSingleObject(g_hWorkerShutdown, 0) )
          {
            if ( !v13 )
            {
              v6 = -2147023843;
              WdipTraceError(
                (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpstask.cpp",
                (int)L"DpspRequestServiceStart",
                510,
                (int)L"Error = %d",
                29);
              goto LABEL_48;
            }
            v15 = v13;
            if ( v14 <= v13 )
              v15 = v14;
            v14 = v15;
            Sleep(v15);
            if ( !QueryServiceStatus(v7, &ServiceStatus) )
            {
              v16 = GetLastError();
              v6 = v16;
              if ( v16 > 0 )
                v6 = (unsigned __int16)v16 | 0x80070000;
              if ( v6 < 0 )
              {
                v9 = 526;
                goto LABEL_11;
              }
            }
            if ( ServiceStatus.dwCurrentState == 1 )
              goto LABEL_40;
            v13 -= v14;
          }
          v6 = -2147023673;
          WdipTraceError(
            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpstask.cpp",
            (int)L"DpspRequestServiceStart",
            505,
            (int)L"Error = %d",
            199);
          goto LABEL_48;
        }
      }
LABEL_40:
      if ( StartServiceW(v7, 0, 0) )
        goto LABEL_59;
      v17 = GetLastError();
      v6 = v17;
      if ( v17 > 0 )
        v6 = (unsigned __int16)v17 | 0x80070000;
      if ( v6 >= 0 )
      {
LABEL_59:
        if ( QueryServiceStatusEx(v7, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
        {
          v6 = 0;
        }
        else
        {
          v19 = GetLastError();
          v6 = v19;
          if ( v19 > 0 )
            v6 = (unsigned __int16)v19 | 0x80070000;
          if ( v6 < 0 )
          {
            v9 = 539;
            goto LABEL_11;
          }
        }
        *(_DWORD *)(a1 + 4) = HIDWORD(v23);
        goto LABEL_48;
      }
      v9 = 531;
    }
    else
    {
      v9 = 479;
    }
  }
  else
  {
    v9 = 472;
  }
LABEL_11:
  WdipTraceError(
    (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpstask.cpp",
    (int)L"DpspRequestServiceStart",
    v9,
    (int)L"Error = %d",
    v6);
LABEL_48:
  if ( v7 )
    CloseServiceHandle(v7);
LABEL_50:
  if ( v4 )
    CloseServiceHandle(v4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180008ab8  mov     [rsp-8+arg_10], rbx
0x180008abd  push    rbp
0x180008abe  push    rsi
0x180008abf  push    rdi
0x180008ac0  push    r12
0x180008ac2  push    r13
0x180008ac4  push    r14
0x180008ac6  push    r15
0x180008ac8  lea     rbp, [rsp-27h]
0x180008acd  sub     rsp, 90h
0x180008ad4  mov     rax, cs:__security_cookie
0x180008adb  xor     rax, rsp
0x180008ade  mov     [rbp+57h+var_40], rax
0x180008ae2  xor     eax, eax
0x180008ae4  xorps   xmm0, xmm0
0x180008ae7  xorps   xmm1, xmm1
0x180008aea  mov     [rbp+57h+var_48], eax
0x180008aed  mov     rdi, rdx
0x180008af0  mov     [rbp+57h+var_90], eax
0x180008af3  mov     r13, rcx
0x180008af6  xor     edx, edx; lpDatabaseName
0x180008af8  lea     esi, [rax+1]
0x180008afb  xor     ecx, ecx; lpMachineName
0x180008afd  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x180008b01  mov     r8d, esi; dwDesiredAccess
0x180008b04  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x180008b08  movups  xmmword ptr [rbp+57h+Buffer], xmm1
0x180008b0c  movups  [rbp+57h+var_58], xmm1
0x180008b10  call    cs:__imp_OpenSCManagerW
0x180008b16  mov     r15, rax
0x180008b19  mov     r12d, 80070000h
0x180008b1f  lea     rcx, [rax+1]
0x180008b23  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180008b2a  jnz     short loc_180008B6E
0x180008b2c  call    cs:__imp_GetLastError
0x180008b32  mov     ebx, eax
0x180008b34  test    eax, eax
0x180008b36  jle     short loc_180008B3E
0x180008b38  movzx   ebx, ax
0x180008b3b  or      ebx, r12d
0x180008b3e  test    ebx, ebx
0x180008b40  jns     short loc_180008B6E
0x180008b42  movzx   eax, bx
0x180008b45  lea     r9, aErrorD; "Error = %d"
0x180008b4c  mov     r8d, 1D2h; int
0x180008b52  mov     dword ptr [rsp+0C0h+pcbBytesNeeded], eax; Args
0x180008b56  lea     rdx, aDpsprequestser; "DpspRequestServiceStart"
0x180008b5d  lea     rcx, aClientcoreBase_4; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180008b64  call    WdipTraceError
0x180008b69  jmp     loc_180008D60
0x180008b6e  mov     r8d, 94h; dwDesiredAccess
0x180008b74  mov     rdx, rdi; lpServiceName
0x180008b77  mov     rcx, r15; hSCManager
0x180008b7a  call    cs:__imp_OpenServiceW
0x180008b80  mov     rdi, rax
0x180008b83  lea     rcx, [rax+1]
0x180008b87  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180008b8e  jnz     short loc_180008BD2
0x180008b90  call    cs:__imp_GetLastError
0x180008b96  mov     ebx, eax
0x180008b98  test    eax, eax
0x180008b9a  jle     short loc_180008BA2
0x180008b9c  movzx   ebx, ax
0x180008b9f  or      ebx, r12d
0x180008ba2  test    ebx, ebx
0x180008ba4  jns     short loc_180008BD2
0x180008ba6  mov     r8d, 1D8h; int
0x180008bac  movzx   eax, bx
0x180008baf  mov     dword ptr [rsp+0C0h+pcbBytesNeeded], eax; Args
0x180008bb3  lea     r9, aErrorD; "Error = %d"
0x180008bba  lea     rdx, aDpsprequestser; "DpspRequestServiceStart"
0x180008bc1  lea     rcx, aClientcoreBase_4; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180008bc8  call    WdipTraceError
0x180008bcd  jmp     loc_180008D52
0x180008bd2  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x180008bd6  mov     rcx, rdi; hService
0x180008bd9  call    cs:__imp_QueryServiceStatus
0x180008bdf  test    eax, eax
0x180008be1  jnz     short loc_180008C01
0x180008be3  call    cs:__imp_GetLastError
0x180008be9  mov     ebx, eax
0x180008beb  test    eax, eax
0x180008bed  jle     short loc_180008BF5
0x180008bef  movzx   ebx, ax
0x180008bf2  or      ebx, r12d
0x180008bf5  test    ebx, ebx
0x180008bf7  jns     short loc_180008C01
0x180008bf9  mov     r8d, 1DFh
0x180008bff  jmp     short loc_180008BAC
0x180008c01  mov     eax, [rbp+57h+ServiceStatus.dwCurrentState]
0x180008c04  cmp     eax, esi
0x180008c06  jz      loc_180008CF4
0x180008c0c  cmp     eax, 3
0x180008c0f  jz      short loc_180008C48
0x180008c11  lea     r8, [rbp+57h+ServiceStatus]; lpServiceStatus
0x180008c15  mov     edx, esi; dwControl
0x180008c17  mov     rcx, rdi; hService
0x180008c1a  call    cs:__imp_ControlService
0x180008c20  test    eax, eax
0x180008c22  jnz     short loc_180008C45
0x180008c24  call    cs:__imp_GetLastError
0x180008c2a  mov     ebx, eax
0x180008c2c  test    eax, eax
0x180008c2e  jle     short loc_180008C36
0x180008c30  movzx   ebx, ax
0x180008c33  or      ebx, r12d
0x180008c36  test    ebx, ebx
0x180008c38  jns     short loc_180008C45
0x180008c3a  mov     r8d, 1EBh
0x180008c40  jmp     loc_180008BAC
0x180008c45  mov     eax, [rbp+57h+ServiceStatus.dwCurrentState]
0x180008c48  mov     esi, 2710h
0x180008c4d  mov     r14d, 3E8h
0x180008c53  cmp     eax, 1
0x180008c56  jz      loc_180008CF4
0x180008c5c  mov     rcx, cs:g_hWorkerShutdown; hHandle
0x180008c63  xor     edx, edx; dwMilliseconds
0x180008c65  call    cs:__imp_WaitForSingleObject
0x180008c6b  test    eax, eax
0x180008c6d  jz      short loc_180008CDC
0x180008c6f  test    esi, esi
0x180008c71  jz      short loc_180008CC4
0x180008c73  cmp     r14d, esi
0x180008c76  mov     eax, esi
0x180008c78  cmovbe  eax, r14d
0x180008c7c  mov     ecx, eax; dwMilliseconds
0x180008c7e  mov     r14d, eax
0x180008c81  call    cs:__imp_Sleep
0x180008c87  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x180008c8b  mov     rcx, rdi; hService
0x180008c8e  call    cs:__imp_QueryServiceStatus
0x180008c94  test    eax, eax
0x180008c96  jnz     short loc_180008CAE
0x180008c98  call    cs:__imp_GetLastError
0x180008c9e  mov     ebx, eax
0x180008ca0  test    eax, eax
0x180008ca2  jle     short loc_180008CAA
0x180008ca4  movzx   ebx, ax
0x180008ca7  or      ebx, r12d
0x180008caa  test    ebx, ebx
0x180008cac  js      short loc_180008CB9
0x180008cae  cmp     [rbp+57h+ServiceStatus.dwCurrentState], 1
0x180008cb2  jz      short loc_180008CF4
0x180008cb4  sub     esi, r14d
0x180008cb7  jmp     short loc_180008C5C
0x180008cb9  mov     r8d, 20Eh
0x180008cbf  jmp     loc_180008BAC
0x180008cc4  mov     ebx, 8007041Dh
0x180008cc9  mov     dword ptr [rsp+0C0h+pcbBytesNeeded], 41Dh
0x180008cd1  mov     r8d, 1FEh
0x180008cd7  jmp     loc_180008BB3
0x180008cdc  mov     ebx, 800704C7h
0x180008ce1  mov     dword ptr [rsp+0C0h+pcbBytesNeeded], 4C7h
0x180008ce9  mov     r8d, 1F9h
0x180008cef  jmp     loc_180008BB3
0x180008cf4  xor     r8d, r8d; lpServiceArgVectors
0x180008cf7  xor     edx, edx; dwNumServiceArgs
0x180008cf9  mov     rcx, rdi; hService
0x180008cfc  call    cs:__imp_StartServiceW
0x180008d02  test    eax, eax
0x180008d04  jnz     short loc_180008D27
0x180008d06  call    cs:__imp_GetLastError
0x180008d0c  mov     ebx, eax
0x180008d0e  test    eax, eax
0x180008d10  jle     short loc_180008D18
0x180008d12  movzx   ebx, ax
0x180008d15  or      ebx, r12d
0x180008d18  test    ebx, ebx
0x180008d1a  jns     short loc_180008D27
0x180008d1c  mov     r8d, 213h
0x180008d22  jmp     loc_180008BAC
0x180008d27  lea     rax, [rbp+57h+var_90]
0x180008d2b  mov     r9d, 24h ; '$'; cbBufSize
0x180008d31  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x180008d35  mov     [rsp+0C0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180008d3a  xor     edx, edx; InfoLevel
0x180008d3c  mov     rcx, rdi; hService
0x180008d3f  call    cs:__imp_QueryServiceStatusEx
0x180008d45  test    eax, eax
0x180008d47  jz      short loc_180008D97
0x180008d49  xor     ebx, ebx
0x180008d4b  mov     eax, dword ptr [rbp+57h+var_58+0Ch]
0x180008d4e  mov     [r13+4], eax
0x180008d52  test    rdi, rdi
0x180008d55  jz      short loc_180008D60
0x180008d57  mov     rcx, rdi; hSCObject
0x180008d5a  call    cs:__imp_CloseServiceHandle
0x180008d60  test    r15, r15
0x180008d63  jz      short loc_180008D6E
0x180008d65  mov     rcx, r15; hSCObject
0x180008d68  call    cs:__imp_CloseServiceHandle
0x180008d6e  mov     eax, ebx
0x180008d70  mov     rcx, [rbp+57h+var_40]
0x180008d74  xor     rcx, rsp; StackCookie
0x180008d77  call    __security_check_cookie
0x180008d7c  mov     rbx, [rsp+0C0h+arg_10]
0x180008d84  add     rsp, 90h
0x180008d8b  pop     r15
0x180008d8d  pop     r14
0x180008d8f  pop     r13
0x180008d91  pop     r12
0x180008d93  pop     rdi
0x180008d94  pop     rsi
0x180008d95  pop     rbp
0x180008d96  retn
0x180008d97  call    cs:__imp_GetLastError
0x180008d9d  mov     ebx, eax
0x180008d9f  test    eax, eax
0x180008da1  jle     short loc_180008DA9
0x180008da3  movzx   ebx, ax
0x180008da6  or      ebx, r12d
0x180008da9  test    ebx, ebx
0x180008dab  jns     short loc_180008D4B
0x180008dad  mov     r8d, 21Bh
0x180008db3  jmp     loc_180008BAC
```
