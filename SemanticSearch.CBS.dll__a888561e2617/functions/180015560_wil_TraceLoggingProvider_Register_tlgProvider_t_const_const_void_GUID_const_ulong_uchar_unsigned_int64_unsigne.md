# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x180015560`
- end: `0x180015619`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `185`
- prototype: `void(wil::TraceLoggingProvider *__hidden this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180015090`
- `0x180015a70`

## callees

- `0x180015560`
- `0x18004c070`
- `0x18005e260`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800155df`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800155df`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800155c4`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800155c4`

## pseudocode

```c

```
