# ?_Delete_this@?$_Ref_count_obj2@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@std@@EEAAXXZ

- ea: `0x18000a300`
- end: `0x18000a31f`
- name: `?_Delete_this@?$_Ref_count_obj2@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@std@@EEAAXXZ`
- size: `31`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000a300`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall __Delete_this____Ref_count_obj2_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___std__EEAAXXZ(
        __int64 a1)
{
  __int64 result; // rax

  if ( a1 )
    return (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 16LL))(a1, 1);
  return result;
}

```

## disassembly

```asm
0x18000a300  sub     rsp, 28h
0x18000a304  test    rcx, rcx
0x18000a307  jz      short loc_18000A31A
0x18000a309  mov     rax, [rcx]
0x18000a30c  mov     edx, 1
0x18000a311  mov     rax, [rax+10h]
0x18000a315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a31a  add     rsp, 28h
0x18000a31e  retn
```
