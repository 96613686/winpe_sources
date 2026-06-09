# StaleAccountCleanupPolicyEngine::IsStaleAccount(IUserAccount *)

- ea: `0x18001f3f0`
- end: `0x18001f47d`
- name: `?IsStaleAccount@StaleAccountCleanupPolicyEngine@@AEAA_NPEAUIUserAccount@@@Z`
- size: `141`
- prototype: `bool(StaleAccountCleanupPolicyEngine *__hidden this, struct IUserAccount *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f490`

## callees

- `0x18000ccd4`
- `0x180013c1c`
- `0x18001f3f0`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001f40e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001f40e`

## string_xrefs

- `0x18001f444`: `shellcommon\shell\sharedpc\accountmanager\lib\policy\staleaccountcleanuppolicyengine.cpp`

## pseudocode

```c
bool __fastcall StaleAccountCleanupPolicyEngine::IsStaleAccount(
        StaleAccountCleanupPolicyEngine *this,
        struct IUserAccount *a2)
{
  __int64 v4; // rax
  int v5; // eax
  const struct _FILETIME *v6; // rdx
  unsigned __int64 v7; // rax
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp+10h] BYREF
  __int64 v12; // [rsp+40h] [rbp+18h] BYREF

  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v4 = *(_QWORD *)a2;
  v12 = 0;
  v5 = (*(__int64 (__fastcall **)(struct IUserAccount *, __int64 *))(v4 + 48))(a2, &v12);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x49,
      (int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\policy\\staleaccountcleanuppolicyengine.cpp",
      (const char *)(unsigned int)v5,
      v9);
  v7 = wil::FileTime::ToInt64((wil::FileTime *)&SystemTimeAsFileTime, v6);
  return v7 > v12 + *((_QWORD *)this + 9);
}

```

## disassembly

```asm
0x18001f3f0  mov     [rsp+arg_0], rbx
0x18001f3f5  push    rdi; int
0x18001f3f6  sub     rsp, 20h
0x18001f3fa  mov     rdi, rcx
0x18001f3fd  mov     qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18001f406  lea     rcx, [rsp+28h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001f40b  mov     rbx, rdx
0x18001f40e  call    cs:__imp_GetSystemTimeAsFileTime
0x18001f414  mov     rax, qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime]
0x18001f419  lea     rdx, [rsp+28h+arg_10]
0x18001f41e  mov     qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001f423  mov     rcx, rbx
0x18001f426  mov     rax, [rbx]
0x18001f429  mov     [rsp+28h+arg_10], 0
0x18001f432  mov     rax, [rax+30h]
0x18001f436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f43b  test    eax, eax
0x18001f43d  jns     short loc_18001F459
0x18001f43f  mov     rcx, [rsp+28h]; this
0x18001f444  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\sharedpc\\accountma"...
0x18001f44b  mov     r9d, eax; char *
0x18001f44e  mov     edx, 49h ; 'I'; void *
0x18001f453  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001f459  lea     rcx, [rsp+28h+SystemTimeAsFileTime]; this
0x18001f45e  call    ?ToInt64@FileTime@wil@@YA_KAEBU_FILETIME@@@Z; wil::FileTime::ToInt64(_FILETIME const &)
0x18001f463  mov     rdx, [rdi+48h]
0x18001f467  add     rdx, [rsp+28h+arg_10]
0x18001f46c  mov     rbx, [rsp+28h+arg_0]
0x18001f471  cmp     rax, rdx
0x18001f474  setnbe  al
0x18001f477  add     rsp, 20h
0x18001f47b  pop     rdi
0x18001f47c  retn
```
