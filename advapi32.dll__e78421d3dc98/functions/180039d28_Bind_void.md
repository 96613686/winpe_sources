# Bind(void)

- ea: `0x180039d28`
- end: `0x180039e55`
- name: `?Bind@@YAKXZ`
- size: `301`
- prototype: `unsigned int(void)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800367f0`
- `0x180042db4`
- `0x180043250`
- `0x1800432e0`

## callees

- `0x180037f10`
- `0x180039d28`
- `0x180065090`

## import_xrefs

- `KERNELBASE!Sleep` at `0x180039dfa`
- `KERNELBASE!Sleep` at `0x180039dfa`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180039d86`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180039d86`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180039deb`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180039deb`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180039d64`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180039d64`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180039e1f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180039e37`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180039e1f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180039e37`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180039da5`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180039da5`
- `KERNEL32!GetLastError` at `0x180039e14`
- `KERNEL32!GetLastError` at `0x180039e27`
- `KERNEL32!GetLastError` at `0x180039e14`
- `KERNEL32!GetLastError` at `0x180039e27`

## pseudocode

```c
__int64 Bind(void)
{
  __int64 result; // rax
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rdi
  SC_HANDLE v3; // rsi
  int v4; // ebx
  DWORD v5; // ebp
  void **v6; // rcx
  DWORD LastError; // ebx
  DWORD v8; // edx
  DWORD BindingHandle; // eax
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-58h] BYREF

  result = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( ghRpc )
    return result;
  v1 = OpenSCManagerW(0, 0, 5u);
  v2 = v1;
  if ( !v1 || (v3 = OpenServiceW(v1, L"appmgmt", 0x14u)) == 0 )
  {
    LastError = GetLastError();
    if ( v2 )
      goto LABEL_22;
    return LastError;
  }
  v4 = 0;
  v5 = 100;
  while ( 1 )
  {
    if ( !QueryServiceStatus(v3, &ServiceStatus) )
    {
LABEL_18:
      BindingHandle = GetLastError();
      goto LABEL_19;
    }
    if ( ServiceStatus.dwCurrentState == 1 )
    {
      if ( !StartServiceW(v3, 0, 0) )
        goto LABEL_18;
      goto LABEL_15;
    }
    if ( ServiceStatus.dwCurrentState == 2 )
    {
      v8 = ServiceStatus.dwWaitHint / 0x64;
      if ( ServiceStatus.dwWaitHint / 0x64 >= v5 )
        v8 = v5;
      v5 = v8;
      goto LABEL_15;
    }
    if ( ServiceStatus.dwCurrentState != 3 )
      break;
LABEL_15:
    Sleep(0x64u);
    if ( ++v4 > v5 )
    {
      LastError = 1053;
      goto LABEL_20;
    }
  }
  if ( ServiceStatus.dwCurrentState != 4 )
  {
    LastError = 1052;
    goto LABEL_20;
  }
  BindingHandle = GetBindingHandle(v6);
LABEL_19:
  LastError = BindingHandle;
LABEL_20:
  CloseServiceHandle(v3);
LABEL_22:
  CloseServiceHandle(v2);
  return LastError;
}

```

## disassembly

```asm
0x180039d28  push    rbx
0x180039d2a  push    rbp
0x180039d2b  push    rsi
0x180039d2c  push    rdi
0x180039d2d  sub     rsp, 58h
0x180039d31  mov     rax, cs:__security_cookie
0x180039d38  xor     rax, rsp
0x180039d3b  mov     [rsp+78h+var_38], rax
0x180039d40  xorps   xmm0, xmm0
0x180039d43  xor     eax, eax
0x180039d45  cmp     cs:?ghRpc@@3PEAXEA, rax; void * ghRpc
0x180039d4c  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x180039d51  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x180039d56  jnz     loc_180039E3F
0x180039d5c  xor     edx, edx; lpDatabaseName
0x180039d5e  lea     r8d, [rax+5]; dwDesiredAccess
0x180039d62  xor     ecx, ecx; lpMachineName
0x180039d64  call    cs:__imp_OpenSCManagerW
0x180039d6a  mov     rdi, rax
0x180039d6d  test    rax, rax
0x180039d70  jz      loc_180039E27
0x180039d76  mov     r8d, 14h; dwDesiredAccess
0x180039d7c  lea     rdx, aAppmgmt; "appmgmt"
0x180039d83  mov     rcx, rax; hSCManager
0x180039d86  call    cs:__imp_OpenServiceW
0x180039d8c  mov     rsi, rax
0x180039d8f  test    rax, rax
0x180039d92  jz      loc_180039E27
0x180039d98  xor     ebx, ebx
0x180039d9a  lea     ebp, [rbx+64h]
0x180039d9d  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x180039da2  mov     rcx, rsi; hService
0x180039da5  call    cs:__imp_QueryServiceStatus
0x180039dab  test    eax, eax
0x180039dad  jz      short loc_180039E14
0x180039daf  mov     eax, [rsp+78h+ServiceStatus.dwCurrentState]
0x180039db3  sub     eax, 1
0x180039db6  jz      short loc_180039DE3
0x180039db8  sub     eax, 1
0x180039dbb  jz      short loc_180039DCE
0x180039dbd  sub     eax, 1
0x180039dc0  jz      short loc_180039DF5
0x180039dc2  cmp     eax, 1
0x180039dc5  jz      short loc_180039E0D
0x180039dc7  mov     ebx, 41Ch
0x180039dcc  jmp     short loc_180039E1C
0x180039dce  mov     eax, 51EB851Fh
0x180039dd3  mul     [rsp+78h+ServiceStatus.dwWaitHint]
0x180039dd7  shr     edx, 5
0x180039dda  cmp     edx, ebp
0x180039ddc  cmovnb  edx, ebp
0x180039ddf  mov     ebp, edx
0x180039de1  jmp     short loc_180039DF5
0x180039de3  xor     r8d, r8d; lpServiceArgVectors
0x180039de6  xor     edx, edx; dwNumServiceArgs
0x180039de8  mov     rcx, rsi; hService
0x180039deb  call    cs:__imp_StartServiceW
0x180039df1  test    eax, eax
0x180039df3  jz      short loc_180039E14
0x180039df5  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180039dfa  call    cs:__imp_Sleep
0x180039e00  inc     ebx
0x180039e02  cmp     ebx, ebp
0x180039e04  jbe     short loc_180039D9D
0x180039e06  mov     ebx, 41Dh
0x180039e0b  jmp     short loc_180039E1C
0x180039e0d  call    ?GetBindingHandle@@YAKPEAPEAX@Z; GetBindingHandle(void * *)
0x180039e12  jmp     short loc_180039E1A
0x180039e14  call    cs:__imp_GetLastError
0x180039e1a  mov     ebx, eax
0x180039e1c  mov     rcx, rsi; hSCObject
0x180039e1f  call    cs:__imp_CloseServiceHandle
0x180039e25  jmp     short loc_180039E34
0x180039e27  call    cs:__imp_GetLastError
0x180039e2d  mov     ebx, eax
0x180039e2f  test    rdi, rdi
0x180039e32  jz      short loc_180039E3D
0x180039e34  mov     rcx, rdi; hSCObject
0x180039e37  call    cs:__imp_CloseServiceHandle
0x180039e3d  mov     eax, ebx
0x180039e3f  mov     rcx, [rsp+78h+var_38]
0x180039e44  xor     rcx, rsp; StackCookie
0x180039e47  call    __security_check_cookie
0x180039e4c  add     rsp, 58h
0x180039e50  pop     rdi
0x180039e51  pop     rsi
0x180039e52  pop     rbp
0x180039e53  pop     rbx
0x180039e54  retn
```
