# IsThemeServiceAutoStart(void)

- ea: `0x140006b3c`
- end: `0x140006bf9`
- name: `?IsThemeServiceAutoStart@@YA_NXZ`
- size: `189`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x1400097a0`

## callees

- `0x140006b3c`

## import_xrefs

- `ADVAPI32!OpenServiceW` at `0x140006b73`
- `ADVAPI32!OpenServiceW` at `0x140006b73`
- `ADVAPI32!QueryServiceConfigW` at `0x140006b96`
- `ADVAPI32!QueryServiceConfigW` at `0x140006bc0`
- `ADVAPI32!QueryServiceConfigW` at `0x140006b96`
- `ADVAPI32!QueryServiceConfigW` at `0x140006bc0`
- `ADVAPI32!OpenSCManagerW` at `0x140006b54`
- `ADVAPI32!OpenSCManagerW` at `0x140006b54`
- `ADVAPI32!CloseServiceHandle` at `0x140006bde`
- `ADVAPI32!CloseServiceHandle` at `0x140006be7`
- `ADVAPI32!CloseServiceHandle` at `0x140006bde`
- `ADVAPI32!CloseServiceHandle` at `0x140006be7`
- `KERNEL32!LocalAlloc` at `0x140006ba2`
- `KERNEL32!LocalAlloc` at `0x140006ba2`
- `KERNEL32!LocalFree` at `0x140006bd5`
- `KERNEL32!LocalFree` at `0x140006bd5`

## pseudocode

```c
bool IsThemeServiceAutoStart(void)
{
  bool v0; // bp
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rsi
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rdi
  struct _QUERY_SERVICE_CONFIGW *v5; // rax
  struct _QUERY_SERVICE_CONFIGW *v6; // rbx
  DWORD pcbBytesNeeded; // [rsp+50h] [rbp+8h] BYREF

  v0 = 0;
  v1 = OpenSCManagerW(0, 0, 1u);
  v2 = v1;
  if ( v1 )
  {
    v3 = OpenServiceW(v1, L"Themes", 1u);
    v4 = v3;
    if ( v3 )
    {
      pcbBytesNeeded = 0;
      QueryServiceConfigW(v3, 0, 0, &pcbBytesNeeded);
      v5 = (struct _QUERY_SERVICE_CONFIGW *)LocalAlloc(0, pcbBytesNeeded);
      v6 = v5;
      if ( v5 )
      {
        if ( QueryServiceConfigW(v4, v5, pcbBytesNeeded, &pcbBytesNeeded) )
          v0 = v6->dwStartType == 2;
        LocalFree(v6);
      }
      CloseServiceHandle(v4);
    }
    CloseServiceHandle(v2);
  }
  return v0;
}

```

## disassembly

```asm
0x140006b3c  push    rbx
0x140006b3e  push    rbp
0x140006b3f  push    rsi
0x140006b40  push    rdi
0x140006b41  sub     rsp, 28h
0x140006b45  mov     ebx, 1
0x140006b4a  xor     edx, edx; lpDatabaseName
0x140006b4c  mov     r8d, ebx; dwDesiredAccess
0x140006b4f  xor     ecx, ecx; lpMachineName
0x140006b51  xor     bpl, bpl
0x140006b54  call    cs:__imp_OpenSCManagerW
0x140006b5a  mov     rsi, rax
0x140006b5d  test    rax, rax
0x140006b60  jz      loc_140006BED
0x140006b66  mov     r8d, ebx; dwDesiredAccess
0x140006b69  lea     rdx, ServiceName; "Themes"
0x140006b70  mov     rcx, rax; hSCManager
0x140006b73  call    cs:__imp_OpenServiceW
0x140006b79  mov     rdi, rax
0x140006b7c  test    rax, rax
0x140006b7f  jz      short loc_140006BE4
0x140006b81  lea     r9, [rsp+48h+pcbBytesNeeded]; pcbBytesNeeded
0x140006b86  mov     [rsp+48h+pcbBytesNeeded], 0
0x140006b8e  xor     r8d, r8d; cbBufSize
0x140006b91  xor     edx, edx; lpServiceConfig
0x140006b93  mov     rcx, rax; hService
0x140006b96  call    cs:__imp_QueryServiceConfigW
0x140006b9c  mov     edx, [rsp+48h+pcbBytesNeeded]; uBytes
0x140006ba0  xor     ecx, ecx; uFlags
0x140006ba2  call    cs:__imp_LocalAlloc
0x140006ba8  mov     rbx, rax
0x140006bab  test    rax, rax
0x140006bae  jz      short loc_140006BDB
0x140006bb0  mov     r8d, [rsp+48h+pcbBytesNeeded]; cbBufSize
0x140006bb5  lea     r9, [rsp+48h+pcbBytesNeeded]; pcbBytesNeeded
0x140006bba  mov     rdx, rax; lpServiceConfig
0x140006bbd  mov     rcx, rdi; hService
0x140006bc0  call    cs:__imp_QueryServiceConfigW
0x140006bc6  test    eax, eax
0x140006bc8  jz      short loc_140006BD2
0x140006bca  cmp     dword ptr [rbx+4], 2
0x140006bce  setz    bpl
0x140006bd2  mov     rcx, rbx; hMem
0x140006bd5  call    cs:__imp_LocalFree
0x140006bdb  mov     rcx, rdi; hSCObject
0x140006bde  call    cs:__imp_CloseServiceHandle
0x140006be4  mov     rcx, rsi; hSCObject
0x140006be7  call    cs:__imp_CloseServiceHandle
0x140006bed  mov     al, bpl
0x140006bf0  add     rsp, 28h
0x140006bf4  pop     rdi
0x140006bf5  pop     rsi
0x140006bf6  pop     rbp
0x140006bf7  pop     rbx
0x140006bf8  retn
```
