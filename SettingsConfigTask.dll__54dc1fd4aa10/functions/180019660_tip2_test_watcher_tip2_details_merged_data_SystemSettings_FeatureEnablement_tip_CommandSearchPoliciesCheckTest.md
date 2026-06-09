# tip2::test_watcher<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>>::NotifyFailure(wil::FailureInfo const &)

- ea: `0x180019660`
- end: `0x1800196d0`
- name: `?NotifyFailure@?$test_watcher@V?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@@tip2@@EEAA_NAEBUFailureInfo@wil@@@Z`
- size: `112`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000407c`
- `0x18000b434`
- `0x180019660`
- `0x18001d134`
- `0x18001de88`
- `0x18001fa10`

## pseudocode

```c
char __fastcall tip2::test_watcher<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>>::NotifyFailure(
        __int64 a1,
        const struct wil::FailureInfo *a2)
{
  __int64 v2; // rdi
  char v4; // bl
  _BYTE v6[152]; // [rsp+20h] [rbp-B8h] BYREF
  _BYTE v7[32]; // [rsp+B8h] [rbp-20h] BYREF

  v2 = *(_QWORD *)(a1 + 56);
  if ( tip2::details::shared_data<1,0,0>::begin_update(v2 + 8) )
  {
    wil::StoredFailureInfo::StoredFailureInfo((wil::StoredFailureInfo *)v6, a2);
    v4 = tip2::vector_nothrow<wil::StoredFailureInfo>::push_back(v2 + 80, v6);
    wil::details::shared_buffer::reset((wil::details::shared_buffer *)v7);
    if ( !v4 )
      *(_DWORD *)(v2 + 72) |= 0x100000u;
  }
  tip2::details::shared_data<1,0,0>::end_update(v2 + 8);
  return 0;
}

```

## disassembly

```asm
0x180019660  mov     [rsp+arg_0], rbx
0x180019665  push    rdi
0x180019666  sub     rsp, 0D0h
0x18001966d  mov     rdi, [rcx+38h]
0x180019671  mov     rbx, rdx
0x180019674  lea     rcx, [rdi+8]
0x180019678  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18001967d  test    al, al
0x18001967f  jz      short loc_1800196B4
0x180019681  mov     rdx, rbx; struct wil::FailureInfo *
0x180019684  lea     rcx, [rsp+0D8h+var_B8]; this
0x180019689  call    ??0StoredFailureInfo@wil@@QEAA@AEBUFailureInfo@1@@Z; wil::StoredFailureInfo::StoredFailureInfo(wil::FailureInfo const &)
0x18001968e  lea     rcx, [rdi+50h]
0x180019692  lea     rdx, [rsp+0D8h+var_B8]
0x180019697  call    ?push_back@?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA_N$$QEAVStoredFailureInfo@wil@@@Z; tip2::vector_nothrow<wil::StoredFailureInfo>::push_back(wil::StoredFailureInfo &&)
0x18001969c  lea     rcx, [rsp+0D8h+var_20]; this
0x1800196a4  mov     bl, al
0x1800196a6  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x1800196ab  test    bl, bl
0x1800196ad  jnz     short loc_1800196B4
0x1800196af  bts     dword ptr [rdi+48h], 14h
0x1800196b4  lea     rcx, [rdi+8]
0x1800196b8  call    ?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<1,0,0>::end_update(void)
0x1800196bd  mov     rbx, [rsp+0D8h+arg_0]
0x1800196c5  xor     al, al
0x1800196c7  add     rsp, 0D0h
0x1800196ce  pop     rdi
0x1800196cf  retn
```
