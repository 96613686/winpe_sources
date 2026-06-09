# CodeIntegrity::Management::detail::TransactionHandle<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,CodeIntegrity::Management::detail::UpsertTag>::commit(void)

- ea: `0x18001595c`
- end: `0x1800159a6`
- name: `?commit@?$TransactionHandle@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@UUpsertTag@detail@Management@CodeIntegrity@@@detail@Management@CodeIntegrity@@QEBAXXZ`
- size: `74`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800128f0`

## callees

- `0x18000d470`
- `0x18001595c`
- `0x180021e34`

## string_xrefs

- `0x180015988`: `onecore\base\ci\management\dll\policymgmt.cpp`

## pseudocode

```c
void __fastcall CodeIntegrity::Management::detail::TransactionHandle<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,CodeIntegrity::Management::detail::UpsertTag>::commit(
        __int64 a1)
{
  int updated; // eax
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *(_QWORD *)a1 && *(_DWORD *)(a1 + 8) == 1 )
  {
    updated = SIPolicyPmUpdatePolicyCommit();
    if ( updated < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x1B5,
        (unsigned int)"onecore\\base\\ci\\management\\dll\\policymgmt.cpp",
        (const char *)(unsigned int)updated,
        v3);
    *(_DWORD *)(a1 + 8) = 3;
  }
}

```

## disassembly

```asm
0x18001595c  mov     [rsp+arg_0], rcx
0x180015961  push    rbx; int
0x180015962  sub     rsp, 20h
0x180015966  mov     rbx, rcx
0x180015969  mov     rcx, [rcx]
0x18001596c  test    rcx, rcx
0x18001596f  jz      short loc_1800159A0
0x180015971  cmp     dword ptr [rbx+8], 1
0x180015975  jnz     short loc_1800159A0
0x180015977  call    SIPolicyPmUpdatePolicyCommit
0x18001597c  mov     rcx, [rsp+28h]; this
0x180015981  test    eax, eax
0x180015983  jns     short loc_180015999
0x180015985  mov     r9d, eax; char *
0x180015988  lea     r8, aOnecoreBaseCiM_3; "onecore\\base\\ci\\management\\dll\\pol"...
0x18001598f  mov     edx, 1B5h; void *
0x180015994  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180015999  mov     dword ptr [rbx+8], 3
0x1800159a0  add     rsp, 20h
0x1800159a4  pop     rbx
0x1800159a5  retn
```
