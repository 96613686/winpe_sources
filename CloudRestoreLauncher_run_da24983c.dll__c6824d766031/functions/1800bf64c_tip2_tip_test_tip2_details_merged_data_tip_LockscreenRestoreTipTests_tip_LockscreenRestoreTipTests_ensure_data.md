# tip2::tip_test<tip2::details::merged_data<_tip_LockscreenRestoreTipTests,_tip_LockscreenRestoreTipTests>>::ensure_data(void)

- ea: `0x1800bf64c`
- end: `0x1800bf6a5`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_LockscreenRestoreTipTests@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_LockscreenRestoreTipTests@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `89`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800bc1ac`
- `0x1800bc1d4`
- `0x1800be530`

## callees

- `0x180012ab4`
- `0x1800bba18`
- `0x1800bbd2c`
- `0x1800be9ac`
- `0x1800bf64c`

## import_xrefs

- `OLE32!CoTaskMemAlloc` at `0x1800bf660`
- `OLE32!CoTaskMemAlloc` at `0x1800bf660`

## pseudocode

```c
void **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_LockscreenRestoreTipTests,_tip_LockscreenRestoreTipTests>>::ensure_data(
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
    v4 = tip2::details::merged_data<_tip_LockscreenRestoreTipTests,_tip_LockscreenRestoreTipTests>::merged_data<_tip_LockscreenRestoreTipTests,_tip_LockscreenRestoreTipTests>(v2);
    v5 = *a1;
    v7 = 0;
    *a1 = (void *)v4;
    if ( v5 )
      tip2::details::merged_data<_tip_LockscreenRestoreTipTests,_tip_LockscreenRestoreTipTests>::Release(v5);
    wil::com_ptr_t<tip2::details::merged_data<_tip_LockscreenRestoreTipTests,_tip_LockscreenRestoreTipTests>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_LockscreenRestoreTipTests,_tip_LockscreenRestoreTipTests>,wil::err_returncode_policy>(&v7);
  }
  return a1;
}

```

## disassembly

```asm
0x1800bf64c  push    rbx
0x1800bf64e  sub     rsp, 20h
0x1800bf652  cmp     qword ptr [rcx], 0
0x1800bf656  mov     rbx, rcx
0x1800bf659  jnz     short loc_1800BF696
0x1800bf65b  mov     ecx, 120h; cb
0x1800bf660  call    cs:__imp_CoTaskMemAlloc
0x1800bf666  test    rax, rax
0x1800bf669  jz      short loc_1800BF69F
0x1800bf66b  mov     rcx, rax
0x1800bf66e  call    ??0?$merged_data@U_tip_LockscreenRestoreTipTests@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_LockscreenRestoreTipTests,_tip_LockscreenRestoreTipTests>::merged_data<_tip_LockscreenRestoreTipTests,_tip_LockscreenRestoreTipTests>(void)
0x1800bf673  mov     rcx, [rbx]; pv
0x1800bf676  mov     [rsp+28h+arg_0], 0
0x1800bf67f  mov     [rbx], rax
0x1800bf682  test    rcx, rcx
0x1800bf685  jz      short loc_1800BF68C
0x1800bf687  call    ?Release@?$merged_data@U_tip_LockscreenRestoreTipTests@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_LockscreenRestoreTipTests,_tip_LockscreenRestoreTipTests>::Release(void)
0x1800bf68c  lea     rcx, [rsp+28h+arg_0]
0x1800bf691  call    ??1?$com_ptr_t@V?$merged_data@U_tip_LockscreenRestoreTipTests@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_LockscreenRestoreTipTests,_tip_LockscreenRestoreTipTests>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_LockscreenRestoreTipTests,_tip_LockscreenRestoreTipTests>,wil::err_returncode_policy>(void)
0x1800bf696  mov     rax, rbx
0x1800bf699  add     rsp, 20h
0x1800bf69d  pop     rbx
0x1800bf69e  retn
0x1800bf69f  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
```
