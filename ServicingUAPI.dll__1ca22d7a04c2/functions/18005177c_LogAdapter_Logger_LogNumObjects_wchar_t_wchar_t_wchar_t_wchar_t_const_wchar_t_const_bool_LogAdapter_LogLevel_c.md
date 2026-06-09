# LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *,wchar_t *,wchar_t const *,wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t * const &,wchar_t * const &,wchar_t * const &,wchar_t const * const &,wchar_t const * const &)

- ea: `0x18005177c`
- end: `0x18005197b`
- name: `??$LogNumObjects@PEA_WPEA_WPEA_WPEB_WPEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEA_W33AEBQEB_W4@Z`
- size: `511`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, __int64, struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180053860`
- `0x1800c3294`

## callees

- `0x1800309a4`
- `0x1800497c0`
- `0x18005060c`
- `0x18005177c`
- `0x1801bd010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180051838`
- `ntdll!RtlLeaveCriticalSection` at `0x18005187c`
- `ntdll!RtlLeaveCriticalSection` at `0x180051945`
- `ntdll!RtlLeaveCriticalSection` at `0x180051838`
- `ntdll!RtlLeaveCriticalSection` at `0x18005187c`
- `ntdll!RtlLeaveCriticalSection` at `0x180051945`
- `ntdll!RtlEnterCriticalSection` at `0x1800517ce`
- `ntdll!RtlEnterCriticalSection` at `0x1800517ce`
- `ntdll!RtlRaiseStatus` at `0x18005184a`
- `ntdll!RtlRaiseStatus` at `0x18005188e`
- `ntdll!RtlRaiseStatus` at `0x180051957`
- `ntdll!RtlRaiseStatus` at `0x18005184a`
- `ntdll!RtlRaiseStatus` at `0x18005188e`
- `ntdll!RtlRaiseStatus` at `0x180051957`

## string_xrefs

- `0x18005191a`: `We can only update the same product once per operation. CompDBs specified updating product at least twice: {0} with versions {1} and {2} and types {3} and {4}`

## pseudocode

```c

```
