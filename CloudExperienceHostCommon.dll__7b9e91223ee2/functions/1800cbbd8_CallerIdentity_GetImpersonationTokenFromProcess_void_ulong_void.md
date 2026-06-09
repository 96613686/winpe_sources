# CallerIdentity::GetImpersonationTokenFromProcess(void *,ulong,void * *)

- ea: `0x1800cbbd8`
- end: `0x1800cbc70`
- name: `?GetImpersonationTokenFromProcess@CallerIdentity@@YAJPEAXKPEAPEAX@Z`
- size: `152`
- prototype: `int(CallerIdentity *__hidden this, void *, unsigned int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800cbb44`

## callees

- `0x1800cbbd8`
- `0x1800cbce4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800cbbff`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800cbbff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cbc5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cbc5d`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800cbc30`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800cbc30`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetImpersonationTokenFromProcess(
        CallerIdentity *this,
        void *a2,
        void **a3,
        void **a4)
{
  int Error; // ebx
  char *v6; // rcx
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  *a3 = 0;
  TokenHandle = 0;
  if ( OpenProcessToken(this, 0xEu, &TokenHandle) || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    if ( DuplicateTokenEx(TokenHandle, 0xCu, 0, SecurityImpersonation, TokenImpersonation, a3) )
      Error = 0;
    else
      Error = ResultFromKnownLastError();
  }
  v6 = (char *)TokenHandle;
  TokenHandle = 0;
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800cbbd8  mov     [rsp+arg_0], rbx
0x1800cbbdd  push    rdi
0x1800cbbde  sub     rsp, 30h
0x1800cbbe2  mov     rdi, r8
0x1800cbbe5  mov     qword ptr [r8], 0
0x1800cbbec  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x1800cbbf1  mov     [rsp+38h+TokenHandle], 0
0x1800cbbfa  mov     edx, 0Eh; DesiredAccess
0x1800cbbff  call    cs:__imp_OpenProcessToken
0x1800cbc05  test    eax, eax
0x1800cbc07  jnz     short loc_1800CBC14
0x1800cbc09  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800cbc0e  mov     ebx, eax
0x1800cbc10  test    eax, eax
0x1800cbc12  js      short loc_1800CBC45
0x1800cbc14  mov     rcx, [rsp+38h+TokenHandle]; hExistingToken
0x1800cbc19  mov     r9d, 2; ImpersonationLevel
0x1800cbc1f  mov     [rsp+38h+phNewToken], rdi; phNewToken
0x1800cbc24  xor     r8d, r8d; lpTokenAttributes
0x1800cbc27  mov     [rsp+38h+TokenType], r9d; TokenType
0x1800cbc2c  lea     edx, [r9+0Ah]; dwDesiredAccess
0x1800cbc30  call    cs:__imp_DuplicateTokenEx
0x1800cbc36  test    eax, eax
0x1800cbc38  jz      short loc_1800CBC3E
0x1800cbc3a  xor     ebx, ebx
0x1800cbc3c  jmp     short loc_1800CBC45
0x1800cbc3e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800cbc43  mov     ebx, eax
0x1800cbc45  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x1800cbc4a  mov     [rsp+38h+TokenHandle], 0
0x1800cbc53  lea     rdx, [rcx-1]
0x1800cbc57  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800cbc5b  ja      short loc_1800CBC63
0x1800cbc5d  call    cs:__imp_CloseHandle
0x1800cbc63  mov     eax, ebx
0x1800cbc65  mov     rbx, [rsp+38h+arg_0]
0x1800cbc6a  add     rsp, 30h
0x1800cbc6e  pop     rdi
0x1800cbc6f  retn
```
