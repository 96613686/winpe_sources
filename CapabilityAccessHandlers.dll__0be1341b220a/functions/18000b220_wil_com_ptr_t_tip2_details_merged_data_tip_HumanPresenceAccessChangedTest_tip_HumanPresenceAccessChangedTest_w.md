# wil::com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>,wil::err_returncode_policy>(void)

- ea: `0x18000b220`
- end: `0x18000b236`
- name: `??1?$com_ptr_t@V?$merged_data@U_tip_HumanPresenceAccessChangedTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `22`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b314`
- `0x18000b6f0`
- `0x18000d550`

## callees

- `0x18000b220`
- `0x18000c8bc`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>,wil::err_returncode_policy>(
        void **a1)
{
  void *v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>::Release(v1);
  return result;
}

```

## disassembly

```asm
0x18000b220  sub     rsp, 28h
0x18000b224  mov     rcx, [rcx]; pv
0x18000b227  test    rcx, rcx
0x18000b22a  jz      short loc_18000B231
0x18000b22c  call    ?Release@?$merged_data@U_tip_HumanPresenceAccessChangedTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>::Release(void)
0x18000b231  add     rsp, 28h
0x18000b235  retn
```
