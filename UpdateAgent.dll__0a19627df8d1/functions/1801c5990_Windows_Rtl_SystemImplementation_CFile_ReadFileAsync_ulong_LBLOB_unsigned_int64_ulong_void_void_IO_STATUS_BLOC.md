# Windows::Rtl::SystemImplementation::CFile::ReadFileAsync(ulong,_LBLOB *,unsigned __int64 *,ulong,void (*)(void *,_IO_STATUS_BLOCK *,ulong),void *,_IO_STATUS_BLOCK *,ulong *)

- ea: `0x1801c5990`
- end: `0x1801c5fc0`
- name: `?ReadFileAsync@CFile@SystemImplementation@Rtl@Windows@@UEAAJKPEAU_LBLOB@@PEA_KKP6AXPEAXPEAU_IO_STATUS_BLOCK@@K@Z23PEAK@Z`
- size: `1584`
- prototype: `__int64 __fastcall(Windows::Rtl::SystemImplementation::CFile *__hidden this, unsigned int, struct _LBLOB *, unsigned __int64 *, unsigned int, void (*)(void *, struct _IO_STATUS_BLOCK *, unsigned int), void *, struct _IO_STATUS_BLOCK *, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callees

- `0x1800059d0`
- `0x1800692fc`
- `0x18017b760`
- `0x18017daf8`
- `0x1801c5990`
- `0x1801e4d48`
- `0x1801efdc0`
- `0x1802b1010`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x1801c5e3f`
- `ntdll!NtWaitForSingleObject` at `0x1801c5e3f`
- `ntdll!NtClose` at `0x1801c5bf5`
- `ntdll!NtClose` at `0x1801c5cb7`
- `ntdll!NtClose` at `0x1801c5d8c`
- `ntdll!NtClose` at `0x1801c5eb4`
- `ntdll!NtClose` at `0x1801c5f11`
- `ntdll!NtClose` at `0x1801c5bf5`
- `ntdll!NtClose` at `0x1801c5cb7`
- `ntdll!NtClose` at `0x1801c5d8c`
- `ntdll!NtClose` at `0x1801c5eb4`
- `ntdll!NtClose` at `0x1801c5f11`
- `ntdll!NtCreateEvent` at `0x1801c5ba0`
- `ntdll!NtCreateEvent` at `0x1801c5ba0`
- `ntdll!TpCancelAsyncIoOperation` at `0x1801c5d76`
- `ntdll!TpCancelAsyncIoOperation` at `0x1801c5e9e`
- `ntdll!TpCancelAsyncIoOperation` at `0x1801c5eed`
- `ntdll!TpCancelAsyncIoOperation` at `0x1801c5d76`
- `ntdll!TpCancelAsyncIoOperation` at `0x1801c5e9e`
- `ntdll!TpCancelAsyncIoOperation` at `0x1801c5eed`
- `ntdll!TpStartAsyncIoOperation` at `0x1801c5cea`
- `ntdll!TpStartAsyncIoOperation` at `0x1801c5cea`

## string_xrefs

- `0x1801c5a23`: `Windows::Rtl::SystemImplementation::CFile::ReadFileAsync`
- `0x1801c5c70`: `Windows::Rtl::SystemImplementation::CFile::ReadFileAsync`
- `0x1801c5e61`: `Windows::Rtl::SystemImplementation::CFile::ReadFileAsync`
- `0x1801c5bca`: `::NtCreateEvent( WaitEvent.GetInitPointer(), ((0x000F0000L)|(0x00100000L)|0x3), nullptr, NotificationEvent, 0 )`

## pseudocode

```c

```
