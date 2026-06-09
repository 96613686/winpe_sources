# wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)

- ea: `0x180035688`
- end: `0x18003577b`
- name: `?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z`
- size: `243`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180034d88`

## callees

- `0x1800108f4`
- `0x180010d24`
- `0x180012714`
- `0x180019d4c`
- `0x18001dcf4`
- `0x1800350f0`
- `0x180035688`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800356d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800356d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800356b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800356b2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800356cb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800356cb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180035700`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180035700`

## string_xrefs

- `0x1800356e7`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18003570f`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall wil::impersonate_token_nothrow(__int64 a1, void **a2)
{
  HANDLE CurrentThread; // rax
  const char *v4; // r9
  unsigned int LastError; // ebx
  const char *v6; // r9
  void *v7; // rsi
  void *v8; // rbx
  void *v9; // rdx
  void *TokenHandle[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v13; // [rsp+40h] [rbp+8h] BYREF

  v13 = a1;
  TokenHandle[0] = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    TokenHandle,
    0);
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, TokenHandle) || GetLastError() == 1008 )
  {
    if ( SetThreadToken(0, 0) )
    {
      v7 = TokenHandle[0];
      TokenHandle[0] = 0;
      v8 = *a2;
      if ( *a2 != (void *)-1LL )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v13);
        wil::details::RevertImpersonateToken(v8, v9);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v13);
      }
      *a2 = v7;
      LastError = 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x1C6,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                    v6);
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1C2,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v4);
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x180035688  mov     rax, rsp
0x18003568b  mov     [rax+10h], rbx
0x18003568f  mov     [rax+18h], rsi
0x180035693  mov     [rax+8], rcx
0x180035697  push    rdi
0x180035698  sub     rsp, 30h
0x18003569c  mov     rdi, rdx
0x18003569f  mov     qword ptr [rax-18h], 0
0x1800356a7  xor     edx, edx
0x1800356a9  lea     rcx, [rax-18h]
0x1800356ad  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800356b2  call    cs:__imp_GetCurrentThread
0x1800356b8  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x1800356bd  mov     edx, 0F01FFh; DesiredAccess
0x1800356c2  mov     r8d, 1; OpenAsSelf
0x1800356c8  mov     rcx, rax; ThreadHandle
0x1800356cb  call    cs:__imp_OpenThreadToken
0x1800356d1  test    eax, eax
0x1800356d3  jnz     short loc_1800356FC
0x1800356d5  call    cs:__imp_GetLastError
0x1800356db  cmp     eax, 3F0h
0x1800356e0  jz      short loc_1800356FC
0x1800356e2  mov     rcx, [rsp+38h]; this
0x1800356e7  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800356ee  mov     edx, 1C2h; void *
0x1800356f3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800356f8  mov     ebx, eax
0x1800356fa  jmp     short loc_18003575F
0x1800356fc  xor     edx, edx; Token
0x1800356fe  xor     ecx, ecx; Thread
0x180035700  call    cs:__imp_SetThreadToken
0x180035706  test    eax, eax
0x180035708  jnz     short loc_180035725
0x18003570a  mov     rcx, [rsp+38h]; this
0x18003570f  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180035716  mov     edx, 1C6h; void *
0x18003571b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180035720  nop
0x180035721  mov     ebx, eax
0x180035723  jmp     short loc_18003575F
0x180035725  mov     rsi, [rsp+38h+TokenHandle]
0x18003572a  mov     [rsp+38h+TokenHandle], 0
0x180035733  mov     rbx, [rdi]
0x180035736  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18003573a  jz      short loc_18003575A
0x18003573c  lea     rcx, [rsp+38h+arg_0]; this
0x180035741  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180035746  nop
0x180035747  mov     rcx, rbx; hObject
0x18003574a  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x18003574f  nop
0x180035750  lea     rcx, [rsp+38h+arg_0]; this
0x180035755  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003575a  mov     [rdi], rsi
0x18003575d  xor     ebx, ebx
0x18003575f  lea     rcx, [rsp+38h+TokenHandle]
0x180035764  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180035769  mov     eax, ebx
0x18003576b  mov     rbx, [rsp+38h+arg_8]
0x180035770  mov     rsi, [rsp+38h+arg_10]
0x180035775  add     rsp, 30h
0x180035779  pop     rdi
0x18003577a  retn
```
