# TriggerStartWebclientServiceIfNotRunning

- ea: `0x180003180`
- end: `0x1800032eb`
- name: `TriggerStartWebclientServiceIfNotRunning`
- size: `363`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x1800027c0`

## callees

- `0x180003180`
- `0x180003af0`
- `0x180006100`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180003268`
- `KERNEL32!LocalFree` at `0x180003268`
- `KERNEL32!GetLastError` at `0x1800032a2`
- `KERNEL32!GetLastError` at `0x1800032a2`
- `KERNEL32!Sleep` at `0x1800032c3`
- `KERNEL32!Sleep` at `0x1800032c3`
- `KERNEL32!LocalAlloc` at `0x180003225`
- `KERNEL32!LocalAlloc` at `0x180003225`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180003276`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000327f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180003276`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000327f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800031b4`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800031b4`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800031ea`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800031ea`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180003209`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180003243`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180003209`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180003243`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18000325b`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800032d1`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18000325b`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800032d1`

## pseudocode

```c
int TriggerStartWebclientServiceIfNotRunning()
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rbx
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rdi
  struct _QUERY_SERVICE_CONFIGW *v4; // rax
  struct _QUERY_SERVICE_CONFIGW *v5; // rsi
  unsigned int v6; // ebp
  DWORD pcbBytesNeeded; // [rsp+20h] [rbp-38h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+28h] [rbp-30h] BYREF

  pcbBytesNeeded = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v0 = OpenSCManagerW(0, 0, 1u);
  v1 = v0;
  if ( v0 )
  {
    v2 = OpenServiceW(v0, L"Webclient", 5u);
    v3 = v2;
    if ( v2 )
    {
      if ( QueryServiceConfigW(v2, 0, 0, &pcbBytesNeeded) || GetLastError() == 122 )
      {
        v4 = (struct _QUERY_SERVICE_CONFIGW *)LocalAlloc(0x40u, pcbBytesNeeded);
        v5 = v4;
        if ( v4 )
        {
          if ( QueryServiceConfigW(v3, v4, pcbBytesNeeded, &pcbBytesNeeded) )
          {
            if ( v5->dwStartType != 4 )
            {
              if ( QueryServiceStatus(v3, &ServiceStatus) )
              {
                if ( ServiceStatus.dwCurrentState != 4 )
                {
                  v6 = 0;
                  if ( !(unsigned int)SendWebclientTriggerEvent() )
                  {
                    do
                    {
                      Sleep(0xBB8u);
                      if ( !QueryServiceStatus(v3, &ServiceStatus) )
                        break;
                      if ( ServiceStatus.dwCurrentState == 4 )
                        break;
                      ++v6;
                    }
                    while ( v6 < 5 );
                  }
                }
              }
            }
          }
          LocalFree(v5);
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
0x180003180  push    rbx
0x180003182  sub     rsp, 50h
0x180003186  mov     rax, cs:__security_cookie
0x18000318d  xor     rax, rsp
0x180003190  mov     [rsp+58h+var_10], rax
0x180003195  xorps   xmm0, xmm0
0x180003198  mov     [rsp+58h+pcbBytesNeeded], 0
0x1800031a0  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x1800031a5  xor     edx, edx; lpDatabaseName
0x1800031a7  xor     ecx, ecx; lpMachineName
0x1800031a9  mov     r8d, 1; dwDesiredAccess
0x1800031af  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800031b4  call    cs:__imp_OpenSCManagerW
0x1800031ba  mov     rbx, rax
0x1800031bd  test    rax, rax
0x1800031c0  jnz     short loc_1800031D5
0x1800031c2  mov     rcx, [rsp+58h+var_10]
0x1800031c7  xor     rcx, rsp; StackCookie
0x1800031ca  call    __security_check_cookie
0x1800031cf  add     rsp, 50h
0x1800031d3  pop     rbx
0x1800031d4  retn
0x1800031d5  mov     r8d, 5; dwDesiredAccess
0x1800031db  mov     [rsp+58h+arg_10], rdi
0x1800031e0  lea     rdx, ServiceName; "Webclient"
0x1800031e7  mov     rcx, rbx; hSCManager
0x1800031ea  call    cs:__imp_OpenServiceW
0x1800031f0  mov     rdi, rax
0x1800031f3  test    rax, rax
0x1800031f6  jz      loc_18000327C
0x1800031fc  lea     r9, [rsp+58h+pcbBytesNeeded]; pcbBytesNeeded
0x180003201  xor     r8d, r8d; cbBufSize
0x180003204  xor     edx, edx; lpServiceConfig
0x180003206  mov     rcx, rax; hService
0x180003209  call    cs:__imp_QueryServiceConfigW
0x18000320f  test    eax, eax
0x180003211  jz      loc_1800032A2
0x180003217  mov     edx, [rsp+58h+pcbBytesNeeded]; uBytes
0x18000321b  mov     ecx, 40h ; '@'; uFlags
0x180003220  mov     [rsp+58h+arg_8], rsi
0x180003225  call    cs:__imp_LocalAlloc
0x18000322b  mov     rsi, rax
0x18000322e  test    rax, rax
0x180003231  jz      short loc_18000326E
0x180003233  mov     r8d, [rsp+58h+pcbBytesNeeded]; cbBufSize
0x180003238  lea     r9, [rsp+58h+pcbBytesNeeded]; pcbBytesNeeded
0x18000323d  mov     rdx, rax; lpServiceConfig
0x180003240  mov     rcx, rdi; hService
0x180003243  call    cs:__imp_QueryServiceConfigW
0x180003249  test    eax, eax
0x18000324b  jz      short loc_180003265
0x18000324d  cmp     dword ptr [rsi+4], 4
0x180003251  jz      short loc_180003265
0x180003253  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x180003258  mov     rcx, rdi; hService
0x18000325b  call    cs:__imp_QueryServiceStatus
0x180003261  test    eax, eax
0x180003263  jnz     short loc_18000328F
0x180003265  mov     rcx, rsi; hMem
0x180003268  call    cs:__imp_LocalFree
0x18000326e  mov     rsi, [rsp+58h+arg_8]
0x180003273  mov     rcx, rdi; hSCObject
0x180003276  call    cs:__imp_CloseServiceHandle
0x18000327c  mov     rcx, rbx; hSCObject
0x18000327f  call    cs:__imp_CloseServiceHandle
0x180003285  mov     rdi, [rsp+58h+arg_10]
0x18000328a  jmp     loc_1800031C2
0x18000328f  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 4
0x180003294  mov     [rsp+58h+arg_0], rbp
0x180003299  jnz     short loc_1800032B3
0x18000329b  mov     rbp, [rsp+58h+arg_0]
0x1800032a0  jmp     short loc_180003265
0x1800032a2  call    cs:__imp_GetLastError
0x1800032a8  cmp     eax, 7Ah ; 'z'
0x1800032ab  jz      loc_180003217
0x1800032b1  jmp     short loc_180003273
0x1800032b3  xor     ebp, ebp
0x1800032b5  call    SendWebclientTriggerEvent
0x1800032ba  test    eax, eax
0x1800032bc  jnz     short loc_18000329B
0x1800032be  mov     ecx, 0BB8h; dwMilliseconds
0x1800032c3  call    cs:__imp_Sleep
0x1800032c9  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x1800032ce  mov     rcx, rdi; hService
0x1800032d1  call    cs:__imp_QueryServiceStatus
0x1800032d7  test    eax, eax
0x1800032d9  jz      short loc_18000329B
0x1800032db  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 4
0x1800032e0  jz      short loc_18000329B
0x1800032e2  inc     ebp
0x1800032e4  cmp     ebp, 5
0x1800032e7  jb      short loc_1800032BE
0x1800032e9  jmp     short loc_18000329B
```
