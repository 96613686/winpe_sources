# wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)

- ea: `0x180038e34`
- end: `0x180038f2a`
- name: `?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180038dd8`

## callees

- `0x18002570c`
- `0x180038e34`
- `0x180077e10`
- `0x180077e30`
- `0x1800fc644`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038e76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038e76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038ef7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038f22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038ef7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038f22`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180038e6c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180038e6c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180038e53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180038e53`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180038e87`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180038e87`

## string_xrefs

- `0x180038ecf`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::impersonate_token_nothrow(__int64 a1, void **a2)
{
  HANDLE CurrentThread; // rax
  const char *v4; // r9
  void *v5; // rbx
  char *v6; // rcx
  void *v7; // rsi
  __int64 v9; // rdx
  unsigned int LastError; // ebx
  void *v11; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF
  char v14; // [rsp+40h] [rbp+18h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) || GetLastError() == 1008 )
  {
    if ( SetThreadToken(0, 0) )
    {
      v5 = *a2;
      v6 = 0;
      v7 = TokenHandle;
      TokenHandle = 0;
      if ( v5 != (void *)-1LL )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v14);
        wil::details::RevertImpersonateToken(v5, v11);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v14);
        v6 = (char *)TokenHandle;
      }
      *a2 = v7;
      if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v6);
      return 0;
    }
    v9 = 454;
  }
  else
  {
    v9 = 450;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v9,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                v4);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x180038e34  mov     rax, rsp
0x180038e37  mov     [rax+10h], rbx
0x180038e3b  mov     [rax+20h], rsi
0x180038e3f  mov     [rax+8], rcx
0x180038e43  push    rdi
0x180038e44  sub     rsp, 20h
0x180038e48  mov     rdi, rdx
0x180038e4b  mov     qword ptr [rax+8], 0
0x180038e53  call    cs:__imp_GetCurrentThread
0x180038e59  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180038e5e  mov     edx, 0F01FFh; DesiredAccess
0x180038e63  mov     rcx, rax; ThreadHandle
0x180038e66  mov     r8d, 1; OpenAsSelf
0x180038e6c  call    cs:__imp_OpenThreadToken
0x180038e72  test    eax, eax
0x180038e74  jnz     short loc_180038E83
0x180038e76  call    cs:__imp_GetLastError
0x180038e7c  cmp     eax, 3F0h
0x180038e81  jnz     short loc_180038EC5
0x180038e83  xor     edx, edx; Token
0x180038e85  xor     ecx, ecx; Thread
0x180038e87  call    cs:__imp_SetThreadToken
0x180038e8d  test    eax, eax
0x180038e8f  jz      short loc_180038EF0
0x180038e91  mov     rbx, [rdi]
0x180038e94  xor     ecx, ecx; hObject
0x180038e96  mov     rsi, [rsp+28h+TokenHandle]
0x180038e9b  mov     [rsp+28h+TokenHandle], rcx
0x180038ea0  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180038ea4  jnz     short loc_180038EFF
0x180038ea6  lea     rax, [rcx-1]
0x180038eaa  mov     [rdi], rsi
0x180038ead  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180038eb1  jbe     short loc_180038F22
0x180038eb3  xor     eax, eax
0x180038eb5  mov     rbx, [rsp+28h+arg_8]
0x180038eba  mov     rsi, [rsp+28h+arg_18]
0x180038ebf  add     rsp, 20h
0x180038ec3  pop     rdi
0x180038ec4  retn
0x180038ec5  mov     edx, 1C2h; void *
0x180038eca  mov     rcx, [rsp+28h]; this
0x180038ecf  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180038ed6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180038edb  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180038ee0  mov     ebx, eax
0x180038ee2  lea     rdx, [rcx-1]
0x180038ee6  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180038eea  jbe     short loc_180038EF7
0x180038eec  mov     eax, ebx
0x180038eee  jmp     short loc_180038EB5
0x180038ef0  mov     edx, 1C6h
0x180038ef5  jmp     short loc_180038ECA
0x180038ef7  call    cs:__imp_CloseHandle
0x180038efd  jmp     short loc_180038EEC
0x180038eff  lea     rcx, [rsp+28h+arg_10]; this
0x180038f04  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180038f09  mov     rcx, rbx; hObject
0x180038f0c  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x180038f11  lea     rcx, [rsp+28h+arg_10]; this
0x180038f16  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180038f1b  mov     rcx, [rsp+28h+TokenHandle]
0x180038f20  jmp     short loc_180038EA6
0x180038f22  call    cs:__imp_CloseHandle
0x180038f28  jmp     short loc_180038EB3
```
