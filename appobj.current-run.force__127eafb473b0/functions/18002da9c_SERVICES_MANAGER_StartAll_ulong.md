# SERVICES_MANAGER::StartAll(ulong *)

- ea: `0x18002da9c`
- end: `0x18002dc5a`
- name: `?StartAll@SERVICES_MANAGER@@QEAAJPEAK@Z`
- size: `446`
- prototype: `__int64 __fastcall(SERVICES_MANAGER *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180025170`

## callees

- `0x18002cd18`
- `0x18002d62c`
- `0x18002d690`
- `0x18002da9c`
- `0x180034d00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002daef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dbed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dc0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002daef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dbed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dc0d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002dbc6`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002dbc6`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002dae1`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002dae1`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002db5d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002db5d`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18002db90`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18002db90`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002dbd4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002dc05`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002dc25`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002dbd4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002dc05`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002dc25`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002db77`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002db9e`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002db77`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002db9e`

## pseudocode

```c
__int64 __fastcall SERVICES_MANAGER::StartAll(SERVICES_MANAGER *this, unsigned int *a2)
{
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // r14
  signed int v6; // eax
  signed int Item; // ebx
  unsigned int v8; // edi
  DWORD v9; // ebp
  SC_HANDLE v10; // rax
  SC_HANDLE v11; // rsi
  signed int LastError; // eax
  signed int v13; // eax
  LPCWSTR lpServiceName; // [rsp+20h] [rbp-68h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+28h] [rbp-60h] BYREF

  lpServiceName = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v4 = OpenSCManagerW(0, 0, 1u);
  v5 = v4;
  if ( v4 )
  {
    Item = SERVICES_MANAGER::ResolveDependencies(this, v4);
    if ( Item >= 0 )
    {
      v8 = *((_DWORD *)this + 2);
      v9 = 1000;
LABEL_6:
      if ( (--v8 & 0x80000000) == 0 )
      {
        Item = LIST_ARRAY::GetItem((SERVICES_MANAGER *)((char *)this + 8), v8, (void **)&lpServiceName);
        if ( Item >= 0 )
        {
          v10 = OpenServiceW(v5, lpServiceName, 0xF01FFu);
          v11 = v10;
          if ( v10 )
          {
            if ( QueryServiceStatus(v10, &ServiceStatus) )
            {
              if ( ServiceStatus.dwCurrentState != 4 )
                StartServiceW(v11, 0, 0);
              while ( QueryServiceStatus(v11, &ServiceStatus) )
              {
                if ( ServiceStatus.dwCurrentState == 1 )
                {
                  Item = -2147023834;
                  goto LABEL_24;
                }
                if ( ServiceStatus.dwCurrentState == 4 )
                {
                  CloseServiceHandle(v11);
                  goto LABEL_6;
                }
                if ( *a2 < v9 )
                {
                  if ( !*a2 )
                  {
                    Item = -2147023843;
                    goto LABEL_24;
                  }
                  v9 = *a2;
                }
                Sleep(v9);
                *a2 -= v9;
              }
            }
            LastError = GetLastError();
            Item = LastError;
            if ( LastError > 0 )
              Item = (unsigned __int16)LastError | 0x80070000;
LABEL_24:
            CloseServiceHandle(v11);
          }
          else
          {
            v13 = GetLastError();
            Item = v13;
            if ( v13 > 0 )
              Item = (unsigned __int16)v13 | 0x80070000;
          }
        }
      }
    }
    CloseServiceHandle(v5);
  }
  else
  {
    v6 = GetLastError();
    Item = v6;
    if ( v6 > 0 )
      Item = (unsigned __int16)v6 | 0x80070000;
  }
  SERVICES_MANAGER::ResetDependencies(this);
  return (unsigned int)Item;
}

```

## disassembly

```asm
0x18002da9c  mov     [rsp+arg_10], rbx
0x18002daa1  push    rbp
0x18002daa2  push    rsi
0x18002daa3  push    rdi
0x18002daa4  push    r12
0x18002daa6  push    r13
0x18002daa8  push    r14
0x18002daaa  push    r15
0x18002daac  sub     rsp, 50h
0x18002dab0  mov     rax, cs:__security_cookie
0x18002dab7  xor     rax, rsp
0x18002daba  mov     [rsp+88h+var_40], rax
0x18002dabf  xor     eax, eax
0x18002dac1  xorps   xmm0, xmm0
0x18002dac4  mov     r15, rdx
0x18002dac7  mov     [rsp+88h+lpServiceName], rax
0x18002dacc  mov     r13, rcx
0x18002dacf  xor     edx, edx; lpDatabaseName
0x18002dad1  movups  xmmword ptr [rsp+88h+ServiceStatus.dwServiceType], xmm0
0x18002dad6  lea     r8d, [rax+1]; dwDesiredAccess
0x18002dada  xor     ecx, ecx; lpMachineName
0x18002dadc  movups  xmmword ptr [rsp+88h+ServiceStatus.dwWin32ExitCode], xmm0
0x18002dae1  call    cs:__imp_OpenSCManagerW
0x18002dae7  mov     r14, rax
0x18002daea  test    rax, rax
0x18002daed  jnz     short loc_18002DB0D
0x18002daef  call    cs:__imp_GetLastError
0x18002daf5  mov     ebx, eax
0x18002daf7  test    eax, eax
0x18002daf9  jle     loc_18002DC2B
0x18002daff  movzx   ebx, ax
0x18002db02  or      ebx, 80070000h
0x18002db08  jmp     loc_18002DC2B
0x18002db0d  mov     rdx, r14; struct SC_HANDLE__ *
0x18002db10  mov     rcx, r13; this
0x18002db13  call    ?ResolveDependencies@SERVICES_MANAGER@@QEAAJPEAUSC_HANDLE__@@@Z; SERVICES_MANAGER::ResolveDependencies(SC_HANDLE__ *)
0x18002db18  mov     ebx, eax
0x18002db1a  test    eax, eax
0x18002db1c  js      loc_18002DC22
0x18002db22  mov     edi, [r13+8]
0x18002db26  mov     ebp, 3E8h
0x18002db2b  dec     edi
0x18002db2d  test    edi, edi
0x18002db2f  js      loc_18002DC22
0x18002db35  lea     r8, [rsp+88h+lpServiceName]; void **
0x18002db3a  mov     edx, edi; unsigned int
0x18002db3c  lea     rcx, [r13+8]; this
0x18002db40  call    ?GetItem@LIST_ARRAY@@QEAAJKPEAPEAX@Z; LIST_ARRAY::GetItem(ulong,void * *)
0x18002db45  mov     ebx, eax
0x18002db47  test    eax, eax
0x18002db49  js      loc_18002DC22
0x18002db4f  mov     rdx, [rsp+88h+lpServiceName]; lpServiceName
0x18002db54  mov     r8d, 0F01FFh; dwDesiredAccess
0x18002db5a  mov     rcx, r14; hSCManager
0x18002db5d  call    cs:__imp_OpenServiceW
0x18002db63  mov     rsi, rax
0x18002db66  test    rax, rax
0x18002db69  jz      loc_18002DC0D
0x18002db6f  lea     rdx, [rsp+88h+ServiceStatus]; lpServiceStatus
0x18002db74  mov     rcx, rax; hService
0x18002db77  call    cs:__imp_QueryServiceStatus
0x18002db7d  test    eax, eax
0x18002db7f  jz      short loc_18002DBED
0x18002db81  cmp     [rsp+88h+ServiceStatus.dwCurrentState], 4
0x18002db86  jz      short loc_18002DB96
0x18002db88  xor     r8d, r8d; lpServiceArgVectors
0x18002db8b  xor     edx, edx; dwNumServiceArgs
0x18002db8d  mov     rcx, rsi; hService
0x18002db90  call    cs:__imp_StartServiceW
0x18002db96  lea     rdx, [rsp+88h+ServiceStatus]; lpServiceStatus
0x18002db9b  mov     rcx, rsi; hService
0x18002db9e  call    cs:__imp_QueryServiceStatus
0x18002dba4  test    eax, eax
0x18002dba6  jz      short loc_18002DBED
0x18002dba8  cmp     [rsp+88h+ServiceStatus.dwCurrentState], 1
0x18002dbad  jz      short loc_18002DBE6
0x18002dbaf  cmp     [rsp+88h+ServiceStatus.dwCurrentState], 4
0x18002dbb4  jz      short loc_18002DBD1
0x18002dbb6  cmp     [r15], ebp
0x18002dbb9  jnb     short loc_18002DBC4
0x18002dbbb  cmp     dword ptr [r15], 0
0x18002dbbf  jz      short loc_18002DBDF
0x18002dbc1  mov     ebp, [r15]
0x18002dbc4  mov     ecx, ebp; dwMilliseconds
0x18002dbc6  call    cs:__imp_Sleep
0x18002dbcc  sub     [r15], ebp
0x18002dbcf  jmp     short loc_18002DB96
0x18002dbd1  mov     rcx, rsi; hSCObject
0x18002dbd4  call    cs:__imp_CloseServiceHandle
0x18002dbda  jmp     loc_18002DB2B
0x18002dbdf  mov     ebx, 8007041Dh
0x18002dbe4  jmp     short loc_18002DC02
0x18002dbe6  mov     ebx, 80070426h
0x18002dbeb  jmp     short loc_18002DC02
0x18002dbed  call    cs:__imp_GetLastError
0x18002dbf3  mov     ebx, eax
0x18002dbf5  test    eax, eax
0x18002dbf7  jle     short loc_18002DC02
0x18002dbf9  movzx   ebx, ax
0x18002dbfc  or      ebx, 80070000h
0x18002dc02  mov     rcx, rsi; hSCObject
0x18002dc05  call    cs:__imp_CloseServiceHandle
0x18002dc0b  jmp     short loc_18002DC22
0x18002dc0d  call    cs:__imp_GetLastError
0x18002dc13  mov     ebx, eax
0x18002dc15  test    eax, eax
0x18002dc17  jle     short loc_18002DC22
0x18002dc19  movzx   ebx, ax
0x18002dc1c  or      ebx, 80070000h
0x18002dc22  mov     rcx, r14; hSCObject
0x18002dc25  call    cs:__imp_CloseServiceHandle
0x18002dc2b  mov     rcx, r13; this
0x18002dc2e  call    ?ResetDependencies@SERVICES_MANAGER@@AEAAJXZ; SERVICES_MANAGER::ResetDependencies(void)
0x18002dc33  mov     eax, ebx
0x18002dc35  mov     rcx, [rsp+88h+var_40]
0x18002dc3a  xor     rcx, rsp; StackCookie
0x18002dc3d  call    __security_check_cookie
0x18002dc42  mov     rbx, [rsp+88h+arg_10]
0x18002dc4a  add     rsp, 50h
0x18002dc4e  pop     r15
0x18002dc50  pop     r14
0x18002dc52  pop     r13
0x18002dc54  pop     r12
0x18002dc56  pop     rdi
0x18002dc57  pop     rsi
0x18002dc58  pop     rbp
0x18002dc59  retn
```
