# tip2::tip_test<tip2::details::merged_data<_tip_BackgroundBackupTipTests,_tip_BackgroundBackupTipTests>>::ensure_data(void)

- ea: `0x1800b0e20`
- end: `0x1800b0e79`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_BackgroundBackupTipTests@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_BackgroundBackupTipTests@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `89`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800a8954`
- `0x1800a8cf8`
- `0x1800b1f24`

## callees

- `0x180012ab4`
- `0x1800a054c`
- `0x1800a0da0`
- `0x1800a803c`
- `0x1800b0e20`

## import_xrefs

- `OLE32!CoTaskMemAlloc` at `0x1800b0e34`
- `OLE32!CoTaskMemAlloc` at `0x1800b0e34`

## pseudocode

```c
void **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_BackgroundBackupTipTests,_tip_BackgroundBackupTipTests>>::ensure_data(
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
    v4 = tip2::details::merged_data<_tip_BackgroundBackupTipTests,_tip_BackgroundBackupTipTests>::merged_data<_tip_BackgroundBackupTipTests,_tip_BackgroundBackupTipTests>(v2);
    v5 = *a1;
    v7 = 0;
    *a1 = (void *)v4;
    if ( v5 )
      tip2::details::merged_data<_tip_BackgroundBackupTipTests,_tip_BackgroundBackupTipTests>::Release(v5);
    wil::com_ptr_t<tip2::details::merged_data<_tip_BackgroundBackupTipTests,_tip_BackgroundBackupTipTests>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_BackgroundBackupTipTests,_tip_BackgroundBackupTipTests>,wil::err_returncode_policy>(&v7);
  }
  return a1;
}

```

## disassembly

```asm
0x1800b0e20  push    rbx
0x1800b0e22  sub     rsp, 20h
0x1800b0e26  cmp     qword ptr [rcx], 0
0x1800b0e2a  mov     rbx, rcx
0x1800b0e2d  jnz     short loc_1800B0E6A
0x1800b0e2f  mov     ecx, 120h; cb
0x1800b0e34  call    cs:__imp_CoTaskMemAlloc
0x1800b0e3a  test    rax, rax
0x1800b0e3d  jz      short loc_1800B0E73
0x1800b0e3f  mov     rcx, rax
0x1800b0e42  call    ??0?$merged_data@U_tip_BackgroundBackupTipTests@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_BackgroundBackupTipTests,_tip_BackgroundBackupTipTests>::merged_data<_tip_BackgroundBackupTipTests,_tip_BackgroundBackupTipTests>(void)
0x1800b0e47  mov     rcx, [rbx]; pv
0x1800b0e4a  mov     [rsp+28h+arg_0], 0
0x1800b0e53  mov     [rbx], rax
0x1800b0e56  test    rcx, rcx
0x1800b0e59  jz      short loc_1800B0E60
0x1800b0e5b  call    ?Release@?$merged_data@U_tip_BackgroundBackupTipTests@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_BackgroundBackupTipTests,_tip_BackgroundBackupTipTests>::Release(void)
0x1800b0e60  lea     rcx, [rsp+28h+arg_0]
0x1800b0e65  call    ??1?$com_ptr_t@V?$merged_data@U_tip_BackgroundBackupTipTests@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_BackgroundBackupTipTests,_tip_BackgroundBackupTipTests>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_BackgroundBackupTipTests,_tip_BackgroundBackupTipTests>,wil::err_returncode_policy>(void)
0x1800b0e6a  mov     rax, rbx
0x1800b0e6d  add     rsp, 20h
0x1800b0e71  pop     rbx
0x1800b0e72  retn
0x1800b0e73  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
```
