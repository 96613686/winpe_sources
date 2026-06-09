# [thunk]:OnDemandBrokerClient::Release`adjustor{16}' (void)

- ea: `0x1800060b0`
- end: `0x1800060b9`
- name: `?Release@OnDemandBrokerClient@@WBA@EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001b20`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerClient::Release(__int64 a1)
{
  return OnDemandBrokerClient::Release((OnDemandBrokerClient *)(a1 - 16));
}

```

## disassembly

```asm
0x1800060b0  sub     rcx, 10h; this
0x1800060b4  jmp     ?Release@OnDemandBrokerClient@@UEAAKXZ; OnDemandBrokerClient::Release(void)
```
