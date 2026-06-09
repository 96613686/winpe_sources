# Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::InternalGetTrustLevel(void)

- ea: `0x180005390`
- end: `0x180005396`
- name: `?InternalGetTrustLevel@AppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@SA?AW4TrustLevel@@XZ`
- size: `6`
- prototype: `enum TrustLevel(void)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001de8`

## pseudocode

```c
__int64 Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::InternalGetTrustLevel(void)
{
  return 1;
}

```

## disassembly

```asm
0x180005390  mov     eax, 1
0x180005395  retn
```
