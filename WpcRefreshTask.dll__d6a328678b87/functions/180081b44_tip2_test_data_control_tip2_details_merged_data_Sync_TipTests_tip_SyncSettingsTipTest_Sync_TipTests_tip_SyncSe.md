# tip2::test_data_control<tip2::details::merged_data<Sync::TipTests::_tip_SyncSettingsTipTest,Sync::TipTests::_tip_SyncSettingsTipTest>>::~test_data_control<tip2::details::merged_data<Sync::TipTests::_tip_SyncSettingsTipTest,Sync::TipTests::_tip_SyncSettingsTipTest>>(void)

- ea: `0x180081b44`
- end: `0x180081bc6`
- name: `??1?$test_data_control@V?$merged_data@U_tip_SyncSettingsTipTest@TipTests@Sync@@U123@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180082bd8`

## callees

- `0x180026034`
- `0x1800819a8`
- `0x180081b44`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081b8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081bb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081b8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081bb5`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<Sync::TipTests::_tip_SyncSettingsTipTest,Sync::TipTests::_tip_SyncSettingsTipTest>>::~test_data_control<tip2::details::merged_data<Sync::TipTests::_tip_SyncSettingsTipTest,Sync::TipTests::_tip_SyncSettingsTipTest>>(
        __int64 *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rbx
  __int64 v4; // rbx

  v2 = *a1;
  if ( v2 )
  {
    tip2::details::shared_data<0,0,0>::end_update(v2 + 8);
    v3 = *a1;
    *a1 = 0;
    if ( v3 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 280), 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<Sync::TipTests::_tip_SyncSettingsTipTest,Sync::TipTests::_tip_SyncSettingsTipTest>::~merged_data<Sync::TipTests::_tip_SyncSettingsTipTest,Sync::TipTests::_tip_SyncSettingsTipTest>((struct _RTL_CRITICAL_SECTION *)v3);
        CoTaskMemFree((LPVOID)v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 280), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<Sync::TipTests::_tip_SyncSettingsTipTest,Sync::TipTests::_tip_SyncSettingsTipTest>::~merged_data<Sync::TipTests::_tip_SyncSettingsTipTest,Sync::TipTests::_tip_SyncSettingsTipTest>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
}

```

## disassembly

```asm
0x180081b44  mov     [rsp+arg_8], rbx
0x180081b49  push    rdi
0x180081b4a  sub     rsp, 20h
0x180081b4e  mov     rdi, rcx
0x180081b51  mov     rcx, [rcx]
0x180081b54  test    rcx, rcx
0x180081b57  jz      short loc_180081B92
0x180081b59  add     rcx, 8
0x180081b5d  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180081b62  mov     rbx, [rdi]
0x180081b65  mov     qword ptr [rdi], 0
0x180081b6c  test    rbx, rbx
0x180081b6f  jz      short loc_180081B92
0x180081b71  or      eax, 0FFFFFFFFh
0x180081b74  lock xadd [rbx+118h], eax
0x180081b7c  cmp     eax, 1
0x180081b7f  jnz     short loc_180081B92
0x180081b81  mov     rcx, rbx
0x180081b84  call    ??1?$merged_data@U_tip_SyncSettingsTipTest@TipTests@Sync@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<Sync::TipTests::_tip_SyncSettingsTipTest,Sync::TipTests::_tip_SyncSettingsTipTest>::~merged_data<Sync::TipTests::_tip_SyncSettingsTipTest,Sync::TipTests::_tip_SyncSettingsTipTest>(void)
0x180081b89  mov     rcx, rbx; pv
0x180081b8c  call    cs:__imp_CoTaskMemFree
0x180081b92  mov     rbx, [rdi]
0x180081b95  test    rbx, rbx
0x180081b98  jz      short loc_180081BBB
0x180081b9a  or      eax, 0FFFFFFFFh
0x180081b9d  lock xadd [rbx+118h], eax
0x180081ba5  cmp     eax, 1
0x180081ba8  jnz     short loc_180081BBB
0x180081baa  mov     rcx, rbx
0x180081bad  call    ??1?$merged_data@U_tip_SyncSettingsTipTest@TipTests@Sync@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<Sync::TipTests::_tip_SyncSettingsTipTest,Sync::TipTests::_tip_SyncSettingsTipTest>::~merged_data<Sync::TipTests::_tip_SyncSettingsTipTest,Sync::TipTests::_tip_SyncSettingsTipTest>(void)
0x180081bb2  mov     rcx, rbx; pv
0x180081bb5  call    cs:__imp_CoTaskMemFree
0x180081bbb  mov     rbx, [rsp+28h+arg_8]
0x180081bc0  add     rsp, 20h
0x180081bc4  pop     rdi
0x180081bc5  retn
```
