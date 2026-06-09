# [thunk]:OnDemandBrokerClient::QueryInterface`adjustor{16}' (_GUID const &,void * *)

- ea: `0x180005f50`
- end: `0x180005f59`
- name: `?QueryInterface@OnDemandBrokerClient@@WBA@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004200`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerClient::QueryInterface(__int64 a1, const struct _GUID *a2, void **a3)
{
  return OnDemandBrokerClient::QueryInterface((OnDemandBrokerClient *)(a1 - 16), a2, a3);
}

```

## disassembly

```asm
0x180005f50  sub     rcx, 10h; this
0x180005f54  jmp     ?QueryInterface@OnDemandBrokerClient@@UEAAJAEBU_GUID@@PEAPEAX@Z; OnDemandBrokerClient::QueryInterface(_GUID const &,void * *)
```
