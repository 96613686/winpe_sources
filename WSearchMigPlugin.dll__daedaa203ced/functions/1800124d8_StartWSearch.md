# StartWSearch

- ea: `0x1800124d8`
- end: `0x18001264c`
- name: `StartWSearch`
- size: `372`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x1800149a0`

## callees

- `0x1800026f0`
- `0x180002b9c`
- `0x180002c50`
- `0x18000329c`
- `0x1800124d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012553`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012553`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800125f8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800125f8`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180012527`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180012527`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800125d9`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800125d9`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180012505`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180012505`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180012626`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001262f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180012626`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001262f`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800125bb`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180012605`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800125bb`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180012605`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180012545`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180012599`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180012545`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180012599`

## pseudocode

```c
int StartWSearch()
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // r14
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rbx
  struct _QUERY_SERVICE_CONFIGW *v4; // rax
  struct _QUERY_SERVICE_CONFIGW *v5; // rdi
  int v6; // esi
  DWORD pcbBytesNeeded; // [rsp+20h] [rbp-30h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+28h] [rbp-28h] BYREF

  pcbBytesNeeded = 0;
  v0 = OpenSCManagerW(0, 0, 0xF003Fu);
  v1 = v0;
  if ( v0 )
  {
    v2 = OpenServiceW(v0, L"WSearch", 0xF01FFu);
    v3 = v2;
    if ( v2 )
    {
      if ( !QueryServiceConfigW(v2, 0, 0, &pcbBytesNeeded) && GetLastError() == 122 )
      {
        v4 = (struct _QUERY_SERVICE_CONFIGW *)operator new[](
                                                pcbBytesNeeded,
                                                (const struct std::nothrow_t *)&std::nothrow);
        v5 = v4;
        if ( v4 )
        {
          memset_0(v4, 0, pcbBytesNeeded);
          if ( QueryServiceConfigW(v3, v5, pcbBytesNeeded, &pcbBytesNeeded) )
          {
            if ( v5->dwStartType == 2 )
            {
              memset(&ServiceStatus, 0, sizeof(ServiceStatus));
              if ( QueryServiceStatus(v3, &ServiceStatus) )
              {
                if ( ServiceStatus.dwCurrentState != 4 && (ServiceStatus.dwCurrentState == 2 || StartServiceW(v3, 0, 0)) )
                {
                  v6 = 24;
                  do
                  {
                    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
                    Sleep(0x1388u);
                    if ( !QueryServiceStatus(v3, &ServiceStatus) )
                      break;
                    if ( --v6 <= 0 )
                      break;
                  }
                  while ( ServiceStatus.dwCurrentState == 2 );
                }
              }
            }
          }
          operator delete(v5);
        }
      }
      CloseServiceHandle(v3);
    }
    LODWORD(v0) = CloseServiceHandle(v1);
  }
  return (int)v0;
}

```

## disassembly

```asm
0x1800124d8  push    rbp
0x1800124da  push    rbx
0x1800124db  push    rsi
0x1800124dc  push    rdi
0x1800124dd  push    r14
0x1800124df  mov     rbp, rsp
0x1800124e2  sub     rsp, 50h
0x1800124e6  mov     rax, cs:__security_cookie
0x1800124ed  xor     rax, rsp
0x1800124f0  mov     [rbp+var_8], rax
0x1800124f4  xor     edx, edx; lpDatabaseName
0x1800124f6  mov     [rbp+pcbBytesNeeded], 0
0x1800124fd  xor     ecx, ecx; lpMachineName
0x1800124ff  mov     r8d, 0F003Fh; dwDesiredAccess
0x180012505  call    cs:__imp_OpenSCManagerW
0x18001250b  mov     r14, rax
0x18001250e  test    rax, rax
0x180012511  jz      loc_180012635
0x180012517  mov     r8d, 0F01FFh; dwDesiredAccess
0x18001251d  lea     rdx, ServiceName; "WSearch"
0x180012524  mov     rcx, rax; hSCManager
0x180012527  call    cs:__imp_OpenServiceW
0x18001252d  mov     rbx, rax
0x180012530  test    rax, rax
0x180012533  jz      loc_18001262C
0x180012539  lea     r9, [rbp+pcbBytesNeeded]; pcbBytesNeeded
0x18001253d  xor     r8d, r8d; cbBufSize
0x180012540  xor     edx, edx; lpServiceConfig
0x180012542  mov     rcx, rax; hService
0x180012545  call    cs:__imp_QueryServiceConfigW
0x18001254b  test    eax, eax
0x18001254d  jnz     loc_180012623
0x180012553  call    cs:__imp_GetLastError
0x180012559  cmp     eax, 7Ah ; 'z'
0x18001255c  jnz     loc_180012623
0x180012562  mov     ecx, [rbp+pcbBytesNeeded]; unsigned __int64
0x180012565  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001256c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180012571  mov     rdi, rax
0x180012574  test    rax, rax
0x180012577  jz      loc_180012623
0x18001257d  mov     r8d, [rbp+pcbBytesNeeded]; Size
0x180012581  xor     edx, edx; Val
0x180012583  mov     rcx, rax; void *
0x180012586  call    memset_0
0x18001258b  mov     r8d, [rbp+pcbBytesNeeded]; cbBufSize
0x18001258f  lea     r9, [rbp+pcbBytesNeeded]; pcbBytesNeeded
0x180012593  mov     rdx, rdi; lpServiceConfig
0x180012596  mov     rcx, rbx; hService
0x180012599  call    cs:__imp_QueryServiceConfigW
0x18001259f  test    eax, eax
0x1800125a1  jz      short loc_18001261B
0x1800125a3  cmp     dword ptr [rdi+4], 2
0x1800125a7  jnz     short loc_18001261B
0x1800125a9  xorps   xmm0, xmm0
0x1800125ac  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x1800125b0  movups  xmmword ptr [rbp+ServiceStatus.dwServiceType], xmm0
0x1800125b4  mov     rcx, rbx; hService
0x1800125b7  movups  xmmword ptr [rbp+ServiceStatus.dwWin32ExitCode], xmm0
0x1800125bb  call    cs:__imp_QueryServiceStatus
0x1800125c1  test    eax, eax
0x1800125c3  jz      short loc_18001261B
0x1800125c5  cmp     [rbp+ServiceStatus.dwCurrentState], 4
0x1800125c9  jz      short loc_18001261B
0x1800125cb  cmp     [rbp+ServiceStatus.dwCurrentState], 2
0x1800125cf  jz      short loc_1800125E3
0x1800125d1  xor     r8d, r8d; lpServiceArgVectors
0x1800125d4  xor     edx, edx; dwNumServiceArgs
0x1800125d6  mov     rcx, rbx; hService
0x1800125d9  call    cs:__imp_StartServiceW
0x1800125df  test    eax, eax
0x1800125e1  jz      short loc_18001261B
0x1800125e3  mov     esi, 18h
0x1800125e8  xorps   xmm0, xmm0
0x1800125eb  mov     ecx, 1388h; dwMilliseconds
0x1800125f0  movups  xmmword ptr [rbp+ServiceStatus.dwServiceType], xmm0
0x1800125f4  movups  xmmword ptr [rbp+ServiceStatus.dwWin32ExitCode], xmm0
0x1800125f8  call    cs:__imp_Sleep
0x1800125fe  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x180012602  mov     rcx, rbx; hService
0x180012605  call    cs:__imp_QueryServiceStatus
0x18001260b  test    eax, eax
0x18001260d  jz      short loc_18001261B
0x18001260f  dec     esi
0x180012611  test    esi, esi
0x180012613  jle     short loc_18001261B
0x180012615  cmp     [rbp+ServiceStatus.dwCurrentState], 2
0x180012619  jz      short loc_1800125E8
0x18001261b  mov     rcx, rdi; Block
0x18001261e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012623  mov     rcx, rbx; hSCObject
0x180012626  call    cs:__imp_CloseServiceHandle
0x18001262c  mov     rcx, r14; hSCObject
0x18001262f  call    cs:__imp_CloseServiceHandle
0x180012635  mov     rcx, [rbp+var_8]
0x180012639  xor     rcx, rsp; StackCookie
0x18001263c  call    __security_check_cookie
0x180012641  add     rsp, 50h
0x180012645  pop     r14
0x180012647  pop     rdi
0x180012648  pop     rsi
0x180012649  pop     rbx
0x18001264a  pop     rbp
0x18001264b  retn
```
