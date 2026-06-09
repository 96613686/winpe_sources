# ServiceControl::UnregisterService(void)

- ea: `0x140003b50`
- end: `0x140003c3f`
- name: `?UnregisterService@ServiceControl@@CAJXZ`
- size: `239`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14000356c`
- `0x14000395c`

## callees

- `0x140003b50`
- `0x140003f34`
- `0x1400137e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140003b84`
- `KERNEL32!GetLastError` at `0x140003be7`
- `KERNEL32!GetLastError` at `0x140003b84`
- `KERNEL32!GetLastError` at `0x140003be7`
- `ADVAPI32!DeleteService` at `0x140003bdd`
- `ADVAPI32!DeleteService` at `0x140003bdd`
- `ADVAPI32!QueryServiceStatus` at `0x140003bc7`
- `ADVAPI32!QueryServiceStatus` at `0x140003bc7`
- `ADVAPI32!OpenServiceW` at `0x140003bad`
- `ADVAPI32!OpenServiceW` at `0x140003bad`
- `ADVAPI32!OpenSCManagerW` at `0x140003b76`
- `ADVAPI32!OpenSCManagerW` at `0x140003b76`
- `ADVAPI32!CloseServiceHandle` at `0x140003c11`
- `ADVAPI32!CloseServiceHandle` at `0x140003c1a`
- `ADVAPI32!CloseServiceHandle` at `0x140003c11`
- `ADVAPI32!CloseServiceHandle` at `0x140003c1a`

## string_xrefs

- `0x140003ba3`: `VsStandardCollectorService170`

## pseudocode

```c
__int64 ServiceControl::UnregisterService(void)
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rdi
  signed int v2; // eax
  unsigned int v3; // esi
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rbx
  signed int LastError; // eax
  struct _SERVICE_STATUS ServiceStatus; // [rsp+28h] [rbp-30h] BYREF

  v0 = OpenSCManagerW(0, 0, 1u);
  v1 = v0;
  if ( v0 )
  {
    v4 = OpenServiceW(v0, L"VsStandardCollectorService170", 0x10004u);
    v5 = v4;
    if ( v4 )
    {
      if ( QueryServiceStatus(v4, &ServiceStatus) )
      {
        v3 = 0;
        if ( ServiceStatus.dwCurrentState != 1 )
        {
          v3 = 1;
          goto LABEL_16;
        }
        if ( DeleteService(v5) )
        {
          ServiceControl::OnUnregister();
          goto LABEL_16;
        }
      }
      LastError = GetLastError();
      v3 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v3 = LastError;
    }
    else
    {
      v3 = 0;
    }
    if ( !v5 )
    {
LABEL_17:
      CloseServiceHandle(v1);
      return v3;
    }
LABEL_16:
    CloseServiceHandle(v5);
    goto LABEL_17;
  }
  v2 = GetLastError();
  v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v2 <= 0 )
    return (unsigned int)v2;
  return v3;
}

```

## disassembly

```asm
0x140003b50  mov     [rsp+arg_0], rbx
0x140003b55  mov     [rsp+arg_8], rsi
0x140003b5a  push    rdi
0x140003b5b  sub     rsp, 50h
0x140003b5f  mov     rax, cs:__security_cookie
0x140003b66  xor     rax, rsp
0x140003b69  mov     [rsp+58h+var_10], rax
0x140003b6e  xor     edx, edx; lpDatabaseName
0x140003b70  xor     ecx, ecx; lpMachineName
0x140003b72  lea     r8d, [rdx+1]; dwDesiredAccess
0x140003b76  call    cs:__imp_OpenSCManagerW
0x140003b7c  mov     rdi, rax
0x140003b7f  test    rax, rax
0x140003b82  jnz     short loc_140003B9D
0x140003b84  call    cs:__imp_GetLastError
0x140003b8a  movzx   esi, ax
0x140003b8d  or      esi, 80070000h
0x140003b93  test    eax, eax
0x140003b95  cmovle  esi, eax
0x140003b98  jmp     loc_140003C20
0x140003b9d  mov     r8d, 10004h; dwDesiredAccess
0x140003ba3  lea     rdx, ?WZ_SERVICENAME@@3QBGB; "VsStandardCollectorService170"
0x140003baa  mov     rcx, rdi; hSCManager
0x140003bad  call    cs:__imp_OpenServiceW
0x140003bb3  mov     rbx, rax
0x140003bb6  test    rax, rax
0x140003bb9  jnz     short loc_140003BBF
0x140003bbb  xor     esi, esi
0x140003bbd  jmp     short loc_140003BFB
0x140003bbf  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x140003bc4  mov     rcx, rbx; hService
0x140003bc7  call    cs:__imp_QueryServiceStatus
0x140003bcd  test    eax, eax
0x140003bcf  jz      short loc_140003BE7
0x140003bd1  xor     esi, esi
0x140003bd3  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 1
0x140003bd8  jnz     short loc_140003C09
0x140003bda  mov     rcx, rbx; hService
0x140003bdd  call    cs:__imp_DeleteService
0x140003be3  test    eax, eax
0x140003be5  jnz     short loc_140003C02
0x140003be7  call    cs:__imp_GetLastError
0x140003bed  movzx   esi, ax
0x140003bf0  or      esi, 80070000h
0x140003bf6  test    eax, eax
0x140003bf8  cmovle  esi, eax
0x140003bfb  test    rbx, rbx
0x140003bfe  jz      short loc_140003C17
0x140003c00  jmp     short loc_140003C0E
0x140003c02  call    ?OnUnregister@ServiceControl@@CAXXZ; ServiceControl::OnUnregister(void)
0x140003c07  jmp     short loc_140003C0E
0x140003c09  mov     esi, 1
0x140003c0e  mov     rcx, rbx; hSCObject
0x140003c11  call    cs:__imp_CloseServiceHandle
0x140003c17  mov     rcx, rdi; hSCObject
0x140003c1a  call    cs:__imp_CloseServiceHandle
0x140003c20  mov     eax, esi
0x140003c22  mov     rcx, [rsp+58h+var_10]
0x140003c27  xor     rcx, rsp; StackCookie
0x140003c2a  call    __security_check_cookie
0x140003c2f  mov     rbx, [rsp+58h+arg_0]
0x140003c34  mov     rsi, [rsp+58h+arg_8]
0x140003c39  add     rsp, 50h
0x140003c3d  pop     rdi
0x140003c3e  retn
```
