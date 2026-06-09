# Windows::Internal::CapabilityAccess::Private::GetCallerTokenFromComCall(void)

- ea: `0x180040d7c`
- end: `0x180040e45`
- name: `?GetCallerTokenFromComCall@Private@CapabilityAccess@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ`
- size: `201`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `31`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003f9c8`
- `0x180043b0c`
- `0x180043b94`
- `0x18006ae88`
- `0x18006c6f4`
- `0x180090970`
- `0x180093450`
- `0x1800936e0`
- `0x180093de0`
- `0x1800942e0`
- `0x1800948e0`
- `0x180094b60`
- `0x180094e70`
- `0x1800954a4`
- `0x1800956b0`
- `0x180095a80`
- `0x180095d30`
- `0x180095f90`
- `0x180096170`
- `0x180096290`
- `0x180096840`
- `0x180096c10`
- `0x180098720`
- `0x1800988e0`
- `0x180098aa0`
- `0x180098eb0`
- `0x1800992f0`
- `0x180099730`
- `0x18009b1a0`
- `0x18009d554`
- `0x1800b1c7c`

## callees

- `0x18002392c`
- `0x180039e9c`
- `0x18003f4a0`
- `0x180040d7c`
- `0x1800464d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180040df6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180040df6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180040dda`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180040dda`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180040e31`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180040e31`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180040d89`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180040d89`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void **__fastcall Windows::Internal::CapabilityAccess::Private::GetCallerTokenFromComCall(void **a1)
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
        (void *)0x97,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
        (const char *)(unsigned int)v2,
        v6);
    TokenHandle = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x9F,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
        v4);
    *a1 = TokenHandle;
    TokenHandle = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    CoRevertToSelf();
  }
  return a1;
}

```

## disassembly

```asm
0x180040d7c  mov     [rsp+arg_0], rbx
0x180040d81  push    rdi
0x180040d82  sub     rsp, 30h
0x180040d86  mov     rbx, rcx
0x180040d89  call    cs:__imp_CoImpersonateClient
0x180040d8f  cmp     eax, 80010117h
0x180040d94  jnz     short loc_180040DA2
0x180040d96  mov     qword ptr [rbx], 0
0x180040d9d  jmp     loc_180040E37
0x180040da2  mov     rcx, [rsp+38h]; this
0x180040da7  test    eax, eax
0x180040da9  jns     short loc_180040DC0
0x180040dab  mov     r9d, eax; char *
0x180040dae  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180040db5  mov     edx, 97h; void *
0x180040dba  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180040dc0  mov     [rsp+38h+arg_9], 1
0x180040dc5  mov     [rsp+38h+TokenHandle], 0
0x180040dce  xor     edx, edx
0x180040dd0  lea     rcx, [rsp+38h+TokenHandle]
0x180040dd5  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180040dda  call    cs:__imp_GetCurrentThread
0x180040de0  mov     rdi, [rsp+38h]
0x180040de5  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180040dea  mov     edx, 8; DesiredAccess
0x180040def  lea     r8d, [rdx-7]; OpenAsSelf
0x180040df3  mov     rcx, rax; ThreadHandle
0x180040df6  call    cs:__imp_OpenThreadToken
0x180040dfc  test    eax, eax
0x180040dfe  jnz     short loc_180040E15
0x180040e00  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180040e07  mov     edx, 9Fh; void *
0x180040e0c  mov     rcx, rdi; this
0x180040e0f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180040e15  mov     rax, [rsp+38h+TokenHandle]
0x180040e1a  mov     [rbx], rax
0x180040e1d  mov     [rsp+38h+TokenHandle], 0
0x180040e26  lea     rcx, [rsp+38h+TokenHandle]
0x180040e2b  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180040e30  nop
0x180040e31  call    cs:__imp_CoRevertToSelf
0x180040e37  mov     rax, rbx
0x180040e3a  mov     rbx, [rsp+38h+arg_0]
0x180040e3f  add     rsp, 30h
0x180040e43  pop     rdi
0x180040e44  retn
```
