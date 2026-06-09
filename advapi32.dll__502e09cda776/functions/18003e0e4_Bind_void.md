# Bind(void)

- ea: `0x18003e0e4`
- end: `0x18003e248`
- name: `?Bind@@YAKXZ`
- size: `356`
- prototype: `unsigned int(void)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18003a788`
- `0x180048230`
- `0x180048740`
- `0x1800487d0`

## callees

- `0x18003c0c0`
- `0x18003e0e4`
- `0x1800720b0`

## import_xrefs

- `KERNELBASE!Sleep` at `0x18003e1ce`
- `KERNELBASE!Sleep` at `0x18003e1ce`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18003e148`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18003e148`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18003e1b9`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18003e1b9`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18003e120`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18003e120`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003e1ff`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003e223`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003e1ff`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003e223`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18003e16d`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18003e16d`
- `KERNEL32!GetLastError` at `0x18003e1ee`
- `KERNEL32!GetLastError` at `0x18003e20d`
- `KERNEL32!GetLastError` at `0x18003e1ee`
- `KERNEL32!GetLastError` at `0x18003e20d`

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
0x18003e0e4  push    rbx
0x18003e0e6  push    rbp
0x18003e0e7  push    rsi
0x18003e0e8  push    rdi
0x18003e0e9  sub     rsp, 58h
0x18003e0ed  mov     rax, cs:__security_cookie
0x18003e0f4  xor     rax, rsp
0x18003e0f7  mov     [rsp+78h+var_38], rax
0x18003e0fc  xorps   xmm0, xmm0
0x18003e0ff  xor     eax, eax
0x18003e101  cmp     cs:?ghRpc@@3PEAXEA, rax; void * ghRpc
0x18003e108  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x18003e10d  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x18003e112  jnz     loc_18003E231
0x18003e118  xor     edx, edx; lpDatabaseName
0x18003e11a  lea     r8d, [rax+5]; dwDesiredAccess
0x18003e11e  xor     ecx, ecx; lpMachineName
0x18003e120  call    cs:__imp_OpenSCManagerW
0x18003e127  nop     dword ptr [rax+rax+00h]
0x18003e12c  mov     rdi, rax
0x18003e12f  test    rax, rax
0x18003e132  jz      loc_18003E20D
0x18003e138  mov     r8d, 14h; dwDesiredAccess
0x18003e13e  lea     rdx, aAppmgmt; "appmgmt"
0x18003e145  mov     rcx, rax; hSCManager
0x18003e148  call    cs:__imp_OpenServiceW
0x18003e14f  nop     dword ptr [rax+rax+00h]
0x18003e154  mov     rsi, rax
0x18003e157  test    rax, rax
0x18003e15a  jz      loc_18003E20D
0x18003e160  xor     ebx, ebx
0x18003e162  lea     ebp, [rbx+64h]
0x18003e165  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x18003e16a  mov     rcx, rsi; hService
0x18003e16d  call    cs:__imp_QueryServiceStatus
0x18003e174  nop     dword ptr [rax+rax+00h]
0x18003e179  test    eax, eax
0x18003e17b  jz      short loc_18003E1EE
0x18003e17d  mov     eax, [rsp+78h+ServiceStatus.dwCurrentState]
0x18003e181  sub     eax, 1
0x18003e184  jz      short loc_18003E1B1
0x18003e186  sub     eax, 1
0x18003e189  jz      short loc_18003E19C
0x18003e18b  sub     eax, 1
0x18003e18e  jz      short loc_18003E1C9
0x18003e190  cmp     eax, 1
0x18003e193  jz      short loc_18003E1E7
0x18003e195  mov     ebx, 41Ch
0x18003e19a  jmp     short loc_18003E1FC
0x18003e19c  mov     eax, 51EB851Fh
0x18003e1a1  mul     [rsp+78h+ServiceStatus.dwWaitHint]
0x18003e1a5  shr     edx, 5
0x18003e1a8  cmp     edx, ebp
0x18003e1aa  cmovnb  edx, ebp
0x18003e1ad  mov     ebp, edx
0x18003e1af  jmp     short loc_18003E1C9
0x18003e1b1  xor     r8d, r8d; lpServiceArgVectors
0x18003e1b4  xor     edx, edx; dwNumServiceArgs
0x18003e1b6  mov     rcx, rsi; hService
0x18003e1b9  call    cs:__imp_StartServiceW
0x18003e1c0  nop     dword ptr [rax+rax+00h]
0x18003e1c5  test    eax, eax
0x18003e1c7  jz      short loc_18003E1EE
0x18003e1c9  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18003e1ce  call    cs:__imp_Sleep
0x18003e1d5  nop     dword ptr [rax+rax+00h]
0x18003e1da  inc     ebx
0x18003e1dc  cmp     ebx, ebp
0x18003e1de  jbe     short loc_18003E165
0x18003e1e0  mov     ebx, 41Dh
0x18003e1e5  jmp     short loc_18003E1FC
0x18003e1e7  call    ?GetBindingHandle@@YAKPEAPEAX@Z; GetBindingHandle(void * *)
0x18003e1ec  jmp     short loc_18003E1FA
0x18003e1ee  call    cs:__imp_GetLastError
0x18003e1f5  nop     dword ptr [rax+rax+00h]
0x18003e1fa  mov     ebx, eax
0x18003e1fc  mov     rcx, rsi; hSCObject
0x18003e1ff  call    cs:__imp_CloseServiceHandle
0x18003e206  nop     dword ptr [rax+rax+00h]
0x18003e20b  jmp     short loc_18003E220
0x18003e20d  call    cs:__imp_GetLastError
0x18003e214  nop     dword ptr [rax+rax+00h]
0x18003e219  mov     ebx, eax
0x18003e21b  test    rdi, rdi
0x18003e21e  jz      short loc_18003E22F
0x18003e220  mov     rcx, rdi; hSCObject
0x18003e223  call    cs:__imp_CloseServiceHandle
0x18003e22a  nop     dword ptr [rax+rax+00h]
0x18003e22f  mov     eax, ebx
0x18003e231  mov     rcx, [rsp+78h+var_38]
0x18003e236  xor     rcx, rsp; StackCookie
0x18003e239  call    __security_check_cookie
0x18003e23e  add     rsp, 58h
0x18003e242  pop     rdi
0x18003e243  pop     rsi
0x18003e244  pop     rbp
0x18003e245  pop     rbx
0x18003e246  retn
```
