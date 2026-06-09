# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQIWnfSubscriptionCreationTipTest,_tip_UQIWnfSubscriptionCreationTipTest>,>(void)

- ea: `0x180012c70`
- end: `0x180012d21`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_UQIWnfSubscriptionCreationTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_UQIWnfSubscriptionCreationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `177`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012aa4`

## callees

- `0x18000c258`
- `0x180012c70`
- `0x180013064`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012c82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012c82`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQIWnfSubscriptionCreationTipTest,_tip_UQIWnfSubscriptionCreationTipTest>,>(
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
  v5[0] = 58790150;
  v8 = 0;
  v6 = "UQIWnfSubscriptionCreationTipTest";
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
0x180012c70  mov     [rsp+arg_0], rbx
0x180012c75  push    rdi
0x180012c76  sub     rsp, 50h
0x180012c7a  mov     rdi, rcx
0x180012c7d  mov     ecx, 118h; cb
0x180012c82  call    cs:__imp_CoTaskMemAlloc
0x180012c88  mov     rbx, rax
0x180012c8b  test    rax, rax
0x180012c8e  jz      loc_180012D1B
0x180012c94  xor     edx, edx
0x180012c96  mov     [rsp+58h+var_38], 3811106h
0x180012c9e  lea     rcx, aUqiwnfsubscrip; "UQIWnfSubscriptionCreationTipTest"
0x180012ca5  mov     [rsp+58h+var_26], edx
0x180012ca9  mov     [rsp+58h+var_30], rcx
0x180012cae  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x180012cb5  mov     [rsp+58h+var_22], dx
0x180012cba  lea     rcx, [rbx+8]
0x180012cbe  mov     [rsp+58h+var_10], rdx
0x180012cc3  lea     r8, [rsp+58h+var_38]
0x180012cc8  xorps   xmm0, xmm0
0x180012ccb  mov     [rbx], rax
0x180012cce  mov     rdx, rbx
0x180012cd1  mov     [rsp+58h+var_34], 0C100h
0x180012cd9  mov     [rsp+58h+var_28], 1
0x180012ce0  movdqu  [rsp+58h+var_20], xmm0
0x180012ce6  call    ??0?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x180012ceb  lea     rax, ??_7?$merged_data@U_tip_UQIEnableMetricGroupTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_UQIEnableMetricGroupTipTest,_tip_UQIEnableMetricGroupTipTest>::`vftable'
0x180012cf2  mov     dword ptr [rbx+110h], 1
0x180012cfc  mov     [rbx], rax
0x180012cff  lea     rax, [rbx+10h]
0x180012d03  mov     [rbx+108h], rax
0x180012d0a  mov     rax, rdi
0x180012d0d  mov     [rdi], rbx
0x180012d10  mov     rbx, [rsp+58h+arg_0]
0x180012d15  add     rsp, 50h
0x180012d19  pop     rdi
0x180012d1a  retn
0x180012d1b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
