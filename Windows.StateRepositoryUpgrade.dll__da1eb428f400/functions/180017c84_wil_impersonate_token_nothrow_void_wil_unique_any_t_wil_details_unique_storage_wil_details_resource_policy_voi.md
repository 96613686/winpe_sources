# wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)

- ea: `0x180017c84`
- end: `0x180017d61`
- name: `?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z`
- size: `221`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180024d40`
- `0x180027404`
- `0x1800284b4`

## callees

- `0x180008afc`
- `0x180008d6c`
- `0x18000a3a0`
- `0x180015780`
- `0x180017694`
- `0x180017c84`
- `0x180017d68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017cd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017cd1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180017cc7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180017cc7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180017cae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180017cae`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180017ce9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180017ce9`

## string_xrefs

- `0x180017cfd`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::impersonate_token_nothrow(__int64 a1, void **a2)
{
  HANDLE CurrentThread; // rax
  const char *v4; // r9
  __int64 v5; // rdx
  unsigned int LastError; // ebx
  void *v7; // rbx
  void *v8; // rsi
  void *v9; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF
  char v13; // [rsp+40h] [rbp+18h] BYREF

  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) && GetLastError() != 1008 )
  {
    v5 = 450;
LABEL_6:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v5,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                  v4);
    goto LABEL_10;
  }
  if ( !SetThreadToken(0, 0) )
  {
    v5 = 454;
    goto LABEL_6;
  }
  v7 = *a2;
  v8 = TokenHandle;
  TokenHandle = 0;
  if ( v7 != (void *)-1LL )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v13);
    wil::details::RevertImpersonateToken(v7, v9);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v13);
  }
  *a2 = v8;
  LastError = 0;
LABEL_10:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x180017c84  mov     rax, rsp
0x180017c87  mov     [rax+10h], rbx
0x180017c8b  mov     [rax+20h], rsi
0x180017c8f  mov     [rax+8], rcx
0x180017c93  push    rdi
0x180017c94  sub     rsp, 20h
0x180017c98  mov     rdi, rdx
0x180017c9b  mov     qword ptr [rax+8], 0
0x180017ca3  xor     edx, edx
0x180017ca5  lea     rcx, [rax+8]
0x180017ca9  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180017cae  call    cs:__imp_GetCurrentThread
0x180017cb4  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180017cb9  mov     edx, 0F01FFh; DesiredAccess
0x180017cbe  mov     rcx, rax; ThreadHandle
0x180017cc1  mov     r8d, 1; OpenAsSelf
0x180017cc7  call    cs:__imp_OpenThreadToken
0x180017ccd  test    eax, eax
0x180017ccf  jnz     short loc_180017CE5
0x180017cd1  call    cs:__imp_GetLastError
0x180017cd7  cmp     eax, 3F0h
0x180017cdc  jz      short loc_180017CE5
0x180017cde  mov     edx, 1C2h
0x180017ce3  jmp     short loc_180017CF8
0x180017ce5  xor     edx, edx; Token
0x180017ce7  xor     ecx, ecx; Thread
0x180017ce9  call    cs:__imp_SetThreadToken
0x180017cef  test    eax, eax
0x180017cf1  jnz     short loc_180017D0D
0x180017cf3  mov     edx, 1C6h; void *
0x180017cf8  mov     rcx, [rsp+28h]; this
0x180017cfd  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180017d04  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180017d09  mov     ebx, eax
0x180017d0b  jmp     short loc_180017D45
0x180017d0d  mov     rbx, [rdi]
0x180017d10  mov     rsi, [rsp+28h+TokenHandle]
0x180017d15  mov     [rsp+28h+TokenHandle], 0
0x180017d1e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180017d22  jz      short loc_180017D40
0x180017d24  lea     rcx, [rsp+28h+arg_10]; this
0x180017d29  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180017d2e  mov     rcx, rbx; hObject
0x180017d31  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x180017d36  lea     rcx, [rsp+28h+arg_10]; this
0x180017d3b  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180017d40  mov     [rdi], rsi
0x180017d43  xor     ebx, ebx
0x180017d45  lea     rcx, [rsp+28h+TokenHandle]
0x180017d4a  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180017d4f  mov     rsi, [rsp+28h+arg_18]
0x180017d54  mov     eax, ebx
0x180017d56  mov     rbx, [rsp+28h+arg_8]
0x180017d5b  add     rsp, 20h
0x180017d5f  pop     rdi
0x180017d60  retn
```
