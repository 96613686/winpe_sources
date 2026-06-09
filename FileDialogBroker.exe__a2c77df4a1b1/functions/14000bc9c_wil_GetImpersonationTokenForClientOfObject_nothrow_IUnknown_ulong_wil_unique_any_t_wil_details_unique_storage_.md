# wil::GetImpersonationTokenForClientOfObject_nothrow(IUnknown *,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)

- ea: `0x14000bc9c`
- end: `0x14000be17`
- name: `?GetImpersonationTokenForClientOfObject_nothrow@wil@@YAJPEAUIUnknown@@KAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@@Z`
- size: `379`
- prototype: `__int64 __fastcall(__int64, __int64, void **)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140009bd0`
- `0x140012428`
- `0x1400124c7`

## callees

- `0x140005064`
- `0x140005084`
- `0x140009130`
- `0x14000bc9c`
- `0x14000ddf8`
- `0x14000f9c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bd36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bd36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14000bd13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14000bd13`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14000bd6b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14000bd6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000bd58`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000bd58`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14000bd28`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14000bd28`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000bdf6`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000be04`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000bdf6`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000be04`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x14000bda2`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x14000bda2`
- `combase!__imp_CoImpersonateClientOfObject` at `0x14000bcb9`
- `combase!__imp_CoImpersonateClientOfObject` at `0x14000bcb9`

## pseudocode

```c
__int64 __fastcall wil::GetImpersonationTokenForClientOfObject_nothrow(__int64 a1, __int64 a2, void **a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  bool v7; // bl
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  void *v10; // rdx
  unsigned int v11; // r8d
  HANDLE CurrentProcess; // rax
  const char *v13; // r9
  __int64 v14; // rdx
  unsigned int v15; // edi
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-18h]
  TOKEN_TYPE TokenTypea; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v19; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp+20h] BYREF

  v19 = 0;
  v4 = CoImpersonateClientOfObject(a1, &v19);
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
  v7 = v19 != 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    a3,
    0);
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, a3) )
    goto LABEL_17;
  LastError = GetLastError();
  if ( !v7 && LastError == 1008 )
  {
    TokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle) )
    {
      v14 = 386;
LABEL_11:
      v5 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v14,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
             v13);
      wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      return v5;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      a3,
      0);
    if ( !DuplicateTokenEx(TokenHandle, 8u, 0, SecurityImpersonation, TokenImpersonation, a3) )
    {
      v14 = 388;
      goto LABEL_11;
    }
    wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return 0;
  }
  if ( !LastError )
  {
LABEL_17:
    if ( v7 )
      CoRevertToSelf();
    return 0;
  }
  v15 = wil::details::in1diag3::Return_Win32(retaddr, v10, v11, (const char *)LastError, TokenType);
  if ( v7 )
    CoRevertToSelf();
  return v15;
}

```

## disassembly

```asm
0x14000bc9c  mov     rax, rsp
0x14000bc9f  mov     [rax+8], rbx
0x14000bca3  mov     [rax+10h], edx
0x14000bca6  push    rdi
0x14000bca7  sub     rsp, 30h
0x14000bcab  lea     rdx, [rax+10h]
0x14000bcaf  mov     dword ptr [rax+10h], 0
0x14000bcb6  mov     rdi, r8
0x14000bcb9  call    cs:__imp_CoImpersonateClientOfObject
0x14000bcbf  mov     ebx, eax
0x14000bcc1  test    eax, eax
0x14000bcc3  jns     short loc_14000BCFE
0x14000bcc5  mov     rcx, [rsp+38h]; this
0x14000bcca  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x14000bcd1  mov     r9d, eax; char *
0x14000bcd4  mov     edx, 157h; void *
0x14000bcd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000bcde  mov     rcx, [rsp+38h]; this
0x14000bce3  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x14000bcea  mov     r9d, ebx; char *
0x14000bced  mov     edx, 177h; void *
0x14000bcf2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000bcf7  mov     eax, ebx
0x14000bcf9  jmp     loc_14000BE0C
0x14000bcfe  xor     bl, bl
0x14000bd00  cmp     [rsp+38h+arg_8], 0
0x14000bd05  jz      short loc_14000BD09
0x14000bd07  mov     bl, 1
0x14000bd09  xor     edx, edx
0x14000bd0b  mov     rcx, rdi
0x14000bd0e  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14000bd13  call    cs:__imp_GetCurrentThread
0x14000bd19  mov     edx, 8; DesiredAccess
0x14000bd1e  mov     r9, rdi; TokenHandle
0x14000bd21  mov     rcx, rax; ThreadHandle
0x14000bd24  lea     r8d, [rdx-7]; OpenAsSelf
0x14000bd28  call    cs:__imp_OpenThreadToken
0x14000bd2e  test    eax, eax
0x14000bd30  jnz     loc_14000BE00
0x14000bd36  call    cs:__imp_GetLastError
0x14000bd3c  test    bl, bl
0x14000bd3e  jnz     loc_14000BDDF
0x14000bd44  cmp     eax, 3F0h
0x14000bd49  jnz     loc_14000BDDF
0x14000bd4f  mov     [rsp+38h+TokenHandle], 0
0x14000bd58  call    cs:__imp_GetCurrentProcess
0x14000bd5e  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x14000bd63  mov     edx, 0Ah; DesiredAccess
0x14000bd68  mov     rcx, rax; ProcessHandle
0x14000bd6b  call    cs:__imp_OpenProcessToken
0x14000bd71  test    eax, eax
0x14000bd73  jnz     short loc_14000BD7C
0x14000bd75  mov     edx, 182h
0x14000bd7a  jmp     short loc_14000BDB1
0x14000bd7c  xor     edx, edx
0x14000bd7e  mov     rcx, rdi
0x14000bd81  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14000bd86  mov     rcx, [rsp+38h+TokenHandle]; hExistingToken
0x14000bd8b  mov     r9d, 2; ImpersonationLevel
0x14000bd91  mov     [rsp+38h+phNewToken], rdi; phNewToken
0x14000bd96  xor     r8d, r8d; lpTokenAttributes
0x14000bd99  mov     [rsp+38h+TokenType], r9d; TokenType
0x14000bd9e  lea     edx, [r9+6]; dwDesiredAccess
0x14000bda2  call    cs:__imp_DuplicateTokenEx
0x14000bda8  test    eax, eax
0x14000bdaa  jnz     short loc_14000BDD3
0x14000bdac  mov     edx, 184h; void *
0x14000bdb1  mov     rcx, [rsp+38h]; this
0x14000bdb6  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x14000bdbd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000bdc2  lea     rcx, [rsp+38h+TokenHandle]
0x14000bdc7  mov     ebx, eax
0x14000bdc9  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14000bdce  jmp     loc_14000BCF7
0x14000bdd3  lea     rcx, [rsp+38h+TokenHandle]
0x14000bdd8  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14000bddd  jmp     short loc_14000BE0A
0x14000bddf  test    eax, eax
0x14000bde1  jz      short loc_14000BE00
0x14000bde3  mov     rcx, [rsp+38h]; this
0x14000bde8  mov     r9d, eax; char *
0x14000bdeb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14000bdf0  mov     edi, eax
0x14000bdf2  test    bl, bl
0x14000bdf4  jz      short loc_14000BDFC
0x14000bdf6  call    cs:__imp_CoRevertToSelf
0x14000bdfc  mov     eax, edi
0x14000bdfe  jmp     short loc_14000BE0C
0x14000be00  test    bl, bl
0x14000be02  jz      short loc_14000BE0A
0x14000be04  call    cs:__imp_CoRevertToSelf
0x14000be0a  xor     eax, eax
0x14000be0c  mov     rbx, [rsp+38h+arg_0]
0x14000be11  add     rsp, 30h
0x14000be15  pop     rdi
0x14000be16  retn
```
