# tip2::tip_test<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>::ensure_data(void)

- ea: `0x1800ff778`
- end: `0x1800ff7d1`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_DesktopSettingRestoreTipTests@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_DesktopSettingRestoreTipTests@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800fe9dc`
- `0x1800fec70`

## callees

- `0x180012ab4`
- `0x1800fe804`
- `0x1800fe89c`
- `0x1800ff0fc`
- `0x1800ff778`

## import_xrefs

- `OLE32!CoTaskMemAlloc` at `0x1800ff78c`
- `OLE32!CoTaskMemAlloc` at `0x1800ff78c`

## pseudocode

```c
void **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>>::ensure_data(
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
    v4 = tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>(v2);
    v5 = *a1;
    v7 = 0;
    *a1 = (void *)v4;
    if ( v5 )
      tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>::Release(v5);
    wil::com_ptr_t<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>,wil::err_returncode_policy>(&v7);
  }
  return a1;
}

```

## disassembly

```asm
0x1800ff778  push    rbx
0x1800ff77a  sub     rsp, 20h
0x1800ff77e  cmp     qword ptr [rcx], 0
0x1800ff782  mov     rbx, rcx
0x1800ff785  jnz     short loc_1800FF7C2
0x1800ff787  mov     ecx, 120h; cb
0x1800ff78c  call    cs:__imp_CoTaskMemAlloc
0x1800ff792  test    rax, rax
0x1800ff795  jz      short loc_1800FF7CB
0x1800ff797  mov     rcx, rax
0x1800ff79a  call    ??0?$merged_data@U_tip_DesktopSettingRestoreTipTests@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>(void)
0x1800ff79f  mov     rcx, [rbx]; pv
0x1800ff7a2  mov     [rsp+28h+arg_0], 0
0x1800ff7ab  mov     [rbx], rax
0x1800ff7ae  test    rcx, rcx
0x1800ff7b1  jz      short loc_1800FF7B8
0x1800ff7b3  call    ?Release@?$merged_data@U_tip_DesktopSettingRestoreTipTests@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>::Release(void)
0x1800ff7b8  lea     rcx, [rsp+28h+arg_0]
0x1800ff7bd  call    ??1?$com_ptr_t@V?$merged_data@U_tip_DesktopSettingRestoreTipTests@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_DesktopSettingRestoreTipTests,_tip_DesktopSettingRestoreTipTests>,wil::err_returncode_policy>(void)
0x1800ff7c2  mov     rax, rbx
0x1800ff7c5  add     rsp, 20h
0x1800ff7c9  pop     rbx
0x1800ff7ca  retn
0x1800ff7cb  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
```
