# tip2::tip_test<tip2::details::merged_data<_tip_SecondaryAccountsBackupTipTests,_tip_SecondaryAccountsBackupTipTests>>::ensure_data(void)

- ea: `0x1800defd0`
- end: `0x1800df029`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_SecondaryAccountsBackupTipTests@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_SecondaryAccountsBackupTipTests@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800dd2d0`
- `0x1800deebc`

## callees

- `0x180012ab4`
- `0x1800da7c4`
- `0x1800dad68`
- `0x1800dd688`
- `0x1800defd0`

## import_xrefs

- `OLE32!CoTaskMemAlloc` at `0x1800defe4`
- `OLE32!CoTaskMemAlloc` at `0x1800defe4`

## pseudocode

```c
void **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_SecondaryAccountsBackupTipTests,_tip_SecondaryAccountsBackupTipTests>>::ensure_data(
        void **a1)
{
  LPVOID v2; // rax
  wil::details::in1diag3 *v3; // rcx
  __int64 v4; // rax
  void *v5; // rcx
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  if ( !*a1 )
  {
    v2 = CoTaskMemAlloc(0x140u);
    if ( !v2 )
      wil::details::in1diag3::FailFastImmediate_Unexpected(v3);
    v4 = tip2::details::merged_data<_tip_SecondaryAccountsBackupTipTests,_tip_SecondaryAccountsBackupTipTests>::merged_data<_tip_SecondaryAccountsBackupTipTests,_tip_SecondaryAccountsBackupTipTests>(v2);
    v5 = *a1;
    v7 = 0;
    *a1 = (void *)v4;
    if ( v5 )
      tip2::details::merged_data<_tip_SecondaryAccountsBackupTipTests,_tip_SecondaryAccountsBackupTipTests>::Release(v5);
    wil::com_ptr_t<tip2::details::merged_data<_tip_SecondaryAccountsBackupTipTests,_tip_SecondaryAccountsBackupTipTests>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SecondaryAccountsBackupTipTests,_tip_SecondaryAccountsBackupTipTests>,wil::err_returncode_policy>(&v7);
  }
  return a1;
}

```

## disassembly

```asm
0x1800defd0  push    rbx
0x1800defd2  sub     rsp, 20h
0x1800defd6  cmp     qword ptr [rcx], 0
0x1800defda  mov     rbx, rcx
0x1800defdd  jnz     short loc_1800DF01A
0x1800defdf  mov     ecx, 140h; cb
0x1800defe4  call    cs:__imp_CoTaskMemAlloc
0x1800defea  test    rax, rax
0x1800defed  jz      short loc_1800DF023
0x1800defef  mov     rcx, rax
0x1800deff2  call    ??0?$merged_data@U_tip_SecondaryAccountsBackupTipTests@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_SecondaryAccountsBackupTipTests,_tip_SecondaryAccountsBackupTipTests>::merged_data<_tip_SecondaryAccountsBackupTipTests,_tip_SecondaryAccountsBackupTipTests>(void)
0x1800deff7  mov     rcx, [rbx]; pv
0x1800deffa  mov     [rsp+28h+arg_0], 0
0x1800df003  mov     [rbx], rax
0x1800df006  test    rcx, rcx
0x1800df009  jz      short loc_1800DF010
0x1800df00b  call    ?Release@?$merged_data@U_tip_SecondaryAccountsBackupTipTests@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_SecondaryAccountsBackupTipTests,_tip_SecondaryAccountsBackupTipTests>::Release(void)
0x1800df010  lea     rcx, [rsp+28h+arg_0]
0x1800df015  call    ??1?$com_ptr_t@V?$merged_data@U_tip_SecondaryAccountsBackupTipTests@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_SecondaryAccountsBackupTipTests,_tip_SecondaryAccountsBackupTipTests>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SecondaryAccountsBackupTipTests,_tip_SecondaryAccountsBackupTipTests>,wil::err_returncode_policy>(void)
0x1800df01a  mov     rax, rbx
0x1800df01d  add     rsp, 20h
0x1800df021  pop     rbx
0x1800df022  retn
0x1800df023  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
```
