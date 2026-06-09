# CLockScreen::_s_IsAppContainerProcess(void)

- ea: `0x18003a5bc`
- end: `0x18003a686`
- name: `?_s_IsAppContainerProcess@CLockScreen@@KA_NXZ`
- size: `202`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009320`
- `0x18003feb0`

## callees

- `0x18003a5bc`
- `0x18003aa84`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003a609`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003a609`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003a5c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003a5c8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003a5d8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003a5d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a66a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a673`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a66a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a673`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003a64a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003a64a`

## pseudocode

```c
bool CLockScreen::_s_IsAppContainerProcess(void)
{
  bool v0; // bl
  DWORD CurrentProcessId; // eax
  HANDLE v2; // rdi
  int TokenInformation; // [rsp+40h] [rbp+8h] BYREF
  DWORD ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  v0 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v2 = OpenProcess(0x1000u, 0, CurrentProcessId);
  if ( v2 || (int)ResultFromKnownLastError() >= 0 )
  {
    TokenHandle = 0;
    if ( OpenProcessToken(v2, 8u, &TokenHandle) || (int)ResultFromKnownLastError() >= 0 )
    {
      ReturnLength = 0;
      TokenInformation = 0;
      if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength)
        || (int)ResultFromKnownLastError() >= 0 )
      {
        v0 = TokenInformation != 0;
      }
      CloseHandle(TokenHandle);
    }
    CloseHandle(v2);
  }
  return v0;
}

```

## disassembly

```asm
0x18003a5bc  mov     [rsp+arg_18], rbx
0x18003a5c1  push    rdi
0x18003a5c2  sub     rsp, 30h
0x18003a5c6  xor     bl, bl
0x18003a5c8  call    cs:__imp_GetCurrentProcessId
0x18003a5ce  xor     edx, edx; bInheritHandle
0x18003a5d0  mov     ecx, 1000h; dwDesiredAccess
0x18003a5d5  mov     r8d, eax; dwProcessId
0x18003a5d8  call    cs:__imp_OpenProcess
0x18003a5de  mov     rdi, rax
0x18003a5e1  test    rax, rax
0x18003a5e4  jnz     short loc_18003A5F3
0x18003a5e6  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003a5eb  test    eax, eax
0x18003a5ed  js      loc_18003A679
0x18003a5f3  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18003a5f8  mov     [rsp+38h+TokenHandle], 0
0x18003a601  mov     edx, 8; DesiredAccess
0x18003a606  mov     rcx, rdi; ProcessHandle
0x18003a609  call    cs:__imp_OpenProcessToken
0x18003a60f  test    eax, eax
0x18003a611  jnz     short loc_18003A61C
0x18003a613  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003a618  test    eax, eax
0x18003a61a  js      short loc_18003A670
0x18003a61c  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18003a621  lea     rax, [rsp+38h+arg_8]
0x18003a626  mov     r9d, 4; TokenInformationLength
0x18003a62c  mov     [rsp+38h+arg_8], 0
0x18003a634  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x18003a639  mov     [rsp+38h+TokenInformation], 0
0x18003a641  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18003a646  lea     edx, [r9+19h]; TokenInformationClass
0x18003a64a  call    cs:__imp_GetTokenInformation
0x18003a650  test    eax, eax
0x18003a652  jnz     short loc_18003A65D
0x18003a654  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003a659  test    eax, eax
0x18003a65b  js      short loc_18003A665
0x18003a65d  cmp     [rsp+38h+TokenInformation], 0
0x18003a662  setnz   bl
0x18003a665  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18003a66a  call    cs:__imp_CloseHandle
0x18003a670  mov     rcx, rdi; hObject
0x18003a673  call    cs:__imp_CloseHandle
0x18003a679  mov     al, bl
0x18003a67b  mov     rbx, [rsp+38h+arg_18]
0x18003a680  add     rsp, 30h
0x18003a684  pop     rdi
0x18003a685  retn
```
