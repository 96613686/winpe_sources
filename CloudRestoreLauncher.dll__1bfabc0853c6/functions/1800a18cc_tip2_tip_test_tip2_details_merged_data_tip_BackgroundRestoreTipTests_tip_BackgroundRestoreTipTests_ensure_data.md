# tip2::tip_test<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>::ensure_data(void)

- ea: `0x1800a18cc`
- end: `0x1800a1925`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_BackgroundRestoreTipTests@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_BackgroundRestoreTipTests@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `89`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800a07c8`
- `0x1800a07f0`
- `0x1800a1d38`

## callees

- `0x180012ab4`
- `0x1800a0454`
- `0x1800a0568`
- `0x1800a0de0`
- `0x1800a18cc`

## import_xrefs

- `OLE32!CoTaskMemAlloc` at `0x1800a18e0`
- `OLE32!CoTaskMemAlloc` at `0x1800a18e0`

## pseudocode

```c
void **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>>::ensure_data(
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
    v4 = tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>(v2);
    v5 = *a1;
    v7 = 0;
    *a1 = (void *)v4;
    if ( v5 )
      tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>::Release(v5);
    wil::com_ptr_t<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>,wil::err_returncode_policy>(&v7);
  }
  return a1;
}

```

## disassembly

```asm
0x1800a18cc  push    rbx
0x1800a18ce  sub     rsp, 20h
0x1800a18d2  cmp     qword ptr [rcx], 0
0x1800a18d6  mov     rbx, rcx
0x1800a18d9  jnz     short loc_1800A1916
0x1800a18db  mov     ecx, 120h; cb
0x1800a18e0  call    cs:__imp_CoTaskMemAlloc
0x1800a18e6  test    rax, rax
0x1800a18e9  jz      short loc_1800A191F
0x1800a18eb  mov     rcx, rax
0x1800a18ee  call    ??0?$merged_data@U_tip_BackgroundRestoreTipTests@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>(void)
0x1800a18f3  mov     rcx, [rbx]; pv
0x1800a18f6  mov     [rsp+28h+arg_0], 0
0x1800a18ff  mov     [rbx], rax
0x1800a1902  test    rcx, rcx
0x1800a1905  jz      short loc_1800A190C
0x1800a1907  call    ?Release@?$merged_data@U_tip_BackgroundRestoreTipTests@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>::Release(void)
0x1800a190c  lea     rcx, [rsp+28h+arg_0]
0x1800a1911  call    ??1?$com_ptr_t@V?$merged_data@U_tip_BackgroundRestoreTipTests@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_BackgroundRestoreTipTests,_tip_BackgroundRestoreTipTests>,wil::err_returncode_policy>(void)
0x1800a1916  mov     rax, rbx
0x1800a1919  add     rsp, 20h
0x1800a191d  pop     rbx
0x1800a191e  retn
0x1800a191f  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
```
