# wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)

- ea: `0x1800162d8`
- end: `0x1800163e5`
- name: `?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z`
- size: `269`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18001c378`
- `0x1800529d0`

## callees

- `0x1800162d8`
- `0x180017dd0`
- `0x1800198fc`
- `0x18001991c`
- `0x18001b1b4`
- `0x180024a44`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001631a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001631a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180016310`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180016310`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800162f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800162f7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001635c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001635c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001634e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800163cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001634e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800163cd`

## string_xrefs

- `0x18001632c`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x18001636b`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::impersonate_token_nothrow(__int64 a1, void **a2)
{
  HANDLE CurrentThread; // rax
  const char *v4; // r9
  unsigned int LastError; // ebx
  const char *v7; // r9
  void *v8; // rbx
  char *v9; // rcx
  void *v10; // rsi
  void *v11; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF
  char v14; // [rsp+40h] [rbp+18h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) && GetLastError() != 1008 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1C2,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                  v4);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
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
  v8 = *a2;
  v9 = 0;
  v10 = TokenHandle;
  TokenHandle = 0;
  if ( v8 != (void *)-1LL )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v14);
    wil::details::RevertImpersonateToken(v8, v11);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v14);
    v9 = (char *)TokenHandle;
  }
  *a2 = v10;
  if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v9);
  return 0;
}

```

## disassembly

```asm
0x1800162d8  mov     rax, rsp
0x1800162db  mov     [rax+10h], rbx
0x1800162df  mov     [rax+20h], rsi
0x1800162e3  mov     [rax+8], rcx
0x1800162e7  push    rdi
0x1800162e8  sub     rsp, 20h
0x1800162ec  mov     rdi, rdx
0x1800162ef  mov     qword ptr [rax+8], 0
0x1800162f7  call    cs:__imp_GetCurrentThread
0x1800162fd  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180016302  mov     edx, 0F01FFh; DesiredAccess
0x180016307  mov     rcx, rax; ThreadHandle
0x18001630a  mov     r8d, 1; OpenAsSelf
0x180016310  call    cs:__imp_OpenThreadToken
0x180016316  test    eax, eax
0x180016318  jnz     short loc_180016358
0x18001631a  call    cs:__imp_GetLastError
0x180016320  cmp     eax, 3F0h
0x180016325  jz      short loc_180016358
0x180016327  mov     rcx, [rsp+28h]; this
0x18001632c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180016333  mov     edx, 1C2h; void *
0x180016338  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001633d  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180016342  mov     ebx, eax
0x180016344  lea     rdx, [rcx-1]
0x180016348  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001634c  ja      short loc_180016354
0x18001634e  call    cs:__imp_CloseHandle
0x180016354  mov     eax, ebx
0x180016356  jmp     short loc_1800163D5
0x180016358  xor     edx, edx; Token
0x18001635a  xor     ecx, ecx; Thread
0x18001635c  call    cs:__imp_SetThreadToken
0x180016362  test    eax, eax
0x180016364  jnz     short loc_18001638A
0x180016366  mov     rcx, [rsp+28h]; this
0x18001636b  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180016372  mov     edx, 1C6h; void *
0x180016377  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001637c  lea     rcx, [rsp+28h+TokenHandle]
0x180016381  mov     ebx, eax
0x180016383  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180016388  jmp     short loc_180016354
0x18001638a  mov     rbx, [rdi]
0x18001638d  xor     ecx, ecx
0x18001638f  mov     rsi, [rsp+28h+TokenHandle]
0x180016394  mov     [rsp+28h+TokenHandle], rcx
0x180016399  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001639d  jz      short loc_1800163C0
0x18001639f  lea     rcx, [rsp+28h+arg_10]; this
0x1800163a4  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800163a9  mov     rcx, rbx; hObject
0x1800163ac  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x1800163b1  lea     rcx, [rsp+28h+arg_10]; this
0x1800163b6  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800163bb  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x1800163c0  lea     rax, [rcx-1]
0x1800163c4  mov     [rdi], rsi
0x1800163c7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800163cb  ja      short loc_1800163D3
0x1800163cd  call    cs:__imp_CloseHandle
0x1800163d3  xor     eax, eax
0x1800163d5  mov     rbx, [rsp+28h+arg_8]
0x1800163da  mov     rsi, [rsp+28h+arg_18]
0x1800163df  add     rsp, 20h
0x1800163e3  pop     rdi
0x1800163e4  retn
```
