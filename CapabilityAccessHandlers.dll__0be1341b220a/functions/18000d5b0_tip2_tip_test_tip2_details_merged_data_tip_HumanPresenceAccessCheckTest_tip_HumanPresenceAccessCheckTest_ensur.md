# tip2::tip_test<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>::ensure_data(void)

- ea: `0x18000d5b0`
- end: `0x18000d609`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `89`
- prototype: `void **__fastcall(void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000b820`

## callees

- `0x180009bb4`
- `0x18000ae74`
- `0x18000b23c`
- `0x18000c8fc`
- `0x18000d5b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d5c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d5c4`

## pseudocode

```c
void **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>::ensure_data(
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
    v4 = tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>((__int64)v2);
    v5 = *a1;
    v7 = 0;
    *a1 = (void *)v4;
    if ( v5 )
      tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>::Release(v5);
    wil::com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>,wil::err_returncode_policy>(&v7);
  }
  return a1;
}

```

## disassembly

```asm
0x18000d5b0  push    rbx
0x18000d5b2  sub     rsp, 20h
0x18000d5b6  cmp     qword ptr [rcx], 0
0x18000d5ba  mov     rbx, rcx
0x18000d5bd  jnz     short loc_18000D600
0x18000d5bf  mov     ecx, 130h; cb
0x18000d5c4  call    cs:__imp_CoTaskMemAlloc
0x18000d5ca  test    rax, rax
0x18000d5cd  jnz     short loc_18000D5D5
0x18000d5cf  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000d5d5  mov     rcx, rax
0x18000d5d8  call    ??0?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>(void)
0x18000d5dd  mov     rcx, [rbx]; pv
0x18000d5e0  mov     [rsp+28h+arg_0], 0
0x18000d5e9  mov     [rbx], rax
0x18000d5ec  test    rcx, rcx
0x18000d5ef  jz      short loc_18000D5F6
0x18000d5f1  call    ?Release@?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>::Release(void)
0x18000d5f6  lea     rcx, [rsp+28h+arg_0]
0x18000d5fb  call    ??1?$com_ptr_t@V?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>,wil::err_returncode_policy>(void)
0x18000d600  mov     rax, rbx
0x18000d603  add     rsp, 20h
0x18000d607  pop     rbx
0x18000d608  retn
```
