# tip2::open<tip2::tip_test<tip2::details::merged_data<SpellerTip::_tip_CDSNotificationHandled,SpellerTip::_tip_CDSNotificationHandled>>>(void)

- ea: `0x18007b844`
- end: `0x18007b899`
- name: `??$open@V?$tip_test@V?$merged_data@U_tip_CDSNotificationHandled@SpellerTip@@U12@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_CDSNotificationHandled@SpellerTip@@U12@@details@tip2@@@0@XZ`
- size: `85`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180041524`
- `0x18007ded0`

## callees

- `0x18005c664`
- `0x18006a0b0`
- `0x18007b844`
- `0x18007bcd0`
- `0x18007d0a8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007b859`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007b859`

## pseudocode

```c
_QWORD *__fastcall tip2::open<tip2::tip_test<tip2::details::merged_data<SpellerTip::_tip_CDSNotificationHandled,SpellerTip::_tip_CDSNotificationHandled>>>(
        _QWORD *a1)
{
  LPVOID v2; // rax
  wil::details::in1diag3 *v3; // rcx
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v2 = CoTaskMemAlloc(0x120u);
  if ( !v2 )
    wil::details::in1diag3::FailFastImmediate_Unexpected(v3);
  v5 = tip2::details::merged_data<SpellerTip::_tip_CDSNotificationHandled,SpellerTip::_tip_CDSNotificationHandled>::merged_data<SpellerTip::_tip_CDSNotificationHandled,SpellerTip::_tip_CDSNotificationHandled>(
         v2,
         0);
  wil::com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_CDSNotificationHandled,SpellerTip::_tip_CDSNotificationHandled>,wil::err_returncode_policy>::operator=(
    a1,
    &v5);
  wil::com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_CDSNotificationHandled,SpellerTip::_tip_CDSNotificationHandled>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_CDSNotificationHandled,SpellerTip::_tip_CDSNotificationHandled>,wil::err_returncode_policy>(&v5);
  return a1;
}

```

## disassembly

```asm
0x18007b844  push    rbx
0x18007b846  sub     rsp, 20h
0x18007b84a  mov     rbx, rcx
0x18007b84d  mov     qword ptr [rcx], 0
0x18007b854  mov     ecx, 120h; cb
0x18007b859  call    cs:__imp_CoTaskMemAlloc
0x18007b85f  test    rax, rax
0x18007b862  jnz     short loc_18007B86A
0x18007b864  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
0x18007b86a  xor     edx, edx
0x18007b86c  mov     rcx, rax
0x18007b86f  call    ??0?$merged_data@U_tip_CDSNotificationHandled@SpellerTip@@U12@@details@tip2@@QEAA@PEAU_GUID@@@Z; tip2::details::merged_data<SpellerTip::_tip_CDSNotificationHandled,SpellerTip::_tip_CDSNotificationHandled>::merged_data<SpellerTip::_tip_CDSNotificationHandled,SpellerTip::_tip_CDSNotificationHandled>(_GUID *)
0x18007b874  lea     rdx, [rsp+28h+arg_0]
0x18007b879  mov     [rsp+28h+arg_0], rax
0x18007b87e  mov     rcx, rbx
0x18007b881  call    ??4?$com_ptr_t@V?$merged_data@U_tip_CDSNotificationHandled@SpellerTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_CDSNotificationHandled,SpellerTip::_tip_CDSNotificationHandled>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_CDSNotificationHandled,SpellerTip::_tip_CDSNotificationHandled>,wil::err_returncode_policy> &&)
0x18007b886  lea     rcx, [rsp+28h+arg_0]
0x18007b88b  call    ??1?$com_ptr_t@V?$merged_data@U_tip_CDSNotificationHandled@SpellerTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_CDSNotificationHandled,SpellerTip::_tip_CDSNotificationHandled>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SpellerTip::_tip_CDSNotificationHandled,SpellerTip::_tip_CDSNotificationHandled>,wil::err_returncode_policy>(void)
0x18007b890  mov     rax, rbx
0x18007b893  add     rsp, 20h
0x18007b897  pop     rbx
0x18007b898  retn
```
