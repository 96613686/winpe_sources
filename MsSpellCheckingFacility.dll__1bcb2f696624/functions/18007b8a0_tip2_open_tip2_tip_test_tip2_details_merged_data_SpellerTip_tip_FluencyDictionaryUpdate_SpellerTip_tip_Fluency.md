# tip2::open<tip2::tip_test<tip2::details::merged_data<SpellerTip::_tip_FluencyDictionaryUpdate,SpellerTip::_tip_FluencyDictionaryUpdate>>>(void)

- ea: `0x18007b8a0`
- end: `0x18007b8f5`
- name: `??$open@V?$tip_test@V?$merged_data@U_tip_FluencyDictionaryUpdate@SpellerTip@@U12@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_FluencyDictionaryUpdate@SpellerTip@@U12@@details@tip2@@@0@XZ`
- size: `85`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800510bc`
- `0x180082050`

## callees

- `0x18006a0b0`
- `0x180073df0`
- `0x180074028`
- `0x18007b8a0`
- `0x18007be20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007b8b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007b8b5`

## pseudocode

```c
_QWORD *__fastcall tip2::open<tip2::tip_test<tip2::details::merged_data<SpellerTip::_tip_FluencyDictionaryUpdate,SpellerTip::_tip_FluencyDictionaryUpdate>>>(
        _QWORD *a1)
{
  LPVOID v2; // rax
  wil::details::in1diag3 *v3; // rcx
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v2 = CoTaskMemAlloc(0x120u);
  if ( !v2 )
    wil::details::in1diag3::FailFastImmediate_Unexpected(v3);
  v5 = tip2::details::merged_data<SpellerTip::_tip_FluencyDictionaryUpdate,SpellerTip::_tip_FluencyDictionaryUpdate>::merged_data<SpellerTip::_tip_FluencyDictionaryUpdate,SpellerTip::_tip_FluencyDictionaryUpdate>(
         v2,
         0);
  wil::com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_FluencyDictionaryUpdate,SpellerTip::_tip_FluencyDictionaryUpdate>,wil::err_returncode_policy>::operator=(
    a1,
    &v5);
  wil::com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_FluencyDictionaryUpdate,SpellerTip::_tip_FluencyDictionaryUpdate>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_FluencyDictionaryUpdate,SpellerTip::_tip_FluencyDictionaryUpdate>,wil::err_returncode_policy>(&v5);
  return a1;
}

```

## disassembly

```asm
0x18007b8a0  push    rbx
0x18007b8a2  sub     rsp, 20h
0x18007b8a6  mov     rbx, rcx
0x18007b8a9  mov     qword ptr [rcx], 0
0x18007b8b0  mov     ecx, 120h; cb
0x18007b8b5  call    cs:__imp_CoTaskMemAlloc
0x18007b8bb  test    rax, rax
0x18007b8be  jnz     short loc_18007B8C6
0x18007b8c0  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
0x18007b8c6  xor     edx, edx
0x18007b8c8  mov     rcx, rax
0x18007b8cb  call    ??0?$merged_data@U_tip_FluencyDictionaryUpdate@SpellerTip@@U12@@details@tip2@@QEAA@PEAU_GUID@@@Z; tip2::details::merged_data<SpellerTip::_tip_FluencyDictionaryUpdate,SpellerTip::_tip_FluencyDictionaryUpdate>::merged_data<SpellerTip::_tip_FluencyDictionaryUpdate,SpellerTip::_tip_FluencyDictionaryUpdate>(_GUID *)
0x18007b8d0  lea     rdx, [rsp+28h+arg_0]
0x18007b8d5  mov     [rsp+28h+arg_0], rax
0x18007b8da  mov     rcx, rbx
0x18007b8dd  call    ??4?$com_ptr_t@V?$merged_data@U_tip_FluencyDictionaryUpdate@SpellerTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_FluencyDictionaryUpdate,SpellerTip::_tip_FluencyDictionaryUpdate>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_FluencyDictionaryUpdate,SpellerTip::_tip_FluencyDictionaryUpdate>,wil::err_returncode_policy> &&)
0x18007b8e2  lea     rcx, [rsp+28h+arg_0]
0x18007b8e7  call    ??1?$com_ptr_t@V?$merged_data@U_tip_FluencyDictionaryUpdate@SpellerTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_FluencyDictionaryUpdate,SpellerTip::_tip_FluencyDictionaryUpdate>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_FluencyDictionaryUpdate,SpellerTip::_tip_FluencyDictionaryUpdate>,wil::err_returncode_policy>(void)
0x18007b8ec  mov     rax, rbx
0x18007b8ef  add     rsp, 20h
0x18007b8f3  pop     rbx
0x18007b8f4  retn
```
