# [thunk]:OnDemandBrokerClient::AddRef`adjustor{16}' (void)

- ea: `0x180005220`
- end: `0x180005229`
- name: `?AddRef@OnDemandBrokerClient@@WBA@EAAKXZ`
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
  return OnDemandBrokerClient::AddRef((OnDemandBrokerClient *)(a1 - 16));
}

```

## disassembly

```asm
0x180005220  sub     rcx, 10h; this
0x180005224  jmp     ?AddRef@OnDemandBrokerClient@@UEAAKXZ; OnDemandBrokerClient::AddRef(void)
```
