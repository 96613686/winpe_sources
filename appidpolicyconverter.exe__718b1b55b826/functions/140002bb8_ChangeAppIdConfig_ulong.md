# ChangeAppIdConfig(ulong)

- ea: `0x140002bb8`
- end: `0x140002c6b`
- name: `?ChangeAppIdConfig@@YAKK@Z`
- size: `179`
- prototype: `__int64 __fastcall(DWORD dwStartType)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x14000458c`

## callees

- `0x140002bb8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002bd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002c01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002c46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002bd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002c01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002c46`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140002bcb`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140002bcb`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140002bf3`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140002bf3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140002c51`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140002c5a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140002c51`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140002c5a`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x140002c3c`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x140002c3c`

## pseudocode

```c
__int64 __fastcall ChangeAppIdConfig(DWORD dwStartType)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rdi
  DWORD LastError; // ebx
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rsi

  v2 = OpenSCManagerW(0, 0, 1u);
  v3 = v2;
  if ( v2 )
  {
    v5 = OpenServiceW(v2, L"AppID", 2u);
    v6 = v5;
    if ( v5 )
    {
      LastError = 0;
      if ( !ChangeServiceConfigW(v5, 0xFFFFFFFF, dwStartType, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
        LastError = GetLastError();
      CloseServiceHandle(v6);
    }
    else
    {
      LastError = GetLastError();
    }
    CloseServiceHandle(v3);
  }
  else
  {
    return GetLastError();
  }
  return LastError;
}

```

## disassembly

```asm
0x140002bb8  push    rbx
0x140002bba  push    rbp
0x140002bbb  push    rsi
0x140002bbc  push    rdi
0x140002bbd  sub     rsp, 68h
0x140002bc1  xor     edx, edx; lpDatabaseName
0x140002bc3  mov     ebp, ecx
0x140002bc5  xor     ecx, ecx; lpMachineName
0x140002bc7  lea     r8d, [rdx+1]; dwDesiredAccess
0x140002bcb  call    cs:__imp_OpenSCManagerW
0x140002bd1  mov     rdi, rax
0x140002bd4  test    rax, rax
0x140002bd7  jnz     short loc_140002BE3
0x140002bd9  call    cs:__imp_GetLastError
0x140002bdf  mov     ebx, eax
0x140002be1  jmp     short loc_140002C60
0x140002be3  mov     r8d, 2; dwDesiredAccess
0x140002be9  lea     rdx, ServiceName; "AppID"
0x140002bf0  mov     rcx, rdi; hSCManager
0x140002bf3  call    cs:__imp_OpenServiceW
0x140002bf9  mov     rsi, rax
0x140002bfc  test    rax, rax
0x140002bff  jnz     short loc_140002C0B
0x140002c01  call    cs:__imp_GetLastError
0x140002c07  mov     ebx, eax
0x140002c09  jmp     short loc_140002C57
0x140002c0b  xor     ebx, ebx
0x140002c0d  or      edx, 0FFFFFFFFh; dwServiceType
0x140002c10  mov     [rsp+88h+lpDisplayName], rbx; lpDisplayName
0x140002c15  mov     r9d, edx; dwErrorControl
0x140002c18  mov     [rsp+88h+lpPassword], rbx; lpPassword
0x140002c1d  mov     r8d, ebp; dwStartType
0x140002c20  mov     [rsp+88h+lpServiceStartName], rbx; lpServiceStartName
0x140002c25  mov     rcx, rsi; hService
0x140002c28  mov     [rsp+88h+lpDependencies], rbx; lpDependencies
0x140002c2d  mov     [rsp+88h+lpdwTagId], rbx; lpdwTagId
0x140002c32  mov     [rsp+88h+lpLoadOrderGroup], rbx; lpLoadOrderGroup
0x140002c37  mov     [rsp+88h+lpBinaryPathName], rbx; lpBinaryPathName
0x140002c3c  call    cs:__imp_ChangeServiceConfigW
0x140002c42  test    eax, eax
0x140002c44  jnz     short loc_140002C4E
0x140002c46  call    cs:__imp_GetLastError
0x140002c4c  mov     ebx, eax
0x140002c4e  mov     rcx, rsi; hSCObject
0x140002c51  call    cs:__imp_CloseServiceHandle
0x140002c57  mov     rcx, rdi; hSCObject
0x140002c5a  call    cs:__imp_CloseServiceHandle
0x140002c60  mov     eax, ebx
0x140002c62  add     rsp, 68h
0x140002c66  pop     rdi
0x140002c67  pop     rsi
0x140002c68  pop     rbp
0x140002c69  pop     rbx
0x140002c6a  retn
```
