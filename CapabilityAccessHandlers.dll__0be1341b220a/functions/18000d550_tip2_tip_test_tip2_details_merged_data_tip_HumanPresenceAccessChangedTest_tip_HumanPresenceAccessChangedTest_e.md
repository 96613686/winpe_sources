# tip2::tip_test<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>>::ensure_data(void)

- ea: `0x18000d550`
- end: `0x18000d5a9`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_HumanPresenceAccessChangedTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_HumanPresenceAccessChangedTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `89`
- prototype: `void **__fastcall(void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b5bc`
- `0x18000b6f0`

## callees

- `0x180009bb4`
- `0x18000adc4`
- `0x18000b220`
- `0x18000c8bc`
- `0x18000d550`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d564`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d564`

## pseudocode

```c
void **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>>::ensure_data(
        void **a1)
{
  LPVOID v2; // rax
  wil::details::in1diag3 *v3; // rcx
  __int64 v4; // rax
  void *v5; // rcx
  void *v7; // [rsp+30h] [rbp+8h] BYREF

  if ( !*a1 )
  {
    v2 = CoTaskMemAlloc(0x130u);
    if ( !v2 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
    v4 = tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>((__int64)v2);
    v5 = *a1;
    v7 = 0;
    *a1 = (void *)v4;
    if ( v5 )
      tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>::Release(v5);
    wil::com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>,wil::err_returncode_policy>(&v7);
  }
  return a1;
}

```

## disassembly

```asm
0x18000d550  push    rbx
0x18000d552  sub     rsp, 20h
0x18000d556  cmp     qword ptr [rcx], 0
0x18000d55a  mov     rbx, rcx
0x18000d55d  jnz     short loc_18000D5A0
0x18000d55f  mov     ecx, 130h; cb
0x18000d564  call    cs:__imp_CoTaskMemAlloc
0x18000d56a  test    rax, rax
0x18000d56d  jnz     short loc_18000D575
0x18000d56f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000d575  mov     rcx, rax
0x18000d578  call    ??0?$merged_data@U_tip_HumanPresenceAccessChangedTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>(void)
0x18000d57d  mov     rcx, [rbx]; pv
0x18000d580  mov     [rsp+28h+arg_0], 0
0x18000d589  mov     [rbx], rax
0x18000d58c  test    rcx, rcx
0x18000d58f  jz      short loc_18000D596
0x18000d591  call    ?Release@?$merged_data@U_tip_HumanPresenceAccessChangedTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>::Release(void)
0x18000d596  lea     rcx, [rsp+28h+arg_0]
0x18000d59b  call    ??1?$com_ptr_t@V?$merged_data@U_tip_HumanPresenceAccessChangedTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>,wil::err_returncode_policy>(void)
0x18000d5a0  mov     rax, rbx
0x18000d5a3  add     rsp, 20h
0x18000d5a7  pop     rbx
0x18000d5a8  retn
```
