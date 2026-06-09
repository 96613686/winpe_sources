# SERVICES_MANAGER::Kill(void)

- ea: `0x18002cfb8`
- end: `0x18002d625`
- name: `?Kill@SERVICES_MANAGER@@QEAAJXZ`
- size: `1645`
- prototype: `__int64 __fastcall(SERVICES_MANAGER *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x180025170`

## callees

- `0x180001044`
- `0x180001084`
- `0x18002cd18`
- `0x18002cfb8`
- `0x18002d62c`
- `0x18002d690`
- `0x18002e2d4`
- `0x180034cbe`
- `0x180034d00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d034`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d1e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d260`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d41b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d480`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d53f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d034`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d1e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d260`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d41b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d480`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d53f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002d503`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002d503`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002d026`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002d408`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002d026`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002d408`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002d17e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002d470`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002d17e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002d470`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002d23f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002d28f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002d554`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002d571`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002d59b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002d5a9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002d23f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002d28f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002d554`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002d571`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002d59b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002d5a9`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18002d232`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18002d535`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18002d232`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18002d535`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x18002d1d9`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x18002d21c`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x18002d1d9`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x18002d21c`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18002d1a9`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18002d4e5`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18002d1a9`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18002d4e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d3f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d3f7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d376`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d376`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d339`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d339`

## string_xrefs

- `0x18002d295`: `iisw3adm.dll`
- `0x18002d2d3`: `wam.dll`
- `0x18002d2da`: `DLLHOST`
- `0x18002d32b`: `system\CurrentControlSet\services\IISAdmin`

## pseudocode

```c
__int64 __fastcall SERVICES_MANAGER::Kill(SERVICES_MANAGER *this)
{
  signed int v1; // edi
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // r14
  signed int LastError; // eax
  signed int v6; // ebx
  _QWORD *v7; // r15
  unsigned __int64 v8; // rsi
  void *v9; // rax
  _DWORD *v10; // r13
  _QWORD *v11; // rax
  unsigned int i; // edi
  BYTE *v13; // rax
  signed int v14; // eax
  int v15; // r13d
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  unsigned __int16 *v20; // rdi
  int v21; // eax
  __int64 v22; // rax
  int v23; // ecx
  __int64 v24; // rax
  HKEY v25; // r14
  unsigned int v26; // r13d
  unsigned int v27; // ebx
  signed int v28; // eax
  __int64 v29; // rax
  _DWORD *v30; // rax
  _DWORD *v31; // rbx
  unsigned int j; // r12d
  signed int v33; // eax
  void *v34; // rcx
  int Item; // [rsp+30h] [rbp-D0h]
  unsigned int v37; // [rsp+34h] [rbp-CCh]
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbBufSize; // [rsp+3Ch] [rbp-C4h] BYREF
  int v40; // [rsp+40h] [rbp-C0h]
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  DWORD pcbBytesNeeded; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpServiceName; // [rsp+58h] [rbp-A8h] BYREF
  void *Block; // [rsp+60h] [rbp-A0h]
  LIST_ARRAY *v46; // [rsp+68h] [rbp-98h]
  _QWORD *v47; // [rsp+70h] [rbp-90h]
  SERVICES_MANAGER *v48; // [rsp+78h] [rbp-88h]
  __int128 Info; // [rsp+80h] [rbp-80h] BYREF
  __int128 v50; // [rsp+90h] [rbp-70h]
  _QWORD *v51; // [rsp+A0h] [rbp-60h]
  BYTE Buffer[16]; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v53; // [rsp+B8h] [rbp-48h]
  int v54; // [rsp+C8h] [rbp-38h]
  _QWORD v55[4]; // [rsp+D0h] [rbp-30h] BYREF
  BYTE v56[64]; // [rsp+F0h] [rbp-10h] BYREF
  BYTE Data[2044]; // [rsp+130h] [rbp+30h] BYREF
  int v58; // [rsp+92Ch] [rbp+82Ch]

  v1 = 0;
  v48 = this;
  cbBufSize = 0;
  pcbBytesNeeded = 0;
  v51 = 0;
  v54 = 0;
  lpServiceName = 0;
  Info = 0;
  v50 = 0;
  *(_OWORD *)Buffer = 0;
  v53 = 0;
  v3 = OpenSCManagerW(0, 0, 4u);
  v4 = v3;
  if ( !v3 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_90;
  }
  v37 = 0;
  *(_QWORD *)&v50 = &Str;
  *((_QWORD *)&Info + 1) = &Str;
  Block = 0;
  v51 = v55;
  v7 = 0;
  LODWORD(Info) = -1;
  DWORD2(v50) = 3;
  memset(v55, 0, 24);
  Item = SERVICES_MANAGER::ResolveDependencies(this, v3);
  v6 = Item;
  if ( Item < 0 )
  {
LABEL_81:
    CloseServiceHandle(v4);
    goto LABEL_82;
  }
  v8 = *((unsigned int *)this + 2);
  v46 = (SERVICES_MANAGER *)((char *)this + 8);
  v37 = v8;
  v9 = operator new(saturated_mul(v8, 4u));
  Block = v9;
  v10 = v9;
  if ( !v9
    || (memset_0(v9, 0, 4 * v8), v11 = operator new(saturated_mul((unsigned int)v8, 8u)), v47 = v11, (v7 = v11) == 0) )
  {
    v6 = -2147024888;
    v1 = 0;
    goto LABEL_81;
  }
  v40 = 0;
  memset_0(v11, 0, 8 * v8);
  for ( i = 0; ; ++i )
  {
    if ( i >= (unsigned int)v8 )
    {
      CloseServiceHandle(v4);
      v15 = KillTaskByName(L"SVCHOST", "iisw3adm.dll");
      v16 = KillTaskByName(L"W3WP", 0);
      v1 = 0;
      if ( v15 >= 0 )
        v15 = v16;
      v17 = KillTaskByName(L"INETINFO", 0);
      if ( v15 >= 0 )
        v15 = v17;
      v18 = KillTaskByName(L"DLLHOST", "wam.dll");
      if ( v15 >= 0 )
        v15 = v18;
      v19 = KillTaskByName(L"ASPNET_WP", 0);
      phkResult = 0;
      Type = 0;
      if ( v15 >= 0 )
        v15 = v19;
      cbData = 0;
      v40 = v15;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"system\\CurrentControlSet\\services\\IISAdmin", 0, 0x20019u, &phkResult) )
      {
        cbData = 2048;
        if ( !RegQueryValueExW(phkResult, L"KillProcsOnFailure", 0, &Type, Data, &cbData) && Type == 7 && cbData > 2 )
        {
          v58 = 0;
          v20 = (unsigned __int16 *)Data;
          if ( *(_WORD *)Data )
          {
            do
            {
              v21 = KillTaskByName(v20, 0);
              if ( v15 >= 0 )
                v15 = v21;
              v22 = -1;
              do
                ++v22;
              while ( v20[v22] );
              v23 = -2 - 2 * v22;
              v24 = -1;
              cbData += v23;
              do
                ++v24;
              while ( v20[v24] );
              v20 += v24 + 1;
            }
            while ( *v20 );
            v6 = Item;
            v40 = v15;
          }
          v1 = 0;
        }
        RegCloseKey(phkResult);
      }
      goto LABEL_46;
    }
    Item = LIST_ARRAY::GetItem(v46, i, (void **)&lpServiceName);
    v6 = Item;
    if ( Item < 0 )
    {
      v1 = 0;
LABEL_46:
      v8 = 0;
      goto LABEL_47;
    }
    v8 = (unsigned __int64)OpenServiceW(v4, lpServiceName, 7u);
    if ( !v8 || !QueryServiceStatusEx((SC_HANDLE)v8, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
      break;
    v10[i] = HIDWORD(v53);
    if ( !QueryServiceConfig2W((SC_HANDLE)v8, 2u, v56, 0, &cbBufSize) )
    {
      if ( GetLastError() != 122 )
        break;
      v13 = (BYTE *)operator new(cbBufSize);
      v7[i] = v13;
      if ( !v13 )
      {
        v6 = -2147024888;
        v1 = 0;
        Item = -2147024888;
        goto LABEL_47;
      }
      if ( !QueryServiceConfig2W((SC_HANDLE)v8, 2u, v13, cbBufSize, &cbBufSize) )
        break;
    }
    if ( !ChangeServiceConfig2W((SC_HANDLE)v8, 2u, &Info) )
      break;
    CloseServiceHandle((SC_HANDLE)v8);
    LODWORD(v8) = v37;
  }
  v14 = GetLastError();
  v1 = 0;
  Item = v14;
  v6 = v14;
  if ( v14 > 0 )
  {
    v6 = (unsigned __int16)v14 | 0x80070000;
    Item = v6;
  }
LABEL_47:
  phkResult = (HKEY)OpenSCManagerW(0, 0, 4u);
  v25 = phkResult;
  if ( phkResult )
  {
    v26 = 0;
    if ( v37 )
    {
      v27 = v37;
      do
      {
        if ( v7[v26] )
        {
          v1 = LIST_ARRAY::GetItem(v46, v26, (void **)&lpServiceName);
          if ( v1 >= 0 )
          {
            v8 = (unsigned __int64)OpenServiceW((SC_HANDLE)v25, lpServiceName, 0x17u);
            if ( v8 )
            {
              v29 = v7[v26];
              if ( *(_DWORD *)(v29 + 24) != 3 || (v30 = *(_DWORD **)(v29 + 32)) == 0 || *v30 || v30[2] || v30[4] )
              {
                v31 = Block;
                for ( j = 0; j < 0xA; ++j )
                {
                  if ( !QueryServiceStatusEx((SC_HANDLE)v8, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
                    break;
                  if ( HIDWORD(v53) != v31[v26] )
                    break;
                  if ( *(_DWORD *)&Buffer[4] == 1 )
                    break;
                  Sleep(0x64u);
                }
                v25 = phkResult;
                v7 = v47;
                v27 = v37;
              }
              if ( !ChangeServiceConfig2W((SC_HANDLE)v8, 2u, (LPVOID)v7[v26]) )
              {
                v33 = GetLastError();
                v1 = v33;
                if ( v33 > 0 )
                  v1 = (unsigned __int16)v33 | 0x80070000;
              }
              CloseServiceHandle((SC_HANDLE)v8);
              v8 = 0;
            }
            else
            {
              v28 = GetLastError();
              v1 = v28;
              if ( v28 > 0 )
                v1 = (unsigned __int16)v28 | 0x80070000;
            }
          }
        }
        ++v26;
      }
      while ( v26 < v27 );
      v6 = Item;
    }
    CloseServiceHandle((SC_HANDLE)v25);
    if ( v6 >= 0 )
    {
      if ( v40 >= 0 )
      {
        if ( v1 < 0 )
          v6 = v1;
      }
      else
      {
        v6 = v40;
      }
    }
    v1 = 0;
  }
  else
  {
    GetLastError();
  }
  if ( v8 )
    CloseServiceHandle((SC_HANDLE)v8);
LABEL_82:
  if ( v7 )
  {
    if ( v37 )
    {
      do
      {
        v34 = (void *)v7[v1];
        if ( v34 )
        {
          operator delete(v34);
          v7[v1] = 0;
        }
        ++v1;
      }
      while ( v1 < v37 );
    }
    operator delete(v7);
  }
  if ( Block )
    operator delete(Block);
LABEL_90:
  SERVICES_MANAGER::ResetDependencies(v48);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002cfb8  push    rbp
0x18002cfba  push    rbx
0x18002cfbb  push    rsi
0x18002cfbc  push    rdi
0x18002cfbd  push    r12
0x18002cfbf  push    r13
0x18002cfc1  push    r14
0x18002cfc3  push    r15
0x18002cfc5  lea     rbp, [rsp-848h]
0x18002cfcd  sub     rsp, 948h
0x18002cfd4  mov     rax, cs:__security_cookie
0x18002cfdb  xor     rax, rsp
0x18002cfde  mov     [rbp+880h+var_50], rax
0x18002cfe5  xor     edi, edi
0x18002cfe7  mov     [rsp+980h+var_908], rcx
0x18002cfec  xorps   xmm0, xmm0
0x18002cfef  mov     [rsp+980h+cbBufSize], edi
0x18002cff3  xor     eax, eax
0x18002cff5  mov     [rsp+980h+var_938], edi
0x18002cff9  xorps   xmm1, xmm1
0x18002cffc  mov     [rbp+880h+var_8E0], rax
0x18002d000  mov     r12, rcx
0x18002d003  mov     [rbp+880h+var_8B8], eax
0x18002d006  lea     r13d, [rdi+4]
0x18002d00a  mov     [rsp+980h+lpServiceName], rdi
0x18002d00f  mov     r8d, r13d; dwDesiredAccess
0x18002d012  xor     edx, edx; lpDatabaseName
0x18002d014  xor     ecx, ecx; lpMachineName
0x18002d016  movups  [rbp+880h+Info], xmm0
0x18002d01a  movups  [rbp+880h+var_8F0], xmm0
0x18002d01e  movups  xmmword ptr [rbp+880h+Buffer], xmm1
0x18002d022  movups  [rbp+880h+var_8C8], xmm1
0x18002d026  call    cs:__imp_OpenSCManagerW
0x18002d02c  mov     r14, rax
0x18002d02f  test    rax, rax
0x18002d032  jnz     short loc_18002D052
0x18002d034  call    cs:__imp_GetLastError
0x18002d03a  mov     ebx, eax
0x18002d03c  test    eax, eax
0x18002d03e  jle     loc_18002D5F6
0x18002d044  movzx   ebx, ax
0x18002d047  or      ebx, 80070000h
0x18002d04d  jmp     loc_18002D5F6
0x18002d052  lea     rax, Str
0x18002d059  mov     [rsp+980h+var_94C], edi
0x18002d05d  mov     qword ptr [rbp+880h+var_8F0], rax
0x18002d061  mov     rdx, r14; struct SC_HANDLE__ *
0x18002d064  mov     qword ptr [rbp+880h+Info+8], rax
0x18002d068  mov     rcx, r12; this
0x18002d06b  lea     rax, [rbp+880h+var_8B0]
0x18002d06f  mov     [rsp+980h+Block], rdi
0x18002d074  mov     [rbp+880h+var_8E0], rax
0x18002d078  mov     r15, rdi
0x18002d07b  mov     dword ptr [rbp+880h+Info], 0FFFFFFFFh
0x18002d082  mov     dword ptr [rbp+880h+var_8F0+8], 3
0x18002d089  mov     [rbp+880h+var_8B0], rdi
0x18002d08d  mov     [rbp+880h+var_8A8], rdi
0x18002d091  mov     [rbp+880h+var_8A0], rdi
0x18002d095  call    ?ResolveDependencies@SERVICES_MANAGER@@QEAAJPEAUSC_HANDLE__@@@Z; SERVICES_MANAGER::ResolveDependencies(SC_HANDLE__ *)
0x18002d09a  mov     [rsp+980h+var_950], eax
0x18002d09e  mov     ebx, eax
0x18002d0a0  test    eax, eax
0x18002d0a2  js      loc_18002D5A6
0x18002d0a8  lea     rax, [r12+8]
0x18002d0ad  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002d0b4  mov     esi, [rax]
0x18002d0b6  mov     [rsp+980h+var_918], rax
0x18002d0bb  mov     edi, esi
0x18002d0bd  mov     rax, r13
0x18002d0c0  mov     [rsp+980h+var_94C], esi
0x18002d0c4  mul     rsi
0x18002d0c7  cmovb   rax, rcx
0x18002d0cb  mov     rcx, rax; Size
0x18002d0ce  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002d0d3  xor     r12d, r12d
0x18002d0d6  mov     [rsp+980h+Block], rax
0x18002d0db  mov     r13, rax
0x18002d0de  test    rax, rax
0x18002d0e1  jnz     short loc_18002D0EF
0x18002d0e3  mov     ebx, 80070008h
0x18002d0e8  xor     edi, edi
0x18002d0ea  jmp     loc_18002D5A6
0x18002d0ef  lea     r8, ds:0[rsi*4]; Size
0x18002d0f7  xor     edx, edx; Val
0x18002d0f9  mov     rcx, r13; void *
0x18002d0fc  call    memset_0
0x18002d101  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002d108  mov     eax, 8
0x18002d10d  mul     rdi
0x18002d110  cmovb   rax, rcx
0x18002d114  mov     rcx, rax; Size
0x18002d117  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002d11c  mov     [rsp+980h+var_910], rax
0x18002d121  mov     r15, rax
0x18002d124  test    rax, rax
0x18002d127  jz      short loc_18002D0E3
0x18002d129  lea     r8, ds:0[rsi*8]; Size
0x18002d131  mov     [rsp+980h+var_940], r12d
0x18002d136  xor     edx, edx; Val
0x18002d138  mov     rcx, rax; void *
0x18002d13b  call    memset_0
0x18002d140  mov     edi, r12d
0x18002d143  mov     r12d, 80070000h
0x18002d149  cmp     edi, esi
0x18002d14b  jnb     loc_18002D28C
0x18002d151  mov     rcx, [rsp+980h+var_918]; this
0x18002d156  lea     r8, [rsp+980h+lpServiceName]; void **
0x18002d15b  mov     edx, edi; unsigned int
0x18002d15d  call    ?GetItem@LIST_ARRAY@@QEAAJKPEAPEAX@Z; LIST_ARRAY::GetItem(ulong,void * *)
0x18002d162  mov     [rsp+980h+var_950], eax
0x18002d166  mov     ebx, eax
0x18002d168  test    eax, eax
0x18002d16a  js      loc_18002D285
0x18002d170  mov     rdx, [rsp+980h+lpServiceName]; lpServiceName
0x18002d175  mov     r8d, 7; dwDesiredAccess
0x18002d17b  mov     rcx, r14; hSCManager
0x18002d17e  call    cs:__imp_OpenServiceW
0x18002d184  mov     rsi, rax
0x18002d187  test    rax, rax
0x18002d18a  jz      loc_18002D260
0x18002d190  lea     rax, [rsp+980h+var_938]
0x18002d195  mov     r9d, 24h ; '$'; cbBufSize
0x18002d19b  lea     r8, [rbp+880h+Buffer]; lpBuffer
0x18002d19f  mov     [rsp+980h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18002d1a4  xor     edx, edx; InfoLevel
0x18002d1a6  mov     rcx, rsi; hService
0x18002d1a9  call    cs:__imp_QueryServiceStatusEx
0x18002d1af  test    eax, eax
0x18002d1b1  jz      loc_18002D260
0x18002d1b7  mov     eax, dword ptr [rbp+880h+var_8C8+0Ch]
0x18002d1ba  lea     r8, [rbp+880h+var_890]; lpBuffer
0x18002d1be  mov     ecx, edi
0x18002d1c0  xor     r9d, r9d; cbBufSize
0x18002d1c3  mov     [r13+rcx*4+0], eax
0x18002d1c8  lea     edx, [r9+2]; dwInfoLevel
0x18002d1cc  lea     rax, [rsp+980h+cbBufSize]
0x18002d1d1  mov     rcx, rsi; hService
0x18002d1d4  mov     [rsp+980h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18002d1d9  call    cs:__imp_QueryServiceConfig2W
0x18002d1df  test    eax, eax
0x18002d1e1  jnz     short loc_18002D226
0x18002d1e3  call    cs:__imp_GetLastError
0x18002d1e9  cmp     eax, 7Ah ; 'z'
0x18002d1ec  jnz     short loc_18002D260
0x18002d1ee  mov     ecx, [rsp+980h+cbBufSize]; Size
0x18002d1f2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002d1f7  mov     ecx, edi
0x18002d1f9  mov     [r15+rcx*8], rax
0x18002d1fd  test    rax, rax
0x18002d200  jz      short loc_18002D250
0x18002d202  mov     r9d, [rsp+980h+cbBufSize]; cbBufSize
0x18002d207  lea     rcx, [rsp+980h+cbBufSize]
0x18002d20c  mov     [rsp+980h+pcbBytesNeeded], rcx; pcbBytesNeeded
0x18002d211  mov     r8, rax; lpBuffer
0x18002d214  mov     rcx, rsi; hService
0x18002d217  mov     edx, 2; dwInfoLevel
0x18002d21c  call    cs:__imp_QueryServiceConfig2W
0x18002d222  test    eax, eax
0x18002d224  jz      short loc_18002D260
0x18002d226  lea     r8, [rbp+880h+Info]; lpInfo
0x18002d22a  mov     edx, 2; dwInfoLevel
0x18002d22f  mov     rcx, rsi; hService
0x18002d232  call    cs:__imp_ChangeServiceConfig2W
0x18002d238  test    eax, eax
0x18002d23a  jz      short loc_18002D260
0x18002d23c  mov     rcx, rsi; hSCObject
0x18002d23f  call    cs:__imp_CloseServiceHandle
0x18002d245  mov     esi, [rsp+980h+var_94C]
0x18002d249  inc     edi
0x18002d24b  jmp     loc_18002D143
0x18002d250  mov     ebx, 80070008h
0x18002d255  xor     edi, edi
0x18002d257  mov     [rsp+980h+var_950], ebx
0x18002d25b  jmp     loc_18002D400
0x18002d260  call    cs:__imp_GetLastError
0x18002d266  xor     edi, edi
0x18002d268  mov     [rsp+980h+var_950], eax
0x18002d26c  mov     ebx, eax
0x18002d26e  test    eax, eax
0x18002d270  jle     loc_18002D400
0x18002d276  movzx   ebx, ax
0x18002d279  or      ebx, r12d
0x18002d27c  mov     [rsp+980h+var_950], ebx
0x18002d280  jmp     loc_18002D400
0x18002d285  xor     edi, edi
0x18002d287  jmp     loc_18002D3FD
0x18002d28c  mov     rcx, r14; hSCObject
0x18002d28f  call    cs:__imp_CloseServiceHandle
0x18002d295  lea     rdx, aIisw3admDll; "iisw3adm.dll"
0x18002d29c  lea     rcx, aSvchost; "SVCHOST"
0x18002d2a3  call    ?KillTaskByName@@YAJPEAGPEAD@Z; KillTaskByName(ushort *,char *)
0x18002d2a8  xor     edx, edx; char *
0x18002d2aa  lea     rcx, aW3wp; "W3WP"
0x18002d2b1  mov     r13d, eax
0x18002d2b4  call    ?KillTaskByName@@YAJPEAGPEAD@Z; KillTaskByName(ushort *,char *)
0x18002d2b9  xor     edi, edi
0x18002d2bb  lea     rcx, aInetinfo; "INETINFO"
0x18002d2c2  test    r13d, r13d
0x18002d2c5  cmovns  r13d, eax
0x18002d2c9  xor     edx, edx; char *
0x18002d2cb  call    ?KillTaskByName@@YAJPEAGPEAD@Z; KillTaskByName(ushort *,char *)
0x18002d2d0  test    r13d, r13d
0x18002d2d3  lea     rdx, aWamDll; "wam.dll"
0x18002d2da  lea     rcx, aDllhost; "DLLHOST"
0x18002d2e1  cmovns  r13d, eax
0x18002d2e5  call    ?KillTaskByName@@YAJPEAGPEAD@Z; KillTaskByName(ushort *,char *)
0x18002d2ea  test    r13d, r13d
0x18002d2ed  lea     rcx, aAspnetWp; "ASPNET_WP"
0x18002d2f4  cmovns  r13d, eax
0x18002d2f8  xor     edx, edx; char *
0x18002d2fa  call    ?KillTaskByName@@YAJPEAGPEAD@Z; KillTaskByName(ushort *,char *)
0x18002d2ff  test    r13d, r13d
0x18002d302  mov     [rsp+980h+phkResult], rdi
0x18002d307  mov     r9d, 20019h; samDesired
0x18002d30d  mov     [rsp+980h+Type], edi
0x18002d311  cmovns  r13d, eax
0x18002d315  mov     [rsp+980h+cbData], edi
0x18002d319  lea     rax, [rsp+980h+phkResult]
0x18002d31e  mov     [rsp+980h+var_940], r13d
0x18002d323  xor     r8d, r8d; ulOptions
0x18002d326  mov     [rsp+980h+pcbBytesNeeded], rax; phkResult
0x18002d32b  lea     rdx, SubKey; "system\\CurrentControlSet\\services\\II"...
0x18002d332  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d339  call    cs:__imp_RegOpenKeyExW
0x18002d33f  test    eax, eax
0x18002d341  jnz     loc_18002D3FD
0x18002d347  mov     rcx, [rsp+980h+phkResult]; hKey
0x18002d34c  lea     rax, [rsp+980h+cbData]
0x18002d351  mov     [rsp+980h+lpcbData], rax; lpcbData
0x18002d356  lea     r9, [rsp+980h+Type]; lpType
0x18002d35b  lea     rax, [rbp+880h+Data]
0x18002d35f  mov     [rsp+980h+cbData], 800h
0x18002d367  xor     r8d, r8d; lpReserved
0x18002d36a  mov     [rsp+980h+pcbBytesNeeded], rax; lpData
0x18002d36f  lea     rdx, ValueName; "KillProcsOnFailure"
0x18002d376  call    cs:__imp_RegQueryValueExW
0x18002d37c  test    eax, eax
0x18002d37e  jnz     short loc_18002D3F2
0x18002d380  cmp     [rsp+980h+Type], 7
0x18002d385  jnz     short loc_18002D3F2
0x18002d387  cmp     [rsp+980h+cbData], 2
0x18002d38c  jbe     short loc_18002D3F2
0x18002d38e  xor     esi, esi
0x18002d390  mov     [rbp+880h+var_54], edi
0x18002d396  lea     rdi, [rbp+880h+Data]
0x18002d39a  cmp     word ptr [rbp+880h+Data], si
0x18002d39e  jz      short loc_18002D3F0
0x18002d3a0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002d3a4  xor     edx, edx; char *
0x18002d3a6  mov     rcx, rdi; unsigned __int16 *
0x18002d3a9  call    ?KillTaskByName@@YAJPEAGPEAD@Z; KillTaskByName(ushort *,char *)
0x18002d3ae  test    r13d, r13d
0x18002d3b1  cmovns  r13d, eax
0x18002d3b5  mov     rax, rbx
0x18002d3b8  inc     rax
0x18002d3bb  cmp     [rdi+rax*2], si
0x18002d3bf  jnz     short loc_18002D3B8
0x18002d3c1  add     eax, eax
0x18002d3c3  mov     ecx, 0FFFFFFFEh
0x18002d3c8  sub     ecx, eax
0x18002d3ca  mov     rax, rbx
0x18002d3cd  add     [rsp+980h+cbData], ecx
0x18002d3d1  inc     rax
0x18002d3d4  cmp     [rdi+rax*2], si
0x18002d3d8  jnz     short loc_18002D3D1
0x18002d3da  lea     rdi, [rdi+rax*2]
0x18002d3de  add     rdi, 2
0x18002d3e2  cmp     [rdi], si
0x18002d3e5  jnz     short loc_18002D3A4
0x18002d3e7  mov     ebx, [rsp+980h+var_950]
0x18002d3eb  mov     [rsp+980h+var_940], r13d
0x18002d3f0  xor     edi, edi
0x18002d3f2  mov     rcx, [rsp+980h+phkResult]; hKey
0x18002d3f7  call    cs:__imp_RegCloseKey
0x18002d3fd  mov     rsi, rdi
0x18002d400  xor     edx, edx; lpDatabaseName
0x18002d402  xor     ecx, ecx; lpMachineName
0x18002d404  lea     r8d, [rdx+4]; dwDesiredAccess
0x18002d408  call    cs:__imp_OpenSCManagerW
0x18002d40e  mov     [rsp+980h+phkResult], rax
0x18002d413  mov     r14, rax
0x18002d416  test    rax, rax
0x18002d419  jnz     short loc_18002D426
0x18002d41b  call    cs:__imp_GetLastError
0x18002d421  jmp     loc_18002D593
0x18002d426  xor     ecx, ecx
0x18002d428  mov     r13d, ecx
0x18002d42b  cmp     [rsp+980h+var_94C], ecx
0x18002d42f  jbe     loc_18002D56E
0x18002d435  mov     ebx, [rsp+980h+var_94C]
0x18002d439  mov     eax, r13d
0x18002d43c  cmp     [r15+rax*8], rcx
0x18002d440  jz      loc_18002D55E
0x18002d446  mov     rcx, [rsp+980h+var_918]; this
0x18002d44b  lea     r8, [rsp+980h+lpServiceName]; void **
0x18002d450  mov     edx, r13d; unsigned int
0x18002d453  call    ?GetItem@LIST_ARRAY@@QEAAJKPEAPEAX@Z; LIST_ARRAY::GetItem(ulong,void * *)
0x18002d458  xor     ecx, ecx
0x18002d45a  mov     edi, eax
0x18002d45c  test    eax, eax
  ... truncated ...
```
