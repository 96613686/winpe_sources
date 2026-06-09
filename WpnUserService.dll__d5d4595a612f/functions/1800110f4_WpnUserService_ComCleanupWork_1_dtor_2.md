# _WpnUserService::_ComCleanupWork_::_1_::dtor$2

- ea: `0x1800110f4`
- end: `0x180011100`
- name: `_WpnUserService::_ComCleanupWork_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800081d8`

## pseudocode

```c
__int64 __fastcall WpnUserService::_ComCleanupWork_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return __1__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(a2 + 168);
}

```

## disassembly

```asm
0x1800110f4  lea     rcx, [rdx+0A8h]
0x1800110fb  jmp     ??1?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAA@XZ
```
