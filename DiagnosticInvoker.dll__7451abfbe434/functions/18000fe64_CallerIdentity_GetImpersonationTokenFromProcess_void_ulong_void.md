# CallerIdentity::GetImpersonationTokenFromProcess(void *,ulong,void * *)

- ea: `0x18000fe64`
- end: `0x18000ff00`
- name: `?GetImpersonationTokenFromProcess@CallerIdentity@@YAJPEAXKPEAPEAX@Z`
- size: `156`
- prototype: `__int64 __fastcall(CallerIdentity *this, void *, void **, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000fc74`

## callees

- `0x18000fe64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000febb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000febb`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000fe87`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000fe87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fef2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fef2`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000fead`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000fead`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetImpersonationTokenFromProcess(
        CallerIdentity *this,
        void *a2,
        void **a3,
        void **a4)
{
  signed int v5; // ebx
  signed int LastError; // eax
  char *v7; // rcx
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  *a3 = 0;
  TokenHandle = 0;
  if ( OpenProcessToken(this, 0xEu, &TokenHandle)
    && DuplicateTokenEx(TokenHandle, 0xCu, 0, SecurityImpersonation, TokenImpersonation, a3) )
  {
    v5 = 0;
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 >= 0 )
      v5 = -2147467259;
  }
  v7 = (char *)TokenHandle;
  TokenHandle = 0;
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v7);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000fe64  push    rbx
0x18000fe66  sub     rsp, 30h
0x18000fe6a  mov     rbx, r8
0x18000fe6d  mov     qword ptr [r8], 0
0x18000fe74  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18000fe79  mov     [rsp+38h+TokenHandle], 0
0x18000fe82  mov     edx, 0Eh; DesiredAccess
0x18000fe87  call    cs:__imp_OpenProcessToken
0x18000fe8d  test    eax, eax
0x18000fe8f  jz      short loc_18000FEBB
0x18000fe91  mov     rcx, [rsp+38h+TokenHandle]; hExistingToken
0x18000fe96  mov     r9d, 2; ImpersonationLevel
0x18000fe9c  mov     [rsp+38h+phNewToken], rbx; phNewToken
0x18000fea1  xor     r8d, r8d; lpTokenAttributes
0x18000fea4  mov     [rsp+38h+TokenType], r9d; TokenType
0x18000fea9  lea     edx, [r9+0Ah]; dwDesiredAccess
0x18000fead  call    cs:__imp_DuplicateTokenEx
0x18000feb3  test    eax, eax
0x18000feb5  jz      short loc_18000FEBB
0x18000feb7  xor     ebx, ebx
0x18000feb9  jmp     short loc_18000FEDA
0x18000febb  call    cs:__imp_GetLastError
0x18000fec1  mov     ebx, eax
0x18000fec3  test    eax, eax
0x18000fec5  jle     short loc_18000FED0
0x18000fec7  movzx   ebx, ax
0x18000feca  or      ebx, 80070000h
0x18000fed0  test    ebx, ebx
0x18000fed2  mov     eax, 80004005h
0x18000fed7  cmovns  ebx, eax
0x18000feda  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18000fedf  mov     [rsp+38h+TokenHandle], 0
0x18000fee8  lea     rdx, [rcx-1]
0x18000feec  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000fef0  ja      short loc_18000FEF8
0x18000fef2  call    cs:__imp_CloseHandle
0x18000fef8  mov     eax, ebx
0x18000fefa  add     rsp, 30h
0x18000fefe  pop     rbx
0x18000feff  retn
```
