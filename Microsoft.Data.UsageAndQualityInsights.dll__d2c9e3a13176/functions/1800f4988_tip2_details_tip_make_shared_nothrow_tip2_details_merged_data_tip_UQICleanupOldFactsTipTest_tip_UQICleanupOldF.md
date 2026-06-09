# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQICleanupOldFactsTipTest,_tip_UQICleanupOldFactsTipTest>,>(void)

- ea: `0x1800f4988`
- end: `0x1800f4a39`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_UQICleanupOldFactsTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_UQICleanupOldFactsTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `177`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800f4eb4`

## callees

- `0x18000c258`
- `0x180013064`
- `0x1800f4988`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f499a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f499a`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQICleanupOldFactsTipTest,_tip_UQICleanupOldFactsTipTest>,>(
        _QWORD *a1)
{
  wil::details::in1diag3 *v2; // rcx
  _DWORD *v3; // rbx
  _QWORD *result; // rax
  _DWORD v5[2]; // [rsp+20h] [rbp-38h] BYREF
  const char *v6; // [rsp+28h] [rbp-30h]
  __int16 v7; // [rsp+30h] [rbp-28h]
  int v8; // [rsp+32h] [rbp-26h]
  __int16 v9; // [rsp+36h] [rbp-22h]
  __int128 v10; // [rsp+38h] [rbp-20h]
  __int64 v11; // [rsp+48h] [rbp-10h]

  v3 = CoTaskMemAlloc(0x118u);
  if ( !v3 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v2);
  v5[0] = 60191337;
  v8 = 0;
  v6 = "UQICleanupOldFactsTipTest";
  v9 = 0;
  v11 = 0;
  *(_QWORD *)v3 = &tip2::details::test_data_interface::`vftable';
  v5[1] = 49408;
  v7 = 1;
  v10 = 0;
  tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(v3 + 2, v3, v5);
  v3[68] = 1;
  *(_QWORD *)v3 = &tip2::details::merged_data<_tip_UQIEnableMetricGroupTipTest,_tip_UQIEnableMetricGroupTipTest>::`vftable';
  *((_QWORD *)v3 + 33) = v3 + 4;
  result = a1;
  *a1 = v3;
  return result;
}

```

## disassembly

```asm
0x1800f4988  mov     [rsp+arg_0], rbx
0x1800f498d  push    rdi
0x1800f498e  sub     rsp, 50h
0x1800f4992  mov     rdi, rcx
0x1800f4995  mov     ecx, 118h; cb
0x1800f499a  call    cs:__imp_CoTaskMemAlloc
0x1800f49a0  mov     rbx, rax
0x1800f49a3  test    rax, rax
0x1800f49a6  jz      loc_1800F4A33
0x1800f49ac  xor     edx, edx
0x1800f49ae  mov     [rsp+58h+var_38], 3967269h
0x1800f49b6  lea     rcx, aUqicleanupoldf; "UQICleanupOldFactsTipTest"
0x1800f49bd  mov     [rsp+58h+var_26], edx
0x1800f49c1  mov     [rsp+58h+var_30], rcx
0x1800f49c6  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x1800f49cd  mov     [rsp+58h+var_22], dx
0x1800f49d2  lea     rcx, [rbx+8]
0x1800f49d6  mov     [rsp+58h+var_10], rdx
0x1800f49db  lea     r8, [rsp+58h+var_38]
0x1800f49e0  xorps   xmm0, xmm0
0x1800f49e3  mov     [rbx], rax
0x1800f49e6  mov     rdx, rbx
0x1800f49e9  mov     [rsp+58h+var_34], 0C100h
0x1800f49f1  mov     [rsp+58h+var_28], 1
0x1800f49f8  movdqu  [rsp+58h+var_20], xmm0
0x1800f49fe  call    ??0?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x1800f4a03  lea     rax, ??_7?$merged_data@U_tip_UQIEnableMetricGroupTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_UQIEnableMetricGroupTipTest,_tip_UQIEnableMetricGroupTipTest>::`vftable'
0x1800f4a0a  mov     dword ptr [rbx+110h], 1
0x1800f4a14  mov     [rbx], rax
0x1800f4a17  lea     rax, [rbx+10h]
0x1800f4a1b  mov     [rbx+108h], rax
0x1800f4a22  mov     rax, rdi
0x1800f4a25  mov     [rdi], rbx
0x1800f4a28  mov     rbx, [rsp+58h+arg_0]
0x1800f4a2d  add     rsp, 50h
0x1800f4a31  pop     rdi
0x1800f4a32  retn
0x1800f4a33  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
