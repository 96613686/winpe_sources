# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>,>(void)

- ea: `0x1800128c4`
- end: `0x18001297f`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_A9InitialConfigurationTaskTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_A9InitialConfigurationTaskTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180022070`

## callees

- `0x18000c5c4`
- `0x1800128c4`
- `0x180012f30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800128d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800128d6`

## string_xrefs

- `0x180012905`: `A9InitialConfigurationTaskTipTest`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>,>(
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
  v6[0] = 54115220;
  v9 = 0;
  *v2 = &tip2::details::test_data_interface::`vftable';
  v10 = 0;
  v12 = 0;
  v7 = "A9InitialConfigurationTaskTipTest";
  v6[1] = 49408;
  v8 = 257;
  v11 = 0;
  tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(v2 + 1, v2, v6);
  *((_DWORD *)v4 + 68) = 1;
  *v4 = &tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>::`vftable';
  v4[33] = v4 + 2;
  result = a1;
  *((_DWORD *)v4 + 70) = 1;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x1800128c4  mov     [rsp+arg_0], rbx
0x1800128c9  push    rdi
0x1800128ca  sub     rsp, 50h
0x1800128ce  mov     rdi, rcx
0x1800128d1  mov     ecx, 120h; cb
0x1800128d6  call    cs:__imp_CoTaskMemAlloc
0x1800128dc  mov     rbx, rax
0x1800128df  test    rax, rax
0x1800128e2  jz      loc_180012979
0x1800128e8  xor     ecx, ecx
0x1800128ea  mov     [rsp+58h+var_38], 339BB94h
0x1800128f2  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x1800128f9  mov     [rsp+58h+var_26], ecx
0x1800128fd  mov     [rbx], rax
0x180012900  lea     r8, [rsp+58h+var_38]
0x180012905  lea     rax, aA9initialconfi; "A9InitialConfigurationTaskTipTest"
0x18001290c  mov     [rsp+58h+var_22], cx
0x180012911  xorps   xmm0, xmm0
0x180012914  mov     [rsp+58h+var_10], rcx
0x180012919  lea     rcx, [rbx+8]
0x18001291d  mov     [rsp+58h+var_30], rax
0x180012922  mov     rdx, rbx
0x180012925  mov     [rsp+58h+var_34], 0C100h
0x18001292d  mov     [rsp+58h+var_28], 101h
0x180012934  movdqu  [rsp+58h+var_20], xmm0
0x18001293a  call    ??0?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x18001293f  lea     rax, ??_7?$merged_data@U_tip_A9InitialConfigurationTaskTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>::`vftable'
0x180012946  mov     dword ptr [rbx+110h], 1
0x180012950  mov     [rbx], rax
0x180012953  lea     rax, [rbx+10h]
0x180012957  mov     [rbx+108h], rax
0x18001295e  mov     rax, rdi
0x180012961  mov     dword ptr [rbx+118h], 1
0x18001296b  mov     [rdi], rbx
0x18001296e  mov     rbx, [rsp+58h+arg_0]
0x180012973  add     rsp, 50h
0x180012977  pop     rdi
0x180012978  retn
0x180012979  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
