# CallerIdentity::GetImpersonationTokenFromProcess(void *,ulong,void * *)

- ea: `0x180067ec4`
- end: `0x180067f49`
- name: `?GetImpersonationTokenFromProcess@CallerIdentity@@YAJPEAXKPEAPEAX@Z`
- size: `133`
- prototype: `int(CallerIdentity *__hidden this, void *, unsigned int, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006896c`

## callees

- `0x180015fd4`
- `0x180024118`
- `0x180067ec4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180067eeb`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180067eeb`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180067f1c`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180067f1c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CallerIdentity::GetImpersonationTokenFromProcess(
        CallerIdentity *this,
        void *a2,
        void **a3,
        void **a4)
{
  int Error; // ebx
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
  CTSmartObj<void *,CAutoHandle_Policy<void *>>::~CTSmartObj<void *,CAutoHandle_Policy<void *>>(&TokenHandle);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180067ec4  mov     [rsp+arg_0], rbx
0x180067ec9  push    rdi
0x180067eca  sub     rsp, 30h
0x180067ece  mov     rdi, r8
0x180067ed1  mov     qword ptr [r8], 0
0x180067ed8  mov     [rsp+38h+TokenHandle], 0
0x180067ee1  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180067ee6  mov     edx, 0Eh; DesiredAccess
0x180067eeb  call    cs:__imp_OpenProcessToken
0x180067ef1  test    eax, eax
0x180067ef3  jnz     short loc_180067F00
0x180067ef5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180067efa  mov     ebx, eax
0x180067efc  test    eax, eax
0x180067efe  js      short loc_180067F31
0x180067f00  mov     [rsp+38h+phNewToken], rdi; phNewToken
0x180067f05  mov     r9d, 2; ImpersonationLevel
0x180067f0b  mov     [rsp+38h+TokenType], r9d; TokenType
0x180067f10  xor     r8d, r8d; lpTokenAttributes
0x180067f13  lea     edx, [r9+0Ah]; dwDesiredAccess
0x180067f17  mov     rcx, [rsp+38h+TokenHandle]; hExistingToken
0x180067f1c  call    cs:__imp_DuplicateTokenEx
0x180067f22  test    eax, eax
0x180067f24  jz      short loc_180067F2A
0x180067f26  xor     ebx, ebx
0x180067f28  jmp     short loc_180067F31
0x180067f2a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180067f2f  mov     ebx, eax
0x180067f31  lea     rcx, [rsp+38h+TokenHandle]
0x180067f36  call    ??1?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAA@XZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::~CTSmartObj<void *,CAutoHandle_Policy<void *>>(void)
0x180067f3b  nop
0x180067f3c  mov     eax, ebx
0x180067f3e  mov     rbx, [rsp+38h+arg_0]
0x180067f43  add     rsp, 30h
0x180067f47  pop     rdi
0x180067f48  retn
```
