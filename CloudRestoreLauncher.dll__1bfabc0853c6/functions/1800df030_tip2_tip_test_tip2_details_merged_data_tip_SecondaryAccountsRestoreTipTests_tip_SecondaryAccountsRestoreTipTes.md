# tip2::tip_test<tip2::details::merged_data<_tip_SecondaryAccountsRestoreTipTests,_tip_SecondaryAccountsRestoreTipTests>>::ensure_data(void)

- ea: `0x1800df030`
- end: `0x1800df089`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_SecondaryAccountsRestoreTipTests@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_SecondaryAccountsRestoreTipTests@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800dd3f0`
- `0x1800deef8`

## callees

- `0x180012ab4`
- `0x1800da890`
- `0x1800dad84`
- `0x1800dd6c8`
- `0x1800df030`

## import_xrefs

- `OLE32!CoTaskMemAlloc` at `0x1800df044`
- `OLE32!CoTaskMemAlloc` at `0x1800df044`

## pseudocode

```c
void **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_SecondaryAccountsRestoreTipTests,_tip_SecondaryAccountsRestoreTipTests>>::ensure_data(
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
      wil::details::in1diag3::FailFastImmediate_Unexpected(v3);
    v4 = tip2::details::merged_data<_tip_SecondaryAccountsRestoreTipTests,_tip_SecondaryAccountsRestoreTipTests>::merged_data<_tip_SecondaryAccountsRestoreTipTests,_tip_SecondaryAccountsRestoreTipTests>(v2);
    v5 = *a1;
    v7 = 0;
    *a1 = (void *)v4;
    if ( v5 )
      tip2::details::merged_data<_tip_SecondaryAccountsRestoreTipTests,_tip_SecondaryAccountsRestoreTipTests>::Release(v5);
    wil::com_ptr_t<tip2::details::merged_data<_tip_SecondaryAccountsRestoreTipTests,_tip_SecondaryAccountsRestoreTipTests>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SecondaryAccountsRestoreTipTests,_tip_SecondaryAccountsRestoreTipTests>,wil::err_returncode_policy>(&v7);
  }
  return a1;
}

```

## disassembly

```asm
0x1800df030  push    rbx
0x1800df032  sub     rsp, 20h
0x1800df036  cmp     qword ptr [rcx], 0
0x1800df03a  mov     rbx, rcx
0x1800df03d  jnz     short loc_1800DF07A
0x1800df03f  mov     ecx, 120h; cb
0x1800df044  call    cs:__imp_CoTaskMemAlloc
0x1800df04a  test    rax, rax
0x1800df04d  jz      short loc_1800DF083
0x1800df04f  mov     rcx, rax
0x1800df052  call    ??0?$merged_data@U_tip_SecondaryAccountsRestoreTipTests@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_SecondaryAccountsRestoreTipTests,_tip_SecondaryAccountsRestoreTipTests>::merged_data<_tip_SecondaryAccountsRestoreTipTests,_tip_SecondaryAccountsRestoreTipTests>(void)
0x1800df057  mov     rcx, [rbx]; pv
0x1800df05a  mov     [rsp+28h+arg_0], 0
0x1800df063  mov     [rbx], rax
0x1800df066  test    rcx, rcx
0x1800df069  jz      short loc_1800DF070
0x1800df06b  call    ?Release@?$merged_data@U_tip_SecondaryAccountsRestoreTipTests@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_SecondaryAccountsRestoreTipTests,_tip_SecondaryAccountsRestoreTipTests>::Release(void)
0x1800df070  lea     rcx, [rsp+28h+arg_0]
0x1800df075  call    ??1?$com_ptr_t@V?$merged_data@U_tip_SecondaryAccountsRestoreTipTests@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_SecondaryAccountsRestoreTipTests,_tip_SecondaryAccountsRestoreTipTests>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SecondaryAccountsRestoreTipTests,_tip_SecondaryAccountsRestoreTipTests>,wil::err_returncode_policy>(void)
0x1800df07a  mov     rax, rbx
0x1800df07d  add     rsp, 20h
0x1800df081  pop     rbx
0x1800df082  retn
0x1800df083  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
```
