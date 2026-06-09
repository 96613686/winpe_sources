# wil::GetImpersonationTokenForClientOfObject_nothrow(IUnknown *,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)

- ea: `0x18008a16c`
- end: `0x18008a2f3`
- name: `?GetImpersonationTokenForClientOfObject_nothrow@wil@@YAJPEAUIUnknown@@KAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@@Z`
- size: `391`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008acb8`

## callees

- `0x18000cc6c`
- `0x18000cc8c`
- `0x180017870`
- `0x180041c44`
- `0x180088a08`
- `0x18008a16c`

## import_xrefs

- `combase!__imp_CoImpersonateClientOfObject` at `0x18008a189`
- `combase!__imp_CoImpersonateClientOfObject` at `0x18008a189`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a206`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a206`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008a23b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008a23b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008a228`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008a228`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008a1f8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008a1f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008a1e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008a1e3`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18008a272`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18008a272`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18008a2d2`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18008a2e0`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18008a2d2`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18008a2e0`

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
    goto LABEL_17;
  LastError = GetLastError();
  if ( !v7 && LastError == 1008 )
  {
    TokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle) )
    {
      v12 = 386;
LABEL_11:
      v5 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v12,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
             v11);
      wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      return v5;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      a3,
      0);
    if ( !DuplicateTokenEx(TokenHandle, 8u, 0, SecurityImpersonation, TokenImpersonation, a3) )
    {
      v12 = 388;
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
0x18008a16c  mov     rax, rsp
0x18008a16f  mov     [rax+8], rbx
0x18008a173  mov     [rax+10h], edx
0x18008a176  push    rdi
0x18008a177  sub     rsp, 30h
0x18008a17b  lea     rdx, [rax+10h]
0x18008a17f  mov     dword ptr [rax+10h], 0
0x18008a186  mov     rdi, r8
0x18008a189  call    cs:__imp_CoImpersonateClientOfObject
0x18008a18f  mov     ebx, eax
0x18008a191  test    eax, eax
0x18008a193  jns     short loc_18008A1CE
0x18008a195  mov     rcx, [rsp+38h]; this
0x18008a19a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x18008a1a1  mov     r9d, eax; char *
0x18008a1a4  mov     edx, 157h; void *
0x18008a1a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008a1ae  mov     rcx, [rsp+38h]; this
0x18008a1b3  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x18008a1ba  mov     r9d, ebx; char *
0x18008a1bd  mov     edx, 177h; void *
0x18008a1c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008a1c7  mov     eax, ebx
0x18008a1c9  jmp     loc_18008A2E8
0x18008a1ce  xor     bl, bl
0x18008a1d0  cmp     [rsp+38h+arg_8], 0
0x18008a1d5  jz      short loc_18008A1D9
0x18008a1d7  mov     bl, 1
0x18008a1d9  xor     edx, edx
0x18008a1db  mov     rcx, rdi
0x18008a1de  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18008a1e3  call    cs:__imp_GetCurrentThread
0x18008a1e9  mov     edx, 8; DesiredAccess
0x18008a1ee  mov     r9, rdi; TokenHandle
0x18008a1f1  mov     rcx, rax; ThreadHandle
0x18008a1f4  lea     r8d, [rdx-7]; OpenAsSelf
0x18008a1f8  call    cs:__imp_OpenThreadToken
0x18008a1fe  test    eax, eax
0x18008a200  jnz     loc_18008A2DC
0x18008a206  call    cs:__imp_GetLastError
0x18008a20c  test    bl, bl
0x18008a20e  jnz     loc_18008A2AF
0x18008a214  cmp     eax, 3F0h
0x18008a219  jnz     loc_18008A2AF
0x18008a21f  mov     [rsp+38h+TokenHandle], 0
0x18008a228  call    cs:__imp_GetCurrentProcess
0x18008a22e  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18008a233  mov     edx, 0Ah; DesiredAccess
0x18008a238  mov     rcx, rax; ProcessHandle
0x18008a23b  call    cs:__imp_OpenProcessToken
0x18008a241  test    eax, eax
0x18008a243  jnz     short loc_18008A24C
0x18008a245  mov     edx, 182h
0x18008a24a  jmp     short loc_18008A281
0x18008a24c  xor     edx, edx
0x18008a24e  mov     rcx, rdi
0x18008a251  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18008a256  mov     rcx, [rsp+38h+TokenHandle]; hExistingToken
0x18008a25b  mov     r9d, 2; ImpersonationLevel
0x18008a261  mov     [rsp+38h+phNewToken], rdi; phNewToken
0x18008a266  xor     r8d, r8d; lpTokenAttributes
0x18008a269  mov     [rsp+38h+TokenType], r9d; TokenType
0x18008a26e  lea     edx, [r9+6]; dwDesiredAccess
0x18008a272  call    cs:__imp_DuplicateTokenEx
0x18008a278  test    eax, eax
0x18008a27a  jnz     short loc_18008A2A3
0x18008a27c  mov     edx, 184h; void *
0x18008a281  mov     rcx, [rsp+38h]; this
0x18008a286  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x18008a28d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008a292  lea     rcx, [rsp+38h+TokenHandle]
0x18008a297  mov     ebx, eax
0x18008a299  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008a29e  jmp     loc_18008A1C7
0x18008a2a3  lea     rcx, [rsp+38h+TokenHandle]
0x18008a2a8  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008a2ad  jmp     short loc_18008A2E6
0x18008a2af  test    eax, eax
0x18008a2b1  jz      short loc_18008A2DC
0x18008a2b3  mov     rcx, [rsp+38h]; this
0x18008a2b8  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x18008a2bf  mov     r9d, eax; char *
0x18008a2c2  mov     edx, 188h; void *
0x18008a2c7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18008a2cc  mov     edi, eax
0x18008a2ce  test    bl, bl
0x18008a2d0  jz      short loc_18008A2D8
0x18008a2d2  call    cs:__imp_CoRevertToSelf
0x18008a2d8  mov     eax, edi
0x18008a2da  jmp     short loc_18008A2E8
0x18008a2dc  test    bl, bl
0x18008a2de  jz      short loc_18008A2E6
0x18008a2e0  call    cs:__imp_CoRevertToSelf
0x18008a2e6  xor     eax, eax
0x18008a2e8  mov     rbx, [rsp+38h+arg_0]
0x18008a2ed  add     rsp, 30h
0x18008a2f1  pop     rdi
0x18008a2f2  retn
```
