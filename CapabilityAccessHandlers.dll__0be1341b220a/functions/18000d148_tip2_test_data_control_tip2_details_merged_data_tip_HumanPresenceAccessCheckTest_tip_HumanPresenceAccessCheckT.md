# tip2::test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>::close(void)

- ea: `0x18000d148`
- end: `0x18000d170`
- name: `?close@?$test_data_control@V?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@@tip2@@QEAAXXZ`
- size: `40`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000b34c`
- `0x18000b820`

## callees

- `0x18000d148`
- `0x18000d3ec`
- `0x18000e2fc`

## pseudocode

```c
__int64 __fastcall tip2::test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>::close(
        __int64 *a1)
{
  __int64 v2; // rcx
  __int64 result; // rax

  v2 = *a1;
  if ( v2 )
  {
    tip2::details::shared_data<0,0,0>::end_update(v2 + 8);
    return wil::com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>,wil::err_returncode_policy>::reset(a1);
  }
  return result;
}

```

## disassembly

```asm
0x18000d148  push    rbx
0x18000d14a  sub     rsp, 20h
0x18000d14e  mov     rbx, rcx
0x18000d151  mov     rcx, [rcx]
0x18000d154  test    rcx, rcx
0x18000d157  jz      short loc_18000D16A
0x18000d159  add     rcx, 8
0x18000d15d  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x18000d162  mov     rcx, rbx
0x18000d165  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>,wil::err_returncode_policy>::reset(void)
0x18000d16a  add     rsp, 20h
0x18000d16e  pop     rbx
0x18000d16f  retn
```
