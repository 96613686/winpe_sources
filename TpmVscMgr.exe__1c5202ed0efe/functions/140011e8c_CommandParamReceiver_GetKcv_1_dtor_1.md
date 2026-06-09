# _CommandParamReceiver::GetKcv_::_1_::dtor$1

- ea: `0x140011e8c`
- end: `0x140011e98`
- name: `_CommandParamReceiver::GetKcv_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400084dc`

## pseudocode

```c
__int64 __fastcall CommandParamReceiver::GetKcv_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return __1__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil__QEAA_XZ(a2 + 96);
}

```

## disassembly

```asm
0x140011e8c  lea     rcx, [rdx+60h]
0x140011e93  jmp     ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ
```
