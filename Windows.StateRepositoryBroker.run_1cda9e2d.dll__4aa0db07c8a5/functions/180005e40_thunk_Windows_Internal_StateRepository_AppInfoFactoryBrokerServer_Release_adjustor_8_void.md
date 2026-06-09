# [thunk]:Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::Release`adjustor{8}' (void)

- ea: `0x180005e40`
- end: `0x180005e49`
- name: `?Release@AppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005e30`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::Release(
        __int64 a1,
        volatile int *a2)
{
  return Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::Release(a1 - 8, a2);
}

```

## disassembly

```asm
0x180005e40  sub     rcx, 8; this
0x180005e44  jmp     ?Release@AppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@UEAAKXZ; Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::Release(void)
```
