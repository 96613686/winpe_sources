# SystemSettings::FeatureEnablement::IsCommandSearchApplicable(void)

- ea: `0x180018be0`
- end: `0x180018cf6`
- name: `?IsCommandSearchApplicable@FeatureEnablement@SystemSettings@@YA_NXZ`
- size: `278`
- prototype: `char __fastcall(SystemSettings::FeatureEnablement *this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180012f68`

## callees

- `0x180002e88`
- `0x180002ef4`
- `0x18000ae60`
- `0x180011954`
- `0x180012594`
- `0x180012858`
- `0x180012d64`
- `0x180013230`
- `0x180018be0`
- `0x18001d564`
- `0x18001ef60`
- `0x1800210a4`
- `0x180021648`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018bfa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018bfa`

## pseudocode

```c
char __fastcall SystemSettings::FeatureEnablement::IsCommandSearchApplicable(SystemSettings::FeatureEnablement *this)
{
  LPVOID v1; // rax
  wil::details::in1diag3 *v2; // rcx
  char v3; // bl
  char v4; // bl
  _BYTE v6[16]; // [rsp+20h] [rbp-50h] BYREF
  _BYTE v7[64]; // [rsp+30h] [rbp-40h] BYREF
  __int64 v8; // [rsp+80h] [rbp+10h] BYREF
  __int64 *v9; // [rsp+88h] [rbp+18h] BYREF

  v8 = 0;
  v1 = CoTaskMemAlloc(0x120u);
  if ( !v1 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v2);
  v9 = (__int64 *)tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>(
                    v1,
                    0);
  wil::com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy>::operator=(
    &v8,
    &v9);
  wil::com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy>(&v9);
  v3 = 0;
  if ( !(unsigned __int8)tip2::details::shared_data<1,0,0>::has_ever_started(v8 + 8) )
  {
    tip2::tip_test<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>>::start(
      &v8,
      v6);
    v3 = 1;
  }
  tip2::tip_test<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>>::watch_errors(
    &v8,
    v7);
  if ( __TSS0__1__IsCommandSearchApplicable_FeatureEnablement_SystemSettings__YA_NXZ_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) )
  {
    Init_thread_header(&__TSS0__1__IsCommandSearchApplicable_FeatureEnablement_SystemSettings__YA_NXZ_4HA);
    if ( __TSS0__1__IsCommandSearchApplicable_FeatureEnablement_SystemSettings__YA_NXZ_4HA == -1 )
    {
      v9 = &v8;
      `SystemSettings::FeatureEnablement::IsCommandSearchApplicable'::`2'::s_isCommandSearchApplicable = _lambda_bb196cb6630f11e5b0ce563567273d64_::operator()(&v9);
      Init_thread_footer(&__TSS0__1__IsCommandSearchApplicable_FeatureEnablement_SystemSettings__YA_NXZ_4HA);
    }
  }
  if ( v3 )
    tip2::tip_test<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>>::complete(&v8);
  v4 = `SystemSettings::FeatureEnablement::IsCommandSearchApplicable'::`2'::s_isCommandSearchApplicable;
  tip2::test_watcher<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>>::~test_watcher<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>>(v7);
  wil::com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy>(&v8);
  return v4;
}

```

## disassembly

```asm
0x180018be0  mov     [rsp-8+arg_10], rbx
0x180018be5  push    rbp
0x180018be6  mov     rbp, rsp
0x180018be9  sub     rsp, 70h
0x180018bed  mov     [rbp+arg_0], 0
0x180018bf5  mov     ecx, 120h; cb
0x180018bfa  call    cs:__imp_CoTaskMemAlloc
0x180018c00  test    rax, rax
0x180018c03  jz      loc_180018CF0
0x180018c09  xor     edx, edx
0x180018c0b  mov     rcx, rax
0x180018c0e  call    ??0?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@QEAA@PEAU_GUID@@@Z; tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>(_GUID *)
0x180018c13  mov     [rbp+arg_8], rax
0x180018c17  lea     rdx, [rbp+arg_8]
0x180018c1b  lea     rcx, [rbp+arg_0]
0x180018c1f  call    ??4?$com_ptr_t@V?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy> &&)
0x180018c24  lea     rcx, [rbp+arg_8]
0x180018c28  call    ??1?$com_ptr_t@V?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy>(void)
0x180018c2d  xor     bl, bl
0x180018c2f  mov     rcx, [rbp+arg_0]
0x180018c33  add     rcx, 8
0x180018c37  call    ?has_ever_started@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::has_ever_started(void)
0x180018c3c  test    al, al
0x180018c3e  jnz     short loc_180018C4F
0x180018c40  lea     rdx, [rbp+var_50]
0x180018c44  lea     rcx, [rbp+arg_0]
0x180018c48  call    ?start@?$tip_test@V?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>>::start(void)
0x180018c4d  mov     bl, 1
0x180018c4f  lea     rdx, [rbp+var_40]
0x180018c53  lea     rcx, [rbp+arg_0]
0x180018c57  call    ?watch_errors@?$tip_test@V?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>>::watch_errors(void)
0x180018c5c  nop
0x180018c5d  mov     ecx, cs:_tls_index
0x180018c63  mov     rax, gs:58h
0x180018c6c  mov     edx, 4
0x180018c71  mov     rax, [rax+rcx*8]
0x180018c75  mov     eax, [rdx+rax]
0x180018c78  cmp     cs:?$TSS0@?1??IsCommandSearchApplicable@FeatureEnablement@SystemSettings@@YA_NXZ@4HA, eax
0x180018c7e  jg      short loc_180018CB6
0x180018c80  test    bl, bl
0x180018c82  jz      short loc_180018C8D
0x180018c84  lea     rcx, [rbp+arg_0]
0x180018c88  call    ?complete@?$tip_test@V?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>>::complete(void)
0x180018c8d  mov     bl, cs:?s_isCommandSearchApplicable@?1??IsCommandSearchApplicable@FeatureEnablement@SystemSettings@@YA_NXZ@4_NA; bool `SystemSettings::FeatureEnablement::IsCommandSearchApplicable(void)'::`2'::s_isCommandSearchApplicable
0x180018c93  lea     rcx, [rbp+var_40]
0x180018c97  call    ??1?$test_watcher@V?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>>::~test_watcher<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>>(void)
0x180018c9c  nop
0x180018c9d  lea     rcx, [rbp+arg_0]
0x180018ca1  call    ??1?$com_ptr_t@V?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>,wil::err_returncode_policy>(void)
0x180018ca6  mov     al, bl
0x180018ca8  mov     rbx, [rsp+70h+arg_10]
0x180018cb0  add     rsp, 70h
0x180018cb4  pop     rbp
0x180018cb5  retn
0x180018cb6  lea     rcx, ?$TSS0@?1??IsCommandSearchApplicable@FeatureEnablement@SystemSettings@@YA_NXZ@4HA
0x180018cbd  call    _Init_thread_header
0x180018cc2  cmp     cs:?$TSS0@?1??IsCommandSearchApplicable@FeatureEnablement@SystemSettings@@YA_NXZ@4HA, 0FFFFFFFFh
0x180018cc9  jnz     short loc_180018C80
0x180018ccb  lea     rax, [rbp+arg_0]
0x180018ccf  mov     [rbp+arg_8], rax
0x180018cd3  lea     rcx, [rbp+arg_8]
0x180018cd7  call    ??R_lambda_bb196cb6630f11e5b0ce563567273d64_@@QEBA@XZ; _lambda_bb196cb6630f11e5b0ce563567273d64_::operator()(void)
0x180018cdc  mov     cs:?s_isCommandSearchApplicable@?1??IsCommandSearchApplicable@FeatureEnablement@SystemSettings@@YA_NXZ@4_NA, al; bool `SystemSettings::FeatureEnablement::IsCommandSearchApplicable(void)'::`2'::s_isCommandSearchApplicable
0x180018ce2  lea     rcx, ?$TSS0@?1??IsCommandSearchApplicable@FeatureEnablement@SystemSettings@@YA_NXZ@4HA
0x180018ce9  call    _Init_thread_footer
0x180018cee  jmp     short loc_180018C80
0x180018cf0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
