# tip2::tip_test<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>>::ensure_data(void)

- ea: `0x18003ca04`
- end: `0x18003ca56`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_ShellHostAppManagerTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_ShellHostAppManagerTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `82`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800376e8`
- `0x18003ee9c`
- `0x18003f184`

## callees

- `0x180007d14`
- `0x180035e74`
- `0x180036e3c`
- `0x1800375b0`
- `0x18003ca04`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003ca18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003ca18`

## pseudocode

```c
_QWORD *__fastcall tip2::tip_test<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>>::ensure_data(
        _QWORD *a1)
{
  LPVOID v2; // rax
  wil::details::in1diag3 *v3; // rcx
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF

  if ( !*a1 )
  {
    v2 = CoTaskMemAlloc(0x180u);
    if ( !v2 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
    v5 = tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>(v2);
    wil::com_ptr_t<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>,wil::err_returncode_policy>::operator=(
      a1,
      &v5);
    wil::com_ptr_t<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>,wil::err_returncode_policy>(&v5);
  }
  return a1;
}

```

## disassembly

```asm
0x18003ca04  push    rbx
0x18003ca06  sub     rsp, 20h
0x18003ca0a  cmp     qword ptr [rcx], 0
0x18003ca0e  mov     rbx, rcx
0x18003ca11  jnz     short loc_18003CA47
0x18003ca13  mov     ecx, 180h; cb
0x18003ca18  call    cs:__imp_CoTaskMemAlloc
0x18003ca1e  test    rax, rax
0x18003ca21  jz      short loc_18003CA50
0x18003ca23  mov     rcx, rax
0x18003ca26  call    ??0?$merged_data@U_tip_ShellHostAppManagerTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>(void)
0x18003ca2b  lea     rdx, [rsp+28h+arg_0]
0x18003ca30  mov     [rsp+28h+arg_0], rax
0x18003ca35  mov     rcx, rbx
0x18003ca38  call    ??4?$com_ptr_t@V?$merged_data@U_tip_ShellHostAppManagerTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>,wil::err_returncode_policy> &&)
0x18003ca3d  lea     rcx, [rsp+28h+arg_0]
0x18003ca42  call    ??1?$com_ptr_t@V?$merged_data@U_tip_ShellHostAppManagerTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>,wil::err_returncode_policy>(void)
0x18003ca47  mov     rax, rbx
0x18003ca4a  add     rsp, 20h
0x18003ca4e  pop     rbx
0x18003ca4f  retn
0x18003ca50  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
