# wil::com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>,wil::err_returncode_policy>::reset(void)

- ea: `0x18000e2fc`
- end: `0x18000e31c`
- name: `?reset@?$com_ptr_t@V?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ`
- size: `32`
- prototype: `volatile signed __int32 *__fastcall(volatile signed __int32 **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000b820`
- `0x18000d148`

## callees

- `0x18000c8fc`
- `0x18000e2fc`

## pseudocode

```c
volatile signed __int32 *__fastcall wil::com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>,wil::err_returncode_policy>::reset(
        volatile signed __int32 **a1)
{
  volatile signed __int32 *result; // rax

  result = *a1;
  *a1 = 0;
  if ( result )
    return (volatile signed __int32 *)tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>::Release(result);
  return result;
}

```

## disassembly

```asm
0x18000e2fc  sub     rsp, 28h
0x18000e300  mov     rax, [rcx]
0x18000e303  mov     qword ptr [rcx], 0
0x18000e30a  test    rax, rax
0x18000e30d  jz      short loc_18000E317
0x18000e30f  mov     rcx, rax; pv
0x18000e312  call    ?Release@?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>::Release(void)
0x18000e317  add     rsp, 28h
0x18000e31b  retn
```
