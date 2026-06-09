# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x180035c58`
- end: `0x180035d16`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `190`
- prototype: `void(wil::TraceLoggingProvider *__hidden this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a2ac`
- `0x18000b514`
- `0x18003e044`

## callees

- `0x180035c58`
- `0x180056500`
- `0x18005c5e0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180035cc5`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180035cc5`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180035cdd`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180035cdd`

## pseudocode

```c

```
