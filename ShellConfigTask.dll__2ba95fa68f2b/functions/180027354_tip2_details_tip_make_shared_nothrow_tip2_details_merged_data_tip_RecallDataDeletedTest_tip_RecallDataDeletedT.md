# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>,>(void)

- ea: `0x180027354`
- end: `0x180027410`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002e79c`

## callees

- `0x18000c5c4`
- `0x180012f30`
- `0x180027354`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027366`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027366`

## string_xrefs

- `0x180027395`: `RecallDataDeletedTest`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>,>(
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

  v2 = CoTaskMemAlloc(0x128u);
  v4 = v2;
  if ( !v2 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
  v6[0] = 55802458;
  v9 = 0;
  *v2 = &tip2::details::test_data_interface::`vftable';
  v10 = 0;
  v12 = 0;
  v7 = "RecallDataDeletedTest";
  v6[1] = 49408;
  v8 = 513;
  v11 = 0;
  tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(v2 + 1, v2, v6);
  v4[34] = 0;
  *v4 = &tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>::`vftable';
  v4[33] = v4 + 2;
  result = a1;
  *((_DWORD *)v4 + 72) = 1;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x180027354  mov     [rsp+arg_0], rbx
0x180027359  push    rdi
0x18002735a  sub     rsp, 50h
0x18002735e  mov     rdi, rcx
0x180027361  mov     ecx, 128h; cb
0x180027366  call    cs:__imp_CoTaskMemAlloc
0x18002736c  mov     rbx, rax
0x18002736f  test    rax, rax
0x180027372  jz      loc_18002740A
0x180027378  xor     ecx, ecx
0x18002737a  mov     [rsp+58h+var_38], 3537A5Ah
0x180027382  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x180027389  mov     [rsp+58h+var_26], ecx
0x18002738d  mov     [rbx], rax
0x180027390  lea     r8, [rsp+58h+var_38]
0x180027395  lea     rax, aRecalldatadele; "RecallDataDeletedTest"
0x18002739c  mov     [rsp+58h+var_22], cx
0x1800273a1  xorps   xmm0, xmm0
0x1800273a4  mov     [rsp+58h+var_10], rcx
0x1800273a9  lea     rcx, [rbx+8]
0x1800273ad  mov     [rsp+58h+var_30], rax
0x1800273b2  mov     rdx, rbx
0x1800273b5  mov     [rsp+58h+var_34], 0C100h
0x1800273bd  mov     [rsp+58h+var_28], 201h
0x1800273c4  movdqu  [rsp+58h+var_20], xmm0
0x1800273ca  call    ??0?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x1800273cf  lea     rax, ??_7?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>::`vftable'
0x1800273d6  mov     qword ptr [rbx+110h], 0
0x1800273e1  mov     [rbx], rax
0x1800273e4  lea     rax, [rbx+10h]
0x1800273e8  mov     [rbx+108h], rax
0x1800273ef  mov     rax, rdi
0x1800273f2  mov     dword ptr [rbx+120h], 1
0x1800273fc  mov     [rdi], rbx
0x1800273ff  mov     rbx, [rsp+58h+arg_0]
0x180027404  add     rsp, 50h
0x180027408  pop     rdi
0x180027409  retn
0x18002740a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
