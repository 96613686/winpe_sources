# SystemSettings::FeatureEnablement::IsCommandSearchEnabled(void)

- ea: `0x180018d58`
- end: `0x180018e50`
- name: `?IsCommandSearchEnabled@FeatureEnablement@SystemSettings@@YA_NXZ`
- size: `248`
- prototype: `char __fastcall(SystemSettings::FeatureEnablement *this)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001c380`

## callees

- `0x18000ae60`
- `0x18000aeb4`
- `0x180011954`
- `0x180012594`
- `0x180012858`
- `0x180012d64`
- `0x180012f68`
- `0x180018d58`
- `0x1800192e0`
- `0x18001cef8`
- `0x18001d564`
- `0x18001ef60`
- `0x18001ffe4`
- `0x1800210a4`
- `0x180021648`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018d86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018d86`

## pseudocode

```c
char __fastcall SystemSettings::FeatureEnablement::IsCommandSearchEnabled(SystemSettings::FeatureEnablement *this)
{
  char result; // al
  LPVOID v2; // rax
  wil::details::in1diag3 *v3; // rcx
  bool IsSettingsAgentFeatureAllowedByEnterpriseControl; // bl
  SystemSettings::FeatureEnablement *v5; // rcx
  char v6; // bl
  __int64 *v7; // [rsp+20h] [rbp-50h] BYREF
  bool v8; // [rsp+28h] [rbp-48h]
  _BYTE v9[64]; // [rsp+30h] [rbp-40h] BYREF
  __int64 v10; // [rsp+80h] [rbp+10h] BYREF
  __int64 v11; // [rsp+88h] [rbp+18h] BYREF

  result = wil::details::FeatureImpl<__WilFeatureTraits_Feature_53427769>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_53427769>::GetImpl'::`2'::impl);
  if ( result )
  {
    v10 = 0;
    v2 = CoTaskMemAlloc(0x120u);
    if ( !v2 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
    v11 = tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>(
            v2,
            0);
    wil::com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy>::operator=(
      &v10,
      &v11);
    wil::com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy>(&v11);
    if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::has_ever_started(v10 + 8) )
      wil::com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy>::reset(&v10);
    IsSettingsAgentFeatureAllowedByEnterpriseControl = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_61214098>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_61214098>::GetImpl'::`2'::impl) )
      IsSettingsAgentFeatureAllowedByEnterpriseControl = SystemSettings::FeatureEnablement::IsSettingsAgentFeatureAllowedByEnterpriseControl(v5);
    tip2::tip_test<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>>::start(
      &v10,
      &v7);
    tip2::tip_test<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>>::watch_errors(
      &v10,
      v9);
    v7 = &v10;
    v8 = IsSettingsAgentFeatureAllowedByEnterpriseControl;
    v6 = _lambda_3277820fe4ae076ed05634a37d41a927_::operator()(&v7);
    tip2::tip_test<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>>::complete(&v10);
    tip2::test_watcher<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>>::~test_watcher<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>>(v9);
    wil::com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy>(&v10);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x180018d58  mov     [rsp-8+arg_10], rbx
0x180018d5d  push    rbp
0x180018d5e  mov     rbp, rsp
0x180018d61  sub     rsp, 70h
0x180018d65  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_53427769@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_53427769@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53427769> `wil::Feature<__WilFeatureTraits_Feature_53427769>::GetImpl(void)'::`2'::impl
0x180018d6c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_53427769@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53427769>::__private_IsEnabled(void)
0x180018d71  test    al, al
0x180018d73  jz      loc_180018E3C
0x180018d79  mov     [rbp+arg_0], 0
0x180018d81  mov     ecx, 120h; cb
0x180018d86  call    cs:__imp_CoTaskMemAlloc
0x180018d8c  test    rax, rax
0x180018d8f  jz      loc_180018E4A
0x180018d95  xor     edx, edx
0x180018d97  mov     rcx, rax
0x180018d9a  call    ??0?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@QEAA@PEAU_GUID@@@Z; tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>(_GUID *)
0x180018d9f  mov     [rbp+arg_8], rax
0x180018da3  lea     rdx, [rbp+arg_8]
0x180018da7  lea     rcx, [rbp+arg_0]
0x180018dab  call    ??4?$com_ptr_t@V?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy> &&)
0x180018db0  lea     rcx, [rbp+arg_8]
0x180018db4  call    ??1?$com_ptr_t@V?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy>(void)
0x180018db9  mov     rcx, [rbp+arg_0]
0x180018dbd  add     rcx, 8
0x180018dc1  call    ?has_ever_started@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::has_ever_started(void)
0x180018dc6  test    al, al
0x180018dc8  jz      short loc_180018DD3
0x180018dca  lea     rcx, [rbp+arg_0]
0x180018dce  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy>::reset(void)
0x180018dd3  xor     bl, bl
0x180018dd5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_61214098@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_61214098@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_61214098> `wil::Feature<__WilFeatureTraits_Feature_61214098>::GetImpl(void)'::`2'::impl
0x180018ddc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_61214098@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_61214098>::__private_IsEnabled(void)
0x180018de1  test    al, al
0x180018de3  jz      short loc_180018DEC
0x180018de5  call    ?IsSettingsAgentFeatureAllowedByEnterpriseControl@FeatureEnablement@SystemSettings@@YA_NXZ; SystemSettings::FeatureEnablement::IsSettingsAgentFeatureAllowedByEnterpriseControl(void)
0x180018dea  mov     bl, al
0x180018dec  lea     rdx, [rbp+var_50]
0x180018df0  lea     rcx, [rbp+arg_0]
0x180018df4  call    ?start@?$tip_test@V?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>>::start(void)
0x180018df9  lea     rdx, [rbp+var_40]
0x180018dfd  lea     rcx, [rbp+arg_0]
0x180018e01  call    ?watch_errors@?$tip_test@V?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>>::watch_errors(void)
0x180018e06  nop
0x180018e07  lea     rax, [rbp+arg_0]
0x180018e0b  mov     [rbp+var_50], rax
0x180018e0f  mov     [rbp+var_48], bl
0x180018e12  lea     rcx, [rbp+var_50]
0x180018e16  call    ??R_lambda_3277820fe4ae076ed05634a37d41a927_@@QEBA@XZ; _lambda_3277820fe4ae076ed05634a37d41a927_::operator()(void)
0x180018e1b  mov     bl, al
0x180018e1d  lea     rcx, [rbp+arg_0]
0x180018e21  call    ?complete@?$tip_test@V?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>>::complete(void)
0x180018e26  nop
0x180018e27  lea     rcx, [rbp+var_40]
0x180018e2b  call    ??1?$test_watcher@V?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>>::~test_watcher<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>>(void)
0x180018e30  nop
0x180018e31  lea     rcx, [rbp+arg_0]
0x180018e35  call    ??1?$com_ptr_t@V?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy>(void)
0x180018e3a  mov     al, bl
0x180018e3c  mov     rbx, [rsp+70h+arg_10]
0x180018e44  add     rsp, 70h
0x180018e48  pop     rbp
0x180018e49  retn
0x180018e4a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
