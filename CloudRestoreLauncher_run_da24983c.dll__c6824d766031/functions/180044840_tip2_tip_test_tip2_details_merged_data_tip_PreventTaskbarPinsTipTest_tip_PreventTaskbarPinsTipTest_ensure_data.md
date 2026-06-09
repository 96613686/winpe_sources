# tip2::tip_test<tip2::details::merged_data<_tip_PreventTaskbarPinsTipTest,_tip_PreventTaskbarPinsTipTest>>::ensure_data(void)

- ea: `0x180044840`
- end: `0x180044892`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_PreventTaskbarPinsTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_PreventTaskbarPinsTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `82`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180034800`
- `0x180069324`

## callees

- `0x180012ab4`
- `0x1800352ac`
- `0x18003628c`
- `0x180036c44`
- `0x180044840`

## import_xrefs

- `OLE32!CoTaskMemAlloc` at `0x180044854`
- `OLE32!CoTaskMemAlloc` at `0x180044854`

## pseudocode

```c
_QWORD *__fastcall tip2::tip_test<tip2::details::merged_data<_tip_PreventTaskbarPinsTipTest,_tip_PreventTaskbarPinsTipTest>>::ensure_data(
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
    v5 = tip2::details::merged_data<_tip_PreventTaskbarPinsTipTest,_tip_PreventTaskbarPinsTipTest>::merged_data<_tip_PreventTaskbarPinsTipTest,_tip_PreventTaskbarPinsTipTest>(v2);
    wil::com_ptr_t<tip2::details::merged_data<_tip_PreventTaskbarPinsTipTest,_tip_PreventTaskbarPinsTipTest>,wil::err_returncode_policy>::operator=(
      a1,
      &v5);
    wil::com_ptr_t<tip2::details::merged_data<_tip_PreventTaskbarPinsTipTest,_tip_PreventTaskbarPinsTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PreventTaskbarPinsTipTest,_tip_PreventTaskbarPinsTipTest>,wil::err_returncode_policy>(&v5);
  }
  return a1;
}

```

## disassembly

```asm
0x180044840  push    rbx
0x180044842  sub     rsp, 20h
0x180044846  cmp     qword ptr [rcx], 0
0x18004484a  mov     rbx, rcx
0x18004484d  jnz     short loc_180044883
0x18004484f  mov     ecx, 120h; cb
0x180044854  call    cs:__imp_CoTaskMemAlloc
0x18004485a  test    rax, rax
0x18004485d  jz      short loc_18004488C
0x18004485f  mov     rcx, rax
0x180044862  call    ??0?$merged_data@U_tip_PreventTaskbarPinsTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_PreventTaskbarPinsTipTest,_tip_PreventTaskbarPinsTipTest>::merged_data<_tip_PreventTaskbarPinsTipTest,_tip_PreventTaskbarPinsTipTest>(void)
0x180044867  lea     rdx, [rsp+28h+arg_0]
0x18004486c  mov     [rsp+28h+arg_0], rax
0x180044871  mov     rcx, rbx
0x180044874  call    ??4?$com_ptr_t@V?$merged_data@U_tip_PreventTaskbarPinsTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<_tip_PreventTaskbarPinsTipTest,_tip_PreventTaskbarPinsTipTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_PreventTaskbarPinsTipTest,_tip_PreventTaskbarPinsTipTest>,wil::err_returncode_policy> &&)
0x180044879  lea     rcx, [rsp+28h+arg_0]
0x18004487e  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PreventTaskbarPinsTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PreventTaskbarPinsTipTest,_tip_PreventTaskbarPinsTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PreventTaskbarPinsTipTest,_tip_PreventTaskbarPinsTipTest>,wil::err_returncode_policy>(void)
0x180044883  mov     rax, rbx
0x180044886  add     rsp, 20h
0x18004488a  pop     rbx
0x18004488b  retn
0x18004488c  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
```
