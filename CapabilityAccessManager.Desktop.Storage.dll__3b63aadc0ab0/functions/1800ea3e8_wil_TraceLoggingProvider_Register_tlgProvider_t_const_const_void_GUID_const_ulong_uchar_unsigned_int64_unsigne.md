# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x1800ea3e8`
- end: `0x1800ea4a6`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `190`
- prototype: `void(wil::TraceLoggingProvider *__hidden this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800e8a1c`
- `0x1800fb134`

## callees

- `0x180003060`
- `0x1800ea3e8`
- `0x18010d010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800ea46d`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800ea46d`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800ea455`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800ea455`

## pseudocode

```c

```
