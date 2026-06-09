# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x180009eb8`
- end: `0x180009f76`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `190`
- prototype: `void(wil::TraceLoggingProvider *__hidden this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000896c`
- `0x18002fa0c`

## callees

- `0x180002590`
- `0x180009eb8`
- `0x180033010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180009f3d`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180009f3d`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180009f25`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180009f25`

## pseudocode

```c

```
