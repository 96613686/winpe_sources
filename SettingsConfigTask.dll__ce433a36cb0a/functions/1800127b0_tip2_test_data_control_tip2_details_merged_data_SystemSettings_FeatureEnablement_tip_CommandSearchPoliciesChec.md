# tip2::test_data_control<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>>::~test_data_control<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>>(void)

- ea: `0x1800127b0`
- end: `0x1800127df`
- name: `??1?$test_data_control@V?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@@tip2@@QEAA@XZ`
- size: `47`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180012f68`
- `0x180013230`

## callees

- `0x180012594`
- `0x1800127b0`
- `0x18001de88`
- `0x18001ffe4`

## pseudocode

```c
__int64 __fastcall tip2::test_data_control<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>>::~test_data_control<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>>(
        void **a1)
{
  char *v2; // rcx

  v2 = (char *)*a1;
  if ( v2 )
  {
    tip2::details::shared_data<1,0,0>::end_update(v2 + 8);
    wil::com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy>::reset(a1);
  }
  return wil::com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy>(a1);
}

```

## disassembly

```asm
0x1800127b0  push    rbx
0x1800127b2  sub     rsp, 20h
0x1800127b6  mov     rbx, rcx
0x1800127b9  mov     rcx, [rcx]
0x1800127bc  test    rcx, rcx
0x1800127bf  jz      short loc_1800127D2
0x1800127c1  add     rcx, 8
0x1800127c5  call    ?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<1,0,0>::end_update(void)
0x1800127ca  mov     rcx, rbx
0x1800127cd  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy>::reset(void)
0x1800127d2  mov     rcx, rbx
0x1800127d5  add     rsp, 20h
0x1800127d9  pop     rbx
0x1800127da  jmp     ??1?$com_ptr_t@V?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy>(void)
```
