# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQIEnableMetricGroupTipTest,_tip_UQIEnableMetricGroupTipTest>,>(void)

- ea: `0x1800e5030`
- end: `0x1800e50e1`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_UQIEnableMetricGroupTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_UQIEnableMetricGroupTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `177`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800e6bb8`

## callees

- `0x18000c258`
- `0x180013064`
- `0x1800e5030`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e5042`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e5042`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQIEnableMetricGroupTipTest,_tip_UQIEnableMetricGroupTipTest>,>(
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
  v5[0] = 58766058;
  v8 = 0;
  v6 = "UQIEnableMetricGroupTipTest";
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
0x1800e5030  mov     [rsp+arg_0], rbx
0x1800e5035  push    rdi
0x1800e5036  sub     rsp, 50h
0x1800e503a  mov     rdi, rcx
0x1800e503d  mov     ecx, 118h; cb
0x1800e5042  call    cs:__imp_CoTaskMemAlloc
0x1800e5048  mov     rbx, rax
0x1800e504b  test    rax, rax
0x1800e504e  jz      loc_1800E50DB
0x1800e5054  xor     edx, edx
0x1800e5056  mov     [rsp+58h+var_38], 380B2EAh
0x1800e505e  lea     rcx, aUqienablemetri; "UQIEnableMetricGroupTipTest"
0x1800e5065  mov     [rsp+58h+var_26], edx
0x1800e5069  mov     [rsp+58h+var_30], rcx
0x1800e506e  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x1800e5075  mov     [rsp+58h+var_22], dx
0x1800e507a  lea     rcx, [rbx+8]
0x1800e507e  mov     [rsp+58h+var_10], rdx
0x1800e5083  lea     r8, [rsp+58h+var_38]
0x1800e5088  xorps   xmm0, xmm0
0x1800e508b  mov     [rbx], rax
0x1800e508e  mov     rdx, rbx
0x1800e5091  mov     [rsp+58h+var_34], 0C100h
0x1800e5099  mov     [rsp+58h+var_28], 1
0x1800e50a0  movdqu  [rsp+58h+var_20], xmm0
0x1800e50a6  call    ??0?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x1800e50ab  lea     rax, ??_7?$merged_data@U_tip_UQIEnableMetricGroupTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_UQIEnableMetricGroupTipTest,_tip_UQIEnableMetricGroupTipTest>::`vftable'
0x1800e50b2  mov     dword ptr [rbx+110h], 1
0x1800e50bc  mov     [rbx], rax
0x1800e50bf  lea     rax, [rbx+10h]
0x1800e50c3  mov     [rbx+108h], rax
0x1800e50ca  mov     rax, rdi
0x1800e50cd  mov     [rdi], rbx
0x1800e50d0  mov     rbx, [rsp+58h+arg_0]
0x1800e50d5  add     rsp, 50h
0x1800e50d9  pop     rdi
0x1800e50da  retn
0x1800e50db  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
