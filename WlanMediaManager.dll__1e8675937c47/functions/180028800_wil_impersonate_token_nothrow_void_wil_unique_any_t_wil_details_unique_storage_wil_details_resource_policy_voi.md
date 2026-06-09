# wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)

- ea: `0x180028800`
- end: `0x1800288dd`
- name: `?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z`
- size: `221`
- prototype: `__int64 __fastcall(HANDLE Token, void **)`
- caller_count: `12`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002073c`
- `0x180025370`
- `0x1800253e0`
- `0x180025460`
- `0x1800287a0`
- `0x1800348a0`
- `0x180054020`
- `0x18005413c`
- `0x180054238`
- `0x180068ecc`
- `0x180072150`
- `0x18007cbc0`

## callees

- `0x180007a2c`
- `0x180007d10`
- `0x180009794`
- `0x18000bbf4`
- `0x1800166b0`
- `0x180028800`
- `0x180028984`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002884c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002884c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180028865`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180028865`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180028829`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180028829`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180028842`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180028842`

## string_xrefs

- `0x180028879`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
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
0x180028800  mov     rax, rsp
0x180028803  mov     [rax+8], rbx
0x180028807  mov     [rax+10h], rsi
0x18002880b  push    rdi
0x18002880c  sub     rsp, 20h
0x180028810  mov     rdi, rdx
0x180028813  mov     qword ptr [rax+18h], 0
0x18002881b  mov     rbx, rcx
0x18002881e  xor     edx, edx
0x180028820  lea     rcx, [rax+18h]
0x180028824  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180028829  call    cs:__imp_GetCurrentThread
0x18002882f  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180028834  mov     edx, 0F01FFh; DesiredAccess
0x180028839  mov     rcx, rax; ThreadHandle
0x18002883c  mov     r8d, 1; OpenAsSelf
0x180028842  call    cs:__imp_OpenThreadToken
0x180028848  test    eax, eax
0x18002884a  jnz     short loc_180028860
0x18002884c  call    cs:__imp_GetLastError
0x180028852  cmp     eax, 3F0h
0x180028857  jz      short loc_180028860
0x180028859  mov     edx, 1C2h
0x18002885e  jmp     short loc_180028874
0x180028860  mov     rdx, rbx; Token
0x180028863  xor     ecx, ecx; Thread
0x180028865  call    cs:__imp_SetThreadToken
0x18002886b  test    eax, eax
0x18002886d  jnz     short loc_180028889
0x18002886f  mov     edx, 1C6h; void *
0x180028874  mov     rcx, [rsp+28h]; this
0x180028879  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180028880  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180028885  mov     ebx, eax
0x180028887  jmp     short loc_1800288C1
0x180028889  mov     rbx, [rdi]
0x18002888c  mov     rsi, [rsp+28h+TokenHandle]
0x180028891  mov     [rsp+28h+TokenHandle], 0
0x18002889a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18002889e  jz      short loc_1800288BC
0x1800288a0  lea     rcx, [rsp+28h+arg_18]; this
0x1800288a5  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800288aa  mov     rcx, rbx; hObject
0x1800288ad  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x1800288b2  lea     rcx, [rsp+28h+arg_18]; this
0x1800288b7  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800288bc  mov     [rdi], rsi
0x1800288bf  xor     ebx, ebx
0x1800288c1  lea     rcx, [rsp+28h+TokenHandle]
0x1800288c6  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800288cb  mov     rsi, [rsp+28h+arg_8]
0x1800288d0  mov     eax, ebx
0x1800288d2  mov     rbx, [rsp+28h+arg_0]
0x1800288d7  add     rsp, 20h
0x1800288db  pop     rdi
0x1800288dc  retn
```
