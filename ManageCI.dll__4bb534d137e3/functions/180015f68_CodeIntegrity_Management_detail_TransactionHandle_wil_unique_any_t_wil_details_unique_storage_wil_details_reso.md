# CodeIntegrity::Management::detail::TransactionHandle<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,CodeIntegrity::Management::detail::UpsertTag>::rollback(void)

- ea: `0x180015f68`
- end: `0x180015fb1`
- name: `?rollback@?$TransactionHandle@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@UUpsertTag@detail@Management@CodeIntegrity@@@detail@Management@CodeIntegrity@@QEBAXXZ`
- size: `73`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180014d20`
- `0x1800158dc`

## callees

- `0x18000d470`
- `0x180015f68`
- `0x180021f5c`

## string_xrefs

- `0x180015f97`: `onecore\base\ci\management\dll\policymgmt.cpp`

## pseudocode

```c
void __fastcall CodeIntegrity::Management::detail::TransactionHandle<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,CodeIntegrity::Management::detail::UpsertTag>::rollback(
        __int64 a1)
{
  _DWORD *v1; // rax
  _QWORD *v2; // rcx
  int updated; // eax
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *(_QWORD *)a1 )
  {
    v1 = (_DWORD *)(a1 + 8);
    if ( *(_DWORD *)(a1 + 8) == 1 || *v1 == 2 )
    {
      v2 = *(_QWORD **)a1;
      *v1 = 3;
      updated = SIPolicyPmUpdatePolicyRollback(v2);
      if ( updated < 0 )
        wil::details::in1diag3::_Throw_NtStatus(
          retaddr,
          (void *)0x1BA,
          (int)"onecore\\base\\ci\\management\\dll\\policymgmt.cpp",
          (const char *)(unsigned int)updated,
          v4);
    }
  }
}

```

## disassembly

```asm
0x180015f68  sub     rsp, 28h
0x180015f6c  cmp     qword ptr [rcx], 0
0x180015f70  jz      short loc_180015FAC
0x180015f72  lea     rax, [rcx+8]
0x180015f76  cmp     dword ptr [rax], 1
0x180015f79  jz      short loc_180015F80
0x180015f7b  cmp     dword ptr [rax], 2
0x180015f7e  jnz     short loc_180015FAC
0x180015f80  mov     rcx, [rcx]
0x180015f83  mov     dword ptr [rax], 3
0x180015f89  call    SIPolicyPmUpdatePolicyRollback
0x180015f8e  test    eax, eax
0x180015f90  jns     short loc_180015FAC
0x180015f92  mov     rcx, [rsp+28h]; this
0x180015f97  lea     r8, aOnecoreBaseCiM_3; "onecore\\base\\ci\\management\\dll\\pol"...
0x180015f9e  mov     r9d, eax; char *
0x180015fa1  mov     edx, 1BAh; void *
0x180015fa6  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180015fac  add     rsp, 28h
0x180015fb0  retn
```
