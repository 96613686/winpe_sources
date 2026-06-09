# IsCurrentThreadImpersonating(void)

- ea: `0x180037134`
- end: `0x1800371db`
- name: `?IsCurrentThreadImpersonating@@YA_NXZ`
- size: `167`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x18004c3b0`

## callees

- `0x180003a00`
- `0x180011318`
- `0x180037134`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037181`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037181`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180037156`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180037156`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003716f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003716f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800371a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800371a8`

## string_xrefs

- `0x1800371c9`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char IsCurrentThreadImpersonating(void)
{
  HANDLE CurrentThread; // rax
  char v1; // bl
  const char *v2; // r9
  char v3; // di
  void *TokenHandle; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  v1 = 1;
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    v3 = 1;
  }
  else
  {
    v3 = 0;
    if ( GetLastError() != 1008 )
      goto LABEL_5;
  }
  v1 = 0;
LABEL_5:
  if ( v1 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x188,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
      v2);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return v3;
}

```

## disassembly

```asm
0x180037134  mov     [rsp+arg_0], rbx
0x180037139  push    rdi
0x18003713a  sub     rsp, 30h
0x18003713e  mov     rax, cs:__security_cookie
0x180037145  xor     rax, rsp
0x180037148  mov     [rsp+38h+var_10], rax
0x18003714d  mov     [rsp+38h+TokenHandle], 0
0x180037156  call    cs:__imp_GetCurrentThread
0x18003715c  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180037161  mov     ebx, 1
0x180037166  mov     r8d, ebx; OpenAsSelf
0x180037169  lea     edx, [rbx+7]; DesiredAccess
0x18003716c  mov     rcx, rax; ThreadHandle
0x18003716f  call    cs:__imp_OpenThreadToken
0x180037175  test    eax, eax
0x180037177  jz      short loc_18003717E
0x180037179  mov     dil, bl
0x18003717c  jmp     short loc_18003718E
0x18003717e  xor     dil, dil
0x180037181  call    cs:__imp_GetLastError
0x180037187  cmp     eax, 3F0h
0x18003718c  jnz     short loc_180037190
0x18003718e  xor     bl, bl
0x180037190  mov     rcx, [rsp+38h]; this
0x180037195  test    bl, bl
0x180037197  jnz     short loc_1800371C9
0x180037199  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18003719e  lea     rdx, [rcx-1]
0x1800371a2  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800371a6  ja      short loc_1800371AE
0x1800371a8  call    cs:__imp_CloseHandle
0x1800371ae  mov     al, dil
0x1800371b1  mov     rcx, [rsp+38h+var_10]
0x1800371b6  xor     rcx, rsp; StackCookie
0x1800371b9  call    __security_check_cookie
0x1800371be  mov     rbx, [rsp+38h+arg_0]
0x1800371c3  add     rsp, 30h
0x1800371c7  pop     rdi
0x1800371c8  retn
0x1800371c9  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x1800371d0  mov     edx, 188h; void *
0x1800371d5  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
