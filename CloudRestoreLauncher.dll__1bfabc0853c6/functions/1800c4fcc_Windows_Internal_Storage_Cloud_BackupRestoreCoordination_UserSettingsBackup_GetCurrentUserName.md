# Windows::Internal::Storage::Cloud::BackupRestoreCoordination::UserSettingsBackup::GetCurrentUserName

- ea: `0x1800c4fcc`
- end: `0x1800c5059`
- name: `Windows::Internal::Storage::Cloud::BackupRestoreCoordination::UserSettingsBackup::GetCurrentUserName`
- size: `141`
- prototype: `__int64 __fastcall(winrt::hstring *this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800c5380`
- `0x1800c57e0`

## callees

- `0x18000c6e0`
- `0x180035dac`
- `0x18008cedc`
- `0x1800c4fcc`

## import_xrefs

- `SECUR32!GetUserNameExW` at `0x1800c5006`
- `SECUR32!GetUserNameExW` at `0x1800c5006`

## string_xrefs

- `0x1800c5018`: `pcshell\shell\cloudrestorelauncher\cloudbackuprestore\manifestdrivenbackuprestorehandler.cpp`

## pseudocode

```c

```
