# Windows::Rtl::CRtlObjectTypeDescription<MicrodomImplementation::CMicrodom>::CreateInstance<MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff,MicrodomImplementation::MdCreateParams,Windows::Microdom::Rtl::IRtlMicrodom>(MicrodomImplementation::MdCreateParams const &,Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *> *)

- ea: `0x1400663c8`
- end: `0x1400666fb`
- name: `??$CreateInstance@VCMicrodom_IRtlMicrodomTearoff@MicrodomImplementation@@UMdCreateParams@2@UIRtlMicrodom@Rtl@Microdom@Windows@@@?$CRtlObjectTypeDescription@VCMicrodom@MicrodomImplementation@@@Rtl@Windows@@QEAAJAEBUMdCreateParams@MicrodomImplementation@@PEAV?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@2@@Z`
- size: `819`
- prototype: `NTSTATUS __fastcall(__int64, const struct MicrodomImplementation::MdCreateParams *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14006db80`

## callees

- `0x1400663c8`
- `0x140066b40`
- `0x14006ce64`
- `0x140072764`
- `0x140082010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x140066459`
- `KERNEL32!HeapAlloc` at `0x1400665de`
- `KERNEL32!HeapAlloc` at `0x140066459`
- `KERNEL32!HeapAlloc` at `0x1400665de`
- `KERNEL32!GetProcessHeap` at `0x140066442`
- `KERNEL32!GetProcessHeap` at `0x1400665c9`
- `KERNEL32!GetProcessHeap` at `0x140066442`
- `KERNEL32!GetProcessHeap` at `0x1400665c9`
- `ntdll!NtYieldExecution` at `0x140066427`
- `ntdll!NtYieldExecution` at `0x140066427`

## string_xrefs

- `0x14006666f`: `Windows::Rtl::CRtlObjectTypeDescription<class MicrodomImplementation::CMicrodom>::CreateInstance`
- `0x1400666bc`: `Windows::Rtl::CRtlObjectTypeDescription<class MicrodomImplementation::CMicrodom>::CreateInstance`

## pseudocode

```c

```
