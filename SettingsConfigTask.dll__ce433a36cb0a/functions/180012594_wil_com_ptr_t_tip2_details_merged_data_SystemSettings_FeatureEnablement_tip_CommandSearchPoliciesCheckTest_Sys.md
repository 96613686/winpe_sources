# wil::com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy>(void)

- ea: `0x180012594`
- end: `0x1800125aa`
- name: `??1?$com_ptr_t@V?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `22`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800127b0`
- `0x180012858`
- `0x1800128a8`
- `0x180018be0`
- `0x180018d58`
- `0x18001e0f4`

## callees

- `0x180012594`
- `0x18001a54c`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy>(
        void **a1)
{
  void *v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>::Release(v1);
  return result;
}

```

## disassembly

```asm
0x180012594  sub     rsp, 28h
0x180012598  mov     rcx, [rcx]; pv
0x18001259b  test    rcx, rcx
0x18001259e  jz      short loc_1800125A5
0x1800125a0  call    ?Release@?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@AEAAKXZ; tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>::Release(void)
0x1800125a5  add     rsp, 28h
0x1800125a9  retn
```
