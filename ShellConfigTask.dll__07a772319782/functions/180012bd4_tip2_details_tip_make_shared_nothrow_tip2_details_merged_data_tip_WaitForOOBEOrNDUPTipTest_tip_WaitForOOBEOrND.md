# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>,>(void)

- ea: `0x180012bd4`
- end: `0x180012c8f`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `187`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800222c0`

## callees

- `0x18000c5c4`
- `0x180012bd4`
- `0x180012f30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012be6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012be6`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>,>(
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
  v6[0] = 54221479;
  v9 = 0;
  *v2 = &tip2::details::test_data_interface::`vftable';
  v10 = 0;
  v12 = 0;
  v7 = "WaitForOOBEOrNDUPTipTest";
  v6[1] = 49408;
  v8 = 257;
  v11 = 0;
  tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(v2 + 1, v2, v6);
  *((_DWORD *)v4 + 68) = 1;
  *v4 = &tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>::`vftable';
  v4[33] = v4 + 2;
  result = a1;
  *((_DWORD *)v4 + 70) = 1;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x180012bd4  mov     [rsp+arg_0], rbx
0x180012bd9  push    rdi
0x180012bda  sub     rsp, 50h
0x180012bde  mov     rdi, rcx
0x180012be1  mov     ecx, 120h; cb
0x180012be6  call    cs:__imp_CoTaskMemAlloc
0x180012bec  mov     rbx, rax
0x180012bef  test    rax, rax
0x180012bf2  jz      loc_180012C89
0x180012bf8  xor     ecx, ecx
0x180012bfa  mov     [rsp+58h+var_38], 33B5AA7h
0x180012c02  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x180012c09  mov     [rsp+58h+var_26], ecx
0x180012c0d  mov     [rbx], rax
0x180012c10  lea     r8, [rsp+58h+var_38]
0x180012c15  lea     rax, aWaitforoobeorn; "WaitForOOBEOrNDUPTipTest"
0x180012c1c  mov     [rsp+58h+var_22], cx
0x180012c21  xorps   xmm0, xmm0
0x180012c24  mov     [rsp+58h+var_10], rcx
0x180012c29  lea     rcx, [rbx+8]
0x180012c2d  mov     [rsp+58h+var_30], rax
0x180012c32  mov     rdx, rbx
0x180012c35  mov     [rsp+58h+var_34], 0C100h
0x180012c3d  mov     [rsp+58h+var_28], 101h
0x180012c44  movdqu  [rsp+58h+var_20], xmm0
0x180012c4a  call    ??0?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x180012c4f  lea     rax, ??_7?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>::`vftable'
0x180012c56  mov     dword ptr [rbx+110h], 1
0x180012c60  mov     [rbx], rax
0x180012c63  lea     rax, [rbx+10h]
0x180012c67  mov     [rbx+108h], rax
0x180012c6e  mov     rax, rdi
0x180012c71  mov     dword ptr [rbx+118h], 1
0x180012c7b  mov     [rdi], rbx
0x180012c7e  mov     rbx, [rsp+58h+arg_0]
0x180012c83  add     rsp, 50h
0x180012c87  pop     rdi
0x180012c88  retn
0x180012c89  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
