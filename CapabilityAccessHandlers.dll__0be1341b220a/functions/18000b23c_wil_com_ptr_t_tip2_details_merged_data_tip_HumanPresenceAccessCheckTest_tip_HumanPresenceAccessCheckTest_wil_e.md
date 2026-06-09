# wil::com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>,wil::err_returncode_policy>(void)

- ea: `0x18000b23c`
- end: `0x18000b252`
- name: `??1?$com_ptr_t@V?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `22`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000b34c`
- `0x18000b820`
- `0x18000d5b0`

## callees

- `0x18000b23c`
- `0x18000c8fc`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>,wil::err_returncode_policy>(
        void **a1)
{
  void *v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>::Release(v1);
  return result;
}

```

## disassembly

```asm
0x18000b23c  sub     rsp, 28h
0x18000b240  mov     rcx, [rcx]; pv
0x18000b243  test    rcx, rcx
0x18000b246  jz      short loc_18000B24D
0x18000b248  call    ?Release@?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>::Release(void)
0x18000b24d  add     rsp, 28h
0x18000b251  retn
```
