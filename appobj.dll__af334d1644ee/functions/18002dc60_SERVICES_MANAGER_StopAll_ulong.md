# SERVICES_MANAGER::StopAll(ulong *)

- ea: `0x18002dc60`
- end: `0x18002ded8`
- name: `?StopAll@SERVICES_MANAGER@@QEAAJPEAK@Z`
- size: `632`
- prototype: `__int64 __fastcall(SERVICES_MANAGER *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x180025170`

## callees

- `0x180001fb0`
- `0x18002cd18`
- `0x18002d62c`
- `0x18002d690`
- `0x18002d974`
- `0x18002dc60`
- `0x180033954`
- `0x180034cbe`
- `0x180034d00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dcdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dd86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002de4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dcdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dd86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002de4b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002de33`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002de33`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002dccb`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002dccb`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002dd74`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002dd74`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002de81`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002de98`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002de81`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002de98`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002ddd5`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002ddd5`

## pseudocode

```c
__int64 __fastcall SERVICES_MANAGER::StopAll(SERVICES_MANAGER *this, unsigned int *a2)
{
  SERVICES_MANAGER *v2; // rdi
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // r12
  signed int v5; // eax
  signed int Item; // ebx
  LIST_ARRAY *v7; // r15
  _QWORD *v8; // rsi
  signed int v9; // edi
  SC_HANDLE v10; // rax
  signed int LastError; // eax
  DWORD v12; // r12d
  int v13; // r13d
  int i; // r14d
  SC_HANDLE v15; // rcx
  unsigned int v16; // edx
  signed int v17; // eax
  unsigned int *v18; // r14
  signed int v19; // eax
  unsigned int v20; // edi
  SC_HANDLE v21; // rcx
  SC_HANDLE v23; // [rsp+20h] [rbp-59h]
  LPCWSTR lpServiceName; // [rsp+30h] [rbp-49h] BYREF
  unsigned int *v26; // [rsp+38h] [rbp-41h]
  _QWORD v27[4]; // [rsp+40h] [rbp-39h] BYREF
  void *v28; // [rsp+60h] [rbp-19h]
  int v29; // [rsp+68h] [rbp-11h]
  __int16 v30; // [rsp+6Ch] [rbp-Dh]
  struct _SERVICE_STATUS ServiceStatus; // [rsp+70h] [rbp-9h] BYREF

  v26 = a2;
  v28 = v27;
  v2 = this;
  v27[0] = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v29 = 32;
  v30 = 256;
  lpServiceName = 0;
  v3 = OpenSCManagerW(0, 0, 1u);
  v23 = v3;
  v4 = v3;
  if ( v3 )
  {
    Item = SERVICES_MANAGER::ResolveDependencies(v2, v3);
    if ( Item >= 0 )
    {
      v7 = (SERVICES_MANAGER *)((char *)v2 + 8);
      if ( BUFFER::Resize((BUFFER *)v27, 8 * *((_DWORD *)v2 + 2)) )
      {
        v8 = v28;
        memset_0(v28, 0, 8LL * *(unsigned int *)v7);
        v9 = *(_DWORD *)v7;
        while ( --v9 >= 0 )
        {
          Item = LIST_ARRAY::GetItem(v7, v9, (void **)&lpServiceName);
          if ( Item < 0 )
            goto LABEL_35;
          v10 = OpenServiceW(v4, lpServiceName, 0xF01FFu);
          v8[v9] = v10;
          if ( !v10 )
          {
            LastError = GetLastError();
            Item = LastError;
            if ( LastError > 0 )
              Item = (unsigned __int16)LastError | 0x80070000;
            goto LABEL_35;
          }
        }
        v12 = 1000;
        v13 = 0;
LABEL_14:
        if ( v13 != *(_DWORD *)v7 )
        {
          v13 = 0;
          for ( i = *(_DWORD *)v7 - 1; ; --i )
          {
            if ( i < 0 )
            {
              v18 = v26;
              if ( *v26 < v12 )
              {
                if ( !*v26 )
                {
                  Item = -2147023843;
                  break;
                }
                v12 = *v26;
              }
              Sleep(v12);
              *v18 -= v12;
              goto LABEL_14;
            }
            v15 = (SC_HANDLE)v8[i];
            if ( v15 )
            {
              if ( !QueryServiceStatus(v15, &ServiceStatus) )
              {
                v19 = GetLastError();
                Item = v19;
                if ( v19 > 0 )
                  Item = (unsigned __int16)v19 | 0x80070000;
                break;
              }
              if ( ServiceStatus.dwCurrentState == 1 )
              {
                ++v13;
              }
              else if ( ServiceStatus.dwCurrentState != 3 )
              {
                v17 = SendControlToService((struct SC_HANDLE__ *)v8[i], v16, v26);
                Item = v17;
                if ( v17 == -2147023843 )
                {
                  v8[i] = 0;
                  break;
                }
                if ( (int)(v17 + 0x80000000) >= 0 && v17 != -2147023845 )
                  break;
              }
            }
          }
        }
        v4 = v23;
LABEL_35:
        if ( v8 )
        {
          v20 = *(_DWORD *)v7;
          while ( (--v20 & 0x80000000) == 0 )
          {
            v21 = (SC_HANDLE)v8[v20];
            if ( v21 )
            {
              CloseServiceHandle(v21);
              v8[v20] = 0;
            }
          }
        }
        v2 = this;
      }
      else
      {
        Item = -2147024888;
      }
    }
    CloseServiceHandle(v4);
  }
  else
  {
    v5 = GetLastError();
    Item = v5;
    if ( v5 > 0 )
      Item = (unsigned __int16)v5 | 0x80070000;
  }
  SERVICES_MANAGER::ResetDependencies(v2);
  BUFFER::~BUFFER((BUFFER *)v27);
  return (unsigned int)Item;
}

```

## disassembly

```asm
0x18002dc60  mov     [rsp-8+arg_10], rbx
0x18002dc65  push    rbp
0x18002dc66  push    rsi
0x18002dc67  push    rdi
0x18002dc68  push    r12
0x18002dc6a  push    r13
0x18002dc6c  push    r14
0x18002dc6e  push    r15
0x18002dc70  lea     rbp, [rsp-27h]
0x18002dc75  sub     rsp, 0A0h
0x18002dc7c  mov     rax, cs:__security_cookie
0x18002dc83  xor     rax, rsp
0x18002dc86  mov     [rbp+57h+var_40], rax
0x18002dc8a  xorps   xmm0, xmm0
0x18002dc8d  mov     [rbp+57h+var_98], rdx
0x18002dc91  lea     rax, [rbp+57h+var_90]
0x18002dc95  mov     [rbp+57h+var_A8], rcx
0x18002dc99  mov     [rbp+57h+var_70], rax
0x18002dc9d  mov     rdi, rcx
0x18002dca0  xor     eax, eax
0x18002dca2  mov     [rbp+57h+var_90], 0
0x18002dcaa  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x18002dcae  xor     edx, edx; lpDatabaseName
0x18002dcb0  mov     [rbp+57h+var_68], 20h ; ' '
0x18002dcb7  xor     ecx, ecx; lpMachineName
0x18002dcb9  mov     [rbp+57h+var_64], 100h
0x18002dcbf  lea     r8d, [rax+1]; dwDesiredAccess
0x18002dcc3  mov     [rbp+57h+lpServiceName], rax
0x18002dcc7  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x18002dccb  call    cs:__imp_OpenSCManagerW
0x18002dcd1  mov     [rbp+57h+var_B0], rax
0x18002dcd5  mov     r12, rax
0x18002dcd8  test    rax, rax
0x18002dcdb  jnz     short loc_18002DCFB
0x18002dcdd  call    cs:__imp_GetLastError
0x18002dce3  mov     ebx, eax
0x18002dce5  test    eax, eax
0x18002dce7  jle     loc_18002DE9E
0x18002dced  movzx   ebx, ax
0x18002dcf0  or      ebx, 80070000h
0x18002dcf6  jmp     loc_18002DE9E
0x18002dcfb  mov     rdx, r12; struct SC_HANDLE__ *
0x18002dcfe  mov     rcx, rdi; this
0x18002dd01  call    ?ResolveDependencies@SERVICES_MANAGER@@QEAAJPEAUSC_HANDLE__@@@Z; SERVICES_MANAGER::ResolveDependencies(SC_HANDLE__ *)
0x18002dd06  mov     ebx, eax
0x18002dd08  test    eax, eax
0x18002dd0a  js      loc_18002DE95
0x18002dd10  lea     r15, [rdi+8]
0x18002dd14  mov     edx, [r15]
0x18002dd17  lea     rcx, [rbp+57h+var_90]; this
0x18002dd1b  shl     edx, 3; unsigned int
0x18002dd1e  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18002dd23  test    al, al
0x18002dd25  jnz     short loc_18002DD31
0x18002dd27  mov     ebx, 80070008h
0x18002dd2c  jmp     loc_18002DE95
0x18002dd31  mov     rsi, [rbp+57h+var_70]
0x18002dd35  xor     edx, edx; Val
0x18002dd37  mov     r8d, [r15]
0x18002dd3a  mov     rcx, rsi; void *
0x18002dd3d  shl     r8, 3; Size
0x18002dd41  call    memset_0
0x18002dd46  mov     edi, [r15]
0x18002dd49  dec     edi
0x18002dd4b  test    edi, edi
0x18002dd4d  js      short loc_18002DDA4
0x18002dd4f  lea     r8, [rbp+57h+lpServiceName]; void **
0x18002dd53  mov     edx, edi; unsigned int
0x18002dd55  mov     rcx, r15; this
0x18002dd58  call    ?GetItem@LIST_ARRAY@@QEAAJKPEAPEAX@Z; LIST_ARRAY::GetItem(ulong,void * *)
0x18002dd5d  mov     ebx, eax
0x18002dd5f  test    eax, eax
0x18002dd61  js      loc_18002DE6B
0x18002dd67  mov     rdx, [rbp+57h+lpServiceName]; lpServiceName
0x18002dd6b  mov     r8d, 0F01FFh; dwDesiredAccess
0x18002dd71  mov     rcx, r12; hSCManager
0x18002dd74  call    cs:__imp_OpenServiceW
0x18002dd7a  movsxd  rcx, edi
0x18002dd7d  mov     [rsi+rcx*8], rax
0x18002dd81  test    rax, rax
0x18002dd84  jnz     short loc_18002DD49
0x18002dd86  call    cs:__imp_GetLastError
0x18002dd8c  mov     ebx, eax
0x18002dd8e  test    eax, eax
0x18002dd90  jle     loc_18002DE6B
0x18002dd96  movzx   ebx, ax
0x18002dd99  or      ebx, 80070000h
0x18002dd9f  jmp     loc_18002DE6B
0x18002dda4  mov     r12d, 3E8h
0x18002ddaa  xor     r13d, r13d
0x18002ddad  mov     eax, [r15]
0x18002ddb0  cmp     r13d, eax
0x18002ddb3  jz      loc_18002DE67
0x18002ddb9  xor     r13d, r13d
0x18002ddbc  lea     r14d, [rax-1]
0x18002ddc0  test    r14d, r14d
0x18002ddc3  js      short loc_18002DE1E
0x18002ddc5  movsxd  rdi, r14d
0x18002ddc8  mov     rcx, [rsi+rdi*8]; hService
0x18002ddcc  test    rcx, rcx
0x18002ddcf  jz      short loc_18002DE19
0x18002ddd1  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x18002ddd5  call    cs:__imp_QueryServiceStatus
0x18002dddb  test    eax, eax
0x18002dddd  jz      short loc_18002DE4B
0x18002dddf  cmp     [rbp+57h+ServiceStatus.dwCurrentState], 1
0x18002dde3  jnz     short loc_18002DDEA
0x18002dde5  inc     r13d
0x18002dde8  jmp     short loc_18002DE19
0x18002ddea  cmp     [rbp+57h+ServiceStatus.dwCurrentState], 3
0x18002ddee  jz      short loc_18002DE19
0x18002ddf0  mov     r8, [rbp+57h+var_98]; unsigned int *
0x18002ddf4  mov     rcx, [rsi+rdi*8]; struct SC_HANDLE__ *
0x18002ddf8  call    ?SendControlToService@@YAJPEAUSC_HANDLE__@@KPEAK@Z; SendControlToService(SC_HANDLE__ *,ulong,ulong *)
0x18002ddfd  mov     ebx, eax
0x18002ddff  cmp     eax, 8007041Dh
0x18002de04  jz      short loc_18002DE41
0x18002de06  mov     ecx, 80000000h
0x18002de0b  add     eax, ecx
0x18002de0d  test    ecx, eax
0x18002de0f  jnz     short loc_18002DE19
0x18002de11  cmp     ebx, 8007041Bh
0x18002de17  jnz     short loc_18002DE67
0x18002de19  dec     r14d
0x18002de1c  jmp     short loc_18002DDC0
0x18002de1e  mov     r14, [rbp+57h+var_98]
0x18002de22  cmp     [r14], r12d
0x18002de25  jnb     short loc_18002DE30
0x18002de27  cmp     dword ptr [r14], 0
0x18002de2b  jz      short loc_18002DE62
0x18002de2d  mov     r12d, [r14]
0x18002de30  mov     ecx, r12d; dwMilliseconds
0x18002de33  call    cs:__imp_Sleep
0x18002de39  sub     [r14], r12d
0x18002de3c  jmp     loc_18002DDAD
0x18002de41  mov     qword ptr [rsi+rdi*8], 0
0x18002de49  jmp     short loc_18002DE67
0x18002de4b  call    cs:__imp_GetLastError
0x18002de51  mov     ebx, eax
0x18002de53  test    eax, eax
0x18002de55  jle     short loc_18002DE67
0x18002de57  movzx   ebx, ax
0x18002de5a  or      ebx, 80070000h
0x18002de60  jmp     short loc_18002DE67
0x18002de62  mov     ebx, 8007041Dh
0x18002de67  mov     r12, [rbp+57h+var_B0]
0x18002de6b  test    rsi, rsi
0x18002de6e  jz      short loc_18002DE91
0x18002de70  mov     edi, [r15]
0x18002de73  sub     edi, 1
0x18002de76  js      short loc_18002DE91
0x18002de78  mov     rcx, [rsi+rdi*8]; hSCObject
0x18002de7c  test    rcx, rcx
0x18002de7f  jz      short loc_18002DE73
0x18002de81  call    cs:__imp_CloseServiceHandle
0x18002de87  mov     qword ptr [rsi+rdi*8], 0
0x18002de8f  jmp     short loc_18002DE73
0x18002de91  mov     rdi, [rbp+57h+var_A8]
0x18002de95  mov     rcx, r12; hSCObject
0x18002de98  call    cs:__imp_CloseServiceHandle
0x18002de9e  mov     rcx, rdi; this
0x18002dea1  call    ?ResetDependencies@SERVICES_MANAGER@@AEAAJXZ; SERVICES_MANAGER::ResetDependencies(void)
0x18002dea6  lea     rcx, [rbp+57h+var_90]; this
0x18002deaa  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002deaf  mov     eax, ebx
0x18002deb1  mov     rcx, [rbp+57h+var_40]
0x18002deb5  xor     rcx, rsp; StackCookie
0x18002deb8  call    __security_check_cookie
0x18002debd  mov     rbx, [rsp+0D0h+arg_10]
0x18002dec5  add     rsp, 0A0h
0x18002decc  pop     r15
0x18002dece  pop     r14
0x18002ded0  pop     r13
0x18002ded2  pop     r12
0x18002ded4  pop     rdi
0x18002ded5  pop     rsi
0x18002ded6  pop     rbp
0x18002ded7  retn
```
