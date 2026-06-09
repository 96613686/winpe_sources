# wil::com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>,wil::err_returncode_policy>::reset(void)

- ea: `0x18000e2d4`
- end: `0x18000e2f4`
- name: `?reset@?$com_ptr_t@V?$merged_data@U_tip_HumanPresenceAccessChangedTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ`
- size: `32`
- prototype: `volatile signed __int32 *__fastcall(volatile signed __int32 **)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b314`
- `0x18000b6f0`

## callees

- `0x18000c8bc`
- `0x18000e2d4`

## pseudocode

```c
volatile signed __int32 *__fastcall wil::com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>,wil::err_returncode_policy>::reset(
        volatile signed __int32 **a1)
{
  volatile signed __int32 *result; // rax

  result = *a1;
  *a1 = 0;
  if ( result )
    return (volatile signed __int32 *)tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>::Release(result);
  return result;
}

```

## disassembly

```asm
0x18000e2d4  sub     rsp, 28h
0x18000e2d8  mov     rax, [rcx]
0x18000e2db  mov     qword ptr [rcx], 0
0x18000e2e2  test    rax, rax
0x18000e2e5  jz      short loc_18000E2EF
0x18000e2e7  mov     rcx, rax; pv
0x18000e2ea  call    ?Release@?$merged_data@U_tip_HumanPresenceAccessChangedTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>::Release(void)
0x18000e2ef  add     rsp, 28h
0x18000e2f3  retn
```
