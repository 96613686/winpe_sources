# tip2::tip_test<tip2::details::merged_data<SpellerTip::_tip_CDSNotificationHandled,SpellerTip::_tip_CDSNotificationHandled>>::ensure_data(void)

- ea: `0x18005c60c`
- end: `0x18005c65e`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_CDSNotificationHandled@SpellerTip@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_CDSNotificationHandled@SpellerTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `82`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005c35c`
- `0x18007ded0`

## callees

- `0x18005c60c`
- `0x18005c664`
- `0x18006a0b0`
- `0x18007bd88`
- `0x18007d0a8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005c620`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005c620`

## pseudocode

```c
_QWORD *__fastcall tip2::tip_test<tip2::details::merged_data<SpellerTip::_tip_CDSNotificationHandled,SpellerTip::_tip_CDSNotificationHandled>>::ensure_data(
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
    v5 = tip2::details::merged_data<SpellerTip::_tip_CDSNotificationHandled,SpellerTip::_tip_CDSNotificationHandled>::merged_data<SpellerTip::_tip_CDSNotificationHandled,SpellerTip::_tip_CDSNotificationHandled>(v2);
    wil::com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_CDSNotificationHandled,SpellerTip::_tip_CDSNotificationHandled>,wil::err_returncode_policy>::operator=(
      a1,
      &v5);
    wil::com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_CDSNotificationHandled,SpellerTip::_tip_CDSNotificationHandled>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_CDSNotificationHandled,SpellerTip::_tip_CDSNotificationHandled>,wil::err_returncode_policy>(&v5);
  }
  return a1;
}

```

## disassembly

```asm
0x18005c60c  push    rbx
0x18005c60e  sub     rsp, 20h
0x18005c612  cmp     qword ptr [rcx], 0
0x18005c616  mov     rbx, rcx
0x18005c619  jnz     short loc_18005C655
0x18005c61b  mov     ecx, 120h; cb
0x18005c620  call    cs:__imp_CoTaskMemAlloc
0x18005c626  test    rax, rax
0x18005c629  jnz     short loc_18005C631
0x18005c62b  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
0x18005c631  mov     rcx, rax
0x18005c634  call    ??0?$merged_data@U_tip_CDSNotificationHandled@SpellerTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<SpellerTip::_tip_CDSNotificationHandled,SpellerTip::_tip_CDSNotificationHandled>::merged_data<SpellerTip::_tip_CDSNotificationHandled,SpellerTip::_tip_CDSNotificationHandled>(void)
0x18005c639  lea     rdx, [rsp+28h+arg_0]
0x18005c63e  mov     [rsp+28h+arg_0], rax
0x18005c643  mov     rcx, rbx
0x18005c646  call    ??4?$com_ptr_t@V?$merged_data@U_tip_CDSNotificationHandled@SpellerTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_CDSNotificationHandled,SpellerTip::_tip_CDSNotificationHandled>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_CDSNotificationHandled,SpellerTip::_tip_CDSNotificationHandled>,wil::err_returncode_policy> &&)
0x18005c64b  lea     rcx, [rsp+28h+arg_0]
0x18005c650  call    ??1?$com_ptr_t@V?$merged_data@U_tip_CDSNotificationHandled@SpellerTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_CDSNotificationHandled,SpellerTip::_tip_CDSNotificationHandled>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_CDSNotificationHandled,SpellerTip::_tip_CDSNotificationHandled>,wil::err_returncode_policy>(void)
0x18005c655  mov     rax, rbx
0x18005c658  add     rsp, 20h
0x18005c65c  pop     rbx
0x18005c65d  retn
```
