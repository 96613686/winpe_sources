# _anonymous_namespace_::TryImpersonateClient

- ea: `0x180011578`
- end: `0x180011619`
- name: `_anonymous_namespace_::TryImpersonateClient`
- size: `161`
- prototype: `void **__fastcall(void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800114c4`

## callees

- `0x180011578`
- `0x18002a514`
- `0x180031540`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800115c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800115c3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800115da`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800115da`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180011581`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180011581`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001160a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001160a`

## string_xrefs

- `0x1800115a3`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerutils.cpp`
- `0x1800115e9`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerutils.cpp`

## pseudocode

```c
void **__fastcall anonymous_namespace_::TryImpersonateClient(void **a1)
{
  HRESULT v2; // eax
  HANDLE CurrentThread; // rax
  const char *v4; // r9
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  v2 = CoImpersonateClient();
  if ( v2 == -2147417833 )
  {
    *a1 = 0;
  }
  else
  {
    if ( v2 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x46,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerutils.cpp",
        (const char *)(unsigned int)v2,
        v6);
    TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x50,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerutils.cpp",
        v4);
    *a1 = TokenHandle;
    TokenHandle = 0;
    CoRevertToSelf();
  }
  return a1;
}

```

## disassembly

```asm
0x180011578  push    rbx
0x18001157a  sub     rsp, 30h
0x18001157e  mov     rbx, rcx
0x180011581  call    cs:__imp_CoImpersonateClient
0x180011587  cmp     eax, 80010117h
0x18001158c  jnz     short loc_180011597
0x18001158e  mov     qword ptr [rbx], 0
0x180011595  jmp     short loc_180011610
0x180011597  mov     rcx, [rsp+38h]; this
0x18001159c  test    eax, eax
0x18001159e  jns     short loc_1800115B5
0x1800115a0  mov     r9d, eax; char *
0x1800115a3  lea     r8, aOnecoreWindows_22; "onecore\\windows\\accessibletech\\uiama"...
0x1800115aa  mov     edx, 46h ; 'F'; void *
0x1800115af  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800115b5  mov     [rsp+38h+arg_9], 1
0x1800115ba  mov     [rsp+38h+TokenHandle], 0
0x1800115c3  call    cs:__imp_GetCurrentThread
0x1800115c9  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x1800115ce  mov     edx, 8; DesiredAccess
0x1800115d3  lea     r8d, [rdx-7]; OpenAsSelf
0x1800115d7  mov     rcx, rax; ThreadHandle
0x1800115da  call    cs:__imp_OpenThreadToken
0x1800115e0  mov     rcx, [rsp+38h]; this
0x1800115e5  test    eax, eax
0x1800115e7  jnz     short loc_1800115F9
0x1800115e9  lea     r8, aOnecoreWindows_22; "onecore\\windows\\accessibletech\\uiama"...
0x1800115f0  lea     edx, [rax+50h]; void *
0x1800115f3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800115f9  mov     rax, [rsp+38h+TokenHandle]
0x1800115fe  mov     [rbx], rax
0x180011601  mov     [rsp+38h+TokenHandle], 0
0x18001160a  call    cs:__imp_CoRevertToSelf
0x180011610  mov     rax, rbx
0x180011613  add     rsp, 30h
0x180011617  pop     rbx
0x180011618  retn
```
