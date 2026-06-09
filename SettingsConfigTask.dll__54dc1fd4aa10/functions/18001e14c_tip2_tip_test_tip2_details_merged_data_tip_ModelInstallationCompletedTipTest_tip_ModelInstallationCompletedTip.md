# tip2::tip_test<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::ensure_data(void)

- ea: `0x18001e14c`
- end: `0x18001e1a5`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180012e64`
- `0x1800211c4`

## callees

- `0x18000ae60`
- `0x180011ac4`
- `0x1800125b0`
- `0x18001a58c`
- `0x18001e14c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e160`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e160`

## pseudocode

```c
void **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::ensure_data(
        void **a1)
{
  LPVOID v2; // rax
  wil::details::in1diag3 *v3; // rcx
  __int64 v4; // rax
  void *v5; // rcx
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  if ( !*a1 )
  {
    v2 = CoTaskMemAlloc(0x120u);
    if ( !v2 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
    v4 = tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>(v2);
    v5 = *a1;
    v7 = 0;
    *a1 = (void *)v4;
    if ( v5 )
      tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>::Release(v5);
    wil::com_ptr_t<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>,wil::err_returncode_policy>(&v7);
  }
  return a1;
}

```

## disassembly

```asm
0x18001e14c  push    rbx
0x18001e14e  sub     rsp, 20h
0x18001e152  cmp     qword ptr [rcx], 0
0x18001e156  mov     rbx, rcx
0x18001e159  jnz     short loc_18001E196
0x18001e15b  mov     ecx, 120h; cb
0x18001e160  call    cs:__imp_CoTaskMemAlloc
0x18001e166  test    rax, rax
0x18001e169  jz      short loc_18001E19F
0x18001e16b  mov     rcx, rax
0x18001e16e  call    ??0?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>(void)
0x18001e173  mov     rcx, [rbx]; pv
0x18001e176  mov     [rsp+28h+arg_0], 0
0x18001e17f  mov     [rbx], rax
0x18001e182  test    rcx, rcx
0x18001e185  jz      short loc_18001E18C
0x18001e187  call    ?Release@?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>::Release(void)
0x18001e18c  lea     rcx, [rsp+28h+arg_0]
0x18001e191  call    ??1?$com_ptr_t@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>,wil::err_returncode_policy>(void)
0x18001e196  mov     rax, rbx
0x18001e199  add     rsp, 20h
0x18001e19d  pop     rbx
0x18001e19e  retn
0x18001e19f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
