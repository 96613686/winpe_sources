# [thunk]:Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IAppInfoFactoryBroker,Microsoft::WRL::FtmBase>::Release`adjustor{8}' (void)

- ea: `0x180005d50`
- end: `0x180005d59`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIAppInfoFactoryBroker@StateRepository@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005cd0`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IAppInfoFactoryBroker,Microsoft::WRL::FtmBase>::Release(
        __int64 a1,
        volatile int *a2)
{
  return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IAppInfoFactoryBroker,Microsoft::WRL::FtmBase>::Release(
           a1 - 8,
           a2);
}

```

## disassembly

```asm
0x180005d50  sub     rcx, 8
0x180005d54  jmp     ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIAppInfoFactoryBroker@StateRepository@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IAppInfoFactoryBroker,Microsoft::WRL::FtmBase>::Release(void)
```
