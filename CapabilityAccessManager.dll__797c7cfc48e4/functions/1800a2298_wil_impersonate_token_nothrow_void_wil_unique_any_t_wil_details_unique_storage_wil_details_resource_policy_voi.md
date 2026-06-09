# wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)

- ea: `0x1800a2298`
- end: `0x1800a239f`
- name: `?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z`
- size: `263`
- prototype: ``
- caller_count: `7`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800abd5c`
- `0x1800ad0a4`
- `0x1800adfc0`
- `0x1800ae0c0`
- `0x1800ae150`
- `0x1800ae1d0`
- `0x1800ae390`

## callees

- `0x180016944`
- `0x180017098`
- `0x18001ab7c`
- `0x18003f4a0`
- `0x1800464d0`
- `0x1800a1bb0`
- `0x1800a2298`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a22e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a22e5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800a231d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800a231d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800a22db`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800a22db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a22c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a22c2`

## string_xrefs

- `0x1800a22f7`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x1800a232c`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::impersonate_token_nothrow(__int64 a1, void **a2)
{
  HANDLE CurrentThread; // rax
  const char *v4; // r9
  unsigned int LastError; // ebx
  const char *v7; // r9
  void *v8; // rsi
  void *v9; // rbx
  void *v10; // rdx
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
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1C2,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                  v4);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return LastError;
  }
  if ( !SetThreadToken(0, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1C6,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                  v7);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return LastError;
  }
  v8 = TokenHandle;
  TokenHandle = 0;
  v9 = *a2;
  if ( *a2 != (void *)-1LL )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v13);
    wil::details::RevertImpersonateToken(v9, v10);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v13);
  }
  *a2 = v8;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x1800a2298  mov     rax, rsp
0x1800a229b  mov     [rax+10h], rbx
0x1800a229f  mov     [rax+20h], rsi
0x1800a22a3  mov     [rax+8], rcx
0x1800a22a7  push    rdi
0x1800a22a8  sub     rsp, 20h
0x1800a22ac  mov     rdi, rdx
0x1800a22af  mov     qword ptr [rax+8], 0
0x1800a22b7  xor     edx, edx
0x1800a22b9  lea     rcx, [rax+8]
0x1800a22bd  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800a22c2  call    cs:__imp_GetCurrentThread
0x1800a22c8  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800a22cd  mov     edx, 0F01FFh; DesiredAccess
0x1800a22d2  mov     r8d, 1; OpenAsSelf
0x1800a22d8  mov     rcx, rax; ThreadHandle
0x1800a22db  call    cs:__imp_OpenThreadToken
0x1800a22e1  test    eax, eax
0x1800a22e3  jnz     short loc_1800A2319
0x1800a22e5  call    cs:__imp_GetLastError
0x1800a22eb  cmp     eax, 3F0h
0x1800a22f0  jz      short loc_1800A2319
0x1800a22f2  mov     rcx, [rsp+28h]; this
0x1800a22f7  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800a22fe  mov     edx, 1C2h; void *
0x1800a2303  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a2308  mov     ebx, eax
0x1800a230a  lea     rcx, [rsp+28h+TokenHandle]
0x1800a230f  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a2314  nop
0x1800a2315  mov     eax, ebx
0x1800a2317  jmp     short loc_1800A238F
0x1800a2319  xor     edx, edx; Token
0x1800a231b  xor     ecx, ecx; Thread
0x1800a231d  call    cs:__imp_SetThreadToken
0x1800a2323  test    eax, eax
0x1800a2325  jnz     short loc_1800A234C
0x1800a2327  mov     rcx, [rsp+28h]; this
0x1800a232c  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800a2333  mov     edx, 1C6h; void *
0x1800a2338  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a233d  mov     ebx, eax
0x1800a233f  lea     rcx, [rsp+28h+TokenHandle]
0x1800a2344  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a2349  nop
0x1800a234a  jmp     short loc_1800A2315
0x1800a234c  mov     rsi, [rsp+28h+TokenHandle]
0x1800a2351  mov     [rsp+28h+TokenHandle], 0
0x1800a235a  mov     rbx, [rdi]
0x1800a235d  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800a2361  jz      short loc_1800A237F
0x1800a2363  lea     rcx, [rsp+28h+arg_10]; this
0x1800a2368  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800a236d  mov     rcx, rbx; hObject
0x1800a2370  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x1800a2375  lea     rcx, [rsp+28h+arg_10]; this
0x1800a237a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800a237f  mov     [rdi], rsi
0x1800a2382  lea     rcx, [rsp+28h+TokenHandle]
0x1800a2387  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a238c  nop
0x1800a238d  xor     eax, eax
0x1800a238f  mov     rbx, [rsp+28h+arg_8]
0x1800a2394  mov     rsi, [rsp+28h+arg_18]
0x1800a2399  add     rsp, 20h
0x1800a239d  pop     rdi
0x1800a239e  retn
```
