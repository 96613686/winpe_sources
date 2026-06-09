# tip2::tip_test<tip2::details::merged_data<_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes,tip2::test_data_basic>>::start(void)

- ea: `0x14002fd70`
- end: `0x14002fe0b`
- name: `?start@?$tip_test@V?$merged_data@U_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14002dbb4`

## callees

- `0x14000b524`
- `0x14002d10c`
- `0x14002d5b0`
- `0x14002e680`
- `0x14002fc40`
- `0x14002fd70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002fdb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002fdb2`

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
  void *v10; // [rsp+30h] [rbp+8h] BYREF

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
    v7 = tip2::details::merged_data<_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes,tip2::test_data_basic>::merged_data<_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes,tip2::test_data_basic>((__int64)v5);
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
0x14002fd70  mov     [rsp+arg_8], rbx
0x14002fd75  push    rdi
0x14002fd76  sub     rsp, 20h
0x14002fd7a  mov     rbx, rcx
0x14002fd7d  mov     rdi, rdx
0x14002fd80  mov     rcx, [rcx]; pv
0x14002fd83  test    rcx, rcx
0x14002fd86  jz      short loc_14002FDA7
0x14002fd88  cmp     qword ptr [rcx+0F8h], 0
0x14002fd90  jnz     short loc_14002FD9B
0x14002fd92  test    dword ptr [rcx+48h], 100h
0x14002fd99  jz      short loc_14002FDA7
0x14002fd9b  mov     qword ptr [rbx], 0
0x14002fda2  call    ?Release@?$merged_data@U_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes,tip2::test_data_basic>::Release(void)
0x14002fda7  cmp     qword ptr [rbx], 0
0x14002fdab  jnz     short loc_14002FDEE
0x14002fdad  mov     ecx, 158h; cb
0x14002fdb2  call    cs:__imp_CoTaskMemAlloc
0x14002fdb8  test    rax, rax
0x14002fdbb  jnz     short loc_14002FDC3
0x14002fdbd  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14002fdc3  mov     rcx, rax
0x14002fdc6  call    ??0?$merged_data@U_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes,tip2::test_data_basic>::merged_data<_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes,tip2::test_data_basic>(void)
0x14002fdcb  mov     rcx, [rbx]; pv
0x14002fdce  mov     [rsp+28h+arg_0], 0
0x14002fdd7  mov     [rbx], rax
0x14002fdda  test    rcx, rcx
0x14002fddd  jz      short loc_14002FDE4
0x14002fddf  call    ?Release@?$merged_data@U_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes,tip2::test_data_basic>::Release(void)
0x14002fde4  lea     rcx, [rsp+28h+arg_0]
0x14002fde9  call    ??1?$com_ptr_t@V?$merged_data@U_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes,tip2::test_data_basic>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SemanticIndexingAllowedRegKeyReadPerfTest_attributes,tip2::test_data_basic>,wil::err_returncode_policy>(void)
0x14002fdee  mov     rcx, [rbx]
0x14002fdf1  mov     rdx, rdi
0x14002fdf4  add     rcx, 8
0x14002fdf8  call    ?start@?$shared_data@$0A@$0A@$00@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,1>::start(void)
0x14002fdfd  mov     rbx, [rsp+28h+arg_8]
0x14002fe02  mov     rax, rdi
0x14002fe05  add     rsp, 20h
0x14002fe09  pop     rdi
0x14002fe0a  retn
```
