# tip2::tip_test<tip2::details::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>>::ensure_data(void)

- ea: `0x180034e04`
- end: `0x180034e56`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_NetworkUXManagerInitializationTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_NetworkUXManagerInitializationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `82`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180028ff4`
- `0x180031dec`

## callees

- `0x18000f034`
- `0x180027270`
- `0x180028304`
- `0x180028ec4`
- `0x180034e04`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034e18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034e18`

## pseudocode

```c
void **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>>::ensure_data(
        void **a1)
{
  LPVOID v2; // rax
  wil::details::in1diag3 *v3; // rcx
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF

  if ( !*a1 )
  {
    v2 = CoTaskMemAlloc(0x138u);
    if ( !v2 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
    v5 = tip2::details::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>(v2);
    wil::com_ptr_t<tip2::details::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>,wil::err_returncode_policy>::operator=(
      a1,
      (void **)&v5);
    wil::com_ptr_t<tip2::details::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>,wil::err_returncode_policy>((void **)&v5);
  }
  return a1;
}

```

## disassembly

```asm
0x180034e04  push    rbx
0x180034e06  sub     rsp, 20h
0x180034e0a  cmp     qword ptr [rcx], 0
0x180034e0e  mov     rbx, rcx
0x180034e11  jnz     short loc_180034E47
0x180034e13  mov     ecx, 138h; cb
0x180034e18  call    cs:__imp_CoTaskMemAlloc
0x180034e1e  test    rax, rax
0x180034e21  jz      short loc_180034E50
0x180034e23  mov     rcx, rax
0x180034e26  call    ??0?$merged_data@U_tip_NetworkUXManagerInitializationTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>(void)
0x180034e2b  lea     rdx, [rsp+28h+arg_0]
0x180034e30  mov     [rsp+28h+arg_0], rax
0x180034e35  mov     rcx, rbx
0x180034e38  call    ??4?$com_ptr_t@V?$merged_data@U_tip_NetworkUXManagerInitializationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>,wil::err_returncode_policy> &&)
0x180034e3d  lea     rcx, [rsp+28h+arg_0]
0x180034e42  call    ??1?$com_ptr_t@V?$merged_data@U_tip_NetworkUXManagerInitializationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>,wil::err_returncode_policy>(void)
0x180034e47  mov     rax, rbx
0x180034e4a  add     rsp, 20h
0x180034e4e  pop     rbx
0x180034e4f  retn
0x180034e50  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
