# wil::GetImpersonationTokenForClientOfObject_nothrow(IUnknown *,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)

- ea: `0x1801185c0`
- end: `0x180118751`
- name: `?GetImpersonationTokenForClientOfObject_nothrow@wil@@YAJPEAUIUnknown@@KAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@@Z`
- size: `401`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1801183b4`

## callees

- `0x18001aca4`
- `0x18004f5d0`
- `0x1801185c0`
- `0x180161174`
- `0x18019a0e8`
- `0x1801b98c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011865a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011865a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180118637`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180118637`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18011864c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18011864c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18011867c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18011867c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18011868f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18011868f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801186bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801186bf`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180118730`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18011873e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180118730`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18011873e`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1801186f0`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1801186f0`
- `combase!__imp_CoImpersonateClientOfObject` at `0x1801185dd`
- `combase!__imp_CoImpersonateClientOfObject` at `0x1801185dd`

## pseudocode

```c
__int64 __fastcall wil::GetImpersonationTokenForClientOfObject_nothrow(__int64 a1, __int64 a2, void **a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  bool v7; // bl
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  HANDLE CurrentProcess; // rax
  const char *v11; // r9
  __int64 v12; // rdx
  unsigned int v13; // edi
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-18h]
  TOKEN_TYPE TokenTypea; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v17; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp+20h] BYREF

  v17 = 0;
  v4 = CoImpersonateClientOfObject(a1, &v17);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x157,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
      (const char *)(unsigned int)v4,
      TokenType);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
      (const char *)v5,
      TokenTypea);
    return v5;
  }
  v7 = v17 != 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    a3,
    0);
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, a3) )
    goto LABEL_18;
  LastError = GetLastError();
  if ( !v7 && LastError == 1008 )
  {
    TokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle) )
    {
      v12 = 386;
      goto LABEL_9;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      a3,
      0);
    if ( !DuplicateTokenEx(TokenHandle, 8u, 0, SecurityImpersonation, TokenImpersonation, a3) )
    {
      v12 = 388;
LABEL_9:
      v5 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v12,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
             v11);
      if ( TokenHandle )
        CloseHandle(TokenHandle);
      return v5;
    }
    wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return 0;
  }
  if ( !LastError )
  {
LABEL_18:
    if ( v7 )
      CoRevertToSelf();
    return 0;
  }
  v13 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0x188,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
          (const char *)LastError,
          TokenType);
  if ( v7 )
    CoRevertToSelf();
  return v13;
}

```

## disassembly

```asm
0x1801185c0  mov     rax, rsp
0x1801185c3  mov     [rax+8], rbx
0x1801185c7  mov     [rax+10h], edx
0x1801185ca  push    rdi
0x1801185cb  sub     rsp, 30h
0x1801185cf  lea     rdx, [rax+10h]
0x1801185d3  mov     dword ptr [rax+10h], 0
0x1801185da  mov     rdi, r8
0x1801185dd  call    cs:__imp_CoImpersonateClientOfObject
0x1801185e3  mov     ebx, eax
0x1801185e5  test    eax, eax
0x1801185e7  jns     short loc_180118622
0x1801185e9  mov     rcx, [rsp+38h]; this
0x1801185ee  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x1801185f5  mov     r9d, eax; char *
0x1801185f8  mov     edx, 157h; void *
0x1801185fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180118602  mov     rcx, [rsp+38h]; this
0x180118607  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x18011860e  mov     r9d, ebx; char *
0x180118611  mov     edx, 177h; void *
0x180118616  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011861b  mov     eax, ebx
0x18011861d  jmp     loc_180118746
0x180118622  xor     bl, bl
0x180118624  cmp     [rsp+38h+arg_8], 0
0x180118629  jz      short loc_18011862D
0x18011862b  mov     bl, 1
0x18011862d  xor     edx, edx
0x18011862f  mov     rcx, rdi
0x180118632  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180118637  call    cs:__imp_GetCurrentThread
0x18011863d  mov     edx, 8; DesiredAccess
0x180118642  mov     r9, rdi; TokenHandle
0x180118645  mov     rcx, rax; ThreadHandle
0x180118648  lea     r8d, [rdx-7]; OpenAsSelf
0x18011864c  call    cs:__imp_OpenThreadToken
0x180118652  test    eax, eax
0x180118654  jnz     loc_18011873A
0x18011865a  call    cs:__imp_GetLastError
0x180118660  test    bl, bl
0x180118662  jnz     loc_18011870D
0x180118668  cmp     eax, 3F0h
0x18011866d  jnz     loc_18011870D
0x180118673  mov     [rsp+38h+TokenHandle], 0
0x18011867c  call    cs:__imp_GetCurrentProcess
0x180118682  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180118687  mov     edx, 0Ah; DesiredAccess
0x18011868c  mov     rcx, rax; ProcessHandle
0x18011868f  call    cs:__imp_OpenProcessToken
0x180118695  test    eax, eax
0x180118697  jnz     short loc_1801186CA
0x180118699  mov     edx, 182h; void *
0x18011869e  mov     rcx, [rsp+38h]; this
0x1801186a3  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x1801186aa  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801186af  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x1801186b4  mov     ebx, eax
0x1801186b6  test    rcx, rcx
0x1801186b9  jz      loc_18011861B
0x1801186bf  call    cs:__imp_CloseHandle
0x1801186c5  jmp     loc_18011861B
0x1801186ca  xor     edx, edx
0x1801186cc  mov     rcx, rdi
0x1801186cf  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1801186d4  mov     rcx, [rsp+38h+TokenHandle]; hExistingToken
0x1801186d9  mov     r9d, 2; ImpersonationLevel
0x1801186df  mov     [rsp+38h+phNewToken], rdi; phNewToken
0x1801186e4  xor     r8d, r8d; lpTokenAttributes
0x1801186e7  mov     [rsp+38h+TokenType], r9d; TokenType
0x1801186ec  lea     edx, [r9+6]; dwDesiredAccess
0x1801186f0  call    cs:__imp_DuplicateTokenEx
0x1801186f6  test    eax, eax
0x1801186f8  jnz     short loc_180118701
0x1801186fa  mov     edx, 184h
0x1801186ff  jmp     short loc_18011869E
0x180118701  lea     rcx, [rsp+38h+TokenHandle]
0x180118706  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18011870b  jmp     short loc_180118744
0x18011870d  test    eax, eax
0x18011870f  jz      short loc_18011873A
0x180118711  mov     rcx, [rsp+38h]; this
0x180118716  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x18011871d  mov     r9d, eax; char *
0x180118720  mov     edx, 188h; void *
0x180118725  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18011872a  mov     edi, eax
0x18011872c  test    bl, bl
0x18011872e  jz      short loc_180118736
0x180118730  call    cs:__imp_CoRevertToSelf
0x180118736  mov     eax, edi
0x180118738  jmp     short loc_180118746
0x18011873a  test    bl, bl
0x18011873c  jz      short loc_180118744
0x18011873e  call    cs:__imp_CoRevertToSelf
0x180118744  xor     eax, eax
0x180118746  mov     rbx, [rsp+38h+arg_0]
0x18011874b  add     rsp, 30h
0x18011874f  pop     rdi
0x180118750  retn
```
