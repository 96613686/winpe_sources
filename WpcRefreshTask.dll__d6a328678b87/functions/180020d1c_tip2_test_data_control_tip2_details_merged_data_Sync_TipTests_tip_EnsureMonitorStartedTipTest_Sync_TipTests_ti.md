# tip2::test_data_control<tip2::details::merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>>::~test_data_control<tip2::details::merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>>(void)

- ea: `0x180020d1c`
- end: `0x180020d9e`
- name: `??1?$test_data_control@V?$merged_data@U_tip_EnsureMonitorStartedTipTest@TipTests@Sync@@U123@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002252c`

## callees

- `0x180020b8c`
- `0x180020d1c`
- `0x180026034`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020d64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020d8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020d64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020d8d`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>>::~test_data_control<tip2::details::merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>>(
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
        tip2::details::merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>::~merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>((struct _RTL_CRITICAL_SECTION *)v3);
        CoTaskMemFree((LPVOID)v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 280), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>::~merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
}

```

## disassembly

```asm
0x180020d1c  mov     [rsp+arg_8], rbx
0x180020d21  push    rdi
0x180020d22  sub     rsp, 20h
0x180020d26  mov     rdi, rcx
0x180020d29  mov     rcx, [rcx]
0x180020d2c  test    rcx, rcx
0x180020d2f  jz      short loc_180020D6A
0x180020d31  add     rcx, 8
0x180020d35  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180020d3a  mov     rbx, [rdi]
0x180020d3d  mov     qword ptr [rdi], 0
0x180020d44  test    rbx, rbx
0x180020d47  jz      short loc_180020D6A
0x180020d49  or      eax, 0FFFFFFFFh
0x180020d4c  lock xadd [rbx+118h], eax
0x180020d54  cmp     eax, 1
0x180020d57  jnz     short loc_180020D6A
0x180020d59  mov     rcx, rbx
0x180020d5c  call    ??1?$merged_data@U_tip_EnsureMonitorStartedTipTest@TipTests@Sync@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>::~merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>(void)
0x180020d61  mov     rcx, rbx; pv
0x180020d64  call    cs:__imp_CoTaskMemFree
0x180020d6a  mov     rbx, [rdi]
0x180020d6d  test    rbx, rbx
0x180020d70  jz      short loc_180020D93
0x180020d72  or      eax, 0FFFFFFFFh
0x180020d75  lock xadd [rbx+118h], eax
0x180020d7d  cmp     eax, 1
0x180020d80  jnz     short loc_180020D93
0x180020d82  mov     rcx, rbx
0x180020d85  call    ??1?$merged_data@U_tip_EnsureMonitorStartedTipTest@TipTests@Sync@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>::~merged_data<Sync::TipTests::_tip_EnsureMonitorStartedTipTest,Sync::TipTests::_tip_EnsureMonitorStartedTipTest>(void)
0x180020d8a  mov     rcx, rbx; pv
0x180020d8d  call    cs:__imp_CoTaskMemFree
0x180020d93  mov     rbx, [rsp+28h+arg_8]
0x180020d98  add     rsp, 20h
0x180020d9c  pop     rdi
0x180020d9d  retn
```
