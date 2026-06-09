# tip2::tip_test<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::ensure_data(void)

- ea: `0x18002d0e4`
- end: `0x18002d13d`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_UXFrameInvocationTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_UXFrameInvocationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `89`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180021a28`
- `0x1800221e4`
- `0x18002da60`
- `0x18004a43c`

## callees

- `0x18000de84`
- `0x180014c34`
- `0x180016fdc`
- `0x1800213f4`
- `0x18002d0e4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002d0f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002d0f8`

## pseudocode

```c
void **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::ensure_data(
        void **a1)
{
  LPVOID v2; // rax
  wil::details::in1diag3 *v3; // rcx
  __int64 v4; // rax
  void *v5; // rcx
  _QWORD v7[3]; // [rsp+20h] [rbp-18h] BYREF

  if ( !*a1 )
  {
    v2 = CoTaskMemAlloc(0x140u);
    if ( !v2 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
    v4 = tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>(v2);
    v5 = *a1;
    v7[0] = 0;
    *a1 = (void *)v4;
    if ( v5 )
      tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>::Release(v5);
    wil::com_ptr_t<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>,wil::err_returncode_policy>(v7);
  }
  return a1;
}

```

## disassembly

```asm
0x18002d0e4  push    rbx
0x18002d0e6  sub     rsp, 30h
0x18002d0ea  cmp     qword ptr [rcx], 0
0x18002d0ee  mov     rbx, rcx
0x18002d0f1  jnz     short loc_18002D134
0x18002d0f3  mov     ecx, 140h; cb
0x18002d0f8  call    cs:__imp_CoTaskMemAlloc
0x18002d0fe  test    rax, rax
0x18002d101  jnz     short loc_18002D109
0x18002d103  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18002d109  mov     rcx, rax
0x18002d10c  call    ??0?$merged_data@U_tip_UXFrameInvocationTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>(void)
0x18002d111  mov     rcx, [rbx]; pv
0x18002d114  mov     [rsp+38h+var_18], 0
0x18002d11d  mov     [rbx], rax
0x18002d120  test    rcx, rcx
0x18002d123  jz      short loc_18002D12A
0x18002d125  call    ?Release@?$merged_data@U_tip_UXFrameInvocationTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>::Release(void)
0x18002d12a  lea     rcx, [rsp+38h+var_18]
0x18002d12f  call    ??1?$com_ptr_t@V?$merged_data@U_tip_UXFrameInvocationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>,wil::err_returncode_policy>(void)
0x18002d134  mov     rax, rbx
0x18002d137  add     rsp, 30h
0x18002d13b  pop     rbx
0x18002d13c  retn
```
