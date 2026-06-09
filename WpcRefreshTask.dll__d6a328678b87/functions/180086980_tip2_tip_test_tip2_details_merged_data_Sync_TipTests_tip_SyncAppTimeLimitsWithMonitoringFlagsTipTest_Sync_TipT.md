# tip2::tip_test<tip2::details::merged_data<Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest,Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest>>::ensure_data(void)

- ea: `0x180086980`
- end: `0x180086a0c`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest@TipTests@Sync@@U123@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest@TipTests@Sync@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007e778`

## callees

- `0x180081504`
- `0x180081890`
- `0x180086980`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800869cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800869f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800869cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800869f8`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION **__fastcall tip2::tip_test<tip2::details::merged_data<Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest,Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest>>::ensure_data(
        struct _RTL_CRITICAL_SECTION **a1)
{
  struct _RTL_CRITICAL_SECTION **v2; // rax
  struct _RTL_CRITICAL_SECTION *v3; // rdx
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a1 )
  {
    v2 = (struct _RTL_CRITICAL_SECTION **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest,Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest>,>(&pv);
    v3 = *v2;
    *v2 = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 && _InterlockedExchangeAdd(&v4[7].LockCount, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest,Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest>::~merged_data<Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest,Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest>(v4);
      CoTaskMemFree(v4);
    }
    v5 = (struct _RTL_CRITICAL_SECTION *)pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest,Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest>::~merged_data<Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest,Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest>(v5);
      CoTaskMemFree(v5);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180086980  mov     [rsp+arg_10], rbx
0x180086985  push    rdi
0x180086986  sub     rsp, 20h
0x18008698a  cmp     qword ptr [rcx], 0
0x18008698e  mov     rdi, rcx
0x180086991  jnz     short loc_1800869FE
0x180086993  lea     rcx, [rsp+28h+pv]
0x180086998  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest@TipTests@Sync@@U123@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest@TipTests@Sync@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest,Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest>,>(void)
0x18008699d  mov     rdx, [rax]
0x1800869a0  mov     qword ptr [rax], 0
0x1800869a7  mov     rbx, [rdi]
0x1800869aa  mov     [rdi], rdx
0x1800869ad  test    rbx, rbx
0x1800869b0  jz      short loc_1800869D3
0x1800869b2  or      eax, 0FFFFFFFFh
0x1800869b5  lock xadd [rbx+120h], eax
0x1800869bd  cmp     eax, 1
0x1800869c0  jnz     short loc_1800869D3
0x1800869c2  mov     rcx, rbx
0x1800869c5  call    ??1?$merged_data@U_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest@TipTests@Sync@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest,Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest>::~merged_data<Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest,Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest>(void)
0x1800869ca  mov     rcx, rbx; pv
0x1800869cd  call    cs:__imp_CoTaskMemFree
0x1800869d3  mov     rbx, [rsp+28h+pv]
0x1800869d8  test    rbx, rbx
0x1800869db  jz      short loc_1800869FE
0x1800869dd  or      eax, 0FFFFFFFFh
0x1800869e0  lock xadd [rbx+120h], eax
0x1800869e8  cmp     eax, 1
0x1800869eb  jnz     short loc_1800869FE
0x1800869ed  mov     rcx, rbx
0x1800869f0  call    ??1?$merged_data@U_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest@TipTests@Sync@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest,Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest>::~merged_data<Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest,Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest>(void)
0x1800869f5  mov     rcx, rbx; pv
0x1800869f8  call    cs:__imp_CoTaskMemFree
0x1800869fe  mov     rbx, [rsp+28h+arg_10]
0x180086a03  mov     rax, rdi
0x180086a06  add     rsp, 20h
0x180086a0a  pop     rdi
0x180086a0b  retn
```
