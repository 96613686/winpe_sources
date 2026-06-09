# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>,>(void)

- ea: `0x180012b10`
- end: `0x180012bcb`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002222c`

## callees

- `0x18000c5c4`
- `0x180012b10`
- `0x180012f30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012b22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012b22`

## string_xrefs

- `0x180012b51`: `WaitForEnduserSessionOOBEOrOOBECompleteTipTest`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>,>(
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
  v6[0] = 55948556;
  v9 = 0;
  *v2 = &tip2::details::test_data_interface::`vftable';
  v10 = 0;
  v12 = 0;
  v7 = "WaitForEnduserSessionOOBEOrOOBECompleteTipTest";
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
0x180012b10  mov     [rsp+arg_0], rbx
0x180012b15  push    rdi
0x180012b16  sub     rsp, 50h
0x180012b1a  mov     rdi, rcx
0x180012b1d  mov     ecx, 120h; cb
0x180012b22  call    cs:__imp_CoTaskMemAlloc
0x180012b28  mov     rbx, rax
0x180012b2b  test    rax, rax
0x180012b2e  jz      loc_180012BC5
0x180012b34  xor     ecx, ecx
0x180012b36  mov     [rsp+58h+var_38], 355B50Ch
0x180012b3e  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x180012b45  mov     [rsp+58h+var_26], ecx
0x180012b49  mov     [rbx], rax
0x180012b4c  lea     r8, [rsp+58h+var_38]
0x180012b51  lea     rax, aWaitforenduser; "WaitForEnduserSessionOOBEOrOOBEComplete"...
0x180012b58  mov     [rsp+58h+var_22], cx
0x180012b5d  xorps   xmm0, xmm0
0x180012b60  mov     [rsp+58h+var_10], rcx
0x180012b65  lea     rcx, [rbx+8]
0x180012b69  mov     [rsp+58h+var_30], rax
0x180012b6e  mov     rdx, rbx
0x180012b71  mov     [rsp+58h+var_34], 0C100h
0x180012b79  mov     [rsp+58h+var_28], 101h
0x180012b80  movdqu  [rsp+58h+var_20], xmm0
0x180012b86  call    ??0?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x180012b8b  lea     rax, ??_7?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>::`vftable'
0x180012b92  mov     dword ptr [rbx+110h], 1
0x180012b9c  mov     [rbx], rax
0x180012b9f  lea     rax, [rbx+10h]
0x180012ba3  mov     [rbx+108h], rax
0x180012baa  mov     rax, rdi
0x180012bad  mov     dword ptr [rbx+118h], 1
0x180012bb7  mov     [rdi], rbx
0x180012bba  mov     rbx, [rsp+58h+arg_0]
0x180012bbf  add     rsp, 50h
0x180012bc3  pop     rdi
0x180012bc4  retn
0x180012bc5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
