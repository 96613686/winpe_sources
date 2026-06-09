# tip2::tip_test<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::ensure_data(void)

- ea: `0x18009dabc`
- end: `0x18009db15`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_PersonalizationThemeBackupTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_PersonalizationThemeBackupTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18009b7f0`
- `0x18009d8ac`

## callees

- `0x180012ab4`
- `0x180099fdc`
- `0x18009a550`
- `0x18009c774`
- `0x18009dabc`

## import_xrefs

- `OLE32!CoTaskMemAlloc` at `0x18009dad0`
- `OLE32!CoTaskMemAlloc` at `0x18009dad0`

## pseudocode

```c
void **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::ensure_data(
        void **a1)
{
  LPVOID v2; // rax
  wil::details::in1diag3 *v3; // rcx
  __int64 v4; // rax
  void *v5; // rcx
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  if ( !*a1 )
  {
    v2 = CoTaskMemAlloc(0x120u);
    if ( !v2 )
      wil::details::in1diag3::FailFastImmediate_Unexpected(v3);
    v4 = tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>(v2);
    v5 = *a1;
    v7 = 0;
    *a1 = (void *)v4;
    if ( v5 )
      tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>::Release(v5);
    wil::com_ptr_t<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>,wil::err_returncode_policy>(&v7);
  }
  return a1;
}

```

## disassembly

```asm
0x18009dabc  push    rbx
0x18009dabe  sub     rsp, 20h
0x18009dac2  cmp     qword ptr [rcx], 0
0x18009dac6  mov     rbx, rcx
0x18009dac9  jnz     short loc_18009DB06
0x18009dacb  mov     ecx, 120h; cb
0x18009dad0  call    cs:__imp_CoTaskMemAlloc
0x18009dad6  test    rax, rax
0x18009dad9  jz      short loc_18009DB0F
0x18009dadb  mov     rcx, rax
0x18009dade  call    ??0?$merged_data@U_tip_PersonalizationThemeBackupTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>(void)
0x18009dae3  mov     rcx, [rbx]; pv
0x18009dae6  mov     [rsp+28h+arg_0], 0
0x18009daef  mov     [rbx], rax
0x18009daf2  test    rcx, rcx
0x18009daf5  jz      short loc_18009DAFC
0x18009daf7  call    ?Release@?$merged_data@U_tip_PersonalizationThemeBackupTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>::Release(void)
0x18009dafc  lea     rcx, [rsp+28h+arg_0]
0x18009db01  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PersonalizationThemeBackupTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>,wil::err_returncode_policy>(void)
0x18009db06  mov     rax, rbx
0x18009db09  add     rsp, 20h
0x18009db0d  pop     rbx
0x18009db0e  retn
0x18009db0f  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
```
