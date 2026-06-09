# CallerIdentity::GetImpersonationTokenFromProcess(void *,ulong,void * *)

- ea: `0x1800f396c`
- end: `0x1800f3a04`
- name: `?GetImpersonationTokenFromProcess@CallerIdentity@@YAJPEAXKPEAPEAX@Z`
- size: `152`
- prototype: `int(CallerIdentity *__hidden this, void *, unsigned int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180144710`

## callees

- `0x1800f396c`
- `0x1800f3a0c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800f3993`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800f3993`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f39f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f39f1`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800f39c4`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800f39c4`

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
0x1800f396c  mov     [rsp+arg_0], rbx
0x1800f3971  push    rdi
0x1800f3972  sub     rsp, 30h
0x1800f3976  mov     rdi, r8
0x1800f3979  mov     qword ptr [r8], 0
0x1800f3980  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x1800f3985  mov     [rsp+38h+TokenHandle], 0
0x1800f398e  mov     edx, 0Eh; DesiredAccess
0x1800f3993  call    cs:__imp_OpenProcessToken
0x1800f3999  test    eax, eax
0x1800f399b  jnz     short loc_1800F39A8
0x1800f399d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800f39a2  mov     ebx, eax
0x1800f39a4  test    eax, eax
0x1800f39a6  js      short loc_1800F39D9
0x1800f39a8  mov     rcx, [rsp+38h+TokenHandle]; hExistingToken
0x1800f39ad  mov     r9d, 2; ImpersonationLevel
0x1800f39b3  mov     [rsp+38h+phNewToken], rdi; phNewToken
0x1800f39b8  xor     r8d, r8d; lpTokenAttributes
0x1800f39bb  mov     [rsp+38h+TokenType], r9d; TokenType
0x1800f39c0  lea     edx, [r9+0Ah]; dwDesiredAccess
0x1800f39c4  call    cs:__imp_DuplicateTokenEx
0x1800f39ca  test    eax, eax
0x1800f39cc  jz      short loc_1800F39D2
0x1800f39ce  xor     ebx, ebx
0x1800f39d0  jmp     short loc_1800F39D9
0x1800f39d2  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800f39d7  mov     ebx, eax
0x1800f39d9  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x1800f39de  mov     [rsp+38h+TokenHandle], 0
0x1800f39e7  lea     rdx, [rcx-1]
0x1800f39eb  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800f39ef  ja      short loc_1800F39F7
0x1800f39f1  call    cs:__imp_CloseHandle
0x1800f39f7  mov     eax, ebx
0x1800f39f9  mov     rbx, [rsp+38h+arg_0]
0x1800f39fe  add     rsp, 30h
0x1800f3a02  pop     rdi
0x1800f3a03  retn
```
