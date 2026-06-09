# Windows::Rtl::SystemImplementation::CRtlTransactionCoordinator::GetCurrentThreadTransactionInfo(Windows::Rtl::KtmTransactionInfo * *)

- ea: `0x180152510`
- end: `0x180152692`
- name: `?GetCurrentThreadTransactionInfo@CRtlTransactionCoordinator@SystemImplementation@Rtl@Windows@@UEAAJPEAPEAUKtmTransactionInfo@34@@Z`
- size: `386`
- prototype: `__int64 __fastcall(Windows::Rtl::SystemImplementation::CRtlTransactionCoordinator *__hidden this, struct Windows::Rtl::KtmTransactionInfo **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800497c0`
- `0x180152510`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180152576`
- `ntdll!RtlLeaveCriticalSection` at `0x1801525c5`
- `ntdll!RtlLeaveCriticalSection` at `0x1801525e3`
- `ntdll!RtlLeaveCriticalSection` at `0x180152610`
- `ntdll!RtlLeaveCriticalSection` at `0x180152576`
- `ntdll!RtlLeaveCriticalSection` at `0x1801525c5`
- `ntdll!RtlLeaveCriticalSection` at `0x1801525e3`
- `ntdll!RtlLeaveCriticalSection` at `0x180152610`
- `ntdll!RtlEnterCriticalSection` at `0x180152555`
- `ntdll!RtlEnterCriticalSection` at `0x180152555`
- `ntdll!RtlRaiseStatus` at `0x180152588`
- `ntdll!RtlRaiseStatus` at `0x1801525f5`
- `ntdll!RtlRaiseStatus` at `0x180152622`
- `ntdll!RtlRaiseStatus` at `0x180152588`
- `ntdll!RtlRaiseStatus` at `0x1801525f5`
- `ntdll!RtlRaiseStatus` at `0x180152622`

## string_xrefs

- `0x18015263f`: `Windows::Rtl::SystemImplementation::CRtlTransactionCoordinator::GetCurrentThreadTransactionInfo`

## pseudocode

```c

```
