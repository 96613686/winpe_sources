# ATL::CAccessToken::CheckImpersonation(void)

- ea: `0x180012230`
- end: `0x1800122a1`
- name: `?CheckImpersonation@CAccessToken@ATL@@IEBA_NXZ`
- size: `113`
- prototype: `bool __fastcall(ATL::CAccessToken *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800121bc`

## callees

- `0x180012230`
- `0x1800a98c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012269`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012269`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001225f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001225f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001224c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001224c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012299`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012299`

## pseudocode

```c
char __fastcall ATL::CAccessToken::CheckImpersonation(ATL::CAccessToken *this)
{
  HANDLE CurrentThread; // rax
  void *TokenHandle; // [rsp+20h] [rbp-18h] BYREF

  TokenHandle = (void *)-1LL;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0, 0, &TokenHandle) && GetLastError() != 1008 )
    return 1;
  if ( TokenHandle != (void *)-1LL )
    CloseHandle(TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x180012230  sub     rsp, 38h
0x180012234  mov     rax, cs:__security_cookie
0x18001223b  xor     rax, rsp
0x18001223e  mov     [rsp+38h+var_10], rax
0x180012243  mov     [rsp+38h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18001224c  call    cs:__imp_GetCurrentThread
0x180012252  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180012257  xor     r8d, r8d; OpenAsSelf
0x18001225a  mov     rcx, rax; ThreadHandle
0x18001225d  xor     edx, edx; DesiredAccess
0x18001225f  call    cs:__imp_OpenThreadToken
0x180012265  test    eax, eax
0x180012267  jnz     short loc_18001228A
0x180012269  call    cs:__imp_GetLastError
0x18001226f  cmp     eax, 3F0h
0x180012274  jz      short loc_18001228A
0x180012276  mov     al, 1
0x180012278  mov     rcx, [rsp+38h+var_10]
0x18001227d  xor     rcx, rsp; StackCookie
0x180012280  call    __security_check_cookie
0x180012285  add     rsp, 38h
0x180012289  retn
0x18001228a  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18001228f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180012293  jnz     short loc_180012299
0x180012295  xor     al, al
0x180012297  jmp     short loc_180012278
0x180012299  call    cs:__imp_CloseHandle
0x18001229f  jmp     short loc_180012295
```
