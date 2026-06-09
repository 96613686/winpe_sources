# tip2::test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>::test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>,wil::err_returncode_policy> const &)

- ea: `0x18000afe0`
- end: `0x18000b010`
- name: `??0?$test_data_control@V?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z`
- size: `48`
- prototype: `__int64 *__fastcall(__int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000b820`

## callees

- `0x18000afe0`
- `0x18000d114`

## pseudocode

```c
__int64 *__fastcall tip2::test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>::test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>(
        __int64 *a1,
        __int64 *a2)
{
  __int64 v2; // rax

  v2 = *a2;
  *a1 = *a2;
  if ( v2 )
    _InterlockedIncrement((volatile signed __int32 *)(v2 + 296));
  tip2::details::shared_data<0,0,0>::begin_update(*a1 + 8);
  return a1;
}

```

## disassembly

```asm
0x18000afe0  push    rbx
0x18000afe2  sub     rsp, 20h
0x18000afe6  mov     rax, [rdx]
0x18000afe9  mov     rbx, rcx
0x18000afec  mov     [rcx], rax
0x18000afef  test    rax, rax
0x18000aff2  jz      short loc_18000AFFB
0x18000aff4  lock inc dword ptr [rax+128h]
0x18000affb  mov     rcx, [rcx]
0x18000affe  add     rcx, 8
0x18000b002  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x18000b007  mov     rax, rbx
0x18000b00a  add     rsp, 20h
0x18000b00e  pop     rbx
0x18000b00f  retn
```
