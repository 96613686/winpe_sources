# Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::GetTrustLevel(TrustLevel *)

- ea: `0x180005020`
- end: `0x180005029`
- name: `?GetTrustLevel@AppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@UEAAJPEAW4TrustLevel@@@Z`
- size: `9`
- prototype: `__int64 __fastcall(Windows::Internal::StateRepository::AppInfoFactoryBrokerServer *__hidden this, enum TrustLevel *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::GetTrustLevel(
        Windows::Internal::StateRepository::AppInfoFactoryBrokerServer *this,
        enum TrustLevel *a2)
{
  *a2 = PartialTrust;
  return 0;
}

```

## disassembly

```asm
0x180005020  mov     dword ptr [rdx], 1
0x180005026  xor     eax, eax
0x180005028  retn
```
