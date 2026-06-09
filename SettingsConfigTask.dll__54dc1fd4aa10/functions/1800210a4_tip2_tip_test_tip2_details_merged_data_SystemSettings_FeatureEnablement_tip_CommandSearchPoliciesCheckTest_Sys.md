# tip2::tip_test<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>>::start(void)

- ea: `0x1800210a4`
- end: `0x1800210f6`
- name: `?start@?$tip_test@V?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ`
- size: `82`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018be0`
- `0x180018d58`

## callees

- `0x18001e0f4`
- `0x18001ef60`
- `0x18001ffe4`
- `0x180020e54`
- `0x1800210a4`

## pseudocode

```c
__int64 __fastcall tip2::tip_test<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>>::start(
        __int64 *a1,
        __int64 a2)
{
  __int64 v4; // rcx
  _QWORD *v5; // rax

  v4 = *a1;
  if ( v4 && (unsigned __int8)tip2::details::shared_data<1,0,0>::has_ever_started(v4 + 8) )
    wil::com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy>::reset(a1);
  v5 = tip2::tip_test<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>>::ensure_data(a1);
  tip2::details::shared_data<1,0,0>::start(*v5 + 8LL, a2);
  return a2;
}

```

## disassembly

```asm
0x1800210a4  mov     [rsp+arg_0], rbx
0x1800210a9  push    rdi
0x1800210aa  sub     rsp, 20h
0x1800210ae  mov     rbx, rcx
0x1800210b1  mov     rdi, rdx
0x1800210b4  mov     rcx, [rcx]
0x1800210b7  test    rcx, rcx
0x1800210ba  jz      short loc_1800210D1
0x1800210bc  add     rcx, 8
0x1800210c0  call    ?has_ever_started@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::has_ever_started(void)
0x1800210c5  test    al, al
0x1800210c7  jz      short loc_1800210D1
0x1800210c9  mov     rcx, rbx
0x1800210cc  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy>::reset(void)
0x1800210d1  mov     rcx, rbx
0x1800210d4  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>>::ensure_data(void)
0x1800210d9  mov     rdx, rdi
0x1800210dc  mov     rcx, [rax]
0x1800210df  add     rcx, 8
0x1800210e3  call    ?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<1,0,0>::start(void)
0x1800210e8  mov     rbx, [rsp+28h+arg_0]
0x1800210ed  mov     rax, rdi
0x1800210f0  add     rsp, 20h
0x1800210f4  pop     rdi
0x1800210f5  retn
```
