# wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)

- ea: `0x180061d58`
- end: `0x180061ea4`
- name: `?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z`
- size: `332`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180060ff0`
- `0x1800611fc`
- `0x180061b90`
- `0x180061c20`
- `0x180061cd0`
- `0x1800abd98`
- `0x1800acbec`
- `0x1800ace50`
- `0x1800ad888`
- `0x1800adae8`
- `0x1800ae814`
- `0x180263264`

## callees

- `0x18000e8dc`
- `0x180061d58`
- `0x180061eac`
- `0x1800af2d0`
- `0x1800af2f0`
- `0x1800bee58`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061daf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061daf`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180061dc0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180061dc0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180061d8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180061d8c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180061da5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180061da5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061e67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061e6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061e98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061e67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061e6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061e98`

## string_xrefs

- `0x180061e0e`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x180061e39`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::impersonate_token_nothrow(__int64 a1, void **a2)
{
  HANDLE CurrentThread; // rax
  const char *v4; // r9
  const char *v5; // r9
  void *v6; // rsi
  void *v7; // rbx
  unsigned int LastError; // ebx
  void *v10; // rcx
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
    v10 = TokenHandle;
    if ( (char *)TokenHandle - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      return LastError;
LABEL_10:
    CloseHandle(v10);
    return LastError;
  }
  if ( !SetThreadToken(0, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1C6,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                  v5);
    v10 = TokenHandle;
    if ( (char *)TokenHandle - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      return LastError;
    goto LABEL_10;
  }
  v6 = TokenHandle;
  TokenHandle = 0;
  v7 = *a2;
  if ( *a2 != (void *)-1LL )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v14);
    wil::details::RevertImpersonateToken(v7, v11);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v14);
  }
  *a2 = v6;
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x180061d58  mov     rax, rsp
0x180061d5b  mov     [rax+10h], rbx
0x180061d5f  mov     [rax+20h], rsi
0x180061d63  mov     [rax+8], rcx
0x180061d67  push    rdi
0x180061d68  sub     rsp, 20h
0x180061d6c  mov     rdi, rdx
0x180061d6f  xor     ebx, ebx
0x180061d71  mov     [rax+8], rbx
0x180061d75  mov     rcx, [rax+8]; hObject
0x180061d79  lea     rax, [rcx-1]
0x180061d7d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180061d81  jbe     loc_180061E5D
0x180061d87  mov     [rsp+28h+TokenHandle], rbx
0x180061d8c  call    cs:__imp_GetCurrentThread
0x180061d92  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180061d97  mov     edx, 0F01FFh; DesiredAccess
0x180061d9c  mov     r8d, 1; OpenAsSelf
0x180061da2  mov     rcx, rax; ThreadHandle
0x180061da5  call    cs:__imp_OpenThreadToken
0x180061dab  test    eax, eax
0x180061dad  jnz     short loc_180061DBC
0x180061daf  call    cs:__imp_GetLastError
0x180061db5  cmp     eax, 3F0h
0x180061dba  jnz     short loc_180061E09
0x180061dbc  xor     edx, edx; Token
0x180061dbe  xor     ecx, ecx; Thread
0x180061dc0  call    cs:__imp_SetThreadToken
0x180061dc6  test    eax, eax
0x180061dc8  jz      short loc_180061E34
0x180061dca  mov     rsi, [rsp+28h+TokenHandle]
0x180061dcf  mov     [rsp+28h+TokenHandle], rbx
0x180061dd4  mov     rbx, [rdi]
0x180061dd7  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180061ddb  jnz     loc_180061E77
0x180061de1  mov     [rdi], rsi
0x180061de4  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180061de9  lea     rax, [rcx-1]
0x180061ded  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180061df1  jbe     loc_180061E98
0x180061df7  xor     eax, eax
0x180061df9  mov     rbx, [rsp+28h+arg_8]
0x180061dfe  mov     rsi, [rsp+28h+arg_18]
0x180061e03  add     rsp, 20h
0x180061e07  pop     rdi
0x180061e08  retn
0x180061e09  mov     rcx, [rsp+28h]; this
0x180061e0e  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180061e15  mov     edx, 1C2h; void *
0x180061e1a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180061e1f  mov     ebx, eax
0x180061e21  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180061e26  lea     rdx, [rcx-1]
0x180061e2a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180061e2e  jbe     short loc_180061E67
0x180061e30  mov     eax, ebx
0x180061e32  jmp     short loc_180061DF9
0x180061e34  mov     rcx, [rsp+28h]; this
0x180061e39  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180061e40  mov     edx, 1C6h; void *
0x180061e45  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180061e4a  mov     ebx, eax
0x180061e4c  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180061e51  lea     rdx, [rcx-1]
0x180061e55  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180061e59  jbe     short loc_180061E6F
0x180061e5b  jmp     short loc_180061E30
0x180061e5d  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x180061e62  jmp     loc_180061D87
0x180061e67  call    cs:__imp_CloseHandle
0x180061e6d  jmp     short loc_180061E30
0x180061e6f  call    cs:__imp_CloseHandle
0x180061e75  jmp     short loc_180061E5B
0x180061e77  lea     rcx, [rsp+28h+arg_10]; this
0x180061e7c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180061e81  mov     rcx, rbx; Token
0x180061e84  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x180061e89  lea     rcx, [rsp+28h+arg_10]; this
0x180061e8e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180061e93  jmp     loc_180061DE1
0x180061e98  call    cs:__imp_CloseHandle
0x180061e9e  jmp     loc_180061DF7
```
