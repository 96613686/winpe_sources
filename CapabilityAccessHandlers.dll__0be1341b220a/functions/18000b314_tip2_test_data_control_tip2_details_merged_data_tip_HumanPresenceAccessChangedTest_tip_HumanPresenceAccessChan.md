# tip2::test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>>::~test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>>(void)

- ea: `0x18000b314`
- end: `0x18000b343`
- name: `??1?$test_data_control@V?$merged_data@U_tip_HumanPresenceAccessChangedTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `47`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000b6f0`

## callees

- `0x18000b220`
- `0x18000b314`
- `0x18000d3ec`
- `0x18000e2d4`

## pseudocode

```c
__int64 __fastcall tip2::test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>>::~test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>>(
        void **a1)
{
  char *v2; // rcx

  v2 = (char *)*a1;
  if ( v2 )
  {
    tip2::details::shared_data<0,0,0>::end_update(v2 + 8);
    wil::com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>,wil::err_returncode_policy>::reset(a1);
  }
  return wil::com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>,wil::err_returncode_policy>(a1);
}

```

## disassembly

```asm
0x18000b314  push    rbx
0x18000b316  sub     rsp, 20h
0x18000b31a  mov     rbx, rcx
0x18000b31d  mov     rcx, [rcx]
0x18000b320  test    rcx, rcx
0x18000b323  jz      short loc_18000B336
0x18000b325  add     rcx, 8
0x18000b329  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x18000b32e  mov     rcx, rbx
0x18000b331  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_HumanPresenceAccessChangedTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>,wil::err_returncode_policy>::reset(void)
0x18000b336  mov     rcx, rbx
0x18000b339  add     rsp, 20h
0x18000b33d  pop     rbx
0x18000b33e  jmp     ??1?$com_ptr_t@V?$merged_data@U_tip_HumanPresenceAccessChangedTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>,wil::err_returncode_policy>(void)
```
