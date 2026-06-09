# wil::GetImpersonationTokenForClientOfObject_nothrow(IUnknown *,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)

- ea: `0x1802c2744`
- end: `0x1802c2902`
- name: `?GetImpersonationTokenForClientOfObject_nothrow@wil@@YAJPEAUIUnknown@@KAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@@Z`
- size: `446`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1802c1520`

## callees

- `0x1800378dc`
- `0x18006568c`
- `0x1800f1a00`
- `0x180108c7c`
- `0x1802c0884`
- `0x1802c2744`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802c27f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802c27f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1802c27c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1802c27c1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1802c27dc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1802c27dc`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1802c2831`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1802c2831`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802c2818`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802c2818`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1802c286e`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1802c286e`
- `combase!__imp_CoImpersonateClientOfObject` at `0x1802c2761`
- `combase!__imp_CoImpersonateClientOfObject` at `0x1802c2761`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1802c28d4`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1802c28e8`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1802c28d4`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1802c28e8`

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
0x1802c2744  mov     rax, rsp
0x1802c2747  mov     [rax+8], rbx
0x1802c274b  mov     [rax+10h], edx
0x1802c274e  push    rdi
0x1802c274f  sub     rsp, 30h
0x1802c2753  mov     rdi, r8
0x1802c2756  mov     dword ptr [rax+10h], 0
0x1802c275d  lea     rdx, [rax+10h]
0x1802c2761  call    cs:__imp_CoImpersonateClientOfObject
0x1802c2768  nop     dword ptr [rax+rax+00h]
0x1802c276d  mov     ebx, eax
0x1802c276f  test    eax, eax
0x1802c2771  jns     short loc_1802C27AC
0x1802c2773  mov     rcx, [rsp+38h]; this
0x1802c2778  mov     r9d, eax; char *
0x1802c277b  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x1802c2782  mov     edx, 157h; void *
0x1802c2787  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802c278c  mov     rcx, [rsp+38h]; this
0x1802c2791  mov     r9d, ebx; char *
0x1802c2794  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x1802c279b  mov     edx, 177h; void *
0x1802c27a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802c27a5  mov     eax, ebx
0x1802c27a7  jmp     loc_1802C28F6
0x1802c27ac  xor     bl, bl
0x1802c27ae  cmp     [rsp+38h+arg_8], 0
0x1802c27b3  jz      short loc_1802C27B7
0x1802c27b5  mov     bl, 1
0x1802c27b7  xor     edx, edx
0x1802c27b9  mov     rcx, rdi
0x1802c27bc  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1802c27c1  call    cs:__imp_GetCurrentThread
0x1802c27c8  nop     dword ptr [rax+rax+00h]
0x1802c27cd  mov     r9, rdi; TokenHandle
0x1802c27d0  mov     edx, 8; DesiredAccess
0x1802c27d5  lea     r8d, [rdx-7]; OpenAsSelf
0x1802c27d9  mov     rcx, rax; ThreadHandle
0x1802c27dc  call    cs:__imp_OpenThreadToken
0x1802c27e3  nop     dword ptr [rax+rax+00h]
0x1802c27e8  test    eax, eax
0x1802c27ea  jnz     loc_1802C28E4
0x1802c27f0  call    cs:__imp_GetLastError
0x1802c27f7  nop     dword ptr [rax+rax+00h]
0x1802c27fc  test    bl, bl
0x1802c27fe  jnz     loc_1802C28B1
0x1802c2804  cmp     eax, 3F0h
0x1802c2809  jnz     loc_1802C28B1
0x1802c280f  mov     [rsp+38h+TokenHandle], 0
0x1802c2818  call    cs:__imp_GetCurrentProcess
0x1802c281f  nop     dword ptr [rax+rax+00h]
0x1802c2824  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x1802c2829  mov     edx, 0Ah; DesiredAccess
0x1802c282e  mov     rcx, rax; ProcessHandle
0x1802c2831  call    cs:__imp_OpenProcessToken
0x1802c2838  nop     dword ptr [rax+rax+00h]
0x1802c283d  test    eax, eax
0x1802c283f  jnz     short loc_1802C2848
0x1802c2841  mov     edx, 182h
0x1802c2846  jmp     short loc_1802C2883
0x1802c2848  xor     edx, edx
0x1802c284a  mov     rcx, rdi
0x1802c284d  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1802c2852  mov     [rsp+38h+phNewToken], rdi; phNewToken
0x1802c2857  mov     r9d, 2; ImpersonationLevel
0x1802c285d  mov     [rsp+38h+TokenType], r9d; TokenType
0x1802c2862  xor     r8d, r8d; lpTokenAttributes
0x1802c2865  lea     edx, [r9+6]; dwDesiredAccess
0x1802c2869  mov     rcx, [rsp+38h+TokenHandle]; hExistingToken
0x1802c286e  call    cs:__imp_DuplicateTokenEx
0x1802c2875  nop     dword ptr [rax+rax+00h]
0x1802c287a  test    eax, eax
0x1802c287c  jnz     short loc_1802C28A5
0x1802c287e  mov     edx, 184h; void *
0x1802c2883  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x1802c288a  mov     rcx, [rsp+38h]; this
0x1802c288f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1802c2894  mov     ebx, eax
0x1802c2896  lea     rcx, [rsp+38h+TokenHandle]
0x1802c289b  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1802c28a0  jmp     loc_1802C27A5
0x1802c28a5  lea     rcx, [rsp+38h+TokenHandle]
0x1802c28aa  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1802c28af  jmp     short loc_1802C28F4
0x1802c28b1  test    eax, eax
0x1802c28b3  jz      short loc_1802C28E4
0x1802c28b5  mov     rcx, [rsp+38h]; this
0x1802c28ba  mov     r9d, eax; char *
0x1802c28bd  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x1802c28c4  mov     edx, 188h; void *
0x1802c28c9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1802c28ce  mov     edi, eax
0x1802c28d0  test    bl, bl
0x1802c28d2  jz      short loc_1802C28E0
0x1802c28d4  call    cs:__imp_CoRevertToSelf
0x1802c28db  nop     dword ptr [rax+rax+00h]
0x1802c28e0  mov     eax, edi
0x1802c28e2  jmp     short loc_1802C28F6
0x1802c28e4  test    bl, bl
0x1802c28e6  jz      short loc_1802C28F4
0x1802c28e8  call    cs:__imp_CoRevertToSelf
0x1802c28ef  nop     dword ptr [rax+rax+00h]
0x1802c28f4  xor     eax, eax
0x1802c28f6  mov     rbx, [rsp+38h+arg_0]
0x1802c28fb  add     rsp, 30h
0x1802c28ff  pop     rdi
0x1802c2900  retn
```
