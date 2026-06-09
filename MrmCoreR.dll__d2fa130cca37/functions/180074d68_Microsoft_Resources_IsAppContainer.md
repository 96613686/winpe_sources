# Microsoft::Resources::IsAppContainer

- ea: `0x180074d68`
- end: `0x180074de6`
- name: `Microsoft::Resources::IsAppContainer`
- size: `126`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007f30`
- `0x1800a5e24`

## callees

- `0x180074d68`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180074d7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180074d7d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180074d90`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180074d90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180074dd3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180074dd3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180074dc0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180074dc0`

## pseudocode

```c
bool Microsoft::Resources::IsAppContainer()
{
  HANDLE CurrentProcess; // rax
  int TokenInformation; // [rsp+40h] [rbp+8h] BYREF
  DWORD ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  TokenInformation = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    ReturnLength = 0;
    if ( !GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
      TokenInformation = 0;
    CloseHandle(TokenHandle);
  }
  return TokenInformation != 0;
}

```

## disassembly

```asm
0x180074d68  sub     rsp, 38h
0x180074d6c  mov     [rsp+38h+TokenInformation], 0
0x180074d74  mov     [rsp+38h+TokenHandle], 0
0x180074d7d  call    cs:__imp_GetCurrentProcess
0x180074d83  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180074d88  mov     edx, 8; DesiredAccess
0x180074d8d  mov     rcx, rax; ProcessHandle
0x180074d90  call    cs:__imp_OpenProcessToken
0x180074d96  test    eax, eax
0x180074d98  jz      short loc_180074DD9
0x180074d9a  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180074d9f  lea     rax, [rsp+38h+arg_8]
0x180074da4  mov     r9d, 4; TokenInformationLength
0x180074daa  mov     [rsp+38h+arg_8], 0
0x180074db2  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180074db7  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180074dbc  lea     edx, [r9+19h]; TokenInformationClass
0x180074dc0  call    cs:__imp_GetTokenInformation
0x180074dc6  test    eax, eax
0x180074dc8  jnz     short loc_180074DCE
0x180074dca  mov     [rsp+38h+TokenInformation], eax
0x180074dce  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180074dd3  call    cs:__imp_CloseHandle
0x180074dd9  cmp     [rsp+38h+TokenInformation], 0
0x180074dde  setnz   al
0x180074de1  add     rsp, 38h
0x180074de5  retn
```
