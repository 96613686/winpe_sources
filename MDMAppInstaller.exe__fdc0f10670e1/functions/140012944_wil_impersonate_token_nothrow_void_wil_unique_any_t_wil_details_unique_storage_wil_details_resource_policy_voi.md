# wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)

- ea: `0x140012944`
- end: `0x140012a16`
- name: `?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z`
- size: `210`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140012c58`

## callees

- `0x1400039f0`
- `0x140003dd0`
- `0x140005684`
- `0x140009270`
- `0x1400103e8`
- `0x140012944`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x14001297c`
- `ADVAPI32!OpenThreadToken` at `0x14001297c`
- `ADVAPI32!SetThreadToken` at `0x14001299e`
- `ADVAPI32!SetThreadToken` at `0x14001299e`
- `KERNEL32!GetCurrentThread` at `0x140012963`
- `KERNEL32!GetCurrentThread` at `0x140012963`
- `KERNEL32!GetLastError` at `0x140012986`
- `KERNEL32!GetLastError` at `0x140012986`

## string_xrefs

- `0x1400129b2`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

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
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) && GetLastError() != 1008 )
  {
    v5 = 450;
LABEL_6:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v5,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
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
0x140012944  mov     rax, rsp
0x140012947  mov     [rax+10h], rbx
0x14001294b  mov     [rax+20h], rsi
0x14001294f  mov     [rax+8], rcx
0x140012953  push    rdi
0x140012954  sub     rsp, 20h
0x140012958  mov     rdi, rdx
0x14001295b  mov     qword ptr [rax+8], 0
0x140012963  call    cs:__imp_GetCurrentThread
0x140012969  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x14001296e  mov     edx, 0F01FFh; DesiredAccess
0x140012973  mov     rcx, rax; ThreadHandle
0x140012976  mov     r8d, 1; OpenAsSelf
0x14001297c  call    cs:__imp_OpenThreadToken
0x140012982  test    eax, eax
0x140012984  jnz     short loc_14001299A
0x140012986  call    cs:__imp_GetLastError
0x14001298c  cmp     eax, 3F0h
0x140012991  jz      short loc_14001299A
0x140012993  mov     edx, 1C2h
0x140012998  jmp     short loc_1400129AD
0x14001299a  xor     edx, edx; Token
0x14001299c  xor     ecx, ecx; Thread
0x14001299e  call    cs:__imp_SetThreadToken
0x1400129a4  test    eax, eax
0x1400129a6  jnz     short loc_1400129C2
0x1400129a8  mov     edx, 1C6h; void *
0x1400129ad  mov     rcx, [rsp+28h]; this
0x1400129b2  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400129b9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400129be  mov     ebx, eax
0x1400129c0  jmp     short loc_1400129FA
0x1400129c2  mov     rbx, [rdi]
0x1400129c5  mov     rsi, [rsp+28h+TokenHandle]
0x1400129ca  mov     [rsp+28h+TokenHandle], 0
0x1400129d3  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400129d7  jz      short loc_1400129F5
0x1400129d9  lea     rcx, [rsp+28h+arg_10]; this
0x1400129de  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1400129e3  mov     rcx, rbx; hObject
0x1400129e6  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x1400129eb  lea     rcx, [rsp+28h+arg_10]; this
0x1400129f0  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1400129f5  mov     [rdi], rsi
0x1400129f8  xor     ebx, ebx
0x1400129fa  lea     rcx, [rsp+28h+TokenHandle]
0x1400129ff  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140012a04  mov     rsi, [rsp+28h+arg_18]
0x140012a09  mov     eax, ebx
0x140012a0b  mov     rbx, [rsp+28h+arg_8]
0x140012a10  add     rsp, 20h
0x140012a14  pop     rdi
0x140012a15  retn
```
