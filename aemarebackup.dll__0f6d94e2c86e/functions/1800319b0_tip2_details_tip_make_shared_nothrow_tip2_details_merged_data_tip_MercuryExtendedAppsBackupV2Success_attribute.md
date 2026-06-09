# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>,_GUID * &>(_GUID * &)

- ea: `0x1800319b0`
- end: `0x180031adc`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@AEAPEAU_GUID@@@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_MercuryExtendedAppsBackupV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@AEAPEAU_GUID@@@Z`
- size: `300`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180031910`

## callees

- `0x18000e53c`
- `0x180012174`
- `0x1800319b0`
- `0x180032528`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1800319c5`
- `ole32!CoTaskMemAlloc` at `0x1800319c5`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_MercuryExtendedAppsBackupV2Success_attributes,tip2::test_data_basic>,_GUID * &>(
        _QWORD *a1,
        __int64 *a2)
{
  _QWORD *v4; // rax
  wil::details::in1diag3 *v5; // rcx
  _QWORD *v6; // rsi
  __int64 v7; // rdi
  _QWORD *result; // rax
  _DWORD v9[2]; // [rsp+20h] [rbp-58h] BYREF
  const char *v10; // [rsp+28h] [rbp-50h]
  __int16 v11; // [rsp+30h] [rbp-48h]
  int v12; // [rsp+32h] [rbp-46h]
  __int16 v13; // [rsp+36h] [rbp-42h]
  __int128 v14; // [rsp+38h] [rbp-40h]
  __int64 *v15; // [rsp+48h] [rbp-30h]

  v4 = CoTaskMemAlloc(0x158u);
  v6 = v4;
  if ( !v4 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v5);
  v7 = *a2;
  *v4 = &tip2::details::test_data_interface::`vftable';
  v12 = 0;
  v10 = "MercuryExtendedAppsBackupV2Success";
  v13 = 0;
  v15 = &`_tip_MercuryExtendedAppsBackupV2Success_attributes::__flags_all_clear'::`2'::args;
  v9[0] = 47091517;
  v9[1] = 147712;
  v11 = 1;
  v14 = 0;
  tip2::details::shared_data<1,0,1>::shared_data<1,0,1>(v4 + 1, v4, v9);
  v6[33] = 0;
  *v6 = &tip2::details::merged_data<_tip_MercuryBackupJsonSuccess_attributes,tip2::test_data_basic>::`vftable';
  v6[34] = 0;
  v6[32] = v6 + 2;
  v6[35] = 0;
  v6[36] = 0;
  v6[37] = 0;
  v6[38] = 0;
  v6[39] = 0;
  v6[40] = 0;
  v6[41] = 0;
  *((_DWORD *)v6 + 84) = 1;
  tip2::details::shared_data<1,0,1>::open_without_lock(v6 + 1, v7);
  result = a1;
  *a1 = v6;
  return result;
}

```

## disassembly

```asm
0x1800319b0  push    rbx
0x1800319b2  push    rsi
0x1800319b3  push    rdi
0x1800319b4  push    r14
0x1800319b6  sub     rsp, 58h
0x1800319ba  mov     r14, rcx
0x1800319bd  mov     rdi, rdx
0x1800319c0  mov     ecx, 158h; cb
0x1800319c5  call    cs:__imp_CoTaskMemAlloc
0x1800319cb  mov     rsi, rax
0x1800319ce  test    rax, rax
0x1800319d1  jz      loc_180031AD6
0x1800319d7  mov     rdi, [rdi]
0x1800319da  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x1800319e1  xor     edx, edx
0x1800319e3  mov     [rsi], rax
0x1800319e6  lea     rcx, aMercuryextende; "MercuryExtendedAppsBackupV2Success"
0x1800319ed  mov     [rsp+78h+var_46], edx
0x1800319f1  lea     rax, ?args@?1??__flags_all_clear@_tip_MercuryExtendedAppsBackupV2Success_attributes@@SAPEBUtest_requirement@tip2@@XZ@4QBU34@B; tip2::test_requirement const near * const `_tip_MercuryExtendedAppsBackupV2Success_attributes::__flags_all_clear(void)'::`2'::args
0x1800319f8  mov     [rsp+78h+var_50], rcx
0x1800319fd  mov     [rsp+78h+var_42], dx
0x180031a02  lea     r8, [rsp+78h+var_58]
0x180031a07  xorps   xmm0, xmm0
0x180031a0a  mov     [rsp+78h+var_30], rax
0x180031a0f  mov     rdx, rsi
0x180031a12  mov     [rsp+78h+var_58], 2CE8F3Dh
0x180031a1a  lea     rcx, [rsi+8]
0x180031a1e  mov     [rsp+78h+var_54], 24100h
0x180031a26  mov     [rsp+78h+var_48], 1
0x180031a2d  movdqu  [rsp+78h+var_40], xmm0
0x180031a33  call    ??0?$shared_data@$00$0A@$00@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<1,0,1>::shared_data<1,0,1>(tip2::details::test_data_interface &,tip2::test_info const &)
0x180031a38  lea     rax, ??_7?$merged_data@U_tip_MercuryBackupJsonSuccess_attributes@@Vtest_data_basic@tip2@@@details@tip2@@6B@; const tip2::details::merged_data<_tip_MercuryBackupJsonSuccess_attributes,tip2::test_data_basic>::`vftable'
0x180031a3f  mov     qword ptr [rsi+108h], 0
0x180031a4a  mov     [rsi], rax
0x180031a4d  lea     rcx, [rsi+8]
0x180031a51  lea     rax, [rsi+10h]
0x180031a55  mov     qword ptr [rsi+110h], 0
0x180031a60  mov     rdx, rdi
0x180031a63  mov     [rsi+100h], rax
0x180031a6a  mov     qword ptr [rsi+118h], 0
0x180031a75  mov     qword ptr [rsi+120h], 0
0x180031a80  mov     qword ptr [rsi+128h], 0
0x180031a8b  mov     qword ptr [rsi+130h], 0
0x180031a96  mov     qword ptr [rsi+138h], 0
0x180031aa1  mov     qword ptr [rsi+140h], 0
0x180031aac  mov     qword ptr [rsi+148h], 0
0x180031ab7  mov     dword ptr [rsi+150h], 1
0x180031ac1  call    ?open_without_lock@?$shared_data@$00$0A@$00@details@tip2@@IEAAXPEAU_GUID@@@Z; tip2::details::shared_data<1,0,1>::open_without_lock(_GUID *)
0x180031ac6  mov     rax, r14
0x180031ac9  mov     [r14], rsi
0x180031acc  add     rsp, 58h
0x180031ad0  pop     r14
0x180031ad2  pop     rdi
0x180031ad3  pop     rsi
0x180031ad4  pop     rbx
0x180031ad5  retn
0x180031ad6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
