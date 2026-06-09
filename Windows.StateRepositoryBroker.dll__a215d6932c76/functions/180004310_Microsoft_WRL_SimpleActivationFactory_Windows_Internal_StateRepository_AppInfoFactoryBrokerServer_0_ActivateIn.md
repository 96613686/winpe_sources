# Microsoft::WRL::SimpleActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0>::ActivateInstance(IInspectable * *)

- ea: `0x180004310`
- end: `0x180004318`
- name: `?ActivateInstance@?$SimpleActivationFactory@VAppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@$0A@@WRL@Microsoft@@UEAAJPEAPEAUIInspectable@@@Z`
- size: `8`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800032fc`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0>::ActivateInstance(
        __int64 a1,
        _QWORD *a2)
{
  return Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,IInspectable,>(a2);
}

```

## disassembly

```asm
0x180004310  mov     rcx, rdx
0x180004313  jmp     ??$MakeAndInitialize@VAppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@UIInspectable@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIInspectable@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,IInspectable,>(IInspectable * *)
```
