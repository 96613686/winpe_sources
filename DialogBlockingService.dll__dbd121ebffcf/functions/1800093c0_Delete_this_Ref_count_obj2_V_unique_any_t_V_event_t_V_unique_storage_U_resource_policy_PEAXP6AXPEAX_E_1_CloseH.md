# ?_Delete_this@?$_Ref_count_obj2@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@std@@EEAAXXZ

- ea: `0x1800093c0`
- end: `0x1800093df`
- name: `?_Delete_this@?$_Ref_count_obj2@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@std@@EEAAXXZ`
- size: `31`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1800093c0`
- `0x18000e010`

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
0x1800093c0  sub     rsp, 28h
0x1800093c4  test    rcx, rcx
0x1800093c7  jz      short loc_1800093DA
0x1800093c9  mov     rax, [rcx]
0x1800093cc  mov     edx, 1
0x1800093d1  mov     rax, [rax+10h]
0x1800093d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093da  add     rsp, 28h
0x1800093de  retn
```
