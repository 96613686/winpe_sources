# wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)

- ea: `0x18001aa8c`
- end: `0x18001ab69`
- name: `?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001aa30`

## callees

- `0x180011984`
- `0x180011c34`
- `0x180011dfc`
- `0x18001916c`
- `0x1800191b0`
- `0x18001aa8c`
- `0x18001ab7c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001aacf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001aacf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001aab6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001aab6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001aaf1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001aaf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aad9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aad9`

## string_xrefs

- `0x18001ab05`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

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
0x18001aa8c  mov     rax, rsp
0x18001aa8f  mov     [rax+10h], rbx
0x18001aa93  mov     [rax+20h], rsi
0x18001aa97  mov     [rax+8], rcx
0x18001aa9b  push    rdi
0x18001aa9c  sub     rsp, 20h
0x18001aaa0  mov     rdi, rdx
0x18001aaa3  mov     qword ptr [rax+8], 0
0x18001aaab  xor     edx, edx
0x18001aaad  lea     rcx, [rax+8]
0x18001aab1  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001aab6  call    cs:__imp_GetCurrentThread
0x18001aabc  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18001aac1  mov     edx, 0F01FFh; DesiredAccess
0x18001aac6  mov     rcx, rax; ThreadHandle
0x18001aac9  mov     r8d, 1; OpenAsSelf
0x18001aacf  call    cs:__imp_OpenThreadToken
0x18001aad5  test    eax, eax
0x18001aad7  jnz     short loc_18001AAED
0x18001aad9  call    cs:__imp_GetLastError
0x18001aadf  cmp     eax, 3F0h
0x18001aae4  jz      short loc_18001AAED
0x18001aae6  mov     edx, 1C2h
0x18001aaeb  jmp     short loc_18001AB00
0x18001aaed  xor     edx, edx; Token
0x18001aaef  xor     ecx, ecx; Thread
0x18001aaf1  call    cs:__imp_SetThreadToken
0x18001aaf7  test    eax, eax
0x18001aaf9  jnz     short loc_18001AB15
0x18001aafb  mov     edx, 1C6h; void *
0x18001ab00  mov     rcx, [rsp+28h]; this
0x18001ab05  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001ab0c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001ab11  mov     ebx, eax
0x18001ab13  jmp     short loc_18001AB4D
0x18001ab15  mov     rbx, [rdi]
0x18001ab18  mov     rsi, [rsp+28h+TokenHandle]
0x18001ab1d  mov     [rsp+28h+TokenHandle], 0
0x18001ab26  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001ab2a  jz      short loc_18001AB48
0x18001ab2c  lea     rcx, [rsp+28h+arg_10]; this
0x18001ab31  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001ab36  mov     rcx, rbx; hObject
0x18001ab39  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x18001ab3e  lea     rcx, [rsp+28h+arg_10]; this
0x18001ab43  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001ab48  mov     [rdi], rsi
0x18001ab4b  xor     ebx, ebx
0x18001ab4d  lea     rcx, [rsp+28h+TokenHandle]
0x18001ab52  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001ab57  mov     rsi, [rsp+28h+arg_18]
0x18001ab5c  mov     eax, ebx
0x18001ab5e  mov     rbx, [rsp+28h+arg_8]
0x18001ab63  add     rsp, 20h
0x18001ab67  pop     rdi
0x18001ab68  retn
```
