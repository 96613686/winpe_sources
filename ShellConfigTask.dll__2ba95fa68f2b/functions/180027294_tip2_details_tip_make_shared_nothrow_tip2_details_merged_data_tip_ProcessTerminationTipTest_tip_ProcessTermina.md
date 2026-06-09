# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>,>(void)

- ea: `0x180027294`
- end: `0x18002734e`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_ProcessTerminationTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_ProcessTerminationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002e708`

## callees

- `0x18000c5c4`
- `0x180012f30`
- `0x180027294`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800272a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800272a6`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>,>(
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
  v6[0] = 54221458;
  v9 = 0;
  *v2 = &tip2::details::test_data_interface::`vftable';
  v10 = 0;
  v12 = 0;
  v7 = "ProcessTerminationTipTest";
  v6[1] = 49408;
  v8 = 257;
  v11 = 0;
  tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(v2 + 1, v2, v6);
  *((_WORD *)v4 + 136) = 0;
  *v4 = &tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>::`vftable';
  v4[33] = v4 + 2;
  result = a1;
  *((_DWORD *)v4 + 70) = 1;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x180027294  mov     [rsp+arg_0], rbx
0x180027299  push    rdi
0x18002729a  sub     rsp, 50h
0x18002729e  mov     rdi, rcx
0x1800272a1  mov     ecx, 120h; cb
0x1800272a6  call    cs:__imp_CoTaskMemAlloc
0x1800272ac  mov     rbx, rax
0x1800272af  test    rax, rax
0x1800272b2  jz      loc_180027348
0x1800272b8  xor     ecx, ecx
0x1800272ba  mov     [rsp+58h+var_38], 33B5A92h
0x1800272c2  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x1800272c9  mov     [rsp+58h+var_26], ecx
0x1800272cd  mov     [rbx], rax
0x1800272d0  lea     r8, [rsp+58h+var_38]
0x1800272d5  lea     rax, aProcesstermina; "ProcessTerminationTipTest"
0x1800272dc  mov     [rsp+58h+var_22], cx
0x1800272e1  xorps   xmm0, xmm0
0x1800272e4  mov     [rsp+58h+var_10], rcx
0x1800272e9  lea     rcx, [rbx+8]
0x1800272ed  mov     [rsp+58h+var_30], rax
0x1800272f2  mov     rdx, rbx
0x1800272f5  mov     [rsp+58h+var_34], 0C100h
0x1800272fd  mov     [rsp+58h+var_28], 101h
0x180027304  movdqu  [rsp+58h+var_20], xmm0
0x18002730a  call    ??0?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x18002730f  lea     rax, ??_7?$merged_data@U_tip_ProcessTerminationTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>::`vftable'
0x180027316  mov     word ptr [rbx+110h], 0
0x18002731f  mov     [rbx], rax
0x180027322  lea     rax, [rbx+10h]
0x180027326  mov     [rbx+108h], rax
0x18002732d  mov     rax, rdi
0x180027330  mov     dword ptr [rbx+118h], 1
0x18002733a  mov     [rdi], rbx
0x18002733d  mov     rbx, [rsp+58h+arg_0]
0x180027342  add     rsp, 50h
0x180027346  pop     rdi
0x180027347  retn
0x180027348  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
