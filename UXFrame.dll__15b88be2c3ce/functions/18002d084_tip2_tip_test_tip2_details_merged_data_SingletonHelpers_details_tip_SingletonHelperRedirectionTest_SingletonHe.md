# tip2::tip_test<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::ensure_data(void)

- ea: `0x18002d084`
- end: `0x18002d0dd`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800221a8`
- `0x18002d9cc`

## callees

- `0x180016fdc`
- `0x180021340`
- `0x180021be8`
- `0x180029f7c`
- `0x18002d084`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002d098`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002d098`

## pseudocode

```c
void **__fastcall tip2::tip_test<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::ensure_data(
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
    v4 = tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>(v2);
    v5 = *a1;
    v7[0] = 0;
    *a1 = (void *)v4;
    if ( v5 )
      tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>::Release(v5);
    wil::com_ptr_t<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>,wil::err_returncode_policy>(v7);
  }
  return a1;
}

```

## disassembly

```asm
0x18002d084  push    rbx
0x18002d086  sub     rsp, 30h
0x18002d08a  cmp     qword ptr [rcx], 0
0x18002d08e  mov     rbx, rcx
0x18002d091  jnz     short loc_18002D0CE
0x18002d093  mov     ecx, 140h; cb
0x18002d098  call    cs:__imp_CoTaskMemAlloc
0x18002d09e  test    rax, rax
0x18002d0a1  jz      short loc_18002D0D7
0x18002d0a3  mov     rcx, rax
0x18002d0a6  call    ??0?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>(void)
0x18002d0ab  mov     rcx, [rbx]; pv
0x18002d0ae  mov     [rsp+38h+var_18], 0
0x18002d0b7  mov     [rbx], rax
0x18002d0ba  test    rcx, rcx
0x18002d0bd  jz      short loc_18002D0C4
0x18002d0bf  call    ?Release@?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@AEAAKXZ; tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>::Release(void)
0x18002d0c4  lea     rcx, [rsp+38h+var_18]
0x18002d0c9  call    ??1?$com_ptr_t@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>,wil::err_returncode_policy>(void)
0x18002d0ce  mov     rax, rbx
0x18002d0d1  add     rsp, 30h
0x18002d0d5  pop     rbx
0x18002d0d6  retn
0x18002d0d7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
