# CodeIntegrity::Management::detail::TransactionHandle<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,CodeIntegrity::Management::detail::DeleteTag>::commit(void)

- ea: `0x18001590c`
- end: `0x180015956`
- name: `?commit@?$TransactionHandle@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@UDeleteTag@detail@Management@CodeIntegrity@@@detail@Management@CodeIntegrity@@QEBAXXZ`
- size: `74`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800128f0`

## callees

- `0x18000d470`
- `0x18001590c`
- `0x180021a38`

## string_xrefs

- `0x180015938`: `onecore\base\ci\management\dll\policymgmt.cpp`

## pseudocode

```c
void __fastcall CodeIntegrity::Management::detail::TransactionHandle<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,CodeIntegrity::Management::detail::DeleteTag>::commit(
        __int64 a1)
{
  __int64 v2; // rcx
  int v3; // eax
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = *(_QWORD *)a1;
  if ( v2 && *(_DWORD *)(a1 + 8) == 1 )
  {
    try
    {
      v3 = SIPolicyPmDeletePolicyCommit(v2);
      if ( v3 < 0 )
        wil::details::in1diag3::_Throw_NtStatus(
          retaddr,
          (void *)0x1C1,
          (int)"onecore\\base\\ci\\management\\dll\\policymgmt.cpp",
          (const char *)(unsigned int)v3,
          v4);
      *(_DWORD *)(a1 + 8) = 3;
    }
    catch ( ... )
    {
      *(_DWORD *)(a1 + 8) = 2;
      throw;
    }
  }
}

```

## disassembly

```asm
0x18001590c  mov     [rsp+arg_0], rcx
0x180015911  push    rbx; int
0x180015912  sub     rsp, 20h
0x180015916  mov     rbx, rcx
0x180015919  mov     rcx, [rcx]
0x18001591c  test    rcx, rcx
0x18001591f  jz      short loc_180015950
0x180015921  cmp     dword ptr [rbx+8], 1
0x180015925  jnz     short loc_180015950
0x180015927  call    SIPolicyPmDeletePolicyCommit
0x18001592c  mov     rcx, [rsp+28h]; this
0x180015931  test    eax, eax
0x180015933  jns     short loc_180015949
0x180015935  mov     r9d, eax; char *
0x180015938  lea     r8, aOnecoreBaseCiM_3; "onecore\\base\\ci\\management\\dll\\pol"...
0x18001593f  mov     edx, 1C1h; void *
0x180015944  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180015949  mov     dword ptr [rbx+8], 3
0x180015950  add     rsp, 20h
0x180015954  pop     rbx
0x180015955  retn
```
