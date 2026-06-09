# tip2::tip_test<tip2::details::merged_data<SpellerTip::_tip_FluencyDictionaryUpdate,SpellerTip::_tip_FluencyDictionaryUpdate>>::ensure_data(void)

- ea: `0x1800766c8`
- end: `0x18007671a`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_FluencyDictionaryUpdate@SpellerTip@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_FluencyDictionaryUpdate@SpellerTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `82`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800510bc`
- `0x180058634`
- `0x180082050`

## callees

- `0x18006a0b0`
- `0x1800738a0`
- `0x180073df0`
- `0x180074028`
- `0x1800766c8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800766dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800766dc`

## pseudocode

```c
_QWORD *__fastcall tip2::tip_test<tip2::details::merged_data<SpellerTip::_tip_FluencyDictionaryUpdate,SpellerTip::_tip_FluencyDictionaryUpdate>>::ensure_data(
        _QWORD *a1)
{
  LPVOID v2; // rax
  wil::details::in1diag3 *v3; // rcx
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF

  if ( !*a1 )
  {
    v2 = CoTaskMemAlloc(0x120u);
    if ( !v2 )
      wil::details::in1diag3::FailFastImmediate_Unexpected(v3);
    v5 = tip2::details::merged_data<SpellerTip::_tip_FluencyDictionaryUpdate,SpellerTip::_tip_FluencyDictionaryUpdate>::merged_data<SpellerTip::_tip_FluencyDictionaryUpdate,SpellerTip::_tip_FluencyDictionaryUpdate>(v2);
    wil::com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_FluencyDictionaryUpdate,SpellerTip::_tip_FluencyDictionaryUpdate>,wil::err_returncode_policy>::operator=(
      a1,
      &v5);
    wil::com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_FluencyDictionaryUpdate,SpellerTip::_tip_FluencyDictionaryUpdate>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_FluencyDictionaryUpdate,SpellerTip::_tip_FluencyDictionaryUpdate>,wil::err_returncode_policy>(&v5);
  }
  return a1;
}

```

## disassembly

```asm
0x1800766c8  push    rbx
0x1800766ca  sub     rsp, 20h
0x1800766ce  cmp     qword ptr [rcx], 0
0x1800766d2  mov     rbx, rcx
0x1800766d5  jnz     short loc_180076711
0x1800766d7  mov     ecx, 120h; cb
0x1800766dc  call    cs:__imp_CoTaskMemAlloc
0x1800766e2  test    rax, rax
0x1800766e5  jnz     short loc_1800766ED
0x1800766e7  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
0x1800766ed  mov     rcx, rax
0x1800766f0  call    ??0?$merged_data@U_tip_FluencyDictionaryUpdate@SpellerTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<SpellerTip::_tip_FluencyDictionaryUpdate,SpellerTip::_tip_FluencyDictionaryUpdate>::merged_data<SpellerTip::_tip_FluencyDictionaryUpdate,SpellerTip::_tip_FluencyDictionaryUpdate>(void)
0x1800766f5  lea     rdx, [rsp+28h+arg_0]
0x1800766fa  mov     [rsp+28h+arg_0], rax
0x1800766ff  mov     rcx, rbx
0x180076702  call    ??4?$com_ptr_t@V?$merged_data@U_tip_FluencyDictionaryUpdate@SpellerTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_FluencyDictionaryUpdate,SpellerTip::_tip_FluencyDictionaryUpdate>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_FluencyDictionaryUpdate,SpellerTip::_tip_FluencyDictionaryUpdate>,wil::err_returncode_policy> &&)
0x180076707  lea     rcx, [rsp+28h+arg_0]
0x18007670c  call    ??1?$com_ptr_t@V?$merged_data@U_tip_FluencyDictionaryUpdate@SpellerTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_FluencyDictionaryUpdate,SpellerTip::_tip_FluencyDictionaryUpdate>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_FluencyDictionaryUpdate,SpellerTip::_tip_FluencyDictionaryUpdate>,wil::err_returncode_policy>(void)
0x180076711  mov     rax, rbx
0x180076714  add     rsp, 20h
0x180076718  pop     rbx
0x180076719  retn
```
