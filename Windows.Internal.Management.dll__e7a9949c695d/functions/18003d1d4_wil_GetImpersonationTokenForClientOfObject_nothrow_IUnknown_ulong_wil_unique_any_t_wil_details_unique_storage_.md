# wil::GetImpersonationTokenForClientOfObject_nothrow(IUnknown *,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)

- ea: `0x18003d1d4`
- end: `0x18003d385`
- name: `?GetImpersonationTokenForClientOfObject_nothrow@wil@@YAJPEAUIUnknown@@KAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@@Z`
- size: `433`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003d174`

## callees

- `0x18000a284`
- `0x18000a2a4`
- `0x180019e94`
- `0x18003446c`
- `0x18003c2c4`
- `0x18003d1d4`
- `0x18003ed18`

## import_xrefs

- `combase!__imp_CoImpersonateClientOfObject` at `0x18003d1f1`
- `combase!__imp_CoImpersonateClientOfObject` at `0x18003d1f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d27d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d27d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003d2be`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003d2be`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003d26f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003d26f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003d2ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003d2ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003d25a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003d25a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003d364`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003d372`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003d364`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003d372`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18003d304`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18003d304`

## pseudocode

```c
__int64 __fastcall wil::GetImpersonationTokenForClientOfObject_nothrow(__int64 a1, __int64 a2, HANDLE *a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  bool v7; // bl
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  HANDLE CurrentProcess; // rax
  const char *v11; // r9
  __int64 v12; // rdx
  void *v13; // rcx
  unsigned int v14; // edi
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-18h]
  TOKEN_TYPE TokenTypea; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v18; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp+20h] BYREF

  v18 = 0;
  v4 = CoImpersonateClientOfObject(a1, &v18);
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
  v7 = v18 != 0;
  if ( (char *)*a3 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*a3);
  *a3 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, a3) )
    goto LABEL_21;
  LastError = GetLastError();
  if ( !v7 && LastError == 1008 )
  {
    TokenHandle = 0;
    wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle) )
    {
      v12 = 386;
LABEL_15:
      v5 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v12,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
             v11);
      wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      return v5;
    }
    if ( (char *)*a3 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*a3);
    v13 = TokenHandle;
    *a3 = 0;
    if ( !DuplicateTokenEx(v13, 8u, 0, SecurityImpersonation, TokenImpersonation, a3) )
    {
      v12 = 388;
      goto LABEL_15;
    }
    wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return 0;
  }
  if ( !LastError )
  {
LABEL_21:
    if ( v7 )
      CoRevertToSelf();
    return 0;
  }
  v14 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0x188,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
          (const char *)LastError,
          TokenType);
  if ( v7 )
    CoRevertToSelf();
  return v14;
}

```

## disassembly

```asm
0x18003d1d4  mov     rax, rsp
0x18003d1d7  mov     [rax+8], rbx
0x18003d1db  mov     [rax+10h], edx
0x18003d1de  push    rdi
0x18003d1df  sub     rsp, 30h
0x18003d1e3  lea     rdx, [rax+10h]
0x18003d1e7  mov     dword ptr [rax+10h], 0
0x18003d1ee  mov     rdi, r8
0x18003d1f1  call    cs:__imp_CoImpersonateClientOfObject
0x18003d1f7  mov     ebx, eax
0x18003d1f9  test    eax, eax
0x18003d1fb  jns     short loc_18003D236
0x18003d1fd  mov     rcx, [rsp+38h]; this
0x18003d202  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x18003d209  mov     r9d, eax; char *
0x18003d20c  mov     edx, 157h; void *
0x18003d211  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d216  mov     rcx, [rsp+38h]; this
0x18003d21b  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x18003d222  mov     r9d, ebx; char *
0x18003d225  mov     edx, 177h; void *
0x18003d22a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d22f  mov     eax, ebx
0x18003d231  jmp     loc_18003D37A
0x18003d236  xor     bl, bl
0x18003d238  cmp     [rsp+38h+arg_8], 0
0x18003d23d  jz      short loc_18003D241
0x18003d23f  mov     bl, 1
0x18003d241  mov     rcx, [rdi]; hObject
0x18003d244  lea     rax, [rcx-1]
0x18003d248  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003d24c  ja      short loc_18003D253
0x18003d24e  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18003d253  mov     qword ptr [rdi], 0
0x18003d25a  call    cs:__imp_GetCurrentThread
0x18003d260  mov     edx, 8; DesiredAccess
0x18003d265  mov     r9, rdi; TokenHandle
0x18003d268  mov     rcx, rax; ThreadHandle
0x18003d26b  lea     r8d, [rdx-7]; OpenAsSelf
0x18003d26f  call    cs:__imp_OpenThreadToken
0x18003d275  test    eax, eax
0x18003d277  jnz     loc_18003D36E
0x18003d27d  call    cs:__imp_GetLastError
0x18003d283  test    bl, bl
0x18003d285  jnz     loc_18003D341
0x18003d28b  cmp     eax, 3F0h
0x18003d290  jnz     loc_18003D341
0x18003d296  xor     edx, edx
0x18003d298  mov     [rsp+38h+TokenHandle], 0
0x18003d2a1  lea     rcx, [rsp+38h+TokenHandle]
0x18003d2a6  call    ?reset@?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18003d2ab  call    cs:__imp_GetCurrentProcess
0x18003d2b1  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18003d2b6  mov     edx, 0Ah; DesiredAccess
0x18003d2bb  mov     rcx, rax; ProcessHandle
0x18003d2be  call    cs:__imp_OpenProcessToken
0x18003d2c4  test    eax, eax
0x18003d2c6  jnz     short loc_18003D2CF
0x18003d2c8  mov     edx, 182h
0x18003d2cd  jmp     short loc_18003D313
0x18003d2cf  mov     rcx, [rdi]; hObject
0x18003d2d2  lea     rax, [rcx-1]
0x18003d2d6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003d2da  ja      short loc_18003D2E1
0x18003d2dc  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18003d2e1  mov     rcx, [rsp+38h+TokenHandle]; hExistingToken
0x18003d2e6  mov     r9d, 2; ImpersonationLevel
0x18003d2ec  mov     [rsp+38h+phNewToken], rdi; phNewToken
0x18003d2f1  xor     r8d, r8d; lpTokenAttributes
0x18003d2f4  mov     qword ptr [rdi], 0
0x18003d2fb  mov     [rsp+38h+TokenType], r9d; TokenType
0x18003d300  lea     edx, [r9+6]; dwDesiredAccess
0x18003d304  call    cs:__imp_DuplicateTokenEx
0x18003d30a  test    eax, eax
0x18003d30c  jnz     short loc_18003D335
0x18003d30e  mov     edx, 184h; void *
0x18003d313  mov     rcx, [rsp+38h]; this
0x18003d318  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x18003d31f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003d324  lea     rcx, [rsp+38h+TokenHandle]
0x18003d329  mov     ebx, eax
0x18003d32b  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003d330  jmp     loc_18003D22F
0x18003d335  lea     rcx, [rsp+38h+TokenHandle]
0x18003d33a  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003d33f  jmp     short loc_18003D378
0x18003d341  test    eax, eax
0x18003d343  jz      short loc_18003D36E
0x18003d345  mov     rcx, [rsp+38h]; this
0x18003d34a  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x18003d351  mov     r9d, eax; char *
0x18003d354  mov     edx, 188h; void *
0x18003d359  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003d35e  mov     edi, eax
0x18003d360  test    bl, bl
0x18003d362  jz      short loc_18003D36A
0x18003d364  call    cs:__imp_CoRevertToSelf
0x18003d36a  mov     eax, edi
0x18003d36c  jmp     short loc_18003D37A
0x18003d36e  test    bl, bl
0x18003d370  jz      short loc_18003D378
0x18003d372  call    cs:__imp_CoRevertToSelf
0x18003d378  xor     eax, eax
0x18003d37a  mov     rbx, [rsp+38h+arg_0]
0x18003d37f  add     rsp, 30h
0x18003d383  pop     rdi
0x18003d384  retn
```
