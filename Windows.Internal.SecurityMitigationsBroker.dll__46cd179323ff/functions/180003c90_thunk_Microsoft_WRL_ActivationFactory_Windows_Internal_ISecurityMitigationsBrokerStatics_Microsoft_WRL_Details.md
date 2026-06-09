# [thunk]:Microsoft::WRL::ActivationFactory<Windows::Internal::ISecurityMitigationsBrokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetRuntimeClassName`adjustor{8}' (HSTRING__ * *)

- ea: `0x180003c90`
- end: `0x180003c99`
- name: `?GetRuntimeClassName@?$ActivationFactory@UISecurityMitigationsBrokerStatics@Internal@Windows@@VNil@Details@WRL@Microsoft@@V4567@$0A@@WRL@Microsoft@@W7EAAJPEAPEAUHSTRING__@@@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003c60`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Windows::Internal::ISecurityMitigationsBrokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetRuntimeClassName(
        __int64 a1,
        _QWORD *a2)
{
  return Microsoft::WRL::ActivationFactory<Windows::Internal::ISecurityMitigationsBrokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetRuntimeClassName(
           a1 - 8,
           a2);
}

```

## disassembly

```asm
0x180003c90  sub     rcx, 8
0x180003c94  jmp     ?GetRuntimeClassName@?$ActivationFactory@UISecurityMitigationsBrokerStatics@Internal@Windows@@VNil@Details@WRL@Microsoft@@V4567@$0A@@WRL@Microsoft@@UEAAJPEAPEAUHSTRING__@@@Z; Microsoft::WRL::ActivationFactory<Windows::Internal::ISecurityMitigationsBrokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetRuntimeClassName(HSTRING__ * *)
```
