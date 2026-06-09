# LogonSoundHelpers::IsSoundOn

- ea: `0x1800453ac`
- end: `0x18004549e`
- name: `LogonSoundHelpers::IsSoundOn`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180045230`

## callees

- `0x1800453ac`
- `0x180061c5c`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18004543b`
- `KERNEL32!LocalAlloc` at `0x18004543b`
- `KERNEL32!LocalFree` at `0x180045471`
- `KERNEL32!LocalFree` at `0x180045471`
- `KERNEL32!GetLastError` at `0x180045429`
- `KERNEL32!GetLastError` at `0x180045429`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004547a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180045483`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004547a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180045483`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800453fc`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800453fc`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800453da`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800453da`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18004541f`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180045459`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18004541f`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180045459`

## pseudocode

```c
bool LogonSoundHelpers::IsSoundOn()
{
  bool v0; // bl
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rbp
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rsi
  struct _QUERY_SERVICE_CONFIGW *v5; // rax
  struct _QUERY_SERVICE_CONFIGW *v6; // rdi
  DWORD pcbBytesNeeded; // [rsp+40h] [rbp+8h] BYREF

  v0 = 0;
  if ( (unsigned __int8)LogonSoundHelpers::IsSoundEnabled() )
  {
    v1 = OpenSCManagerW(0, 0, 1u);
    v2 = v1;
    if ( v1 )
    {
      v3 = OpenServiceW(v1, L"AudioSrv", 0x80000000);
      v4 = v3;
      if ( v3 )
      {
        pcbBytesNeeded = 0;
        if ( !QueryServiceConfigW(v3, 0, 0, &pcbBytesNeeded) && GetLastError() == 122 )
        {
          v5 = (struct _QUERY_SERVICE_CONFIGW *)LocalAlloc(0x40u, pcbBytesNeeded);
          v6 = v5;
          if ( v5 )
          {
            if ( QueryServiceConfigW(v4, v5, pcbBytesNeeded, &pcbBytesNeeded) )
              v0 = v6->dwStartType == 2;
            LocalFree(v6);
          }
        }
        CloseServiceHandle(v4);
      }
      CloseServiceHandle(v2);
    }
  }
  return v0;
}

```

## disassembly

```asm
0x1800453ac  mov     [rsp+arg_8], rbx
0x1800453b1  mov     [rsp+arg_10], rbp
0x1800453b6  push    rsi
0x1800453b7  push    rdi
0x1800453b8  push    r14
0x1800453ba  sub     rsp, 20h
0x1800453be  xor     bl, bl
0x1800453c0  call    LogonSoundHelpers__IsSoundEnabled
0x1800453c5  test    al, al
0x1800453c7  jz      loc_180045489
0x1800453cd  mov     r14d, 1
0x1800453d3  xor     edx, edx; lpDatabaseName
0x1800453d5  mov     r8d, r14d; dwDesiredAccess
0x1800453d8  xor     ecx, ecx; lpMachineName
0x1800453da  call    cs:__imp_OpenSCManagerW
0x1800453e0  mov     rbp, rax
0x1800453e3  test    rax, rax
0x1800453e6  jz      loc_180045489
0x1800453ec  mov     r8d, 80000000h; dwDesiredAccess
0x1800453f2  lea     rdx, ServiceName; "AudioSrv"
0x1800453f9  mov     rcx, rax; hSCManager
0x1800453fc  call    cs:__imp_OpenServiceW
0x180045402  mov     rsi, rax
0x180045405  test    rax, rax
0x180045408  jz      short loc_180045480
0x18004540a  lea     r9, [rsp+38h+pcbBytesNeeded]; pcbBytesNeeded
0x18004540f  mov     [rsp+38h+pcbBytesNeeded], 0
0x180045417  xor     r8d, r8d; cbBufSize
0x18004541a  xor     edx, edx; lpServiceConfig
0x18004541c  mov     rcx, rax; hService
0x18004541f  call    cs:__imp_QueryServiceConfigW
0x180045425  test    eax, eax
0x180045427  jnz     short loc_180045477
0x180045429  call    cs:__imp_GetLastError
0x18004542f  cmp     eax, 7Ah ; 'z'
0x180045432  jnz     short loc_180045477
0x180045434  mov     edx, [rsp+38h+pcbBytesNeeded]; uBytes
0x180045438  lea     ecx, [rax-3Ah]; uFlags
0x18004543b  call    cs:__imp_LocalAlloc
0x180045441  mov     rdi, rax
0x180045444  test    rax, rax
0x180045447  jz      short loc_180045477
0x180045449  mov     r8d, [rsp+38h+pcbBytesNeeded]; cbBufSize
0x18004544e  lea     r9, [rsp+38h+pcbBytesNeeded]; pcbBytesNeeded
0x180045453  mov     rdx, rax; lpServiceConfig
0x180045456  mov     rcx, rsi; hService
0x180045459  call    cs:__imp_QueryServiceConfigW
0x18004545f  test    eax, eax
0x180045461  jz      short loc_18004546E
0x180045463  cmp     dword ptr [rdi+4], 2
0x180045467  movzx   ebx, bl
0x18004546a  cmovz   ebx, r14d
0x18004546e  mov     rcx, rdi; hMem
0x180045471  call    cs:__imp_LocalFree
0x180045477  mov     rcx, rsi; hSCObject
0x18004547a  call    cs:__imp_CloseServiceHandle
0x180045480  mov     rcx, rbp; hSCObject
0x180045483  call    cs:__imp_CloseServiceHandle
0x180045489  mov     rbp, [rsp+38h+arg_10]
0x18004548e  mov     al, bl
0x180045490  mov     rbx, [rsp+38h+arg_8]
0x180045495  add     rsp, 20h
0x180045499  pop     r14
0x18004549b  pop     rdi
0x18004549c  pop     rsi
0x18004549d  retn
```
