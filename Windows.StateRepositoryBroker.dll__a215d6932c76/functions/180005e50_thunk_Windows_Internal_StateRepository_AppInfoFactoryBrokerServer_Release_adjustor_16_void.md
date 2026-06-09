# [thunk]:Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::Release`adjustor{16}' (void)

- ea: `0x180005e50`
- end: `0x180005e59`
- name: `?Release@AppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@WBA@EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64, volatile int *)`
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
  return Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::Release(a1 - 16, a2);
}

```

## disassembly

```asm
0x180005e50  sub     rcx, 10h; this
0x180005e54  jmp     ?Release@AppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@UEAAKXZ; Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::Release(void)
```
