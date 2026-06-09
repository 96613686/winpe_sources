# CallerIdentity::GetImpersonationTokenFromProcess(void *,ulong,void * *)

- ea: `0x1800e13f8`
- end: `0x1800e1490`
- name: `?GetImpersonationTokenFromProcess@CallerIdentity@@YAJPEAXKPEAPEAX@Z`
- size: `152`
- prototype: `int(CallerIdentity *__hidden this, void *, unsigned int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800e1268`

## callees

- `0x1800e13f8`
- `0x1800e14c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800e141f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800e141f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e147d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e147d`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800e1450`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800e1450`

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
0x1800e13f8  mov     [rsp+arg_0], rbx
0x1800e13fd  push    rdi
0x1800e13fe  sub     rsp, 30h
0x1800e1402  mov     rdi, r8
0x1800e1405  mov     qword ptr [r8], 0
0x1800e140c  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x1800e1411  mov     [rsp+38h+TokenHandle], 0
0x1800e141a  mov     edx, 0Eh; DesiredAccess
0x1800e141f  call    cs:__imp_OpenProcessToken
0x1800e1425  test    eax, eax
0x1800e1427  jnz     short loc_1800E1434
0x1800e1429  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800e142e  mov     ebx, eax
0x1800e1430  test    eax, eax
0x1800e1432  js      short loc_1800E1465
0x1800e1434  mov     rcx, [rsp+38h+TokenHandle]; hExistingToken
0x1800e1439  mov     r9d, 2; ImpersonationLevel
0x1800e143f  mov     [rsp+38h+phNewToken], rdi; phNewToken
0x1800e1444  xor     r8d, r8d; lpTokenAttributes
0x1800e1447  mov     [rsp+38h+TokenType], r9d; TokenType
0x1800e144c  lea     edx, [r9+0Ah]; dwDesiredAccess
0x1800e1450  call    cs:__imp_DuplicateTokenEx
0x1800e1456  test    eax, eax
0x1800e1458  jz      short loc_1800E145E
0x1800e145a  xor     ebx, ebx
0x1800e145c  jmp     short loc_1800E1465
0x1800e145e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800e1463  mov     ebx, eax
0x1800e1465  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x1800e146a  mov     [rsp+38h+TokenHandle], 0
0x1800e1473  lea     rdx, [rcx-1]
0x1800e1477  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800e147b  ja      short loc_1800E1483
0x1800e147d  call    cs:__imp_CloseHandle
0x1800e1483  mov     eax, ebx
0x1800e1485  mov     rbx, [rsp+38h+arg_0]
0x1800e148a  add     rsp, 30h
0x1800e148e  pop     rdi
0x1800e148f  retn
```
