# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQIIncrementServiceUsageTest,_tip_UQIIncrementServiceUsageTest>,>(void)

- ea: `0x18002b054`
- end: `0x18002b105`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_UQIIncrementServiceUsageTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_UQIIncrementServiceUsageTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `177`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002b6a8`

## callees

- `0x18000c258`
- `0x180013064`
- `0x18002b054`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b066`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b066`

## string_xrefs

- `0x18002b082`: `UQIIncrementServiceUsageTest`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQIIncrementServiceUsageTest,_tip_UQIIncrementServiceUsageTest>,>(
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
  v5[0] = 59675292;
  v8 = 0;
  v6 = "UQIIncrementServiceUsageTest";
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
0x18002b054  mov     [rsp+arg_0], rbx
0x18002b059  push    rdi
0x18002b05a  sub     rsp, 50h
0x18002b05e  mov     rdi, rcx
0x18002b061  mov     ecx, 118h; cb
0x18002b066  call    cs:__imp_CoTaskMemAlloc
0x18002b06c  mov     rbx, rax
0x18002b06f  test    rax, rax
0x18002b072  jz      loc_18002B0FF
0x18002b078  xor     edx, edx
0x18002b07a  mov     [rsp+58h+var_38], 38E929Ch
0x18002b082  lea     rcx, aUqiincrementse; "UQIIncrementServiceUsageTest"
0x18002b089  mov     [rsp+58h+var_26], edx
0x18002b08d  mov     [rsp+58h+var_30], rcx
0x18002b092  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x18002b099  mov     [rsp+58h+var_22], dx
0x18002b09e  lea     rcx, [rbx+8]
0x18002b0a2  mov     [rsp+58h+var_10], rdx
0x18002b0a7  lea     r8, [rsp+58h+var_38]
0x18002b0ac  xorps   xmm0, xmm0
0x18002b0af  mov     [rbx], rax
0x18002b0b2  mov     rdx, rbx
0x18002b0b5  mov     [rsp+58h+var_34], 0C100h
0x18002b0bd  mov     [rsp+58h+var_28], 1
0x18002b0c4  movdqu  [rsp+58h+var_20], xmm0
0x18002b0ca  call    ??0?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x18002b0cf  lea     rax, ??_7?$merged_data@U_tip_UQIEnableMetricGroupTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_UQIEnableMetricGroupTipTest,_tip_UQIEnableMetricGroupTipTest>::`vftable'
0x18002b0d6  mov     dword ptr [rbx+110h], 1
0x18002b0e0  mov     [rbx], rax
0x18002b0e3  lea     rax, [rbx+10h]
0x18002b0e7  mov     [rbx+108h], rax
0x18002b0ee  mov     rax, rdi
0x18002b0f1  mov     [rdi], rbx
0x18002b0f4  mov     rbx, [rsp+58h+arg_0]
0x18002b0f9  add     rsp, 50h
0x18002b0fd  pop     rdi
0x18002b0fe  retn
0x18002b0ff  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
