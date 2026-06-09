# I_PinCacheGetLuid

- ea: `0x18002a20c`
- end: `0x18002a307`
- name: `I_PinCacheGetLuid`
- size: `251`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002a310`
- `0x18002a368`

## callees

- `0x18002a20c`
- `0x18002cfa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a272`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a29d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a272`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a29d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002a281`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002a281`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002a268`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002a268`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002a252`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002a252`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002a293`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002a293`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a2de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a2de`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002a2c2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002a2c2`

## pseudocode

```c
__int64 __fastcall I_PinCacheGetLuid(_QWORD *a1)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp-50h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-48h] BYREF
  _OWORD TokenInformation[3]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v9; // [rsp+70h] [rbp-10h]

  TokenHandle = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  v9 = 0;
  ReturnLength = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
      goto LABEL_7;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      goto LABEL_4;
  }
  if ( GetTokenInformation(TokenHandle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength) )
  {
    LastError = 0;
    *a1 = *((_QWORD *)&TokenInformation[0] + 1);
  }
  else
  {
LABEL_4:
    LastError = GetLastError();
  }
LABEL_7:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x18002a20c  mov     [rsp-8+arg_8], rbx
0x18002a211  mov     [rsp-8+arg_10], rdi
0x18002a216  push    rbp
0x18002a217  mov     rbp, rsp
0x18002a21a  sub     rsp, 80h
0x18002a221  mov     rax, cs:__security_cookie
0x18002a228  xor     rax, rsp
0x18002a22b  mov     [rbp+var_8], rax
0x18002a22f  xorps   xmm0, xmm0
0x18002a232  mov     [rbp+TokenHandle], 0
0x18002a23a  xor     eax, eax
0x18002a23c  mov     rdi, rcx
0x18002a23f  movups  [rbp+TokenInformation], xmm0
0x18002a243  mov     [rbp+var_10], rax
0x18002a247  movups  [rbp+var_30], xmm0
0x18002a24b  mov     [rbp+var_48], eax
0x18002a24e  movups  [rbp+var_20], xmm0
0x18002a252  call    cs:__imp_GetCurrentThread
0x18002a258  mov     edx, 8; DesiredAccess
0x18002a25d  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18002a261  mov     rcx, rax; ThreadHandle
0x18002a264  lea     r8d, [rdx-7]; OpenAsSelf
0x18002a268  call    cs:__imp_OpenThreadToken
0x18002a26e  test    eax, eax
0x18002a270  jnz     short loc_18002A2A7
0x18002a272  call    cs:__imp_GetLastError
0x18002a278  mov     ebx, eax
0x18002a27a  cmp     eax, 3F0h
0x18002a27f  jnz     short loc_18002A2D5
0x18002a281  call    cs:__imp_GetCurrentProcess
0x18002a287  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18002a28b  mov     edx, 8; DesiredAccess
0x18002a290  mov     rcx, rax; ProcessHandle
0x18002a293  call    cs:__imp_OpenProcessToken
0x18002a299  test    eax, eax
0x18002a29b  jnz     short loc_18002A2A7
0x18002a29d  call    cs:__imp_GetLastError
0x18002a2a3  mov     ebx, eax
0x18002a2a5  jmp     short loc_18002A2D5
0x18002a2a7  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002a2ab  lea     rax, [rbp+var_48]
0x18002a2af  mov     r9d, 38h ; '8'; TokenInformationLength
0x18002a2b5  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x18002a2ba  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18002a2be  lea     edx, [r9-2Eh]; TokenInformationClass
0x18002a2c2  call    cs:__imp_GetTokenInformation
0x18002a2c8  test    eax, eax
0x18002a2ca  jz      short loc_18002A29D
0x18002a2cc  mov     rax, qword ptr [rbp+TokenInformation+8]
0x18002a2d0  xor     ebx, ebx
0x18002a2d2  mov     [rdi], rax
0x18002a2d5  mov     rcx, [rbp+TokenHandle]; hObject
0x18002a2d9  test    rcx, rcx
0x18002a2dc  jz      short loc_18002A2E4
0x18002a2de  call    cs:__imp_CloseHandle
0x18002a2e4  mov     eax, ebx
0x18002a2e6  mov     rcx, [rbp+var_8]
0x18002a2ea  xor     rcx, rsp; StackCookie
0x18002a2ed  call    __security_check_cookie
0x18002a2f2  lea     r11, [rsp+80h+var_s0]
0x18002a2fa  mov     rbx, [r11+18h]
0x18002a2fe  mov     rdi, [r11+20h]
0x18002a302  mov     rsp, r11
0x18002a305  pop     rbp
0x18002a306  retn
```
