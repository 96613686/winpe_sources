# Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::Release(void)

- ea: `0x180005e30`
- end: `0x180005e35`
- name: `?Release@AppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@UEAAKXZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64 this, volatile int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005e40`
- `0x180005e50`

## callees

- `0x180005cd0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::Release(
        __int64 this,
        volatile int *a2)
{
  return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IAppInfoFactoryBroker,Microsoft::WRL::FtmBase>::Release(
           this,
           a2);
}

```

## disassembly

```asm
0x180005e30  jmp     ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIAppInfoFactoryBroker@StateRepository@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IAppInfoFactoryBroker,Microsoft::WRL::FtmBase>::Release(void)
```
