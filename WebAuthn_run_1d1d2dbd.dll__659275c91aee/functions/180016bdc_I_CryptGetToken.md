# I_CryptGetToken

- ea: `0x180016bdc`
- end: `0x180016c7d`
- name: `I_CryptGetToken`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18013abf4`

## callees

- `0x180016bdc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016c63`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016c63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c4f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180016c0a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180016c47`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180016c0a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180016c47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180016bef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180016c34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180016bef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180016c34`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180016c57`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180016c57`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180016c2a`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180016c2a`

## pseudocode

```c
void *I_CryptGetToken()
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  DWORD v2; // ecx
  HANDLE v3; // rax
  BOOL v4; // ebx
  DWORD v5; // edi
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
    {
      v2 = LastError;
LABEL_7:
      SetLastError(v2);
      return 0;
    }
    if ( !ImpersonateSelf(SecurityImpersonation) )
      return 0;
    v3 = GetCurrentThread();
    v4 = OpenThreadToken(v3, 8u, 1, &TokenHandle);
    v5 = GetLastError();
    RevertToSelf();
    if ( !v4 )
    {
      v2 = v5;
      goto LABEL_7;
    }
  }
  return TokenHandle;
}

```

## disassembly

```asm
0x180016bdc  mov     [rsp+arg_0], rbx
0x180016be1  push    rdi
0x180016be2  sub     rsp, 20h
0x180016be6  mov     [rsp+28h+TokenHandle], 0
0x180016bef  call    cs:__imp_GetCurrentThread
0x180016bf5  mov     ebx, 1
0x180016bfa  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180016bff  mov     rcx, rax; ThreadHandle
0x180016c02  mov     r8d, ebx; OpenAsSelf
0x180016c05  lea     edi, [rbx+7]
0x180016c08  mov     edx, edi; DesiredAccess
0x180016c0a  call    cs:__imp_OpenThreadToken
0x180016c10  test    eax, eax
0x180016c12  jnz     short loc_180016C6D
0x180016c14  call    cs:__imp_GetLastError
0x180016c1a  cmp     eax, 3F0h
0x180016c1f  jz      short loc_180016C25
0x180016c21  mov     ecx, eax
0x180016c23  jmp     short loc_180016C63
0x180016c25  mov     ecx, 2; ImpersonationLevel
0x180016c2a  call    cs:__imp_ImpersonateSelf
0x180016c30  test    eax, eax
0x180016c32  jz      short loc_180016C69
0x180016c34  call    cs:__imp_GetCurrentThread
0x180016c3a  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180016c3f  mov     r8d, ebx; OpenAsSelf
0x180016c42  mov     rcx, rax; ThreadHandle
0x180016c45  mov     edx, edi; DesiredAccess
0x180016c47  call    cs:__imp_OpenThreadToken
0x180016c4d  mov     ebx, eax
0x180016c4f  call    cs:__imp_GetLastError
0x180016c55  mov     edi, eax
0x180016c57  call    cs:__imp_RevertToSelf
0x180016c5d  test    ebx, ebx
0x180016c5f  jnz     short loc_180016C6D
0x180016c61  mov     ecx, edi; dwErrCode
0x180016c63  call    cs:__imp_SetLastError
0x180016c69  xor     eax, eax
0x180016c6b  jmp     short loc_180016C72
0x180016c6d  mov     rax, [rsp+28h+TokenHandle]
0x180016c72  mov     rbx, [rsp+28h+arg_0]
0x180016c77  add     rsp, 20h
0x180016c7b  pop     rdi
0x180016c7c  retn
```
