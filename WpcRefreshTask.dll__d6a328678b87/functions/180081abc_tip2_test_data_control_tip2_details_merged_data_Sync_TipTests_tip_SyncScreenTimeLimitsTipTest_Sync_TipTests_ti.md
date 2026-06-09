# tip2::test_data_control<tip2::details::merged_data<Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest,Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest>>::~test_data_control<tip2::details::merged_data<Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest,Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest>>(void)

- ea: `0x180081abc`
- end: `0x180081b3e`
- name: `??1?$test_data_control@V?$merged_data@U_tip_SyncScreenTimeLimitsTipTest@TipTests@Sync@@U123@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180082ad4`

## callees

- `0x180026034`
- `0x18008191c`
- `0x180081abc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081b04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081b2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081b04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081b2d`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest,Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest>>::~test_data_control<tip2::details::merged_data<Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest,Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest>>(
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
        tip2::details::merged_data<Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest,Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest>::~merged_data<Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest,Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest>((struct _RTL_CRITICAL_SECTION *)v3);
        CoTaskMemFree((LPVOID)v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 280), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest,Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest>::~merged_data<Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest,Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
}

```

## disassembly

```asm
0x180081abc  mov     [rsp+arg_8], rbx
0x180081ac1  push    rdi
0x180081ac2  sub     rsp, 20h
0x180081ac6  mov     rdi, rcx
0x180081ac9  mov     rcx, [rcx]
0x180081acc  test    rcx, rcx
0x180081acf  jz      short loc_180081B0A
0x180081ad1  add     rcx, 8
0x180081ad5  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180081ada  mov     rbx, [rdi]
0x180081add  mov     qword ptr [rdi], 0
0x180081ae4  test    rbx, rbx
0x180081ae7  jz      short loc_180081B0A
0x180081ae9  or      eax, 0FFFFFFFFh
0x180081aec  lock xadd [rbx+118h], eax
0x180081af4  cmp     eax, 1
0x180081af7  jnz     short loc_180081B0A
0x180081af9  mov     rcx, rbx
0x180081afc  call    ??1?$merged_data@U_tip_SyncScreenTimeLimitsTipTest@TipTests@Sync@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest,Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest>::~merged_data<Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest,Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest>(void)
0x180081b01  mov     rcx, rbx; pv
0x180081b04  call    cs:__imp_CoTaskMemFree
0x180081b0a  mov     rbx, [rdi]
0x180081b0d  test    rbx, rbx
0x180081b10  jz      short loc_180081B33
0x180081b12  or      eax, 0FFFFFFFFh
0x180081b15  lock xadd [rbx+118h], eax
0x180081b1d  cmp     eax, 1
0x180081b20  jnz     short loc_180081B33
0x180081b22  mov     rcx, rbx
0x180081b25  call    ??1?$merged_data@U_tip_SyncScreenTimeLimitsTipTest@TipTests@Sync@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest,Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest>::~merged_data<Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest,Sync::TipTests::_tip_SyncScreenTimeLimitsTipTest>(void)
0x180081b2a  mov     rcx, rbx; pv
0x180081b2d  call    cs:__imp_CoTaskMemFree
0x180081b33  mov     rbx, [rsp+28h+arg_8]
0x180081b38  add     rsp, 20h
0x180081b3c  pop     rdi
0x180081b3d  retn
```
