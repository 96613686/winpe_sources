# CNonClusterTmInstance::BringOnline(int)

- ea: `0x180005ad0`
- end: `0x180005d19`
- name: `?BringOnline@CNonClusterTmInstance@@UEAAJH@Z`
- size: `585`
- prototype: `__int64 __fastcall(LPCWSTR *this, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180005ad0`
- `0x180081dd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005b3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005cdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005b3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005cdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005b44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005b44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c91`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180005c43`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180005c43`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005ce9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005cf7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005ce9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005cf7`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180005bbd`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180005bbd`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180005afd`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180005afd`
- `api-ms-win-service-winsvc-l1-1-0!StartServiceA` at `0x180005bed`
- `api-ms-win-service-winsvc-l1-1-0!StartServiceA` at `0x180005bed`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180005c24`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180005c24`
- `ADVAPI32!QueryServiceLockStatusA` at `0x180005b60`
- `ADVAPI32!QueryServiceLockStatusA` at `0x180005b60`

## string_xrefs

- `0x180005c4f`: `com\complus\dtc\dtc\adme\nonclustertminstance.cpp`
- `0x180005cb3`: `com\complus\dtc\dtc\adme\nonclustertminstance.cpp`
- `0x180005ca7`: `CNonClusterTmInstance::BringOnline, QueryServiceStatus failed`
- `0x180005c5b`: `CNonClusterTmInstance::BringOnline, status.dwCurrentState != SERVICE_START_PENDING, status.dwCurrentState = %d`

## pseudocode

```c
__int64 __fastcall CNonClusterTmInstance::BringOnline(LPCWSTR *this, int a2)
{
  SC_HANDLE v3; // rsi
  struct _QUERY_SERVICE_LOCK_STATUSA *v4; // rbp
  SC_HANDLE v5; // r14
  signed int LastError; // eax
  DWORD v7; // ebx
  struct _QUERY_SERVICE_LOCK_STATUSA *v8; // rax
  signed int v9; // eax
  SC_HANDLE v10; // rax
  signed int v11; // eax
  signed int v12; // eax
  __int64 v14; // [rsp+28h] [rbp-80h]
  DWORD pcbBytesNeeded; // [rsp+40h] [rbp-68h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+48h] [rbp-60h] BYREF

  v3 = 0;
  v4 = 0;
  v5 = OpenSCManagerW(this[4], 0, 0x11u);
  if ( !v5 )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_33;
  }
  v7 = 0;
  if ( !a2 )
  {
LABEL_18:
    v10 = OpenServiceW(v5, L"MSDTC", 0x14u);
    v3 = v10;
    if ( v10 )
    {
      if ( StartServiceA(v10, 0, 0) || (v11 = GetLastError(), v11 == 1056) )
      {
        while ( 1 )
        {
          memset(&ServiceStatus, 0, sizeof(ServiceStatus));
          if ( !QueryServiceStatus(v3, &ServiceStatus) )
            break;
          if ( ServiceStatus.dwCurrentState == 4 )
            goto LABEL_33;
          if ( ServiceStatus.dwCurrentState != 2 )
          {
            v7 = -2147467259;
            TraceStringInline(
              7,
              1,
              L"com\\complus\\dtc\\dtc\\adme\\nonclustertminstance.cpp",
              660,
              L"CNonClusterTmInstance::BringOnline",
              0,
              L"CNonClusterTmInstance::BringOnline, status.dwCurrentState != SERVICE_START_PENDING, status.dwCurrentState = %d",
              ServiceStatus.dwCurrentState);
            goto LABEL_33;
          }
          Sleep(0xAu);
        }
        v12 = GetLastError();
        v7 = v12;
        if ( v12 > 0 )
          v7 = (unsigned __int16)v12 | 0x80070000;
        LODWORD(v14) = v7;
        TraceStringInline(
          7,
          1,
          L"com\\complus\\dtc\\dtc\\adme\\nonclustertminstance.cpp",
          667,
          L"CNonClusterTmInstance::BringOnline",
          v14,
          L"CNonClusterTmInstance::BringOnline, QueryServiceStatus failed");
        goto LABEL_33;
      }
      if ( v11 <= 0 )
      {
        v7 = v11;
        goto LABEL_33;
      }
    }
    else
    {
      v11 = GetLastError();
      v7 = v11;
      if ( v11 <= 0 )
        goto LABEL_33;
    }
    v7 = (unsigned __int16)v11 | 0x80070000;
    goto LABEL_33;
  }
  for ( pcbBytesNeeded = 0; ; v7 = pcbBytesNeeded )
  {
    CoTaskMemFree(v4);
    v8 = (struct _QUERY_SERVICE_LOCK_STATUSA *)CoTaskMemAlloc(v7);
    v4 = v8;
    if ( !v8 )
    {
      v7 = -2147024882;
      goto LABEL_33;
    }
    if ( QueryServiceLockStatusA(v5, v8, v7, &pcbBytesNeeded) )
    {
      v7 = 0;
      goto LABEL_15;
    }
    v9 = GetLastError();
    v7 = v9;
    if ( v9 > 0 )
      v7 = (unsigned __int16)v9 | 0x80070000;
    if ( v7 != -2147024774 )
      break;
  }
  if ( (v7 & 0x80000000) != 0 )
    goto LABEL_33;
LABEL_15:
  if ( !v4->fIsLocked )
    goto LABEL_18;
  v7 = -2147467259;
LABEL_33:
  CoTaskMemFree(v4);
  if ( v5 )
    CloseServiceHandle(v5);
  if ( v3 )
    CloseServiceHandle(v3);
  return v7;
}

```

## disassembly

```asm
0x180005ad0  push    rbx
0x180005ad2  push    rbp
0x180005ad3  push    rsi
0x180005ad4  push    rdi
0x180005ad5  push    r14
0x180005ad7  push    r15
0x180005ad9  sub     rsp, 78h
0x180005add  mov     rax, cs:__security_cookie
0x180005ae4  xor     rax, rsp
0x180005ae7  mov     [rsp+0A8h+var_40], rax
0x180005aec  mov     rcx, [rcx+20h]; lpMachineName
0x180005af0  mov     r15d, edx
0x180005af3  xor     esi, esi
0x180005af5  xor     edx, edx; lpDatabaseName
0x180005af7  xor     ebp, ebp
0x180005af9  lea     r8d, [rsi+11h]; dwDesiredAccess
0x180005afd  call    cs:__imp_OpenSCManagerW
0x180005b03  mov     r14, rax
0x180005b06  test    rax, rax
0x180005b09  jnz     short loc_180005B29
0x180005b0b  call    cs:__imp_GetLastError
0x180005b11  mov     ebx, eax
0x180005b13  test    eax, eax
0x180005b15  jle     loc_180005CD8
0x180005b1b  movzx   ebx, ax
0x180005b1e  or      ebx, 80070000h
0x180005b24  jmp     loc_180005CD8
0x180005b29  xor     ebx, ebx
0x180005b2b  mov     edi, 80070000h
0x180005b30  test    r15d, r15d
0x180005b33  jz      short loc_180005BAD
0x180005b35  mov     [rsp+0A8h+pcbBytesNeeded], ebx
0x180005b39  mov     rcx, rbp; pv
0x180005b3c  call    cs:__imp_CoTaskMemFree
0x180005b42  mov     ecx, ebx; cb
0x180005b44  call    cs:__imp_CoTaskMemAlloc
0x180005b4a  mov     rbp, rax
0x180005b4d  test    rax, rax
0x180005b50  jz      short loc_180005BA3
0x180005b52  lea     r9, [rsp+0A8h+pcbBytesNeeded]; pcbBytesNeeded
0x180005b57  mov     r8d, ebx; cbBufSize
0x180005b5a  mov     rdx, rax; lpLockStatus
0x180005b5d  mov     rcx, r14; hSCManager
0x180005b60  call    cs:__imp_QueryServiceLockStatusA
0x180005b66  test    eax, eax
0x180005b68  jnz     short loc_180005B92
0x180005b6a  call    cs:__imp_GetLastError
0x180005b70  mov     ebx, eax
0x180005b72  test    eax, eax
0x180005b74  jle     short loc_180005B7B
0x180005b76  movzx   ebx, ax
0x180005b79  or      ebx, edi
0x180005b7b  cmp     ebx, 8007007Ah
0x180005b81  jnz     short loc_180005B89
0x180005b83  mov     ebx, [rsp+0A8h+pcbBytesNeeded]
0x180005b87  jmp     short loc_180005B39
0x180005b89  test    ebx, ebx
0x180005b8b  jns     short loc_180005B94
0x180005b8d  jmp     loc_180005CD8
0x180005b92  xor     ebx, ebx
0x180005b94  cmp     [rbp+0], esi
0x180005b97  jz      short loc_180005BAD
0x180005b99  mov     ebx, 80004005h
0x180005b9e  jmp     loc_180005CD8
0x180005ba3  mov     ebx, 8007000Eh
0x180005ba8  jmp     loc_180005CD8
0x180005bad  mov     r8d, 14h; dwDesiredAccess
0x180005bb3  lea     rdx, aMsdtc; "MSDTC"
0x180005bba  mov     rcx, r14; hSCManager
0x180005bbd  call    cs:__imp_OpenServiceW
0x180005bc3  mov     rsi, rax
0x180005bc6  test    rax, rax
0x180005bc9  jnz     short loc_180005BE5
0x180005bcb  call    cs:__imp_GetLastError
0x180005bd1  mov     ebx, eax
0x180005bd3  test    eax, eax
0x180005bd5  jle     loc_180005CD8
0x180005bdb  movzx   ebx, ax
0x180005bde  or      ebx, edi
0x180005be0  jmp     loc_180005CD8
0x180005be5  xor     r8d, r8d; lpServiceArgVectors
0x180005be8  xor     edx, edx; dwNumServiceArgs
0x180005bea  mov     rcx, rsi; hService
0x180005bed  call    cs:__imp_StartServiceA
0x180005bf3  test    eax, eax
0x180005bf5  jnz     short loc_180005C0F
0x180005bf7  call    cs:__imp_GetLastError
0x180005bfd  cmp     eax, 420h
0x180005c02  jz      short loc_180005C0F
0x180005c04  test    eax, eax
0x180005c06  jg      short loc_180005BDB
0x180005c08  mov     ebx, eax
0x180005c0a  jmp     loc_180005CD8
0x180005c0f  xorps   xmm0, xmm0
0x180005c12  lea     rdx, [rsp+0A8h+ServiceStatus]; lpServiceStatus
0x180005c17  movups  xmmword ptr [rsp+0A8h+ServiceStatus.dwServiceType], xmm0
0x180005c1c  mov     rcx, rsi; hService
0x180005c1f  movups  xmmword ptr [rsp+0A8h+ServiceStatus.dwWin32ExitCode], xmm0
0x180005c24  call    cs:__imp_QueryServiceStatus
0x180005c2a  test    eax, eax
0x180005c2c  jz      short loc_180005C91
0x180005c2e  mov     eax, [rsp+0A8h+ServiceStatus.dwCurrentState]
0x180005c32  cmp     eax, 4
0x180005c35  jz      loc_180005CD8
0x180005c3b  cmp     eax, 2
0x180005c3e  jnz     short loc_180005C4B
0x180005c40  lea     ecx, [rax+8]; dwMilliseconds
0x180005c43  call    cs:__imp_Sleep
0x180005c49  jmp     short loc_180005C0F
0x180005c4b  mov     [rsp+0A8h+var_70], eax
0x180005c4f  lea     r8, aComComplusDtcD_46; "com\\complus\\dtc\\dtc\\adme\\noncluste"...
0x180005c56  mov     edx, 1
0x180005c5b  lea     rax, aCnonclustertmi_8; "CNonClusterTmInstance::BringOnline, sta"...
0x180005c62  mov     [rsp+0A8h+var_78], rax
0x180005c67  mov     r9d, 294h
0x180005c6d  lea     rax, aCnonclustertmi_3; "CNonClusterTmInstance::BringOnline"
0x180005c74  mov     [rsp+0A8h+var_80], 0
0x180005c7d  mov     [rsp+0A8h+var_88], rax
0x180005c82  mov     ebx, 80004005h
0x180005c87  lea     ecx, [rdx+6]
0x180005c8a  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180005c8f  jmp     short loc_180005CD8
0x180005c91  call    cs:__imp_GetLastError
0x180005c97  mov     ebx, eax
0x180005c99  test    eax, eax
0x180005c9b  jle     short loc_180005CA2
0x180005c9d  movzx   ebx, ax
0x180005ca0  or      ebx, edi
0x180005ca2  mov     edx, 1
0x180005ca7  lea     rax, aCnonclustertmi_1; "CNonClusterTmInstance::BringOnline, Que"...
0x180005cae  mov     [rsp+0A8h+var_78], rax
0x180005cb3  lea     r8, aComComplusDtcD_46; "com\\complus\\dtc\\dtc\\adme\\noncluste"...
0x180005cba  lea     rax, aCnonclustertmi_3; "CNonClusterTmInstance::BringOnline"
0x180005cc1  mov     dword ptr [rsp+0A8h+var_80], ebx
0x180005cc5  mov     r9d, 29Bh
0x180005ccb  mov     [rsp+0A8h+var_88], rax
0x180005cd0  lea     ecx, [rdx+6]
0x180005cd3  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180005cd8  mov     rcx, rbp; pv
0x180005cdb  call    cs:__imp_CoTaskMemFree
0x180005ce1  test    r14, r14
0x180005ce4  jz      short loc_180005CEF
0x180005ce6  mov     rcx, r14; hSCObject
0x180005ce9  call    cs:__imp_CloseServiceHandle
0x180005cef  test    rsi, rsi
0x180005cf2  jz      short loc_180005CFD
0x180005cf4  mov     rcx, rsi; hSCObject
0x180005cf7  call    cs:__imp_CloseServiceHandle
0x180005cfd  mov     eax, ebx
0x180005cff  mov     rcx, [rsp+0A8h+var_40]
0x180005d04  xor     rcx, rsp; StackCookie
0x180005d07  call    __security_check_cookie
0x180005d0c  add     rsp, 78h
0x180005d10  pop     r15
0x180005d12  pop     r14
0x180005d14  pop     rdi
0x180005d15  pop     rsi
0x180005d16  pop     rbp
0x180005d17  pop     rbx
0x180005d18  retn
```
