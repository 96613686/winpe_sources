# wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)

- ea: `0x1800759d4`
- end: `0x180075ab1`
- name: `?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z`
- size: `221`
- prototype: `__int64 __fastcall(HANDLE Token)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18007307c`

## callees

- `0x180007964`
- `0x18002fb30`
- `0x1800323d0`
- `0x180033350`
- `0x180033c84`
- `0x1800758a8`
- `0x1800759d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075a20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075a20`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180075a39`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180075a39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800759fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800759fd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180075a16`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180075a16`

## string_xrefs

- `0x180075a4d`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::impersonate_token_nothrow(HANDLE Token, void **a2)
{
  HANDLE CurrentThread; // rax
  const char *v5; // r9
  __int64 v6; // rdx
  unsigned int LastError; // ebx
  void *v8; // rbx
  void *v9; // rsi
  void *v10; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *TokenHandle; // [rsp+40h] [rbp+18h] BYREF
  char v14; // [rsp+48h] [rbp+20h] BYREF

  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) && GetLastError() != 1008 )
  {
    v6 = 450;
LABEL_6:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v6,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v5);
    goto LABEL_10;
  }
  if ( !SetThreadToken(0, Token) )
  {
    v6 = 454;
    goto LABEL_6;
  }
  v8 = *a2;
  v9 = TokenHandle;
  TokenHandle = 0;
  if ( v8 != (void *)-1LL )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v14);
    wil::details::RevertImpersonateToken(v8, v10);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v14);
  }
  *a2 = v9;
  LastError = 0;
LABEL_10:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x1800759d4  mov     rax, rsp
0x1800759d7  mov     [rax+8], rbx
0x1800759db  mov     [rax+10h], rsi
0x1800759df  push    rdi
0x1800759e0  sub     rsp, 20h
0x1800759e4  mov     rdi, rdx
0x1800759e7  mov     qword ptr [rax+18h], 0
0x1800759ef  mov     rbx, rcx
0x1800759f2  xor     edx, edx
0x1800759f4  lea     rcx, [rax+18h]
0x1800759f8  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800759fd  call    cs:__imp_GetCurrentThread
0x180075a03  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180075a08  mov     edx, 0F01FFh; DesiredAccess
0x180075a0d  mov     rcx, rax; ThreadHandle
0x180075a10  mov     r8d, 1; OpenAsSelf
0x180075a16  call    cs:__imp_OpenThreadToken
0x180075a1c  test    eax, eax
0x180075a1e  jnz     short loc_180075A34
0x180075a20  call    cs:__imp_GetLastError
0x180075a26  cmp     eax, 3F0h
0x180075a2b  jz      short loc_180075A34
0x180075a2d  mov     edx, 1C2h
0x180075a32  jmp     short loc_180075A48
0x180075a34  mov     rdx, rbx; Token
0x180075a37  xor     ecx, ecx; Thread
0x180075a39  call    cs:__imp_SetThreadToken
0x180075a3f  test    eax, eax
0x180075a41  jnz     short loc_180075A5D
0x180075a43  mov     edx, 1C6h; void *
0x180075a48  mov     rcx, [rsp+28h]; this
0x180075a4d  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180075a54  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180075a59  mov     ebx, eax
0x180075a5b  jmp     short loc_180075A95
0x180075a5d  mov     rbx, [rdi]
0x180075a60  mov     rsi, [rsp+28h+TokenHandle]
0x180075a65  mov     [rsp+28h+TokenHandle], 0
0x180075a6e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180075a72  jz      short loc_180075A90
0x180075a74  lea     rcx, [rsp+28h+arg_18]; this
0x180075a79  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180075a7e  mov     rcx, rbx; hObject
0x180075a81  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x180075a86  lea     rcx, [rsp+28h+arg_18]; this
0x180075a8b  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180075a90  mov     [rdi], rsi
0x180075a93  xor     ebx, ebx
0x180075a95  lea     rcx, [rsp+28h+TokenHandle]
0x180075a9a  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180075a9f  mov     rsi, [rsp+28h+arg_8]
0x180075aa4  mov     eax, ebx
0x180075aa6  mov     rbx, [rsp+28h+arg_0]
0x180075aab  add     rsp, 20h
0x180075aaf  pop     rdi
0x180075ab0  retn
```
