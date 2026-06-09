# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x140009e74`
- end: `0x140009f32`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `190`
- prototype: `void(wil::TraceLoggingProvider *__hidden this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000984c`
- `0x140046fc4`

## callees

- `0x1400054c0`
- `0x140009e74`
- `0x14005a010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x140009ee1`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x140009ee1`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x140009ef9`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x140009ef9`

## pseudocode

```c

```
