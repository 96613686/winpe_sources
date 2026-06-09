# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>,>(void)

- ea: `0x180012bb0`
- end: `0x180012c68`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_UQIWnfCallbackExecutionTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_UQIWnfCallbackExecutionTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012998`

## callees

- `0x18000c258`
- `0x180012bb0`
- `0x180013064`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012bc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012bc2`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>,>(
        _QWORD *a1)
{
  wil::details::in1diag3 *v2; // rcx
  char *v3; // rbx
  _QWORD *result; // rax
  _DWORD v5[2]; // [rsp+20h] [rbp-38h] BYREF
  const char *v6; // [rsp+28h] [rbp-30h]
  __int16 v7; // [rsp+30h] [rbp-28h]
  int v8; // [rsp+32h] [rbp-26h]
  __int16 v9; // [rsp+36h] [rbp-22h]
  __int128 v10; // [rsp+38h] [rbp-20h]
  __int64 v11; // [rsp+48h] [rbp-10h]

  v3 = (char *)CoTaskMemAlloc(0x120u);
  if ( !v3 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v2);
  v5[0] = 58790159;
  v8 = 0;
  v6 = "UQIWnfCallbackExecutionTipTest";
  v9 = 0;
  v11 = 0;
  *(_QWORD *)v3 = &tip2::details::test_data_interface::`vftable';
  v5[1] = 49408;
  v7 = 1;
  v10 = 0;
  tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(v3 + 8, v3, v5);
  v3[272] = 1;
  *(_QWORD *)v3 = &tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>::`vftable';
  *((_QWORD *)v3 + 33) = v3 + 16;
  result = a1;
  *((_DWORD *)v3 + 70) = 1;
  *a1 = v3;
  return result;
}

```

## disassembly

```asm
0x180012bb0  mov     [rsp+arg_0], rbx
0x180012bb5  push    rdi
0x180012bb6  sub     rsp, 50h
0x180012bba  mov     rdi, rcx
0x180012bbd  mov     ecx, 120h; cb
0x180012bc2  call    cs:__imp_CoTaskMemAlloc
0x180012bc8  mov     rbx, rax
0x180012bcb  test    rax, rax
0x180012bce  jz      loc_180012C62
0x180012bd4  xor     edx, edx
0x180012bd6  mov     [rsp+58h+var_38], 381110Fh
0x180012bde  lea     rcx, aUqiwnfcallback; "UQIWnfCallbackExecutionTipTest"
0x180012be5  mov     [rsp+58h+var_26], edx
0x180012be9  mov     [rsp+58h+var_30], rcx
0x180012bee  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x180012bf5  mov     [rsp+58h+var_22], dx
0x180012bfa  lea     rcx, [rbx+8]
0x180012bfe  mov     [rsp+58h+var_10], rdx
0x180012c03  lea     r8, [rsp+58h+var_38]
0x180012c08  xorps   xmm0, xmm0
0x180012c0b  mov     [rbx], rax
0x180012c0e  mov     rdx, rbx
0x180012c11  mov     [rsp+58h+var_34], 0C100h
0x180012c19  mov     [rsp+58h+var_28], 1
0x180012c20  movdqu  [rsp+58h+var_20], xmm0
0x180012c26  call    ??0?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x180012c2b  lea     rax, ??_7?$merged_data@U_tip_UQIWnfCallbackExecutionTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>::`vftable'
0x180012c32  mov     byte ptr [rbx+110h], 1
0x180012c39  mov     [rbx], rax
0x180012c3c  lea     rax, [rbx+10h]
0x180012c40  mov     [rbx+108h], rax
0x180012c47  mov     rax, rdi
0x180012c4a  mov     dword ptr [rbx+118h], 1
0x180012c54  mov     [rdi], rbx
0x180012c57  mov     rbx, [rsp+58h+arg_0]
0x180012c5c  add     rsp, 50h
0x180012c60  pop     rdi
0x180012c61  retn
0x180012c62  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
