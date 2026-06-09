# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>,>(void)

- ea: `0x180041758`
- end: `0x180041809`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_UQISaveFactsToFactStoreTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_UQISaveFactsToFactStoreTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004c184`

## callees

- `0x18000c258`
- `0x180013064`
- `0x180041758`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004176a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004176a`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>,>(
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
  v5[0] = 60522507;
  v8 = 0;
  v6 = "UQISaveFactsToFactStoreTipTest";
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
0x180041758  mov     [rsp+arg_0], rbx
0x18004175d  push    rdi
0x18004175e  sub     rsp, 50h
0x180041762  mov     rdi, rcx
0x180041765  mov     ecx, 118h; cb
0x18004176a  call    cs:__imp_CoTaskMemAlloc
0x180041770  mov     rbx, rax
0x180041773  test    rax, rax
0x180041776  jz      loc_180041803
0x18004177c  xor     edx, edx
0x18004177e  mov     [rsp+58h+var_38], 39B800Bh
0x180041786  lea     rcx, aUqisavefactsto; "UQISaveFactsToFactStoreTipTest"
0x18004178d  mov     [rsp+58h+var_26], edx
0x180041791  mov     [rsp+58h+var_30], rcx
0x180041796  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x18004179d  mov     [rsp+58h+var_22], dx
0x1800417a2  lea     rcx, [rbx+8]
0x1800417a6  mov     [rsp+58h+var_10], rdx
0x1800417ab  lea     r8, [rsp+58h+var_38]
0x1800417b0  xorps   xmm0, xmm0
0x1800417b3  mov     [rbx], rax
0x1800417b6  mov     rdx, rbx
0x1800417b9  mov     [rsp+58h+var_34], 0C100h
0x1800417c1  mov     [rsp+58h+var_28], 1
0x1800417c8  movdqu  [rsp+58h+var_20], xmm0
0x1800417ce  call    ??0?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x1800417d3  lea     rax, ??_7?$merged_data@U_tip_UQIEnableMetricGroupTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_UQIEnableMetricGroupTipTest,_tip_UQIEnableMetricGroupTipTest>::`vftable'
0x1800417da  mov     dword ptr [rbx+110h], 1
0x1800417e4  mov     [rbx], rax
0x1800417e7  lea     rax, [rbx+10h]
0x1800417eb  mov     [rbx+108h], rax
0x1800417f2  mov     rax, rdi
0x1800417f5  mov     [rdi], rbx
0x1800417f8  mov     rbx, [rsp+58h+arg_0]
0x1800417fd  add     rsp, 50h
0x180041801  pop     rdi
0x180041802  retn
0x180041803  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
