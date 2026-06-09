# tip2::test_data_control<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>(void)

- ea: `0x1800127e8`
- end: `0x180012817`
- name: `??1?$test_data_control@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `47`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001871c`
- `0x1800227e8`
- `0x180022861`

## callees

- `0x1800125b0`
- `0x1800127e8`
- `0x18001dfc0`
- `0x18002000c`

## pseudocode

```c
__int64 __fastcall tip2::test_data_control<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>(
        volatile signed __int32 **a1)
{
  volatile signed __int32 *v2; // rcx

  v2 = *a1;
  if ( v2 )
  {
    tip2::details::shared_data<0,0,0>::end_update((__int64)(v2 + 2));
    wil::com_ptr_t<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>,wil::err_returncode_policy>::reset(a1);
  }
  return wil::com_ptr_t<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>,wil::err_returncode_policy>(a1);
}

```

## disassembly

```asm
0x1800127e8  push    rbx
0x1800127ea  sub     rsp, 20h
0x1800127ee  mov     rbx, rcx
0x1800127f1  mov     rcx, [rcx]
0x1800127f4  test    rcx, rcx
0x1800127f7  jz      short loc_18001280A
0x1800127f9  add     rcx, 8
0x1800127fd  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180012802  mov     rcx, rbx
0x180012805  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>,wil::err_returncode_policy>::reset(void)
0x18001280a  mov     rcx, rbx
0x18001280d  add     rsp, 20h
0x180012811  pop     rbx
0x180012812  jmp     ??1?$com_ptr_t@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>,wil::err_returncode_policy>(void)
```
