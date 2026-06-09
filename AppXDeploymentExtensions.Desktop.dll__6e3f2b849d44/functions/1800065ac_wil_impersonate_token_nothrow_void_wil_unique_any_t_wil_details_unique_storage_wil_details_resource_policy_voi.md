# wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)

- ea: `0x1800065ac`
- end: `0x180006694`
- name: `?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z`
- size: `232`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180006564`
- `0x1800ef318`
- `0x180129af0`

## callees

- `0x1800060d8`
- `0x1800065ac`
- `0x18000669c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006635`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006635`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800065e1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800065e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800065c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800065c2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800065f5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800065f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006678`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006686`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006678`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006686`

## string_xrefs

- `0x18000660f`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::impersonate_token_nothrow(__int64 a1, __int64 a2)
{
  HANDLE CurrentThread; // rax
  const char *v4; // r9
  __int64 v5; // rdx
  unsigned int LastError; // ebx
  void *v8; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) && GetLastError() != 1008 )
  {
    v5 = 450;
    goto LABEL_4;
  }
  if ( !SetThreadToken(0, 0) )
  {
    v5 = 454;
LABEL_4:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v5,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                  v4);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return LastError;
  }
  v8 = TokenHandle;
  TokenHandle = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::reset(
    a2,
    v8);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x1800065ac  mov     [rsp+TokenHandle], rcx
0x1800065b1  push    rbx
0x1800065b2  sub     rsp, 20h
0x1800065b6  mov     rbx, rdx
0x1800065b9  mov     [rsp+28h+TokenHandle], 0
0x1800065c2  call    cs:__imp_GetCurrentThread
0x1800065c9  nop     dword ptr [rax+rax+00h]
0x1800065ce  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800065d3  mov     edx, 0F01FFh; DesiredAccess
0x1800065d8  mov     rcx, rax; ThreadHandle
0x1800065db  mov     r8d, 1; OpenAsSelf
0x1800065e1  call    cs:__imp_OpenThreadToken
0x1800065e8  nop     dword ptr [rax+rax+00h]
0x1800065ed  test    eax, eax
0x1800065ef  jz      short loc_180006635
0x1800065f1  xor     edx, edx; Token
0x1800065f3  xor     ecx, ecx; Thread
0x1800065f5  call    cs:__imp_SetThreadToken
0x1800065fc  nop     dword ptr [rax+rax+00h]
0x180006601  test    eax, eax
0x180006603  jnz     short loc_18000664F
0x180006605  mov     edx, 1C6h; void *
0x18000660a  mov     rcx, [rsp+28h]; this
0x18000660f  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006616  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000661b  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180006620  mov     ebx, eax
0x180006622  lea     rdx, [rcx-1]
0x180006626  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000662a  jbe     short loc_180006678
0x18000662c  mov     eax, ebx
0x18000662e  add     rsp, 20h
0x180006632  pop     rbx
0x180006633  retn
0x180006635  call    cs:__imp_GetLastError
0x18000663c  nop     dword ptr [rax+rax+00h]
0x180006641  cmp     eax, 3F0h
0x180006646  jz      short loc_1800065F1
0x180006648  mov     edx, 1C2h
0x18000664d  jmp     short loc_18000660A
0x18000664f  mov     rdx, [rsp+28h+TokenHandle]
0x180006654  mov     rcx, rbx
0x180006657  mov     [rsp+28h+TokenHandle], 0
0x180006660  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::reset(void *)
0x180006665  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18000666a  lea     rax, [rcx-1]
0x18000666e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180006672  jbe     short loc_180006686
0x180006674  xor     eax, eax
0x180006676  jmp     short loc_18000662E
0x180006678  call    cs:__imp_CloseHandle
0x18000667f  nop     dword ptr [rax+rax+00h]
0x180006684  jmp     short loc_18000662C
0x180006686  call    cs:__imp_CloseHandle
0x18000668d  nop     dword ptr [rax+rax+00h]
0x180006692  jmp     short loc_180006674
```
