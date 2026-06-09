# CallerIdentity::GetImpersonationTokenFromProcess(void *,ulong,void * *)

- ea: `0x1801af64c`
- end: `0x1801af6e4`
- name: `?GetImpersonationTokenFromProcess@CallerIdentity@@YAJPEAXKPEAPEAX@Z`
- size: `152`
- prototype: `int(CallerIdentity *__hidden this, void *, unsigned int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801afaa8`

## callees

- `0x1801af64c`
- `0x1801afa28`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801af6d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801af6d1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801af673`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801af673`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1801af6a4`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1801af6a4`

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
0x1801af64c  mov     [rsp+arg_0], rbx
0x1801af651  push    rdi
0x1801af652  sub     rsp, 30h
0x1801af656  mov     rdi, r8
0x1801af659  mov     qword ptr [r8], 0
0x1801af660  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x1801af665  mov     [rsp+38h+TokenHandle], 0
0x1801af66e  mov     edx, 0Eh; DesiredAccess
0x1801af673  call    cs:__imp_OpenProcessToken
0x1801af679  test    eax, eax
0x1801af67b  jnz     short loc_1801AF688
0x1801af67d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1801af682  mov     ebx, eax
0x1801af684  test    eax, eax
0x1801af686  js      short loc_1801AF6B9
0x1801af688  mov     rcx, [rsp+38h+TokenHandle]; hExistingToken
0x1801af68d  mov     r9d, 2; ImpersonationLevel
0x1801af693  mov     [rsp+38h+phNewToken], rdi; phNewToken
0x1801af698  xor     r8d, r8d; lpTokenAttributes
0x1801af69b  mov     [rsp+38h+TokenType], r9d; TokenType
0x1801af6a0  lea     edx, [r9+0Ah]; dwDesiredAccess
0x1801af6a4  call    cs:__imp_DuplicateTokenEx
0x1801af6aa  test    eax, eax
0x1801af6ac  jz      short loc_1801AF6B2
0x1801af6ae  xor     ebx, ebx
0x1801af6b0  jmp     short loc_1801AF6B9
0x1801af6b2  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1801af6b7  mov     ebx, eax
0x1801af6b9  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x1801af6be  mov     [rsp+38h+TokenHandle], 0
0x1801af6c7  lea     rdx, [rcx-1]
0x1801af6cb  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1801af6cf  ja      short loc_1801AF6D7
0x1801af6d1  call    cs:__imp_CloseHandle
0x1801af6d7  mov     eax, ebx
0x1801af6d9  mov     rbx, [rsp+38h+arg_0]
0x1801af6de  add     rsp, 30h
0x1801af6e2  pop     rdi
0x1801af6e3  retn
```
