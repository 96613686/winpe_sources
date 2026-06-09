# tip2::tip_test<tip2::details::merged_data<_tip_LockscreenBackupTipTests,_tip_LockscreenBackupTipTests>>::ensure_data(void)

- ea: `0x1800bf5ec`
- end: `0x1800bf645`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_LockscreenBackupTipTests@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_LockscreenBackupTipTests@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `89`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800bc184`
- `0x1800bc40c`
- `0x1800bfad8`

## callees

- `0x180012ab4`
- `0x1800bb978`
- `0x1800bbd10`
- `0x1800be96c`
- `0x1800bf5ec`

## import_xrefs

- `OLE32!CoTaskMemAlloc` at `0x1800bf600`
- `OLE32!CoTaskMemAlloc` at `0x1800bf600`

## pseudocode

```c
void **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_LockscreenBackupTipTests,_tip_LockscreenBackupTipTests>>::ensure_data(
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
    v4 = tip2::details::merged_data<_tip_LockscreenBackupTipTests,_tip_LockscreenBackupTipTests>::merged_data<_tip_LockscreenBackupTipTests,_tip_LockscreenBackupTipTests>(v2);
    v5 = *a1;
    v7 = 0;
    *a1 = (void *)v4;
    if ( v5 )
      tip2::details::merged_data<_tip_LockscreenBackupTipTests,_tip_LockscreenBackupTipTests>::Release(v5);
    wil::com_ptr_t<tip2::details::merged_data<_tip_LockscreenBackupTipTests,_tip_LockscreenBackupTipTests>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_LockscreenBackupTipTests,_tip_LockscreenBackupTipTests>,wil::err_returncode_policy>(&v7);
  }
  return a1;
}

```

## disassembly

```asm
0x1800bf5ec  push    rbx
0x1800bf5ee  sub     rsp, 20h
0x1800bf5f2  cmp     qword ptr [rcx], 0
0x1800bf5f6  mov     rbx, rcx
0x1800bf5f9  jnz     short loc_1800BF636
0x1800bf5fb  mov     ecx, 120h; cb
0x1800bf600  call    cs:__imp_CoTaskMemAlloc
0x1800bf606  test    rax, rax
0x1800bf609  jz      short loc_1800BF63F
0x1800bf60b  mov     rcx, rax
0x1800bf60e  call    ??0?$merged_data@U_tip_LockscreenBackupTipTests@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_LockscreenBackupTipTests,_tip_LockscreenBackupTipTests>::merged_data<_tip_LockscreenBackupTipTests,_tip_LockscreenBackupTipTests>(void)
0x1800bf613  mov     rcx, [rbx]; pv
0x1800bf616  mov     [rsp+28h+arg_0], 0
0x1800bf61f  mov     [rbx], rax
0x1800bf622  test    rcx, rcx
0x1800bf625  jz      short loc_1800BF62C
0x1800bf627  call    ?Release@?$merged_data@U_tip_LockscreenBackupTipTests@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_LockscreenBackupTipTests,_tip_LockscreenBackupTipTests>::Release(void)
0x1800bf62c  lea     rcx, [rsp+28h+arg_0]
0x1800bf631  call    ??1?$com_ptr_t@V?$merged_data@U_tip_LockscreenBackupTipTests@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_LockscreenBackupTipTests,_tip_LockscreenBackupTipTests>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_LockscreenBackupTipTests,_tip_LockscreenBackupTipTests>,wil::err_returncode_policy>(void)
0x1800bf636  mov     rax, rbx
0x1800bf639  add     rsp, 20h
0x1800bf63d  pop     rbx
0x1800bf63e  retn
0x1800bf63f  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
```
