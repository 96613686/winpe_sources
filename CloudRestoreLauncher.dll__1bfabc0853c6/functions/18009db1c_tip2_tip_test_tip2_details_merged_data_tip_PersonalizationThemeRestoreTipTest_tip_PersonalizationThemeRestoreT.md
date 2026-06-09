# tip2::tip_test<tip2::details::merged_data<_tip_PersonalizationThemeRestoreTipTest,_tip_PersonalizationThemeRestoreTipTest>>::ensure_data(void)

- ea: `0x18009db1c`
- end: `0x18009db75`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_PersonalizationThemeRestoreTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_PersonalizationThemeRestoreTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18009c380`
- `0x18009d8e8`

## callees

- `0x180012ab4`
- `0x18009a074`
- `0x18009a56c`
- `0x18009c7b4`
- `0x18009db1c`

## import_xrefs

- `OLE32!CoTaskMemAlloc` at `0x18009db30`
- `OLE32!CoTaskMemAlloc` at `0x18009db30`

## pseudocode

```c
void **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_PersonalizationThemeRestoreTipTest,_tip_PersonalizationThemeRestoreTipTest>>::ensure_data(
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
    v4 = tip2::details::merged_data<_tip_PersonalizationThemeRestoreTipTest,_tip_PersonalizationThemeRestoreTipTest>::merged_data<_tip_PersonalizationThemeRestoreTipTest,_tip_PersonalizationThemeRestoreTipTest>(v2);
    v5 = *a1;
    v7 = 0;
    *a1 = (void *)v4;
    if ( v5 )
      tip2::details::merged_data<_tip_PersonalizationThemeRestoreTipTest,_tip_PersonalizationThemeRestoreTipTest>::Release(v5);
    wil::com_ptr_t<tip2::details::merged_data<_tip_PersonalizationThemeRestoreTipTest,_tip_PersonalizationThemeRestoreTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PersonalizationThemeRestoreTipTest,_tip_PersonalizationThemeRestoreTipTest>,wil::err_returncode_policy>(&v7);
  }
  return a1;
}

```

## disassembly

```asm
0x18009db1c  push    rbx
0x18009db1e  sub     rsp, 20h
0x18009db22  cmp     qword ptr [rcx], 0
0x18009db26  mov     rbx, rcx
0x18009db29  jnz     short loc_18009DB66
0x18009db2b  mov     ecx, 120h; cb
0x18009db30  call    cs:__imp_CoTaskMemAlloc
0x18009db36  test    rax, rax
0x18009db39  jz      short loc_18009DB6F
0x18009db3b  mov     rcx, rax
0x18009db3e  call    ??0?$merged_data@U_tip_PersonalizationThemeRestoreTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_PersonalizationThemeRestoreTipTest,_tip_PersonalizationThemeRestoreTipTest>::merged_data<_tip_PersonalizationThemeRestoreTipTest,_tip_PersonalizationThemeRestoreTipTest>(void)
0x18009db43  mov     rcx, [rbx]; pv
0x18009db46  mov     [rsp+28h+arg_0], 0
0x18009db4f  mov     [rbx], rax
0x18009db52  test    rcx, rcx
0x18009db55  jz      short loc_18009DB5C
0x18009db57  call    ?Release@?$merged_data@U_tip_PersonalizationThemeRestoreTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_PersonalizationThemeRestoreTipTest,_tip_PersonalizationThemeRestoreTipTest>::Release(void)
0x18009db5c  lea     rcx, [rsp+28h+arg_0]
0x18009db61  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PersonalizationThemeRestoreTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PersonalizationThemeRestoreTipTest,_tip_PersonalizationThemeRestoreTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PersonalizationThemeRestoreTipTest,_tip_PersonalizationThemeRestoreTipTest>,wil::err_returncode_policy>(void)
0x18009db66  mov     rax, rbx
0x18009db69  add     rsp, 20h
0x18009db6d  pop     rbx
0x18009db6e  retn
0x18009db6f  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
```
