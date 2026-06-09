# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x18001193c`
- end: `0x1800119fa`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `190`
- prototype: `void(wil::TraceLoggingProvider *__hidden this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800117d8`
- `0x180058798`

## callees

- `0x180005020`
- `0x18001193c`
- `0x18005e010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800119c1`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800119c1`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800119a9`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800119a9`

## pseudocode

```c

```
