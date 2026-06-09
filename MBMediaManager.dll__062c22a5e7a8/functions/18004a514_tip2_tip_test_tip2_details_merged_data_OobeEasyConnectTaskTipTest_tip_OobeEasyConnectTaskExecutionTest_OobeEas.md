# tip2::tip_test<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>::ensure_data(void)

- ea: `0x18004a514`
- end: `0x18004a56d`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_OobeEasyConnectTaskExecutionTest@OobeEasyConnectTaskTipTest@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_OobeEasyConnectTaskExecutionTest@OobeEasyConnectTaskTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `89`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001fc40`
- `0x1800215a0`
- `0x180022ee8`
- `0x180047f38`

## callees

- `0x1800310d4`
- `0x18003601c`
- `0x1800365d0`
- `0x180047ac4`
- `0x18004a514`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a528`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a528`

## pseudocode

```c
void **__fastcall tip2::tip_test<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>>::ensure_data(
        void **a1)
{
  LPVOID v2; // rax
  wil::details::in1diag3 *v3; // rcx
  __int64 v4; // rax
  void *v5; // rcx
  void *v7; // [rsp+30h] [rbp+8h] BYREF

  if ( !*a1 )
  {
    v2 = CoTaskMemAlloc(0x130u);
    if ( !v2 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
    v4 = tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>((__int64)v2);
    v5 = *a1;
    v7 = 0;
    *a1 = (void *)v4;
    if ( v5 )
      tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>::Release(v5);
    wil::com_ptr_t<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>,wil::err_returncode_policy>(&v7);
  }
  return a1;
}

```

## disassembly

```asm
0x18004a514  push    rbx
0x18004a516  sub     rsp, 20h
0x18004a51a  cmp     qword ptr [rcx], 0
0x18004a51e  mov     rbx, rcx
0x18004a521  jnz     short loc_18004A564
0x18004a523  mov     ecx, 130h; cb
0x18004a528  call    cs:__imp_CoTaskMemAlloc
0x18004a52e  test    rax, rax
0x18004a531  jnz     short loc_18004A539
0x18004a533  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18004a539  mov     rcx, rax
0x18004a53c  call    ??0?$merged_data@U_tip_OobeEasyConnectTaskExecutionTest@OobeEasyConnectTaskTipTest@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>(void)
0x18004a541  mov     rcx, [rbx]; pv
0x18004a544  mov     [rsp+28h+arg_0], 0
0x18004a54d  mov     [rbx], rax
0x18004a550  test    rcx, rcx
0x18004a553  jz      short loc_18004A55A
0x18004a555  call    ?Release@?$merged_data@U_tip_OobeEasyConnectTaskExecutionTest@OobeEasyConnectTaskTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>::Release(void)
0x18004a55a  lea     rcx, [rsp+28h+arg_0]
0x18004a55f  call    ??1?$com_ptr_t@V?$merged_data@U_tip_OobeEasyConnectTaskExecutionTest@OobeEasyConnectTaskTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest,OobeEasyConnectTaskTipTest::_tip_OobeEasyConnectTaskExecutionTest>,wil::err_returncode_policy>(void)
0x18004a564  mov     rax, rbx
0x18004a567  add     rsp, 20h
0x18004a56b  pop     rbx
0x18004a56c  retn
```
