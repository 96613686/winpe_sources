# Windows::Rtl::SystemImplementation::CRtlTransactionCoordinator::SetCurrentThreadTransaction(Windows::Rtl::KtmTransactionInfo *)

- ea: `0x180152860`
- end: `0x1801529d9`
- name: `?SetCurrentThreadTransaction@CRtlTransactionCoordinator@SystemImplementation@Rtl@Windows@@UEAAJPEAUKtmTransactionInfo@34@@Z`
- size: `377`
- prototype: `__int64 __fastcall(Windows::Rtl::SystemImplementation::CRtlTransactionCoordinator *__hidden this, struct Windows::Rtl::KtmTransactionInfo *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180006198`
- `0x1800062b8`
- `0x180152860`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18015295a`
- `ntdll!RtlLeaveCriticalSection` at `0x180152978`
- `ntdll!RtlLeaveCriticalSection` at `0x1801529a2`
- `ntdll!RtlLeaveCriticalSection` at `0x18015295a`
- `ntdll!RtlLeaveCriticalSection` at `0x180152978`
- `ntdll!RtlLeaveCriticalSection` at `0x1801529a2`
- `ntdll!RtlEnterCriticalSection` at `0x180152896`
- `ntdll!RtlEnterCriticalSection` at `0x180152896`
- `ntdll!RtlRaiseStatus` at `0x18015298a`
- `ntdll!RtlRaiseStatus` at `0x1801529b4`
- `ntdll!RtlRaiseStatus` at `0x18015298a`
- `ntdll!RtlRaiseStatus` at `0x1801529b4`

## pseudocode

```c

```
