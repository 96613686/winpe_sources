# tip2::test_watcher<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::NotifyFailure(wil::FailureInfo const &)

- ea: `0x1800196e0`
- end: `0x180019750`
- name: `?NotifyFailure@?$test_watcher@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@@tip2@@EEAA_NAEBUFailureInfo@wil@@@Z`
- size: `112`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000407c`
- `0x18000b434`
- `0x1800196e0`
- `0x18001d208`
- `0x18001dfc0`
- `0x18001fa10`

## pseudocode

```c
char __fastcall tip2::test_watcher<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::NotifyFailure(
        __int64 a1,
        const struct wil::FailureInfo *a2)
{
  __int64 v2; // rdi
  char v4; // bl
  _BYTE v6[152]; // [rsp+20h] [rbp-B8h] BYREF
  _BYTE v7[32]; // [rsp+B8h] [rbp-20h] BYREF

  v2 = *(_QWORD *)(a1 + 56);
  if ( tip2::details::shared_data<0,0,0>::begin_update(v2 + 8) )
  {
    wil::StoredFailureInfo::StoredFailureInfo((wil::StoredFailureInfo *)v6, a2);
    v4 = tip2::vector_nothrow<wil::StoredFailureInfo>::push_back(v2 + 80, v6);
    wil::details::shared_buffer::reset((wil::details::shared_buffer *)v7);
    if ( !v4 )
      *(_DWORD *)(v2 + 72) |= 0x100000u;
  }
  tip2::details::shared_data<0,0,0>::end_update(v2 + 8);
  return 0;
}

```

## disassembly

```asm
0x1800196e0  mov     [rsp+arg_0], rbx
0x1800196e5  push    rdi
0x1800196e6  sub     rsp, 0D0h
0x1800196ed  mov     rdi, [rcx+38h]
0x1800196f1  mov     rbx, rdx
0x1800196f4  lea     rcx, [rdi+8]
0x1800196f8  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x1800196fd  test    al, al
0x1800196ff  jz      short loc_180019734
0x180019701  mov     rdx, rbx; struct wil::FailureInfo *
0x180019704  lea     rcx, [rsp+0D8h+var_B8]; this
0x180019709  call    ??0StoredFailureInfo@wil@@QEAA@AEBUFailureInfo@1@@Z; wil::StoredFailureInfo::StoredFailureInfo(wil::FailureInfo const &)
0x18001970e  lea     rcx, [rdi+50h]
0x180019712  lea     rdx, [rsp+0D8h+var_B8]
0x180019717  call    ?push_back@?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA_N$$QEAVStoredFailureInfo@wil@@@Z; tip2::vector_nothrow<wil::StoredFailureInfo>::push_back(wil::StoredFailureInfo &&)
0x18001971c  lea     rcx, [rsp+0D8h+var_20]; this
0x180019724  mov     bl, al
0x180019726  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x18001972b  test    bl, bl
0x18001972d  jnz     short loc_180019734
0x18001972f  bts     dword ptr [rdi+48h], 14h
0x180019734  lea     rcx, [rdi+8]
0x180019738  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x18001973d  mov     rbx, [rsp+0D8h+arg_0]
0x180019745  xor     al, al
0x180019747  add     rsp, 0D0h
0x18001974e  pop     rdi
0x18001974f  retn
```
