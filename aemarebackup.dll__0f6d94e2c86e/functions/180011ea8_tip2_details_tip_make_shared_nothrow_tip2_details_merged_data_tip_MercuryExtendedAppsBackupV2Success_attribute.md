# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>,>(void)

- ea: `0x180011ea8`
- end: `0x180011fc3`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `283`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x1800283e0`

## callees

- `0x18000e53c`
- `0x180011ea8`
- `0x180012174`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180011eba`
- `ole32!CoTaskMemAlloc` at `0x180011eba`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>,>(
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
  __int64 *v12; // [rsp+48h] [rbp-10h]

  v2 = CoTaskMemAlloc(0x158u);
  v4 = v2;
  if ( !v2 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
  v6[0] = 47091517;
  v9 = 0;
  *v2 = &tip2::details::test_data_interface::`vftable';
  v7 = "MercuryExtendedAppsBackupV2Success";
  v10 = 0;
  v12 = &`_tip_MercuryExtendedAppsBackupV2Success_attributes::__flags_all_clear'::`2'::args;
  v6[1] = 147712;
  v8 = 1;
  v11 = 0;
  tip2::details::shared_data<1,0,1>::shared_data<1,0,1>(v2 + 1, v2, v6);
  v4[33] = 0;
  *v4 = &tip2::details::merged_data<_tip_MercuryBackupJsonSuccess_attributes,tip2::test_data_basic>::`vftable';
  v4[32] = v4 + 2;
  result = a1;
  v4[34] = 0;
  v4[35] = 0;
  v4[36] = 0;
  v4[37] = 0;
  v4[38] = 0;
  v4[39] = 0;
  v4[40] = 0;
  v4[41] = 0;
  *((_DWORD *)v4 + 84) = 1;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x180011ea8  mov     [rsp+arg_0], rbx
0x180011ead  push    rdi
0x180011eae  sub     rsp, 50h
0x180011eb2  mov     rdi, rcx
0x180011eb5  mov     ecx, 158h; cb
0x180011eba  call    cs:__imp_CoTaskMemAlloc
0x180011ec0  mov     rbx, rax
0x180011ec3  test    rax, rax
0x180011ec6  jz      loc_180011FBD
0x180011ecc  xor     edx, edx
0x180011ece  mov     [rsp+58h+var_38], 2CE8F3Dh
0x180011ed6  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x180011edd  mov     [rsp+58h+var_26], edx
0x180011ee1  lea     rcx, aMercuryextende; "MercuryExtendedAppsBackupV2Success"
0x180011ee8  mov     [rbx], rax
0x180011eeb  lea     rax, ?args@?1??__flags_all_clear@_tip_MercuryExtendedAppsBackupV2Success_attributes@@SAPEBUtest_requirement@tip2@@XZ@4QBU34@B; tip2::test_requirement const near * const `_tip_MercuryExtendedAppsBackupV2Success_attributes::__flags_all_clear(void)'::`2'::args
0x180011ef2  mov     [rsp+58h+var_30], rcx
0x180011ef7  mov     [rsp+58h+var_22], dx
0x180011efc  lea     rcx, [rbx+8]
0x180011f00  xorps   xmm0, xmm0
0x180011f03  mov     [rsp+58h+var_10], rax
0x180011f08  lea     r8, [rsp+58h+var_38]
0x180011f0d  mov     [rsp+58h+var_34], 24100h
0x180011f15  mov     rdx, rbx
0x180011f18  mov     [rsp+58h+var_28], 1
0x180011f1f  movdqu  [rsp+58h+var_20], xmm0
0x180011f25  call    ??0?$shared_data@$00$0A@$00@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<1,0,1>::shared_data<1,0,1>(tip2::details::test_data_interface &,tip2::test_info const &)
0x180011f2a  lea     rax, ??_7?$merged_data@U_tip_MercuryBackupJsonSuccess_attributes@@Vtest_data_basic@tip2@@@details@tip2@@6B@; const tip2::details::merged_data<_tip_MercuryBackupJsonSuccess_attributes,tip2::test_data_basic>::`vftable'
0x180011f31  mov     qword ptr [rbx+108h], 0
0x180011f3c  mov     [rbx], rax
0x180011f3f  lea     rax, [rbx+10h]
0x180011f43  mov     [rbx+100h], rax
0x180011f4a  mov     rax, rdi
0x180011f4d  mov     qword ptr [rbx+110h], 0
0x180011f58  mov     qword ptr [rbx+118h], 0
0x180011f63  mov     qword ptr [rbx+120h], 0
0x180011f6e  mov     qword ptr [rbx+128h], 0
0x180011f79  mov     qword ptr [rbx+130h], 0
0x180011f84  mov     qword ptr [rbx+138h], 0
0x180011f8f  mov     qword ptr [rbx+140h], 0
0x180011f9a  mov     qword ptr [rbx+148h], 0
0x180011fa5  mov     dword ptr [rbx+150h], 1
0x180011faf  mov     [rdi], rbx
0x180011fb2  mov     rbx, [rsp+58h+arg_0]
0x180011fb7  add     rsp, 50h
0x180011fbb  pop     rdi
0x180011fbc  retn
0x180011fbd  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
