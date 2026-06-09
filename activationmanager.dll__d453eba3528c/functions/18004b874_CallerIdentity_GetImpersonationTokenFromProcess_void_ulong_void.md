# CallerIdentity::GetImpersonationTokenFromProcess(void *,ulong,void * *)

- ea: `0x18004b874`
- end: `0x18004b90c`
- name: `?GetImpersonationTokenFromProcess@CallerIdentity@@YAJPEAXKPEAPEAX@Z`
- size: `152`
- prototype: `__int64 __fastcall(CallerIdentity *this, void *, void **, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022c60`

## callees

- `0x18004b874`
- `0x18004b914`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004b89b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004b89b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b8f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b8f9`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18004b8cc`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18004b8cc`

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
0x18004b874  mov     [rsp+arg_0], rbx
0x18004b879  push    rdi
0x18004b87a  sub     rsp, 30h
0x18004b87e  mov     rdi, r8
0x18004b881  mov     qword ptr [r8], 0
0x18004b888  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18004b88d  mov     [rsp+38h+TokenHandle], 0
0x18004b896  mov     edx, 0Eh; DesiredAccess
0x18004b89b  call    cs:__imp_OpenProcessToken
0x18004b8a1  test    eax, eax
0x18004b8a3  jnz     short loc_18004B8B0
0x18004b8a5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18004b8aa  mov     ebx, eax
0x18004b8ac  test    eax, eax
0x18004b8ae  js      short loc_18004B8E1
0x18004b8b0  mov     rcx, [rsp+38h+TokenHandle]; hExistingToken
0x18004b8b5  mov     r9d, 2; ImpersonationLevel
0x18004b8bb  mov     [rsp+38h+phNewToken], rdi; phNewToken
0x18004b8c0  xor     r8d, r8d; lpTokenAttributes
0x18004b8c3  mov     [rsp+38h+TokenType], r9d; TokenType
0x18004b8c8  lea     edx, [r9+0Ah]; dwDesiredAccess
0x18004b8cc  call    cs:__imp_DuplicateTokenEx
0x18004b8d2  test    eax, eax
0x18004b8d4  jz      short loc_18004B8DA
0x18004b8d6  xor     ebx, ebx
0x18004b8d8  jmp     short loc_18004B8E1
0x18004b8da  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18004b8df  mov     ebx, eax
0x18004b8e1  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18004b8e6  mov     [rsp+38h+TokenHandle], 0
0x18004b8ef  lea     rdx, [rcx-1]
0x18004b8f3  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18004b8f7  ja      short loc_18004B8FF
0x18004b8f9  call    cs:__imp_CloseHandle
0x18004b8ff  mov     eax, ebx
0x18004b901  mov     rbx, [rsp+38h+arg_0]
0x18004b906  add     rsp, 30h
0x18004b90a  pop     rdi
0x18004b90b  retn
```
