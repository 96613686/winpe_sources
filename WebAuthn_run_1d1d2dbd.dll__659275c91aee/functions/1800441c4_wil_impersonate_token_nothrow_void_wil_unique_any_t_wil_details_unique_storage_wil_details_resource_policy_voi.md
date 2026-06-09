# wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)

- ea: `0x1800441c4`
- end: `0x18004426c`
- name: `?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z`
- size: `168`
- prototype: `__int64 __fastcall(HANDLE Token)`
- caller_count: `7`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180043f84`
- `0x18006f750`
- `0x18009f1c0`
- `0x18009f958`
- `0x1800a8a78`
- `0x18010f334`
- `0x18011a3cc`

## callees

- `0x18001e824`
- `0x180036dc8`
- `0x1800441c4`
- `0x1800709a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044200`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044200`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800441f6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800441f6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180044219`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180044219`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800441dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800441dd`

## string_xrefs

- `0x18004422d`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::impersonate_token_nothrow(HANDLE Token, __int64 a2)
{
  HANDLE CurrentThread; // rax
  const char *v5; // r9
  __int64 v6; // rdx
  unsigned int LastError; // ebx
  void *v8; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *TokenHandle; // [rsp+40h] [rbp+18h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) || GetLastError() == 1008 )
  {
    if ( SetThreadToken(0, Token) )
    {
      v8 = TokenHandle;
      TokenHandle = 0;
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::reset(
        a2,
        v8);
      LastError = 0;
      goto LABEL_8;
    }
    v6 = 454;
  }
  else
  {
    v6 = 450;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v6,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                v5);
LABEL_8:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x1800441c4  mov     [rsp+arg_0], rbx
0x1800441c9  push    rdi
0x1800441ca  sub     rsp, 20h
0x1800441ce  mov     rbx, rdx
0x1800441d1  mov     [rsp+28h+TokenHandle], 0
0x1800441da  mov     rdi, rcx
0x1800441dd  call    cs:__imp_GetCurrentThread
0x1800441e3  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800441e8  mov     edx, 0F01FFh; DesiredAccess
0x1800441ed  mov     rcx, rax; ThreadHandle
0x1800441f0  mov     r8d, 1; OpenAsSelf
0x1800441f6  call    cs:__imp_OpenThreadToken
0x1800441fc  test    eax, eax
0x1800441fe  jnz     short loc_180044214
0x180044200  call    cs:__imp_GetLastError
0x180044206  cmp     eax, 3F0h
0x18004420b  jz      short loc_180044214
0x18004420d  mov     edx, 1C2h
0x180044212  jmp     short loc_180044228
0x180044214  mov     rdx, rdi; Token
0x180044217  xor     ecx, ecx; Thread
0x180044219  call    cs:__imp_SetThreadToken
0x18004421f  test    eax, eax
0x180044221  jnz     short loc_18004423D
0x180044223  mov     edx, 1C6h; void *
0x180044228  mov     rcx, [rsp+28h]; this
0x18004422d  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180044234  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180044239  mov     ebx, eax
0x18004423b  jmp     short loc_180044255
0x18004423d  mov     rdx, [rsp+28h+TokenHandle]
0x180044242  mov     rcx, rbx
0x180044245  mov     [rsp+28h+TokenHandle], 0
0x18004424e  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::reset(void *)
0x180044253  xor     ebx, ebx
0x180044255  lea     rcx, [rsp+28h+TokenHandle]
0x18004425a  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004425f  mov     eax, ebx
0x180044261  mov     rbx, [rsp+28h+arg_0]
0x180044266  add     rsp, 20h
0x18004426a  pop     rdi
0x18004426b  retn
```
