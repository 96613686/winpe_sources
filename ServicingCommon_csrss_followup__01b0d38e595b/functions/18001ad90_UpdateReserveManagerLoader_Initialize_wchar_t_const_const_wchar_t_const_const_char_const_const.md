# UpdateReserveManagerLoader::Initialize(wchar_t const * const,wchar_t const * const,char const * const)

- ea: `0x18001ad90`
- end: `0x18001ae1d`
- name: `?Initialize@UpdateReserveManagerLoader@@QEAAJQEB_W0QEBD@Z`
- size: `141`
- prototype: `__int64 __fastcall(UpdateReserveManagerLoader *__hidden this, const wchar_t *const, const wchar_t *const, const char *const)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x1800203a0`

## callees

- `0x18001ad90`
- `0x18001ae24`
- `0x18001d694`
- `0x18009e020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18001adb9`
- `KERNEL32!GetProcAddress` at `0x18001adb9`
- `ntdll!RtlRaiseStatus` at `0x18001adef`
- `ntdll!RtlRaiseStatus` at `0x18001adef`

## string_xrefs

- `0x18001adb2`: `GetUpdateReserveManager`
- `0x18001adcf`: `onecore\base\servicing\updatereservemanager\loaderlib\updatereservemanagerloader.cpp`

## pseudocode

```c

```
