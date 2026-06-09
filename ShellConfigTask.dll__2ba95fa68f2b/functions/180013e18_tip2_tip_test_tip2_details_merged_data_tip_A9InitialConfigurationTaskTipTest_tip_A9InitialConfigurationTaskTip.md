# tip2::tip_test<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>>::~tip_test<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>>(void)

- ea: `0x180013e18`
- end: `0x180013e4d`
- name: `??1?$tip_test@V?$merged_data@U_tip_A9InitialConfigurationTaskTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180030f88`

## callees

- `0x1800139c8`
- `0x180013e18`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013e41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013e41`

## pseudocode

```c
void __fastcall tip2::tip_test<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>>::~tip_test<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>>(
        __int64 *a1)
{
  __int64 v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 280), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>::~merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>((struct _RTL_CRITICAL_SECTION *)v1);
      CoTaskMemFree((LPVOID)v1);
    }
  }
}

```

## disassembly

```asm
0x180013e18  push    rbx
0x180013e1a  sub     rsp, 20h
0x180013e1e  mov     rbx, [rcx]
0x180013e21  test    rbx, rbx
0x180013e24  jz      short loc_180013E47
0x180013e26  or      eax, 0FFFFFFFFh
0x180013e29  lock xadd [rbx+118h], eax
0x180013e31  cmp     eax, 1
0x180013e34  jnz     short loc_180013E47
0x180013e36  mov     rcx, rbx
0x180013e39  call    ??1?$merged_data@U_tip_A9InitialConfigurationTaskTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>::~merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>(void)
0x180013e3e  mov     rcx, rbx; pv
0x180013e41  call    cs:__imp_CoTaskMemFree
0x180013e47  add     rsp, 20h
0x180013e4b  pop     rbx
0x180013e4c  retn
```
