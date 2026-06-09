# CallerIdentity::GetImpersonationTokenFromProcess(void *,ulong,void * *)

- ea: `0x180095bb4`
- end: `0x180095c56`
- name: `?GetImpersonationTokenFromProcess@CallerIdentity@@YAJPEAXKPEAPEAX@Z`
- size: `162`
- prototype: `int(CallerIdentity *__hidden this, void *, unsigned int, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008a4f8`
- `0x180095ef4`

## callees

- `0x18001b2c0`
- `0x180095bb4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180095bdf`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180095bdf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180095c3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180095c3e`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180095c11`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180095c11`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetImpersonationTokenFromProcess(
        CallerIdentity *this,
        void *a2,
        void **a3,
        void **a4)
{
  int v5; // edi
  int Error; // ebx
  char *v7; // rcx
  HANDLE hExistingToken; // [rsp+50h] [rbp+18h] BYREF

  *a3 = 0;
  v5 = (int)a2;
  hExistingToken = 0;
  if ( OpenProcessToken(this, (unsigned int)a2 | 0xE, &hExistingToken)
    || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    if ( DuplicateTokenEx(hExistingToken, v5 | 0xC, 0, SecurityImpersonation, TokenImpersonation, a3) )
      Error = 0;
    else
      Error = ResultFromKnownLastError();
  }
  v7 = (char *)hExistingToken;
  hExistingToken = 0;
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v7);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180095bb4  mov     rax, rsp
0x180095bb7  mov     [rax+8], rbx
0x180095bbb  mov     [rax+10h], rsi
0x180095bbf  push    rdi
0x180095bc0  sub     rsp, 30h
0x180095bc4  mov     rsi, r8
0x180095bc7  mov     qword ptr [r8], 0
0x180095bce  mov     edi, edx
0x180095bd0  mov     qword ptr [rax+18h], 0
0x180095bd8  or      edx, 0Eh; DesiredAccess
0x180095bdb  lea     r8, [rax+18h]; TokenHandle
0x180095bdf  call    cs:__imp_OpenProcessToken
0x180095be5  test    eax, eax
0x180095be7  jnz     short loc_180095BF4
0x180095be9  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180095bee  mov     ebx, eax
0x180095bf0  test    eax, eax
0x180095bf2  js      short loc_180095C26
0x180095bf4  mov     rcx, [rsp+38h+hExistingToken]; hExistingToken
0x180095bf9  mov     r9d, 2; ImpersonationLevel
0x180095bff  or      edi, 0Ch
0x180095c02  mov     [rsp+38h+phNewToken], rsi; phNewToken
0x180095c07  mov     edx, edi; dwDesiredAccess
0x180095c09  mov     [rsp+38h+TokenType], r9d; TokenType
0x180095c0e  xor     r8d, r8d; lpTokenAttributes
0x180095c11  call    cs:__imp_DuplicateTokenEx
0x180095c17  test    eax, eax
0x180095c19  jz      short loc_180095C1F
0x180095c1b  xor     ebx, ebx
0x180095c1d  jmp     short loc_180095C26
0x180095c1f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180095c24  mov     ebx, eax
0x180095c26  mov     rcx, [rsp+38h+hExistingToken]; hObject
0x180095c2b  mov     [rsp+38h+hExistingToken], 0
0x180095c34  lea     rdx, [rcx-1]
0x180095c38  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180095c3c  ja      short loc_180095C44
0x180095c3e  call    cs:__imp_CloseHandle
0x180095c44  mov     rsi, [rsp+38h+arg_8]
0x180095c49  mov     eax, ebx
0x180095c4b  mov     rbx, [rsp+38h+arg_0]
0x180095c50  add     rsp, 30h
0x180095c54  pop     rdi
0x180095c55  retn
```
