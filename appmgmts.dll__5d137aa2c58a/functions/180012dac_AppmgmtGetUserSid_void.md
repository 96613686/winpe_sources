# AppmgmtGetUserSid(void *)

- ea: `0x180012dac`
- end: `0x180012ed5`
- name: `?AppmgmtGetUserSid@@YAPEAXPEAX@Z`
- size: `297`
- prototype: `void *__fastcall(void *)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e8e8`
- `0x1800114b4`
- `0x18001b4e0`

## callees

- `0x1800016d0`
- `0x180012dac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012ded`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012ded`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180012e27`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180012e27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180012e17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180012e17`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180012e00`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180012e00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012e0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012e0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012e65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012e65`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180012e9c`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180012e9c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180012e54`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180012e54`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180012e77`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180012e77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012ea9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012ea9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012e84`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012e84`

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
  void *TokenHandle; // [rsp+38h] [rbp-21h] BYREF
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
0x180012dac  mov     [rsp-8+arg_8], rbx
0x180012db1  mov     [rsp-8+arg_10], rdi
0x180012db6  push    rbp
0x180012db7  lea     rbp, [rsp-57h]
0x180012dbc  sub     rsp, 0B0h
0x180012dc3  mov     rax, cs:__security_cookie
0x180012dca  xor     rax, rsp
0x180012dcd  mov     [rbp+57h+var_10], rax
0x180012dd1  mov     [rbp+57h+TokenHandle], 0
0x180012dd9  mov     rbx, rcx
0x180012ddc  mov     [rbp+57h+nDestinationSidLength], 0
0x180012de3  mov     edi, 1
0x180012de8  test    rcx, rcx
0x180012deb  jnz     short loc_180012E33
0x180012ded  call    cs:__imp_GetCurrentThread
0x180012df3  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180012df7  mov     r8d, edi; OpenAsSelf
0x180012dfa  mov     rcx, rax; ThreadHandle
0x180012dfd  lea     edx, [rbx+8]; DesiredAccess
0x180012e00  call    cs:__imp_OpenThreadToken
0x180012e06  test    eax, eax
0x180012e08  jnz     short loc_180012E37
0x180012e0a  call    cs:__imp_GetLastError
0x180012e10  cmp     eax, 3F0h
0x180012e15  jnz     short loc_180012E6F
0x180012e17  call    cs:__imp_GetCurrentProcess
0x180012e1d  mov     rcx, rax; ProcessHandle
0x180012e20  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180012e24  lea     edx, [rbx+8]; DesiredAccess
0x180012e27  call    cs:__imp_OpenProcessToken
0x180012e2d  test    eax, eax
0x180012e2f  jz      short loc_180012E6F
0x180012e31  jmp     short loc_180012E37
0x180012e33  mov     [rbp+57h+TokenHandle], rbx
0x180012e37  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180012e3b  lea     rax, [rbp+57h+nDestinationSidLength]
0x180012e3f  mov     r9d, 54h ; 'T'; TokenInformationLength
0x180012e45  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x180012e4a  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180012e4e  mov     [rbp+57h+nDestinationSidLength], r9d
0x180012e52  mov     edx, edi; TokenInformationClass
0x180012e54  call    cs:__imp_GetTokenInformation
0x180012e5a  mov     edi, eax
0x180012e5c  test    rbx, rbx
0x180012e5f  jnz     short loc_180012E6B
0x180012e61  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180012e65  call    cs:__imp_CloseHandle
0x180012e6b  test    edi, edi
0x180012e6d  jnz     short loc_180012E73
0x180012e6f  xor     eax, eax
0x180012e71  jmp     short loc_180012EB4
0x180012e73  mov     rcx, [rbp+57h+TokenInformation]; pSid
0x180012e77  call    cs:__imp_GetLengthSid
0x180012e7d  mov     edx, eax; uBytes
0x180012e7f  xor     ecx, ecx; uFlags
0x180012e81  mov     [rbp+57h+nDestinationSidLength], edx
0x180012e84  call    cs:__imp_LocalAlloc
0x180012e8a  mov     rbx, rax
0x180012e8d  test    rax, rax
0x180012e90  jz      short loc_180012EB1
0x180012e92  mov     r8, [rbp+57h+TokenInformation]; pSourceSid
0x180012e96  mov     rdx, rax; pDestinationSid
0x180012e99  mov     ecx, [rbp+57h+nDestinationSidLength]; nDestinationSidLength
0x180012e9c  call    cs:__imp_CopySid
0x180012ea2  test    eax, eax
0x180012ea4  jnz     short loc_180012EB1
0x180012ea6  mov     rcx, rbx; hMem
0x180012ea9  call    cs:__imp_LocalFree
0x180012eaf  xor     ebx, ebx
0x180012eb1  mov     rax, rbx
0x180012eb4  mov     rcx, [rbp+57h+var_10]
0x180012eb8  xor     rcx, rsp; StackCookie
0x180012ebb  call    __security_check_cookie
0x180012ec0  lea     r11, [rsp+0B0h+var_s0]
0x180012ec8  mov     rbx, [r11+18h]
0x180012ecc  mov     rdi, [r11+20h]
0x180012ed0  mov     rsp, r11
0x180012ed3  pop     rbp
0x180012ed4  retn
```
