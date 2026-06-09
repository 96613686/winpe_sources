# tip2::tip_test<tip2::details::merged_data<_tip_ContrastThemeRestoreTipTest,_tip_ContrastThemeRestoreTipTest>>::ensure_data(void)

- ea: `0x180096d28`
- end: `0x180096d81`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_ContrastThemeRestoreTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_ContrastThemeRestoreTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `89`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180095170`
- `0x180096bcc`

## callees

- `0x180012ab4`
- `0x1800921ac`
- `0x180092378`
- `0x18009591c`
- `0x180096d28`

## import_xrefs

- `OLE32!CoTaskMemAlloc` at `0x180096d3c`
- `OLE32!CoTaskMemAlloc` at `0x180096d3c`

## pseudocode

```c
void **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_ContrastThemeRestoreTipTest,_tip_ContrastThemeRestoreTipTest>>::ensure_data(
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
    v4 = tip2::details::merged_data<_tip_ContrastThemeRestoreTipTest,_tip_ContrastThemeRestoreTipTest>::merged_data<_tip_ContrastThemeRestoreTipTest,_tip_ContrastThemeRestoreTipTest>(v2);
    v5 = *a1;
    v7 = 0;
    *a1 = (void *)v4;
    if ( v5 )
      tip2::details::merged_data<_tip_ContrastThemeRestoreTipTest,_tip_ContrastThemeRestoreTipTest>::Release(v5);
    wil::com_ptr_t<tip2::details::merged_data<_tip_ContrastThemeRestoreTipTest,_tip_ContrastThemeRestoreTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ContrastThemeRestoreTipTest,_tip_ContrastThemeRestoreTipTest>,wil::err_returncode_policy>(&v7);
  }
  return a1;
}

```

## disassembly

```asm
0x180096d28  push    rbx
0x180096d2a  sub     rsp, 20h
0x180096d2e  cmp     qword ptr [rcx], 0
0x180096d32  mov     rbx, rcx
0x180096d35  jnz     short loc_180096D72
0x180096d37  mov     ecx, 120h; cb
0x180096d3c  call    cs:__imp_CoTaskMemAlloc
0x180096d42  test    rax, rax
0x180096d45  jz      short loc_180096D7B
0x180096d47  mov     rcx, rax
0x180096d4a  call    ??0?$merged_data@U_tip_ContrastThemeRestoreTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_ContrastThemeRestoreTipTest,_tip_ContrastThemeRestoreTipTest>::merged_data<_tip_ContrastThemeRestoreTipTest,_tip_ContrastThemeRestoreTipTest>(void)
0x180096d4f  mov     rcx, [rbx]; pv
0x180096d52  mov     [rsp+28h+arg_0], 0
0x180096d5b  mov     [rbx], rax
0x180096d5e  test    rcx, rcx
0x180096d61  jz      short loc_180096D68
0x180096d63  call    ?Release@?$merged_data@U_tip_ContrastThemeRestoreTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_ContrastThemeRestoreTipTest,_tip_ContrastThemeRestoreTipTest>::Release(void)
0x180096d68  lea     rcx, [rsp+28h+arg_0]
0x180096d6d  call    ??1?$com_ptr_t@V?$merged_data@U_tip_ContrastThemeRestoreTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_ContrastThemeRestoreTipTest,_tip_ContrastThemeRestoreTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ContrastThemeRestoreTipTest,_tip_ContrastThemeRestoreTipTest>,wil::err_returncode_policy>(void)
0x180096d72  mov     rax, rbx
0x180096d75  add     rsp, 20h
0x180096d79  pop     rbx
0x180096d7a  retn
0x180096d7b  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
```
