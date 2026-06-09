# [thunk]:OnDemandBrokerClient::AddRef`adjustor{8}' (void)

- ea: `0x180005210`
- end: `0x180005219`
- name: `?AddRef@OnDemandBrokerClient@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004170`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerClient::AddRef(__int64 a1)
{
  return OnDemandBrokerClient::AddRef((OnDemandBrokerClient *)(a1 - 8));
}

```

## disassembly

```asm
0x180005210  sub     rcx, 8; this
0x180005214  jmp     ?AddRef@OnDemandBrokerClient@@UEAAKXZ; OnDemandBrokerClient::AddRef(void)
```
