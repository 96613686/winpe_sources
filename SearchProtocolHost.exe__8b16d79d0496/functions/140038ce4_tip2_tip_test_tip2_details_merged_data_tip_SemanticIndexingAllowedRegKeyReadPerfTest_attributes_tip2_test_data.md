# tip2::tip_test<tip2::details::merged_data<_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes,tip2::test_data_basic>>::start(void)

- ea: `0x140038ce4`
- end: `0x140038d7f`
- name: `?start@?$tip_test@V?$merged_data@U_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14001d04c`

## callees

- `0x14000cfe8`
- `0x14000eed4`
- `0x140025190`
- `0x140032fa0`
- `0x140038b18`
- `0x140038ce4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140038d26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140038d26`

## pseudocode

```c
__int64 __fastcall tip2::tip_test<tip2::details::merged_data<_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes,tip2::test_data_basic>>::start(
        __int64 *a1,
        __int64 a2)
{
  void *v4; // rcx
  LPVOID v5; // rax
  wil::details::in1diag3 *v6; // rcx
  __int64 v7; // rax
  void *v8; // rcx
  __int64 v10; // [rsp+30h] [rbp+8h] BYREF

  v4 = (void *)*a1;
  if ( v4 && (*((_QWORD *)v4 + 31) || (*((_DWORD *)v4 + 18) & 0x100) != 0) )
  {
    *a1 = 0;
    tip2::details::merged_data<_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes,tip2::test_data_basic>::Release(v4);
  }
  if ( !*a1 )
  {
    v5 = CoTaskMemAlloc(0x158u);
    if ( !v5 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v6);
    v7 = tip2::details::merged_data<_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes,tip2::test_data_basic>::merged_data<_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes,tip2::test_data_basic>(v5);
    v8 = (void *)*a1;
    v10 = 0;
    *a1 = v7;
    if ( v8 )
      tip2::details::merged_data<_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes,tip2::test_data_basic>::Release(v8);
    wil::com_ptr_t<tip2::details::merged_data<_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes,tip2::test_data_basic>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes,tip2::test_data_basic>,wil::err_returncode_policy>(&v10);
  }
  tip2::details::shared_data<0,0,1>::start(*a1 + 8, a2);
  return a2;
}

```

## disassembly

```asm
0x140038ce4  mov     [rsp+arg_8], rbx
0x140038ce9  push    rdi
0x140038cea  sub     rsp, 20h
0x140038cee  mov     rbx, rcx
0x140038cf1  mov     rdi, rdx
0x140038cf4  mov     rcx, [rcx]; pv
0x140038cf7  test    rcx, rcx
0x140038cfa  jz      short loc_140038D1B
0x140038cfc  cmp     qword ptr [rcx+0F8h], 0
0x140038d04  jnz     short loc_140038D0F
0x140038d06  test    dword ptr [rcx+48h], 100h
0x140038d0d  jz      short loc_140038D1B
0x140038d0f  mov     qword ptr [rbx], 0
0x140038d16  call    ?Release@?$merged_data@U_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes,tip2::test_data_basic>::Release(void)
0x140038d1b  cmp     qword ptr [rbx], 0
0x140038d1f  jnz     short loc_140038D62
0x140038d21  mov     ecx, 158h; cb
0x140038d26  call    cs:__imp_CoTaskMemAlloc
0x140038d2c  test    rax, rax
0x140038d2f  jnz     short loc_140038D37
0x140038d31  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140038d37  mov     rcx, rax
0x140038d3a  call    ??0?$merged_data@U_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes,tip2::test_data_basic>::merged_data<_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes,tip2::test_data_basic>(void)
0x140038d3f  mov     rcx, [rbx]; pv
0x140038d42  mov     [rsp+28h+arg_0], 0
0x140038d4b  mov     [rbx], rax
0x140038d4e  test    rcx, rcx
0x140038d51  jz      short loc_140038D58
0x140038d53  call    ?Release@?$merged_data@U_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes,tip2::test_data_basic>::Release(void)
0x140038d58  lea     rcx, [rsp+28h+arg_0]
0x140038d5d  call    ??1?$com_ptr_t@V?$merged_data@U_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes,tip2::test_data_basic>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes,tip2::test_data_basic>,wil::err_returncode_policy>(void)
0x140038d62  mov     rcx, [rbx]
0x140038d65  mov     rdx, rdi
0x140038d68  add     rcx, 8
0x140038d6c  call    ?start@?$shared_data@$0A@$0A@$00@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,1>::start(void)
0x140038d71  mov     rbx, [rsp+28h+arg_8]
0x140038d76  mov     rax, rdi
0x140038d79  add     rsp, 20h
0x140038d7d  pop     rdi
0x140038d7e  retn
```
