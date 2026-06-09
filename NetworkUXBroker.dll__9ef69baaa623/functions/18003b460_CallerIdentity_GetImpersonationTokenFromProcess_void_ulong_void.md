# CallerIdentity::GetImpersonationTokenFromProcess(void *,ulong,void * *)

- ea: `0x18003b460`
- end: `0x18003b4f8`
- name: `?GetImpersonationTokenFromProcess@CallerIdentity@@YAJPEAXKPEAPEAX@Z`
- size: `152`
- prototype: `int(CallerIdentity *__hidden this, void *, unsigned int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003b02c`

## callees

- `0x18003b460`
- `0x18003b8f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003b487`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003b487`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b4e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b4e5`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18003b4b8`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18003b4b8`

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
0x18003b460  mov     [rsp+arg_0], rbx
0x18003b465  push    rdi
0x18003b466  sub     rsp, 30h
0x18003b46a  mov     rdi, r8
0x18003b46d  mov     qword ptr [r8], 0
0x18003b474  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18003b479  mov     [rsp+38h+TokenHandle], 0
0x18003b482  mov     edx, 0Eh; DesiredAccess
0x18003b487  call    cs:__imp_OpenProcessToken
0x18003b48d  test    eax, eax
0x18003b48f  jnz     short loc_18003B49C
0x18003b491  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003b496  mov     ebx, eax
0x18003b498  test    eax, eax
0x18003b49a  js      short loc_18003B4CD
0x18003b49c  mov     rcx, [rsp+38h+TokenHandle]; hExistingToken
0x18003b4a1  mov     r9d, 2; ImpersonationLevel
0x18003b4a7  mov     [rsp+38h+phNewToken], rdi; phNewToken
0x18003b4ac  xor     r8d, r8d; lpTokenAttributes
0x18003b4af  mov     [rsp+38h+TokenType], r9d; TokenType
0x18003b4b4  lea     edx, [r9+0Ah]; dwDesiredAccess
0x18003b4b8  call    cs:__imp_DuplicateTokenEx
0x18003b4be  test    eax, eax
0x18003b4c0  jz      short loc_18003B4C6
0x18003b4c2  xor     ebx, ebx
0x18003b4c4  jmp     short loc_18003B4CD
0x18003b4c6  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003b4cb  mov     ebx, eax
0x18003b4cd  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18003b4d2  mov     [rsp+38h+TokenHandle], 0
0x18003b4db  lea     rdx, [rcx-1]
0x18003b4df  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18003b4e3  ja      short loc_18003B4EB
0x18003b4e5  call    cs:__imp_CloseHandle
0x18003b4eb  mov     eax, ebx
0x18003b4ed  mov     rbx, [rsp+38h+arg_0]
0x18003b4f2  add     rsp, 30h
0x18003b4f6  pop     rdi
0x18003b4f7  retn
```
