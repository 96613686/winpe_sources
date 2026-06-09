# [thunk]:Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180005ac0`
- end: `0x180005ac9`
- name: `?QueryInterface@AppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005a20`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::QueryInterface(
        __int64 a1,
        const struct _GUID *a2,
        void **a3)
{
  return Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::QueryInterface(
           (Windows::Internal::StateRepository::AppInfoFactoryBrokerServer *)(a1 - 8),
           a2,
           a3);
}

```

## disassembly

```asm
0x180005ac0  sub     rcx, 8; this
0x180005ac4  jmp     ?QueryInterface@AppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@UEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::QueryInterface(_GUID const &,void * *)
```
