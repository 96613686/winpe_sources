# tip2::test_data_control<tip2::details::merged_data<Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest,Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest>>::~test_data_control<tip2::details::merged_data<Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest,Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest>>(void)

- ea: `0x180081a34`
- end: `0x180081ab6`
- name: `??1?$test_data_control@V?$merged_data@U_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest@TipTests@Sync@@U123@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18007e778`

## callees

- `0x180026034`
- `0x180081890`
- `0x180081a34`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081a7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081aa5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081a7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081aa5`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest,Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest>>::~test_data_control<tip2::details::merged_data<Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest,Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest>>(
        struct _RTL_CRITICAL_SECTION **a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rcx
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  struct _RTL_CRITICAL_SECTION *v4; // rbx

  v2 = *a1;
  if ( v2 )
  {
    tip2::details::shared_data<0,0,0>::end_update(&v2->LockCount);
    v3 = *a1;
    *a1 = 0;
    if ( v3 )
    {
      if ( _InterlockedExchangeAdd(&v3[7].LockCount, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest,Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest>::~merged_data<Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest,Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest>(v3);
        CoTaskMemFree(v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd(&v4[7].LockCount, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest,Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest>::~merged_data<Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest,Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest>(v4);
      CoTaskMemFree(v4);
    }
  }
}

```

## disassembly

```asm
0x180081a34  mov     [rsp+arg_8], rbx
0x180081a39  push    rdi
0x180081a3a  sub     rsp, 20h
0x180081a3e  mov     rdi, rcx
0x180081a41  mov     rcx, [rcx]
0x180081a44  test    rcx, rcx
0x180081a47  jz      short loc_180081A82
0x180081a49  add     rcx, 8
0x180081a4d  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180081a52  mov     rbx, [rdi]
0x180081a55  mov     qword ptr [rdi], 0
0x180081a5c  test    rbx, rbx
0x180081a5f  jz      short loc_180081A82
0x180081a61  or      eax, 0FFFFFFFFh
0x180081a64  lock xadd [rbx+120h], eax
0x180081a6c  cmp     eax, 1
0x180081a6f  jnz     short loc_180081A82
0x180081a71  mov     rcx, rbx
0x180081a74  call    ??1?$merged_data@U_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest@TipTests@Sync@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest,Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest>::~merged_data<Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest,Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest>(void)
0x180081a79  mov     rcx, rbx; pv
0x180081a7c  call    cs:__imp_CoTaskMemFree
0x180081a82  mov     rbx, [rdi]
0x180081a85  test    rbx, rbx
0x180081a88  jz      short loc_180081AAB
0x180081a8a  or      eax, 0FFFFFFFFh
0x180081a8d  lock xadd [rbx+120h], eax
0x180081a95  cmp     eax, 1
0x180081a98  jnz     short loc_180081AAB
0x180081a9a  mov     rcx, rbx
0x180081a9d  call    ??1?$merged_data@U_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest@TipTests@Sync@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest,Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest>::~merged_data<Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest,Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest>(void)
0x180081aa2  mov     rcx, rbx; pv
0x180081aa5  call    cs:__imp_CoTaskMemFree
0x180081aab  mov     rbx, [rsp+28h+arg_8]
0x180081ab0  add     rsp, 20h
0x180081ab4  pop     rdi
0x180081ab5  retn
```
