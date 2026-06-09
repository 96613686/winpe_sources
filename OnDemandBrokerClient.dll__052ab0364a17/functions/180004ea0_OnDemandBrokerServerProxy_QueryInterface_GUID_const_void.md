# OnDemandBrokerServerProxy::QueryInterface(_GUID const &,void * *)

- ea: `0x180004ea0`
- end: `0x180004ea6`
- name: `?QueryInterface@OnDemandBrokerServerProxy@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `6`
- prototype: `__int64 __fastcall(OnDemandBrokerServerProxy *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerServerProxy::QueryInterface(
        OnDemandBrokerServerProxy *this,
        const struct _GUID *a2,
        void **a3)
{
  return 2147500033LL;
}

```

## disassembly

```asm
0x180004ea0  mov     eax, 80004001h
0x180004ea5  retn
```
