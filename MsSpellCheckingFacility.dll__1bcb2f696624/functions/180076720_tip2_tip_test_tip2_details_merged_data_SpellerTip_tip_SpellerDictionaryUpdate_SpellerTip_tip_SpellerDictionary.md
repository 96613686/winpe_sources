# tip2::tip_test<tip2::details::merged_data<SpellerTip::_tip_SpellerDictionaryUpdate,SpellerTip::_tip_SpellerDictionaryUpdate>>::ensure_data(void)

- ea: `0x180076720`
- end: `0x180076772`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_SpellerDictionaryUpdate@SpellerTip@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_SpellerDictionaryUpdate@SpellerTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
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
- `0x180073940`
- `0x180073e0c`
- `0x18007405c`
- `0x180076720`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180076734`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180076734`

## pseudocode

```c
_QWORD *__fastcall tip2::tip_test<tip2::details::merged_data<SpellerTip::_tip_SpellerDictionaryUpdate,SpellerTip::_tip_SpellerDictionaryUpdate>>::ensure_data(
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
    v5 = tip2::details::merged_data<SpellerTip::_tip_SpellerDictionaryUpdate,SpellerTip::_tip_SpellerDictionaryUpdate>::merged_data<SpellerTip::_tip_SpellerDictionaryUpdate,SpellerTip::_tip_SpellerDictionaryUpdate>(v2);
    wil::com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_SpellerDictionaryUpdate,SpellerTip::_tip_SpellerDictionaryUpdate>,wil::err_returncode_policy>::operator=(
      a1,
      &v5);
    wil::com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_SpellerDictionaryUpdate,SpellerTip::_tip_SpellerDictionaryUpdate>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_SpellerDictionaryUpdate,SpellerTip::_tip_SpellerDictionaryUpdate>,wil::err_returncode_policy>(&v5);
  }
  return a1;
}

```

## disassembly

```asm
0x180076720  push    rbx
0x180076722  sub     rsp, 20h
0x180076726  cmp     qword ptr [rcx], 0
0x18007672a  mov     rbx, rcx
0x18007672d  jnz     short loc_180076769
0x18007672f  mov     ecx, 120h; cb
0x180076734  call    cs:__imp_CoTaskMemAlloc
0x18007673a  test    rax, rax
0x18007673d  jnz     short loc_180076745
0x18007673f  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
0x180076745  mov     rcx, rax
0x180076748  call    ??0?$merged_data@U_tip_SpellerDictionaryUpdate@SpellerTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<SpellerTip::_tip_SpellerDictionaryUpdate,SpellerTip::_tip_SpellerDictionaryUpdate>::merged_data<SpellerTip::_tip_SpellerDictionaryUpdate,SpellerTip::_tip_SpellerDictionaryUpdate>(void)
0x18007674d  lea     rdx, [rsp+28h+arg_0]
0x180076752  mov     [rsp+28h+arg_0], rax
0x180076757  mov     rcx, rbx
0x18007675a  call    ??4?$com_ptr_t@V?$merged_data@U_tip_SpellerDictionaryUpdate@SpellerTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_SpellerDictionaryUpdate,SpellerTip::_tip_SpellerDictionaryUpdate>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_SpellerDictionaryUpdate,SpellerTip::_tip_SpellerDictionaryUpdate>,wil::err_returncode_policy> &&)
0x18007675f  lea     rcx, [rsp+28h+arg_0]
0x180076764  call    ??1?$com_ptr_t@V?$merged_data@U_tip_SpellerDictionaryUpdate@SpellerTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_SpellerDictionaryUpdate,SpellerTip::_tip_SpellerDictionaryUpdate>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_SpellerDictionaryUpdate,SpellerTip::_tip_SpellerDictionaryUpdate>,wil::err_returncode_policy>(void)
0x180076769  mov     rax, rbx
0x18007676c  add     rsp, 20h
0x180076770  pop     rbx
0x180076771  retn
```
