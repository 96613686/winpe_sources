# Windows::Rtl::SystemImplementation::CFile::WriteFileAsync(ulong,_LBLOB const &,unsigned __int64 *,void (*)(void *,_IO_STATUS_BLOCK *,ulong),void *,_IO_STATUS_BLOCK *,ulong *)

- ea: `0x1801c72d0`
- end: `0x1801c791e`
- name: `?WriteFileAsync@CFile@SystemImplementation@Rtl@Windows@@UEAAJKAEBU_LBLOB@@PEA_KP6AXPEAXPEAU_IO_STATUS_BLOCK@@K@Z23PEAK@Z`
- size: `1614`
- prototype: `__int64 __fastcall(Windows::Rtl::SystemImplementation::CFile *__hidden this, unsigned int, const struct _LBLOB *, unsigned __int64 *, void (*)(void *, struct _IO_STATUS_BLOCK *, unsigned int), void *, struct _IO_STATUS_BLOCK *, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callees

- `0x1800059d0`
- `0x1800692fc`
- `0x18017b760`
- `0x18017daf8`
- `0x1801c72d0`
- `0x1801e4d48`
- `0x1801efdc0`
- `0x1802b1010`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x1801c779d`
- `ntdll!NtWaitForSingleObject` at `0x1801c779d`
- `ntdll!NtClose` at `0x1801c74fb`
- `ntdll!NtClose` at `0x1801c75a6`
- `ntdll!NtClose` at `0x1801c762e`
- `ntdll!NtClose` at `0x1801c7712`
- `ntdll!NtClose` at `0x1801c7812`
- `ntdll!NtClose` at `0x1801c786f`
- `ntdll!NtClose` at `0x1801c74fb`
- `ntdll!NtClose` at `0x1801c75a6`
- `ntdll!NtClose` at `0x1801c762e`
- `ntdll!NtClose` at `0x1801c7712`
- `ntdll!NtClose` at `0x1801c7812`
- `ntdll!NtClose` at `0x1801c786f`
- `ntdll!NtCreateEvent` at `0x1801c74a6`
- `ntdll!NtCreateEvent` at `0x1801c74a6`
- `ntdll!TpCancelAsyncIoOperation` at `0x1801c76fc`
- `ntdll!TpCancelAsyncIoOperation` at `0x1801c77fc`
- `ntdll!TpCancelAsyncIoOperation` at `0x1801c784b`
- `ntdll!TpCancelAsyncIoOperation` at `0x1801c76fc`
- `ntdll!TpCancelAsyncIoOperation` at `0x1801c77fc`
- `ntdll!TpCancelAsyncIoOperation` at `0x1801c784b`
- `ntdll!TpStartAsyncIoOperation` at `0x1801c766d`
- `ntdll!TpStartAsyncIoOperation` at `0x1801c766d`

## string_xrefs

- `0x1801c74d0`: `::NtCreateEvent( WaitEvent.GetInitPointer(), ((0x000F0000L)|(0x00100000L)|0x3), nullptr, NotificationEvent, 0 )`
- `0x1801c7363`: `Windows::Rtl::SystemImplementation::CFile::WriteFileAsync`
- `0x1801c755f`: `Windows::Rtl::SystemImplementation::CFile::WriteFileAsync`
- `0x1801c75e7`: `Windows::Rtl::SystemImplementation::CFile::WriteFileAsync`
- `0x1801c77bf`: `Windows::Rtl::SystemImplementation::CFile::WriteFileAsync`

## pseudocode

```c

```
