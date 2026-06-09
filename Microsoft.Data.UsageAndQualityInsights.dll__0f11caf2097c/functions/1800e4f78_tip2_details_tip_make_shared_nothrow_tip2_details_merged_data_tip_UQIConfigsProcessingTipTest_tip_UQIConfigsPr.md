# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQIConfigsProcessingTipTest,_tip_UQIConfigsProcessingTipTest>,>(void)

- ea: `0x1800e4f78`
- end: `0x1800e5029`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_UQIConfigsProcessingTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_UQIConfigsProcessingTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `177`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800e75bc`

## callees

- `0x18000c258`
- `0x180013064`
- `0x1800e4f78`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e4f8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e4f8a`

## string_xrefs

- `0x1800e4fa6`: `UQIConfigsProcessingTipTest`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQIConfigsProcessingTipTest,_tip_UQIConfigsProcessingTipTest>,>(
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
  v5[0] = 58666248;
  v8 = 0;
  v6 = "UQIConfigsProcessingTipTest";
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
0x1800e4f78  mov     [rsp+arg_0], rbx
0x1800e4f7d  push    rdi
0x1800e4f7e  sub     rsp, 50h
0x1800e4f82  mov     rdi, rcx
0x1800e4f85  mov     ecx, 118h; cb
0x1800e4f8a  call    cs:__imp_CoTaskMemAlloc
0x1800e4f90  mov     rbx, rax
0x1800e4f93  test    rax, rax
0x1800e4f96  jz      loc_1800E5023
0x1800e4f9c  xor     edx, edx
0x1800e4f9e  mov     [rsp+58h+var_38], 37F2D08h
0x1800e4fa6  lea     rcx, aUqiconfigsproc; "UQIConfigsProcessingTipTest"
0x1800e4fad  mov     [rsp+58h+var_26], edx
0x1800e4fb1  mov     [rsp+58h+var_30], rcx
0x1800e4fb6  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x1800e4fbd  mov     [rsp+58h+var_22], dx
0x1800e4fc2  lea     rcx, [rbx+8]
0x1800e4fc6  mov     [rsp+58h+var_10], rdx
0x1800e4fcb  lea     r8, [rsp+58h+var_38]
0x1800e4fd0  xorps   xmm0, xmm0
0x1800e4fd3  mov     [rbx], rax
0x1800e4fd6  mov     rdx, rbx
0x1800e4fd9  mov     [rsp+58h+var_34], 0C100h
0x1800e4fe1  mov     [rsp+58h+var_28], 1
0x1800e4fe8  movdqu  [rsp+58h+var_20], xmm0
0x1800e4fee  call    ??0?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x1800e4ff3  lea     rax, ??_7?$merged_data@U_tip_UQIEnableMetricGroupTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_UQIEnableMetricGroupTipTest,_tip_UQIEnableMetricGroupTipTest>::`vftable'
0x1800e4ffa  mov     dword ptr [rbx+110h], 1
0x1800e5004  mov     [rbx], rax
0x1800e5007  lea     rax, [rbx+10h]
0x1800e500b  mov     [rbx+108h], rax
0x1800e5012  mov     rax, rdi
0x1800e5015  mov     [rdi], rbx
0x1800e5018  mov     rbx, [rsp+58h+arg_0]
0x1800e501d  add     rsp, 50h
0x1800e5021  pop     rdi
0x1800e5022  retn
0x1800e5023  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
