# tip2::open<tip2::tip_test<tip2::details::merged_data<SpellerTip::_tip_SpellerDictionaryUpdate,SpellerTip::_tip_SpellerDictionaryUpdate>>>(void)

- ea: `0x18007b8fc`
- end: `0x18007b951`
- name: `??$open@V?$tip_test@V?$merged_data@U_tip_SpellerDictionaryUpdate@SpellerTip@@U12@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_SpellerDictionaryUpdate@SpellerTip@@U12@@details@tip2@@@0@XZ`
- size: `85`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180046b88`
- `0x1800510bc`
- `0x180082050`

## callees

- `0x18006a0b0`
- `0x180073e0c`
- `0x18007405c`
- `0x18007b8fc`
- `0x18007bee0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007b911`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007b911`

## pseudocode

```c
_QWORD *__fastcall tip2::open<tip2::tip_test<tip2::details::merged_data<SpellerTip::_tip_SpellerDictionaryUpdate,SpellerTip::_tip_SpellerDictionaryUpdate>>>(
        _QWORD *a1)
{
  LPVOID v2; // rax
  wil::details::in1diag3 *v3; // rcx
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v2 = CoTaskMemAlloc(0x120u);
  if ( !v2 )
    wil::details::in1diag3::FailFastImmediate_Unexpected(v3);
  v5 = tip2::details::merged_data<SpellerTip::_tip_SpellerDictionaryUpdate,SpellerTip::_tip_SpellerDictionaryUpdate>::merged_data<SpellerTip::_tip_SpellerDictionaryUpdate,SpellerTip::_tip_SpellerDictionaryUpdate>(
         v2,
         0);
  wil::com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_SpellerDictionaryUpdate,SpellerTip::_tip_SpellerDictionaryUpdate>,wil::err_returncode_policy>::operator=(
    a1,
    &v5);
  wil::com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_SpellerDictionaryUpdate,SpellerTip::_tip_SpellerDictionaryUpdate>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_SpellerDictionaryUpdate,SpellerTip::_tip_SpellerDictionaryUpdate>,wil::err_returncode_policy>(&v5);
  return a1;
}

```

## disassembly

```asm
0x18007b8fc  push    rbx
0x18007b8fe  sub     rsp, 20h
0x18007b902  mov     rbx, rcx
0x18007b905  mov     qword ptr [rcx], 0
0x18007b90c  mov     ecx, 120h; cb
0x18007b911  call    cs:__imp_CoTaskMemAlloc
0x18007b917  test    rax, rax
0x18007b91a  jnz     short loc_18007B922
0x18007b91c  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
0x18007b922  xor     edx, edx
0x18007b924  mov     rcx, rax
0x18007b927  call    ??0?$merged_data@U_tip_SpellerDictionaryUpdate@SpellerTip@@U12@@details@tip2@@QEAA@PEAU_GUID@@@Z; tip2::details::merged_data<SpellerTip::_tip_SpellerDictionaryUpdate,SpellerTip::_tip_SpellerDictionaryUpdate>::merged_data<SpellerTip::_tip_SpellerDictionaryUpdate,SpellerTip::_tip_SpellerDictionaryUpdate>(_GUID *)
0x18007b92c  lea     rdx, [rsp+28h+arg_0]
0x18007b931  mov     [rsp+28h+arg_0], rax
0x18007b936  mov     rcx, rbx
0x18007b939  call    ??4?$com_ptr_t@V?$merged_data@U_tip_SpellerDictionaryUpdate@SpellerTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_SpellerDictionaryUpdate,SpellerTip::_tip_SpellerDictionaryUpdate>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_SpellerDictionaryUpdate,SpellerTip::_tip_SpellerDictionaryUpdate>,wil::err_returncode_policy> &&)
0x18007b93e  lea     rcx, [rsp+28h+arg_0]
0x18007b943  call    ??1?$com_ptr_t@V?$merged_data@U_tip_SpellerDictionaryUpdate@SpellerTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_SpellerDictionaryUpdate,SpellerTip::_tip_SpellerDictionaryUpdate>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_SpellerDictionaryUpdate,SpellerTip::_tip_SpellerDictionaryUpdate>,wil::err_returncode_policy>(void)
0x18007b948  mov     rax, rbx
0x18007b94b  add     rsp, 20h
0x18007b94f  pop     rbx
0x18007b950  retn
```
