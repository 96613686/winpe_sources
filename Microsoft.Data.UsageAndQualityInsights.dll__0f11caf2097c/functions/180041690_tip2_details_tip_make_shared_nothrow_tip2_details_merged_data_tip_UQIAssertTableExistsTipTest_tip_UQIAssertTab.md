# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>,>(void)

- ea: `0x180041690`
- end: `0x180041752`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_UQIAssertTableExistsTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_UQIAssertTableExistsTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180046cf0`

## callees

- `0x18000c258`
- `0x180013064`
- `0x180041690`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800416a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800416a2`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>,>(
        _QWORD *a1)
{
  _QWORD *v2; // rax
  wil::details::in1diag3 *v3; // rcx
  _QWORD *v4; // rbx
  _QWORD *result; // rax
  _DWORD v6[2]; // [rsp+20h] [rbp-38h] BYREF
  const char *v7; // [rsp+28h] [rbp-30h]
  __int16 v8; // [rsp+30h] [rbp-28h]
  int v9; // [rsp+32h] [rbp-26h]
  __int16 v10; // [rsp+36h] [rbp-22h]
  __int128 v11; // [rsp+38h] [rbp-20h]
  __int64 v12; // [rsp+48h] [rbp-10h]

  v2 = CoTaskMemAlloc(0x120u);
  v4 = v2;
  if ( !v2 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
  v6[0] = 59771571;
  v9 = 0;
  *v2 = &tip2::details::test_data_interface::`vftable';
  v10 = 0;
  v12 = 0;
  v7 = "UQIAssertTableExistsTipTest";
  v6[1] = 49408;
  v8 = 257;
  v11 = 0;
  tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(v2 + 1, v2, v6);
  *((_BYTE *)v4 + 272) = 0;
  *v4 = &tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>::`vftable';
  v4[33] = v4 + 2;
  result = a1;
  *((_DWORD *)v4 + 69) = 0;
  *((_DWORD *)v4 + 70) = 1;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x180041690  mov     [rsp+arg_0], rbx
0x180041695  push    rdi
0x180041696  sub     rsp, 50h
0x18004169a  mov     rdi, rcx
0x18004169d  mov     ecx, 120h; cb
0x1800416a2  call    cs:__imp_CoTaskMemAlloc
0x1800416a8  mov     rbx, rax
0x1800416ab  test    rax, rax
0x1800416ae  jz      loc_18004174C
0x1800416b4  xor     ecx, ecx
0x1800416b6  mov     [rsp+58h+var_38], 3900AB3h
0x1800416be  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x1800416c5  mov     [rsp+58h+var_26], ecx
0x1800416c9  mov     [rbx], rax
0x1800416cc  lea     r8, [rsp+58h+var_38]
0x1800416d1  lea     rax, aUqiasserttable; "UQIAssertTableExistsTipTest"
0x1800416d8  mov     [rsp+58h+var_22], cx
0x1800416dd  xorps   xmm0, xmm0
0x1800416e0  mov     [rsp+58h+var_10], rcx
0x1800416e5  lea     rcx, [rbx+8]
0x1800416e9  mov     [rsp+58h+var_30], rax
0x1800416ee  mov     rdx, rbx
0x1800416f1  mov     [rsp+58h+var_34], 0C100h
0x1800416f9  mov     [rsp+58h+var_28], 101h
0x180041700  movdqu  [rsp+58h+var_20], xmm0
0x180041706  call    ??0?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x18004170b  lea     rax, ??_7?$merged_data@U_tip_UQIAssertTableExistsTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>::`vftable'
0x180041712  mov     byte ptr [rbx+110h], 0
0x180041719  mov     [rbx], rax
0x18004171c  lea     rax, [rbx+10h]
0x180041720  mov     [rbx+108h], rax
0x180041727  mov     rax, rdi
0x18004172a  mov     dword ptr [rbx+114h], 0
0x180041734  mov     dword ptr [rbx+118h], 1
0x18004173e  mov     [rdi], rbx
0x180041741  mov     rbx, [rsp+58h+arg_0]
0x180041746  add     rsp, 50h
0x18004174a  pop     rdi
0x18004174b  retn
0x18004174c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
