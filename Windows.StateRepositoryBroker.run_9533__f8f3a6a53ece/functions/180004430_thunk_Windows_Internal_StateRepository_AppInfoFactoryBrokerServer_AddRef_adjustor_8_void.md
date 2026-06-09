# [thunk]:Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::AddRef`adjustor{8}' (void)

- ea: `0x180004430`
- end: `0x180004439`
- name: `?AddRef@AppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800043e0`

## pseudocode

```c
unsigned int __fastcall Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::AddRef(__int64 a1)
{
  return Windows::Internal::StateRepository::ApplicationResourceResolverServer::AddRef((Windows::Internal::StateRepository::ApplicationResourceResolverServer *)(a1 - 8));
}

```

## disassembly

```asm
0x180004430  sub     rcx, 8; this
0x180004434  jmp     ?AddRef@ApplicationResourceResolverServer@StateRepository@Internal@Windows@@UEAAKXZ; Windows::Internal::StateRepository::ApplicationResourceResolverServer::AddRef(void)
```
