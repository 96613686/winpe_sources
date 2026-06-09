# tip2::tip_test<tip2::details::merged_data<_tip_OmadmClientAadTokenExpirationTipTest,_tip_OmadmClientAadTokenExpirationTipTest>>::ensure_data(void)

- ea: `0x180078934`
- end: `0x18007898d`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_OmadmClientAadTokenExpirationTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_OmadmClientAadTokenExpirationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180074d0c`
- `0x1800759c0`

## callees

- `0x180059220`
- `0x180074690`
- `0x180074994`
- `0x180074cd8`
- `0x180078934`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180078948`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180078948`

## pseudocode

```c
_QWORD *__fastcall tip2::tip_test<tip2::details::merged_data<_tip_OmadmClientAadTokenExpirationTipTest,_tip_OmadmClientAadTokenExpirationTipTest>>::ensure_data(
        _QWORD *a1)
{
  LPVOID v2; // rax
  wil::details::in1diag3 *v3; // rcx
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF

  if ( !*a1 )
  {
    v2 = CoTaskMemAlloc(0x128u);
    if ( !v2 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
    v5 = tip2::details::merged_data<_tip_OmadmClientAadTokenExpirationTipTest,_tip_OmadmClientAadTokenExpirationTipTest>::merged_data<_tip_OmadmClientAadTokenExpirationTipTest,_tip_OmadmClientAadTokenExpirationTipTest>(v2);
    wil::com_ptr_t<tip2::details::merged_data<_tip_OmadmClientAadTokenExpirationTipTest,_tip_OmadmClientAadTokenExpirationTipTest>,wil::err_returncode_policy>::operator=(
      a1,
      &v5);
    wil::com_ptr_t<tip2::details::merged_data<_tip_OmadmClientAadTokenExpirationTipTest,_tip_OmadmClientAadTokenExpirationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OmadmClientAadTokenExpirationTipTest,_tip_OmadmClientAadTokenExpirationTipTest>,wil::err_returncode_policy>(&v5);
  }
  return a1;
}

```

## disassembly

```asm
0x180078934  push    rbx
0x180078936  sub     rsp, 20h
0x18007893a  cmp     qword ptr [rcx], 0
0x18007893e  mov     rbx, rcx
0x180078941  jnz     short loc_18007897D
0x180078943  mov     ecx, 128h; cb
0x180078948  call    cs:__imp_CoTaskMemAlloc
0x18007894f  nop     dword ptr [rax+rax+00h]
0x180078954  test    rax, rax
0x180078957  jz      short loc_180078987
0x180078959  mov     rcx, rax
0x18007895c  call    ??0?$merged_data@U_tip_OmadmClientAadTokenExpirationTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_OmadmClientAadTokenExpirationTipTest,_tip_OmadmClientAadTokenExpirationTipTest>::merged_data<_tip_OmadmClientAadTokenExpirationTipTest,_tip_OmadmClientAadTokenExpirationTipTest>(void)
0x180078961  lea     rdx, [rsp+28h+arg_0]
0x180078966  mov     [rsp+28h+arg_0], rax
0x18007896b  mov     rcx, rbx
0x18007896e  call    ??4?$com_ptr_t@V?$merged_data@U_tip_OmadmClientAadTokenExpirationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<_tip_OmadmClientAadTokenExpirationTipTest,_tip_OmadmClientAadTokenExpirationTipTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_OmadmClientAadTokenExpirationTipTest,_tip_OmadmClientAadTokenExpirationTipTest>,wil::err_returncode_policy> &&)
0x180078973  lea     rcx, [rsp+28h+arg_0]
0x180078978  call    ??1?$com_ptr_t@V?$merged_data@U_tip_OmadmClientAadTokenExpirationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_OmadmClientAadTokenExpirationTipTest,_tip_OmadmClientAadTokenExpirationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OmadmClientAadTokenExpirationTipTest,_tip_OmadmClientAadTokenExpirationTipTest>,wil::err_returncode_policy>(void)
0x18007897d  mov     rax, rbx
0x180078980  add     rsp, 20h
0x180078984  pop     rbx
0x180078985  retn
0x180078987  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
