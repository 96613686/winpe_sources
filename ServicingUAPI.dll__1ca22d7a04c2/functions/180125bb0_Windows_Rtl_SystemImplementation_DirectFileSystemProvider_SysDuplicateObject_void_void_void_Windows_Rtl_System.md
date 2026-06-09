# Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysDuplicateObject(void *,void *,void *,Windows::Rtl::SystemImplementation::CSilHandle *,ulong,ulong,ulong)

- ea: `0x180125bb0`
- end: `0x1801260cd`
- name: `?SysDuplicateObject@DirectFileSystemProvider@SystemImplementation@Rtl@Windows@@UEAAJPEAX00PEAVCSilHandle@234@KKK@Z`
- size: `1309`
- prototype: `int(Windows::Rtl::SystemImplementation::DirectFileSystemProvider *__hidden this, void *, void *, void *, struct Windows::Rtl::SystemImplementation::CSilHandle *, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting`

## callees

- `0x1800031d0`
- `0x180030b68`
- `0x1800497c0`
- `0x1801189d4`
- `0x18011ae2c`
- `0x18011cba4`
- `0x18011d7d8`
- `0x180125bb0`
- `0x18012cc94`
- `0x18012e1cc`
- `0x18012e2e0`
- `0x1801bd010`

## import_xrefs

- `ntdll!NtDuplicateObject` at `0x180125fa8`
- `ntdll!NtDuplicateObject` at `0x180125fa8`
- `ntdll!NtClose` at `0x180126040`
- `ntdll!NtClose` at `0x18012606f`
- `ntdll!NtClose` at `0x180126040`
- `ntdll!NtClose` at `0x18012606f`

## string_xrefs

- `0x180125eda`: `FsTxDuplicateHandleNT( nullptr , 0x00000020, SourceHandle, DesiredAccess, Options, &FsTxHandleContext)`
- `0x180125c1c`: `Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysDuplicateObject`
- `0x180125d78`: `Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysDuplicateObject`
- `0x180125ecb`: `Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysDuplicateObject`
- `0x180125fd5`: `Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysDuplicateObject`
- `0x180125fe8`: `::NtDuplicateObject( SourceProcessHandle, SourceHandle, TargetProcessHandle, TargetHandleOut ? TargetHandle.GetMutablePointer() : nullptr, DesiredAccess, HandleAttributes, Options)`

## pseudocode

```c

```
