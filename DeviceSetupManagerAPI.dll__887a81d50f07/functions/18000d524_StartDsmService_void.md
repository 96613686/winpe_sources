# StartDsmService(void)

- ea: `0x18000d524`
- end: `0x18000d760`
- name: `?StartDsmService@@YAJXZ`
- size: `572`
- prototype: `__int64(void)`
- caller_count: `11`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180009810`
- `0x180009ba0`
- `0x18000b000`
- `0x18000b0b0`
- `0x18000b160`
- `0x18000b330`
- `0x18000b410`
- `0x18000b4c0`
- `0x18000b5b0`
- `0x18000ca1c`
- `0x18000d0d8`

## callees

- `0x1800017c0`
- `0x1800092c0`
- `0x180009d20`
- `0x18000d524`
- `0x18000d768`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d5a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d5d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d676`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d6c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d5a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d5d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d676`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d6c8`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000d58c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000d58c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000d5ca`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000d5ca`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18000d650`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18000d650`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000d703`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000d70c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000d703`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000d70c`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18000d62c`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18000d62c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000d65f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000d65f`

## pseudocode

```c
__int64 StartDsmService(void)
{
  int v0; // eax
  signed int v1; // ebx
  SC_HANDLE v2; // rsi
  signed int LastError; // eax
  SC_HANDLE v4; // rdi
  signed int v5; // eax
  int v6; // ebx
  signed int v7; // eax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  signed int v10; // eax
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-68h] BYREF

  v0 = WaitDsmReady();
  v1 = v0;
  if ( v0 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_b8e3509543d83c1db711f9919e1dba96_Traceguids,
        (unsigned int)v0);
    v2 = OpenSCManagerW(0, 0, 1u);
    if ( v2 )
      goto LABEL_9;
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    if ( v1 >= 0 )
    {
LABEL_9:
      v4 = OpenServiceW(v2, L"DsmSvc", 0x14u);
      if ( v4 )
        goto LABEL_14;
      v5 = GetLastError();
      v1 = v5;
      if ( v5 > 0 )
        v1 = (unsigned __int16)v5 | 0x80070000;
      if ( v1 >= 0 )
      {
LABEL_14:
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_b8e3509543d83c1db711f9919e1dba96_Traceguids);
        v6 = 0;
        while ( 1 )
        {
          memset(&ServiceStatus, 0, sizeof(ServiceStatus));
          if ( !QueryServiceStatus(v4, &ServiceStatus) )
            break;
          if ( ServiceStatus.dwCurrentState == 4 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_b8e3509543d83c1db711f9919e1dba96_Traceguids);
            v1 = 0;
            goto LABEL_38;
          }
          if ( ServiceStatus.dwCurrentState == 1 && !StartServiceW(v4, 0, 0) )
          {
            v7 = GetLastError();
            v1 = v7;
            if ( v7 > 0 )
              v1 = (unsigned __int16)v7 | 0x80070000;
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              v9 = 18;
LABEL_37:
              WPP_SF_D(v8[2], v9, WPP_b8e3509543d83c1db711f9919e1dba96_Traceguids, (unsigned int)v1);
              goto LABEL_38;
            }
            goto LABEL_38;
          }
          Sleep(0x64u);
          if ( (unsigned int)++v6 >= 0x32 )
          {
            v1 = -2147467259;
            goto LABEL_38;
          }
        }
        v10 = GetLastError();
        v1 = v10;
        if ( v10 > 0 )
          v1 = (unsigned __int16)v10 | 0x80070000;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v9 = 16;
          goto LABEL_37;
        }
LABEL_38:
        CloseServiceHandle(v4);
      }
      CloseServiceHandle(v2);
      if ( v1 >= 0 )
        v1 = WaitDsmReady();
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_b8e3509543d83c1db711f9919e1dba96_Traceguids, (unsigned int)v1);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18000d524  push    rbx
0x18000d526  push    rsi
0x18000d527  push    rdi
0x18000d528  push    r12
0x18000d52a  push    r14
0x18000d52c  push    r15
0x18000d52e  sub     rsp, 58h
0x18000d532  mov     rax, cs:__security_cookie
0x18000d539  xor     rax, rsp
0x18000d53c  mov     [rsp+88h+var_48], rax
0x18000d541  call    ?WaitDsmReady@@YAJXZ; WaitDsmReady(void)
0x18000d546  lea     r14, WPP_GLOBAL_Control
0x18000d54d  mov     ebx, eax
0x18000d54f  lea     r12, WPP_b8e3509543d83c1db711f9919e1dba96_Traceguids
0x18000d556  test    eax, eax
0x18000d558  jns     loc_18000D71D
0x18000d55e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d565  cmp     rcx, r14
0x18000d568  jz      short loc_18000D584
0x18000d56a  test    byte ptr [rcx+1Ch], 1
0x18000d56e  jz      short loc_18000D584
0x18000d570  mov     rcx, [rcx+10h]
0x18000d574  mov     edx, 0Eh
0x18000d579  mov     r9d, eax
0x18000d57c  mov     r8, r12
0x18000d57f  call    WPP_SF_D
0x18000d584  xor     edx, edx; lpDatabaseName
0x18000d586  xor     ecx, ecx; lpMachineName
0x18000d588  lea     r8d, [rdx+1]; dwDesiredAccess
0x18000d58c  call    cs:__imp_OpenSCManagerW
0x18000d592  mov     rsi, rax
0x18000d595  mov     r15d, 80070000h
0x18000d59b  test    rax, rax
0x18000d59e  jnz     short loc_18000D5BA
0x18000d5a0  call    cs:__imp_GetLastError
0x18000d5a6  mov     ebx, eax
0x18000d5a8  test    eax, eax
0x18000d5aa  jle     short loc_18000D5B2
0x18000d5ac  movzx   ebx, ax
0x18000d5af  or      ebx, r15d
0x18000d5b2  test    ebx, ebx
0x18000d5b4  js      loc_18000D71D
0x18000d5ba  mov     r8d, 14h; dwDesiredAccess
0x18000d5c0  lea     rdx, ServiceName; "DsmSvc"
0x18000d5c7  mov     rcx, rsi; hSCManager
0x18000d5ca  call    cs:__imp_OpenServiceW
0x18000d5d0  mov     rdi, rax
0x18000d5d3  test    rax, rax
0x18000d5d6  jnz     short loc_18000D5F2
0x18000d5d8  call    cs:__imp_GetLastError
0x18000d5de  mov     ebx, eax
0x18000d5e0  test    eax, eax
0x18000d5e2  jle     short loc_18000D5EA
0x18000d5e4  movzx   ebx, ax
0x18000d5e7  or      ebx, r15d
0x18000d5ea  test    ebx, ebx
0x18000d5ec  js      loc_18000D709
0x18000d5f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d5f9  cmp     rcx, r14
0x18000d5fc  jz      short loc_18000D615
0x18000d5fe  test    byte ptr [rcx+1Ch], 1
0x18000d602  jz      short loc_18000D615
0x18000d604  mov     rcx, [rcx+10h]
0x18000d608  mov     edx, 0Fh
0x18000d60d  mov     r8, r12
0x18000d610  call    WPP_SF_
0x18000d615  xor     ebx, ebx
0x18000d617  xorps   xmm0, xmm0
0x18000d61a  lea     rdx, [rsp+88h+ServiceStatus]; lpServiceStatus
0x18000d61f  movups  xmmword ptr [rsp+88h+ServiceStatus.dwServiceType], xmm0
0x18000d624  mov     rcx, rdi; hService
0x18000d627  movups  xmmword ptr [rsp+88h+ServiceStatus.dwWin32ExitCode], xmm0
0x18000d62c  call    cs:__imp_QueryServiceStatus
0x18000d632  test    eax, eax
0x18000d634  jz      loc_18000D6C8
0x18000d63a  cmp     [rsp+88h+ServiceStatus.dwCurrentState], 4
0x18000d63f  jz      short loc_18000D6A1
0x18000d641  cmp     [rsp+88h+ServiceStatus.dwCurrentState], 1
0x18000d646  jnz     short loc_18000D65A
0x18000d648  xor     r8d, r8d; lpServiceArgVectors
0x18000d64b  xor     edx, edx; dwNumServiceArgs
0x18000d64d  mov     rcx, rdi; hService
0x18000d650  call    cs:__imp_StartServiceW
0x18000d656  test    eax, eax
0x18000d658  jz      short loc_18000D676
0x18000d65a  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18000d65f  call    cs:__imp_Sleep
0x18000d665  inc     ebx
0x18000d667  cmp     ebx, 32h ; '2'
0x18000d66a  jb      short loc_18000D617
0x18000d66c  mov     ebx, 80004005h
0x18000d671  jmp     loc_18000D700
0x18000d676  call    cs:__imp_GetLastError
0x18000d67c  mov     ebx, eax
0x18000d67e  test    eax, eax
0x18000d680  jle     short loc_18000D688
0x18000d682  movzx   ebx, ax
0x18000d685  or      ebx, r15d
0x18000d688  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d68f  cmp     rcx, r14
0x18000d692  jz      short loc_18000D700
0x18000d694  test    byte ptr [rcx+1Ch], 4
0x18000d698  jz      short loc_18000D700
0x18000d69a  mov     edx, 12h
0x18000d69f  jmp     short loc_18000D6F1
0x18000d6a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d6a8  cmp     rcx, r14
0x18000d6ab  jz      short loc_18000D6C4
0x18000d6ad  test    byte ptr [rcx+1Ch], 1
0x18000d6b1  jz      short loc_18000D6C4
0x18000d6b3  mov     rcx, [rcx+10h]
0x18000d6b7  mov     edx, 11h
0x18000d6bc  mov     r8, r12
0x18000d6bf  call    WPP_SF_
0x18000d6c4  xor     ebx, ebx
0x18000d6c6  jmp     short loc_18000D700
0x18000d6c8  call    cs:__imp_GetLastError
0x18000d6ce  mov     ebx, eax
0x18000d6d0  test    eax, eax
0x18000d6d2  jle     short loc_18000D6DA
0x18000d6d4  movzx   ebx, ax
0x18000d6d7  or      ebx, r15d
0x18000d6da  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d6e1  cmp     rcx, r14
0x18000d6e4  jz      short loc_18000D700
0x18000d6e6  test    byte ptr [rcx+1Ch], 4
0x18000d6ea  jz      short loc_18000D700
0x18000d6ec  mov     edx, 10h
0x18000d6f1  mov     rcx, [rcx+10h]
0x18000d6f5  mov     r9d, ebx
0x18000d6f8  mov     r8, r12
0x18000d6fb  call    WPP_SF_D
0x18000d700  mov     rcx, rdi; hSCObject
0x18000d703  call    cs:__imp_CloseServiceHandle
0x18000d709  mov     rcx, rsi; hSCObject
0x18000d70c  call    cs:__imp_CloseServiceHandle
0x18000d712  test    ebx, ebx
0x18000d714  js      short loc_18000D71D
0x18000d716  call    ?WaitDsmReady@@YAJXZ; WaitDsmReady(void)
0x18000d71b  mov     ebx, eax
0x18000d71d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d724  cmp     rcx, r14
0x18000d727  jz      short loc_18000D743
0x18000d729  test    byte ptr [rcx+1Ch], 1
0x18000d72d  jz      short loc_18000D743
0x18000d72f  mov     rcx, [rcx+10h]
0x18000d733  mov     edx, 13h
0x18000d738  mov     r9d, ebx
0x18000d73b  mov     r8, r12
0x18000d73e  call    WPP_SF_D
0x18000d743  mov     eax, ebx
0x18000d745  mov     rcx, [rsp+88h+var_48]
0x18000d74a  xor     rcx, rsp; StackCookie
0x18000d74d  call    __security_check_cookie
0x18000d752  add     rsp, 58h
0x18000d756  pop     r15
0x18000d758  pop     r14
0x18000d75a  pop     r12
0x18000d75c  pop     rdi
0x18000d75d  pop     rsi
0x18000d75e  pop     rbx
0x18000d75f  retn
```
