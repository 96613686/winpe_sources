# CallerIdentity::GetImpersonationTokenFromProcess(void *,ulong,void * *)

- ea: `0x18006329c`
- end: `0x180063338`
- name: `?GetImpersonationTokenFromProcess@CallerIdentity@@YAJPEAXKPEAPEAX@Z`
- size: `156`
- prototype: `__int64 __fastcall(CallerIdentity *this, void *, void **, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800630dc`

## callees

- `0x18006329c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800632f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800632f3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800632bf`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800632bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006332a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006332a`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800632e5`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800632e5`

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
0x18006329c  push    rbx
0x18006329e  sub     rsp, 30h
0x1800632a2  mov     rbx, r8
0x1800632a5  mov     qword ptr [r8], 0
0x1800632ac  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x1800632b1  mov     [rsp+38h+TokenHandle], 0
0x1800632ba  mov     edx, 0Eh; DesiredAccess
0x1800632bf  call    cs:__imp_OpenProcessToken
0x1800632c5  test    eax, eax
0x1800632c7  jz      short loc_1800632F3
0x1800632c9  mov     rcx, [rsp+38h+TokenHandle]; hExistingToken
0x1800632ce  mov     r9d, 2; ImpersonationLevel
0x1800632d4  mov     [rsp+38h+phNewToken], rbx; phNewToken
0x1800632d9  xor     r8d, r8d; lpTokenAttributes
0x1800632dc  mov     [rsp+38h+TokenType], r9d; TokenType
0x1800632e1  lea     edx, [r9+0Ah]; dwDesiredAccess
0x1800632e5  call    cs:__imp_DuplicateTokenEx
0x1800632eb  test    eax, eax
0x1800632ed  jz      short loc_1800632F3
0x1800632ef  xor     ebx, ebx
0x1800632f1  jmp     short loc_180063312
0x1800632f3  call    cs:__imp_GetLastError
0x1800632f9  mov     ebx, eax
0x1800632fb  test    eax, eax
0x1800632fd  jle     short loc_180063308
0x1800632ff  movzx   ebx, ax
0x180063302  or      ebx, 80070000h
0x180063308  test    ebx, ebx
0x18006330a  mov     eax, 80004005h
0x18006330f  cmovns  ebx, eax
0x180063312  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180063317  mov     [rsp+38h+TokenHandle], 0
0x180063320  lea     rdx, [rcx-1]
0x180063324  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180063328  ja      short loc_180063330
0x18006332a  call    cs:__imp_CloseHandle
0x180063330  mov     eax, ebx
0x180063332  add     rsp, 30h
0x180063336  pop     rbx
0x180063337  retn
```
