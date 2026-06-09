# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>,>(void)

- ea: `0x18002710c`
- end: `0x1800271c7`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_A9PolicyTaskTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_A9PolicyTaskTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `187`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002e5e0`

## callees

- `0x18000c5c4`
- `0x180012f30`
- `0x18002710c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002711e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002711e`

## string_xrefs

- `0x18002714d`: `A9PolicyTaskTipTest`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>,>(
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
  v6[0] = 54115206;
  v9 = 0;
  *v2 = &tip2::details::test_data_interface::`vftable';
  v10 = 0;
  v12 = 0;
  v7 = "A9PolicyTaskTipTest";
  v6[1] = 49408;
  v8 = 257;
  v11 = 0;
  tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(v2 + 1, v2, v6);
  *((_DWORD *)v4 + 68) = 1;
  *v4 = &tip2::details::merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>::`vftable';
  v4[33] = v4 + 2;
  result = a1;
  *((_DWORD *)v4 + 70) = 1;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x18002710c  mov     [rsp+arg_0], rbx
0x180027111  push    rdi
0x180027112  sub     rsp, 50h
0x180027116  mov     rdi, rcx
0x180027119  mov     ecx, 120h; cb
0x18002711e  call    cs:__imp_CoTaskMemAlloc
0x180027124  mov     rbx, rax
0x180027127  test    rax, rax
0x18002712a  jz      loc_1800271C1
0x180027130  xor     ecx, ecx
0x180027132  mov     [rsp+58h+var_38], 339BB86h
0x18002713a  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x180027141  mov     [rsp+58h+var_26], ecx
0x180027145  mov     [rbx], rax
0x180027148  lea     r8, [rsp+58h+var_38]
0x18002714d  lea     rax, aA9policytaskti; "A9PolicyTaskTipTest"
0x180027154  mov     [rsp+58h+var_22], cx
0x180027159  xorps   xmm0, xmm0
0x18002715c  mov     [rsp+58h+var_10], rcx
0x180027161  lea     rcx, [rbx+8]
0x180027165  mov     [rsp+58h+var_30], rax
0x18002716a  mov     rdx, rbx
0x18002716d  mov     [rsp+58h+var_34], 0C100h
0x180027175  mov     [rsp+58h+var_28], 101h
0x18002717c  movdqu  [rsp+58h+var_20], xmm0
0x180027182  call    ??0?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x180027187  lea     rax, ??_7?$merged_data@U_tip_A9PolicyTaskTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_A9PolicyTaskTipTest,_tip_A9PolicyTaskTipTest>::`vftable'
0x18002718e  mov     dword ptr [rbx+110h], 1
0x180027198  mov     [rbx], rax
0x18002719b  lea     rax, [rbx+10h]
0x18002719f  mov     [rbx+108h], rax
0x1800271a6  mov     rax, rdi
0x1800271a9  mov     dword ptr [rbx+118h], 1
0x1800271b3  mov     [rdi], rbx
0x1800271b6  mov     rbx, [rsp+58h+arg_0]
0x1800271bb  add     rsp, 50h
0x1800271bf  pop     rdi
0x1800271c0  retn
0x1800271c1  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
