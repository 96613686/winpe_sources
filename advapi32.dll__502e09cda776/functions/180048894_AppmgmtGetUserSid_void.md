# AppmgmtGetUserSid(void *)

- ea: `0x180048894`
- end: `0x180048a00`
- name: `?AppmgmtGetUserSid@@YAPEAXPEAX@Z`
- size: `364`
- prototype: `void *__fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004a2d0`

## callees

- `0x180048894`
- `0x1800720b0`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x18004899c`
- `KERNELBASE!LocalAlloc` at `0x18004899c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800488ee`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800488ee`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180048927`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180048927`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180048911`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180048911`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800488d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800488d5`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800489ba`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800489ba`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180048989`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180048989`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004895a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004895a`
- `KERNEL32!LocalFree` at `0x1800489cd`
- `KERNEL32!LocalFree` at `0x1800489cd`
- `KERNEL32!GetLastError` at `0x1800488fe`
- `KERNEL32!GetLastError` at `0x1800488fe`
- `KERNEL32!CloseHandle` at `0x180048971`
- `KERNEL32!CloseHandle` at `0x180048971`

## pseudocode

```c
void *__fastcall AppmgmtGetUserSid(void *a1)
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  BOOL v4; // edi
  HLOCAL v6; // rax
  void *v7; // rbx
  DWORD nDestinationSidLength; // [rsp+30h] [rbp-29h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-21h] BYREF
  PSID TokenInformation[12]; // [rsp+40h] [rbp-19h] BYREF

  TokenHandle = 0;
  nDestinationSidLength = 0;
  if ( a1 )
  {
    TokenHandle = a1;
  }
  else
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      if ( GetLastError() != 1008 )
        return 0;
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
        return 0;
    }
  }
  nDestinationSidLength = 84;
  v4 = GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x54u, &nDestinationSidLength);
  if ( !a1 )
    CloseHandle(TokenHandle);
  if ( !v4 )
    return 0;
  nDestinationSidLength = GetLengthSid(TokenInformation[0]);
  v6 = LocalAlloc(0, nDestinationSidLength);
  v7 = v6;
  if ( v6 )
  {
    if ( !CopySid(nDestinationSidLength, v6, TokenInformation[0]) )
    {
      LocalFree(v7);
      return 0;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180048894  mov     [rsp-8+arg_8], rbx
0x180048899  mov     [rsp-8+arg_10], rdi
0x18004889e  push    rbp
0x18004889f  lea     rbp, [rsp-57h]
0x1800488a4  sub     rsp, 0B0h
0x1800488ab  mov     rax, cs:__security_cookie
0x1800488b2  xor     rax, rsp
0x1800488b5  mov     [rbp+57h+var_10], rax
0x1800488b9  mov     [rbp+57h+TokenHandle], 0
0x1800488c1  mov     rbx, rcx
0x1800488c4  mov     [rbp+57h+nDestinationSidLength], 0
0x1800488cb  mov     edi, 1
0x1800488d0  test    rcx, rcx
0x1800488d3  jnz     short loc_180048939
0x1800488d5  call    cs:__imp_GetCurrentThread
0x1800488dc  nop     dword ptr [rax+rax+00h]
0x1800488e1  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800488e5  mov     r8d, edi; OpenAsSelf
0x1800488e8  mov     rcx, rax; ThreadHandle
0x1800488eb  lea     edx, [rbx+8]; DesiredAccess
0x1800488ee  call    cs:__imp_OpenThreadToken
0x1800488f5  nop     dword ptr [rax+rax+00h]
0x1800488fa  test    eax, eax
0x1800488fc  jnz     short loc_18004893D
0x1800488fe  call    cs:__imp_GetLastError
0x180048905  nop     dword ptr [rax+rax+00h]
0x18004890a  cmp     eax, 3F0h
0x18004890f  jnz     short loc_180048981
0x180048911  call    cs:__imp_GetCurrentProcess
0x180048918  nop     dword ptr [rax+rax+00h]
0x18004891d  mov     rcx, rax; ProcessHandle
0x180048920  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180048924  lea     edx, [rbx+8]; DesiredAccess
0x180048927  call    cs:__imp_OpenProcessToken
0x18004892e  nop     dword ptr [rax+rax+00h]
0x180048933  test    eax, eax
0x180048935  jz      short loc_180048981
0x180048937  jmp     short loc_18004893D
0x180048939  mov     [rbp+57h+TokenHandle], rbx
0x18004893d  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180048941  lea     rax, [rbp+57h+nDestinationSidLength]
0x180048945  mov     r9d, 54h ; 'T'; TokenInformationLength
0x18004894b  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x180048950  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180048954  mov     [rbp+57h+nDestinationSidLength], r9d
0x180048958  mov     edx, edi; TokenInformationClass
0x18004895a  call    cs:__imp_GetTokenInformation
0x180048961  nop     dword ptr [rax+rax+00h]
0x180048966  mov     edi, eax
0x180048968  test    rbx, rbx
0x18004896b  jnz     short loc_18004897D
0x18004896d  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180048971  call    cs:__imp_CloseHandle
0x180048978  nop     dword ptr [rax+rax+00h]
0x18004897d  test    edi, edi
0x18004897f  jnz     short loc_180048985
0x180048981  xor     eax, eax
0x180048983  jmp     short loc_1800489DE
0x180048985  mov     rcx, [rbp+57h+TokenInformation]; pSid
0x180048989  call    cs:__imp_GetLengthSid
0x180048990  nop     dword ptr [rax+rax+00h]
0x180048995  mov     edx, eax; uBytes
0x180048997  xor     ecx, ecx; uFlags
0x180048999  mov     [rbp+57h+nDestinationSidLength], edx
0x18004899c  call    cs:__imp_LocalAlloc
0x1800489a3  nop     dword ptr [rax+rax+00h]
0x1800489a8  mov     rbx, rax
0x1800489ab  test    rax, rax
0x1800489ae  jz      short loc_1800489DB
0x1800489b0  mov     r8, [rbp+57h+TokenInformation]; pSourceSid
0x1800489b4  mov     rdx, rax; pDestinationSid
0x1800489b7  mov     ecx, [rbp+57h+nDestinationSidLength]; nDestinationSidLength
0x1800489ba  call    cs:__imp_CopySid
0x1800489c1  nop     dword ptr [rax+rax+00h]
0x1800489c6  test    eax, eax
0x1800489c8  jnz     short loc_1800489DB
0x1800489ca  mov     rcx, rbx; hMem
0x1800489cd  call    cs:__imp_LocalFree
0x1800489d4  nop     dword ptr [rax+rax+00h]
0x1800489d9  xor     ebx, ebx
0x1800489db  mov     rax, rbx
0x1800489de  mov     rcx, [rbp+57h+var_10]
0x1800489e2  xor     rcx, rsp; StackCookie
0x1800489e5  call    __security_check_cookie
0x1800489ea  lea     r11, [rsp+0B0h+var_s0]
0x1800489f2  mov     rbx, [r11+18h]
0x1800489f6  mov     rdi, [r11+20h]
0x1800489fa  mov     rsp, r11
0x1800489fd  pop     rbp
0x1800489fe  retn
```
