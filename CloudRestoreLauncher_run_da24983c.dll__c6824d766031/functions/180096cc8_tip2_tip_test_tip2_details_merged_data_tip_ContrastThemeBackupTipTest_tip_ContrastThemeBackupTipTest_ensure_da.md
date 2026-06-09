# tip2::tip_test<tip2::details::merged_data<_tip_ContrastThemeBackupTipTest,_tip_ContrastThemeBackupTipTest>>::ensure_data(void)

- ea: `0x180096cc8`
- end: `0x180096d21`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_ContrastThemeBackupTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_ContrastThemeBackupTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180094740`
- `0x180096b90`

## callees

- `0x180012ab4`
- `0x180092108`
- `0x18009235c`
- `0x1800958dc`
- `0x180096cc8`

## import_xrefs

- `OLE32!CoTaskMemAlloc` at `0x180096cdc`
- `OLE32!CoTaskMemAlloc` at `0x180096cdc`

## pseudocode

```c
void **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_ContrastThemeBackupTipTest,_tip_ContrastThemeBackupTipTest>>::ensure_data(
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
    v4 = tip2::details::merged_data<_tip_ContrastThemeBackupTipTest,_tip_ContrastThemeBackupTipTest>::merged_data<_tip_ContrastThemeBackupTipTest,_tip_ContrastThemeBackupTipTest>(v2);
    v5 = *a1;
    v7 = 0;
    *a1 = (void *)v4;
    if ( v5 )
      tip2::details::merged_data<_tip_ContrastThemeBackupTipTest,_tip_ContrastThemeBackupTipTest>::Release(v5);
    wil::com_ptr_t<tip2::details::merged_data<_tip_ContrastThemeBackupTipTest,_tip_ContrastThemeBackupTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ContrastThemeBackupTipTest,_tip_ContrastThemeBackupTipTest>,wil::err_returncode_policy>(&v7);
  }
  return a1;
}

```

## disassembly

```asm
0x180096cc8  push    rbx
0x180096cca  sub     rsp, 20h
0x180096cce  cmp     qword ptr [rcx], 0
0x180096cd2  mov     rbx, rcx
0x180096cd5  jnz     short loc_180096D12
0x180096cd7  mov     ecx, 120h; cb
0x180096cdc  call    cs:__imp_CoTaskMemAlloc
0x180096ce2  test    rax, rax
0x180096ce5  jz      short loc_180096D1B
0x180096ce7  mov     rcx, rax
0x180096cea  call    ??0?$merged_data@U_tip_ContrastThemeBackupTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_ContrastThemeBackupTipTest,_tip_ContrastThemeBackupTipTest>::merged_data<_tip_ContrastThemeBackupTipTest,_tip_ContrastThemeBackupTipTest>(void)
0x180096cef  mov     rcx, [rbx]; pv
0x180096cf2  mov     [rsp+28h+arg_0], 0
0x180096cfb  mov     [rbx], rax
0x180096cfe  test    rcx, rcx
0x180096d01  jz      short loc_180096D08
0x180096d03  call    ?Release@?$merged_data@U_tip_ContrastThemeBackupTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_ContrastThemeBackupTipTest,_tip_ContrastThemeBackupTipTest>::Release(void)
0x180096d08  lea     rcx, [rsp+28h+arg_0]
0x180096d0d  call    ??1?$com_ptr_t@V?$merged_data@U_tip_ContrastThemeBackupTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_ContrastThemeBackupTipTest,_tip_ContrastThemeBackupTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ContrastThemeBackupTipTest,_tip_ContrastThemeBackupTipTest>,wil::err_returncode_policy>(void)
0x180096d12  mov     rax, rbx
0x180096d15  add     rsp, 20h
0x180096d19  pop     rbx
0x180096d1a  retn
0x180096d1b  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
```
