# tip2::test_data_control<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>>::~test_data_control<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>>(void)

- ea: `0x180013bf8`
- end: `0x180013c7a`
- name: `??1?$test_data_control@V?$merged_data@U_tip_A9InitialConfigurationTaskTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001a754`
- `0x18001dac8`
- `0x18001fd50`

## callees

- `0x1800139c8`
- `0x180013bf8`
- `0x180021ecc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013c40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013c69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013c40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013c69`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>>::~test_data_control<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>>(
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
        tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>::~merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>((struct _RTL_CRITICAL_SECTION *)v3);
        CoTaskMemFree((LPVOID)v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 280), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>::~merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
}

```

## disassembly

```asm
0x180013bf8  mov     [rsp+arg_8], rbx
0x180013bfd  push    rdi
0x180013bfe  sub     rsp, 20h
0x180013c02  mov     rdi, rcx
0x180013c05  mov     rcx, [rcx]
0x180013c08  test    rcx, rcx
0x180013c0b  jz      short loc_180013C46
0x180013c0d  add     rcx, 8
0x180013c11  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180013c16  mov     rbx, [rdi]
0x180013c19  mov     qword ptr [rdi], 0
0x180013c20  test    rbx, rbx
0x180013c23  jz      short loc_180013C46
0x180013c25  or      eax, 0FFFFFFFFh
0x180013c28  lock xadd [rbx+118h], eax
0x180013c30  cmp     eax, 1
0x180013c33  jnz     short loc_180013C46
0x180013c35  mov     rcx, rbx
0x180013c38  call    ??1?$merged_data@U_tip_A9InitialConfigurationTaskTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>::~merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>(void)
0x180013c3d  mov     rcx, rbx; pv
0x180013c40  call    cs:__imp_CoTaskMemFree
0x180013c46  mov     rbx, [rdi]
0x180013c49  test    rbx, rbx
0x180013c4c  jz      short loc_180013C6F
0x180013c4e  or      eax, 0FFFFFFFFh
0x180013c51  lock xadd [rbx+118h], eax
0x180013c59  cmp     eax, 1
0x180013c5c  jnz     short loc_180013C6F
0x180013c5e  mov     rcx, rbx
0x180013c61  call    ??1?$merged_data@U_tip_A9InitialConfigurationTaskTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>::~merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>(void)
0x180013c66  mov     rcx, rbx; pv
0x180013c69  call    cs:__imp_CoTaskMemFree
0x180013c6f  mov     rbx, [rsp+28h+arg_8]
0x180013c74  add     rsp, 20h
0x180013c78  pop     rdi
0x180013c79  retn
```
