# tip2::test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>::~test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>(void)

- ea: `0x18000b34c`
- end: `0x18000b367`
- name: `??1?$test_data_control@V?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `27`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000b820`

## callees

- `0x18000b23c`
- `0x18000d148`

## pseudocode

```c
__int64 __fastcall tip2::test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>::~test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>(
        void **a1)
{
  tip2::test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>::close();
  return wil::com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>,wil::err_returncode_policy>(a1);
}

```

## disassembly

```asm
0x18000b34c  push    rbx
0x18000b34e  sub     rsp, 20h
0x18000b352  mov     rbx, rcx
0x18000b355  call    ?close@?$test_data_control@V?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@@tip2@@QEAAXXZ
0x18000b35a  mov     rcx, rbx
0x18000b35d  add     rsp, 20h
0x18000b361  pop     rbx
0x18000b362  jmp     ??1?$com_ptr_t@V?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ
```
