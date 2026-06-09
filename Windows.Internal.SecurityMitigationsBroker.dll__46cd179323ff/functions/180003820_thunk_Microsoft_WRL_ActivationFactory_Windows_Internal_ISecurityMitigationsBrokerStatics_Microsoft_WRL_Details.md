# [thunk]:Microsoft::WRL::ActivationFactory<Windows::Internal::ISecurityMitigationsBrokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::AddRef`adjustor{8}' (void)

- ea: `0x180003820`
- end: `0x180003829`
- name: `?AddRef@?$ActivationFactory@UISecurityMitigationsBrokerStatics@Internal@Windows@@VNil@Details@WRL@Microsoft@@V4567@$0A@@WRL@Microsoft@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800037c0`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Windows::Internal::ISecurityMitigationsBrokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::AddRef(
        __int64 a1)
{
  return SecurityMitigationsBrokerStatics::AddRef((SecurityMitigationsBrokerStatics *)(a1 - 8));
}

```

## disassembly

```asm
0x180003820  sub     rcx, 8; this
0x180003824  jmp     ?AddRef@SecurityMitigationsBrokerStatics@@UEAAKXZ; SecurityMitigationsBrokerStatics::AddRef(void)
```
