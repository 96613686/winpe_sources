# tip2::test_data_control<tip2::details::merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>>::~test_data_control<tip2::details::merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>>(void)

- ea: `0x180020da4`
- end: `0x180020e26`
- name: `??1?$test_data_control@V?$merged_data@U_tip_UpdateTaskTriggersTipTest@TipTests@Sync@@U123@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800221d4`

## callees

- `0x180020c18`
- `0x180020da4`
- `0x180026034`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020dec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020e15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020dec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020e15`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>>::~test_data_control<tip2::details::merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>>(
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
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 296), 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>::~merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>((struct _RTL_CRITICAL_SECTION *)v3);
        CoTaskMemFree((LPVOID)v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 296), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>::~merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
}

```

## disassembly

```asm
0x180020da4  mov     [rsp+arg_8], rbx
0x180020da9  push    rdi
0x180020daa  sub     rsp, 20h
0x180020dae  mov     rdi, rcx
0x180020db1  mov     rcx, [rcx]
0x180020db4  test    rcx, rcx
0x180020db7  jz      short loc_180020DF2
0x180020db9  add     rcx, 8
0x180020dbd  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180020dc2  mov     rbx, [rdi]
0x180020dc5  mov     qword ptr [rdi], 0
0x180020dcc  test    rbx, rbx
0x180020dcf  jz      short loc_180020DF2
0x180020dd1  or      eax, 0FFFFFFFFh
0x180020dd4  lock xadd [rbx+128h], eax
0x180020ddc  cmp     eax, 1
0x180020ddf  jnz     short loc_180020DF2
0x180020de1  mov     rcx, rbx
0x180020de4  call    ??1?$merged_data@U_tip_UpdateTaskTriggersTipTest@TipTests@Sync@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>::~merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>(void)
0x180020de9  mov     rcx, rbx; pv
0x180020dec  call    cs:__imp_CoTaskMemFree
0x180020df2  mov     rbx, [rdi]
0x180020df5  test    rbx, rbx
0x180020df8  jz      short loc_180020E1B
0x180020dfa  or      eax, 0FFFFFFFFh
0x180020dfd  lock xadd [rbx+128h], eax
0x180020e05  cmp     eax, 1
0x180020e08  jnz     short loc_180020E1B
0x180020e0a  mov     rcx, rbx
0x180020e0d  call    ??1?$merged_data@U_tip_UpdateTaskTriggersTipTest@TipTests@Sync@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>::~merged_data<Sync::TipTests::_tip_UpdateTaskTriggersTipTest,Sync::TipTests::_tip_UpdateTaskTriggersTipTest>(void)
0x180020e12  mov     rcx, rbx; pv
0x180020e15  call    cs:__imp_CoTaskMemFree
0x180020e1b  mov     rbx, [rsp+28h+arg_8]
0x180020e20  add     rsp, 20h
0x180020e24  pop     rdi
0x180020e25  retn
```
