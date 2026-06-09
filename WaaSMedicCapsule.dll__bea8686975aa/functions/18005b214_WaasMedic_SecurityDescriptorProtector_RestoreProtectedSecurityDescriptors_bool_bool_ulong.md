# WaasMedic::SecurityDescriptorProtector::RestoreProtectedSecurityDescriptors(bool,bool &,ulong &)

- ea: `0x18005b214`
- end: `0x18005c4bd`
- name: `?RestoreProtectedSecurityDescriptors@SecurityDescriptorProtector@WaasMedic@@QEAAJ_NAEA_NAEAK@Z`
- size: `4777`
- prototype: `int(WaasMedic::SecurityDescriptorProtector *__hidden this, bool, bool *, unsigned int *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180050b60`
- `0x1800510d0`

## callees

- `0x180003bb0`
- `0x1800070cc`
- `0x180007590`
- `0x180009a54`
- `0x18002543c`
- `0x18002c284`
- `0x1800321d4`
- `0x180032408`
- `0x180032558`
- `0x180032c70`
- `0x18005b114`
- `0x18005b214`
- `0x18005c4c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005b9c0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005b9c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b323`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b3ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b9aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ba3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bbff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bd47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005be8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bfd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c11f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c267`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b323`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b3ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b9aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ba3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bbff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bd47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005be8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bfd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c11f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c267`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b336`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b3fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b336`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b3fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ba65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005bc28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005bd70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005beb8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c000`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c148`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c290`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ba65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005bc28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005bd70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005beb8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c000`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c148`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c290`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18005b4f5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18005b4f5`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18005ba9d`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18005ba9d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005b369`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005b42d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005b369`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005b42d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b304`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b32e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b3f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b49a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b5cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b729`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bb9f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c4af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b304`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b32e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b3f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b49a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b5cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b729`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bb9f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c4af`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005ba18`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005ba2b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005bbee`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005bd36`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005be7e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005bfc6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005c10e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005c256`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005ba18`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005ba2b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005bbee`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005bd36`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005be7e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005bfc6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005c10e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005c256`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b2f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b3cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b489`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b5be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b66c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b6f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b718`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b86a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b8f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b928`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b990`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005baec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bb17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bb42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bb68`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bb8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bc6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bc99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bcc4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bcea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bdb3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bde1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005be0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005be32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005befb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bf29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bf54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bf7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c043`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c071`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c09c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c0c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c18b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c1b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c1e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c20a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c2d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c301`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c32c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c352`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c3f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c427`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c452`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c478`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c49e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b2f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b3cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b489`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b5be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b66c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b6f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b718`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b86a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b8f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b928`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b990`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005baec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bb17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bb42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bb68`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bb8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bc6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bc99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bcc4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bcea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bdb3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bde1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005be0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005be32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005befb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bf29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bf54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bf7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c043`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c071`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c09c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c0c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c18b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c1b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c1e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c20a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c2d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c301`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c32c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c352`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c3f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c427`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c452`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c478`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c49e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005b607`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005b688`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005b607`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005b688`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18005b2d3`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18005b3af`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18005b46d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18005b53d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18005b59d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18005b650`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18005b6d6`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18005b6fc`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18005b84e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18005b8d8`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18005b90c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18005b974`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18005bad0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18005bafb`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18005bb26`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18005bb4c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18005bb72`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18005bc4f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18005bc7d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18005bca8`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18005bcce`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18005bcf4`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18005bd97`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18005bdc5`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18005bdf0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18005be16`

## string_xrefs

- `0x18005b779`: `SeTakeOwnershipPrivilege`
- `0x18005ba4a`: `Failed to revert the thread token: 0%x08X`
- `0x18005bc08`: `Failed to revert the thread token: 0%x08X`
- `0x18005bd50`: `Failed to revert the thread token: 0%x08X`
- `0x18005be98`: `Failed to revert the thread token: 0%x08X`
- `0x18005bfe0`: `Failed to revert the thread token: 0%x08X`
- `0x18005c128`: `Failed to revert the thread token: 0%x08X`
- `0x18005c270`: `Failed to revert the thread token: 0%x08X`
- `0x18005b795`: `SeSecurityPrivilege`
- `0x18005b7cd`: `SeBackupPrivilege`
- `0x18005b7b1`: `SeRestorePrivilege`
- `0x18005b2a6`: `onecore\enduser\waasmedic\lib\util\securitydescriptorprotector.cpp`
- `0x18005b43e`: `onecore\enduser\waasmedic\lib\util\securitydescriptorprotector.cpp`
- `0x18005b50a`: `onecore\enduser\waasmedic\lib\util\securitydescriptorprotector.cpp`
- `0x18005b623`: `onecore\enduser\waasmedic\lib\util\securitydescriptorprotector.cpp`
- `0x18005b6a8`: `onecore\enduser\waasmedic\lib\util\securitydescriptorprotector.cpp`
- `0x18005bbd5`: `onecore\enduser\waasmedic\lib\util\securitydescriptorprotector.cpp`
- `0x18005bd1d`: `onecore\enduser\waasmedic\lib\util\securitydescriptorprotector.cpp`
- `0x18005be65`: `onecore\enduser\waasmedic\lib\util\securitydescriptorprotector.cpp`
- `0x18005bfad`: `onecore\enduser\waasmedic\lib\util\securitydescriptorprotector.cpp`
- `0x18005c0f5`: `onecore\enduser\waasmedic\lib\util\securitydescriptorprotector.cpp`
- `0x18005c23d`: `onecore\enduser\waasmedic\lib\util\securitydescriptorprotector.cpp`
- `0x18005c3a9`: `onecore\enduser\waasmedic\lib\util\securitydescriptorprotector.cpp`
- `0x18005b56f`: `Failed to open security descriptors store. Error code: 0x%08x`
- `0x18005b5e0`: `Found %d security descriptors to restore.`
- `0x18005b383`: `No security descriptors stored. Skipping.`
- `0x18005b4a7`: `Opening key for read only.`
- `0x18005b9f1`: `Failed to apply security descriptor %s to the folder %s. Error code: 0x%08x`
- `0x18005b9a1`: `Failed to get security descriptor %s from the folder %s. Error code: 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall WaasMedic::SecurityDescriptorProtector::RestoreProtectedSecurityDescriptors(
        WaasMedic::SecurityDescriptorProtector *this,
        char a2,
        bool *a3,
        unsigned int *a4)
{
  HLOCAL v6; // r14
  HLOCAL v7; // rsi
  int SecurityDescriptorStore; // eax
  unsigned int v9; // r15d
  DWORD LastError; // ebx
  const WCHAR *v12; // rdx
  LSTATUS v13; // eax
  unsigned int v14; // ebx
  HLOCAL v15; // rbx
  SIZE_T v16; // rax
  _BYTE *i; // rcx
  HKEY v18; // r15
  DWORD v19; // ebx
  const WCHAR *v20; // rdx
  unsigned int v21; // eax
  unsigned int v22; // esi
  HLOCAL v23; // rbx
  SIZE_T v24; // rax
  _BYTE *k; // rcx
  unsigned int v26; // eax
  SIZE_T v27; // rax
  _BYTE *m; // rcx
  HLOCAL v29; // rsi
  SIZE_T v30; // rax
  _BYTE *j; // rcx
  HLOCAL v32; // rbx
  HLOCAL v33; // rbx
  SIZE_T v34; // rax
  _BYTE *n; // rcx
  BYTE *v36; // r15
  HLOCAL v37; // rsi
  SIZE_T v38; // rax
  _BYTE *ii; // rcx
  SIZE_T v40; // rax
  _BYTE *jj; // rcx
  DWORD v42; // r13d
  DWORD v43; // edx
  int v44; // eax
  int v45; // r13d
  int v46; // eax
  int v47; // eax
  int v48; // eax
  __int64 v49; // r8
  void *v50; // r12
  SIZE_T v51; // rax
  _BYTE *i28; // rcx
  __int64 v53; // r8
  void *v54; // r12
  SIZE_T v55; // rax
  _BYTE *i34; // rcx
  HLOCAL v57; // r12
  SIZE_T v58; // rax
  _BYTE *i35; // rcx
  int SecurityDescriptorStringFromFile; // eax
  unsigned int v61; // r13d
  void *v62; // r12
  SIZE_T v63; // rax
  _BYTE *i36; // rcx
  const unsigned __int16 *v65; // rdx
  DWORD v66; // eax
  unsigned int v67; // eax
  HLOCAL v68; // r12
  SIZE_T v69; // rax
  _BYTE *kk; // rcx
  SIZE_T v71; // rax
  _BYTE *mm; // rcx
  SIZE_T v73; // rax
  _BYTE *nn; // rcx
  SIZE_T v75; // rax
  BYTE *i1; // rcx
  SIZE_T v77; // rax
  _BYTE *i2; // rcx
  DWORD v79; // eax
  HLOCAL v80; // r12
  SIZE_T v81; // rax
  _BYTE *i29; // rcx
  SIZE_T v83; // rax
  _BYTE *i30; // rcx
  SIZE_T v85; // rax
  _BYTE *i31; // rcx
  SIZE_T v87; // rax
  BYTE *i32; // rcx
  SIZE_T v89; // rax
  _BYTE *i33; // rcx
  DWORD v91; // eax
  HLOCAL v92; // r12
  SIZE_T v93; // rax
  _BYTE *i23; // rcx
  SIZE_T v95; // rax
  _BYTE *i24; // rcx
  SIZE_T v97; // rax
  _BYTE *i25; // rcx
  SIZE_T v99; // rax
  BYTE *i26; // rcx
  SIZE_T v101; // rax
  _BYTE *i27; // rcx
  DWORD v103; // eax
  HLOCAL v104; // r12
  SIZE_T v105; // rax
  _BYTE *i18; // rcx
  SIZE_T v107; // rax
  _BYTE *i19; // rcx
  SIZE_T v109; // rax
  _BYTE *i20; // rcx
  SIZE_T v111; // rax
  BYTE *i21; // rcx
  SIZE_T v113; // rax
  _BYTE *i22; // rcx
  DWORD v115; // eax
  HLOCAL v116; // r12
  SIZE_T v117; // rax
  _BYTE *i13; // rcx
  SIZE_T v119; // rax
  _BYTE *i14; // rcx
  SIZE_T v121; // rax
  _BYTE *i15; // rcx
  SIZE_T v123; // rax
  BYTE *i16; // rcx
  SIZE_T v125; // rax
  _BYTE *i17; // rcx
  DWORD v127; // eax
  HLOCAL v128; // r12
  SIZE_T v129; // rax
  _BYTE *i8; // rcx
  SIZE_T v131; // rax
  _BYTE *i9; // rcx
  SIZE_T v133; // rax
  _BYTE *i10; // rcx
  SIZE_T v135; // rax
  BYTE *i11; // rcx
  SIZE_T v137; // rax
  _BYTE *i12; // rcx
  DWORD v139; // eax
  HLOCAL v140; // r12
  SIZE_T v141; // rax
  _BYTE *i3; // rcx
  SIZE_T v143; // rax
  _BYTE *i4; // rcx
  SIZE_T v145; // rax
  _BYTE *i5; // rcx
  SIZE_T v147; // rax
  BYTE *i6; // rcx
  SIZE_T v149; // rax
  _BYTE *i7; // rcx
  LPCWSTR *v151; // rdx
  HLOCAL v152; // r12
  SIZE_T v153; // rax
  _BYTE *i37; // rdx
  SIZE_T v155; // rax
  _BYTE *i38; // rcx
  SIZE_T v157; // rax
  _BYTE *i39; // rcx
  SIZE_T v159; // rax
  BYTE *i40; // rcx
  SIZE_T v161; // rax
  _BYTE *i41; // rcx
  int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultb; // [rsp+20h] [rbp-E0h]
  PHKEY phkResultc; // [rsp+20h] [rbp-E0h]
  LPDWORD lpcbMaxClassLen; // [rsp+30h] [rbp-D0h]
  HLOCAL hMem; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  HANDLE hObject[2]; // [rsp+70h] [rbp-90h] BYREF
  char v171; // [rsp+80h] [rbp-80h]
  DWORD cbMaxValueNameLen; // [rsp+84h] [rbp-7Ch] BYREF
  DWORD cbMaxValueLen[2]; // [rsp+88h] [rbp-78h] BYREF
  DWORD cbData; // [rsp+90h] [rbp-70h] BYREF
  DWORD cchValueName; // [rsp+94h] [rbp-6Ch] BYREF
  HLOCAL v176; // [rsp+98h] [rbp-68h]
  DWORD dwIndex; // [rsp+A0h] [rbp-60h]
  HLOCAL v178; // [rsp+A8h] [rbp-58h]
  BYTE *v179; // [rsp+B0h] [rbp-50h]
  HLOCAL v180; // [rsp+B8h] [rbp-48h]
  HLOCAL v181; // [rsp+C0h] [rbp-40h]
  bool *v182; // [rsp+C8h] [rbp-38h]
  LPCWSTR lpSubKey[2]; // [rsp+D0h] [rbp-30h] BYREF
  __m128i si128; // [rsp+E0h] [rbp-20h]
  LPWSTR StringSecurityDescriptor[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v186; // [rsp+100h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v182 = a3;
  v171 = a2;
  hKey = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen[0] = 0;
  v178 = 0;
  v179 = 0;
  v6 = 0;
  v180 = 0;
  v7 = 0;
  v181 = 0;
  hMem = 0;
  *(_OWORD *)lpSubKey = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpSubKey[0]) = 0;
  SecurityDescriptorStore = WaasMedic::SecurityDescriptorProtector::GetSecurityDescriptorStore(this, lpSubKey);
  v9 = SecurityDescriptorStore;
  if ( SecurityDescriptorStore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x69,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\securitydescriptorprotector.cpp",
      (const char *)(unsigned int)SecurityDescriptorStore,
      phkResult);
    std::wstring::~wstring(lpSubKey);
    hMem = 0;
    return v9;
  }
  *a3 = 0;
  *a4 = 0;
  if ( hKey )
  {
    LastError = GetLastError();
    RegCloseKey(hKey);
    SetLastError(LastError);
  }
  hKey = 0;
  v12 = (const WCHAR *)lpSubKey;
  if ( si128.m128i_i64[1] > 7uLL )
    v12 = lpSubKey[0];
  v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v12, 0, 3u, &hKey);
  v14 = v13;
  if ( v13 )
  {
    if ( v13 == 2 )
    {
      LogLevelW(4u, L"No security descriptors stored. Skipping.");
      std::wstring::~wstring(lpSubKey);
      v15 = hMem;
      hMem = 0;
      if ( v15 )
      {
        v16 = LocalSize(v15);
        for ( i = v15; v16; --v16 )
          *i++ = 0;
        LocalFree(v15);
      }
LABEL_123:
      if ( hKey )
        RegCloseKey(hKey);
      return 0;
    }
    if ( v13 != 5 )
    {
      if ( v13 > 0 )
        v14 = (unsigned __int16)v13 | 0x80070000;
      LogLevelW(2u, L"Failed to open security descriptors store. Error code: 0x%08x", v14);
      std::wstring::~wstring(lpSubKey);
      v29 = hMem;
      hMem = 0;
      if ( v29 )
      {
        v30 = LocalSize(v29);
        for ( j = v29; v30; --v30 )
          *j++ = 0;
        LocalFree(v29);
      }
      if ( hKey )
        RegCloseKey(hKey);
      return v14;
    }
    v18 = hKey;
    if ( hKey )
    {
      v19 = GetLastError();
      RegCloseKey(v18);
      SetLastError(v19);
    }
    hKey = 0;
    v20 = (const WCHAR *)lpSubKey;
    if ( si128.m128i_i64[1] > 7uLL )
      v20 = lpSubKey[0];
    v21 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v20, 0, 1u, &hKey);
    if ( v21 )
    {
      v22 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x7F,
              (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\securitydescriptorprotector.cpp",
              (const char *)v21,
              phkResulta);
      std::wstring::~wstring(lpSubKey);
      v23 = hMem;
      hMem = 0;
      if ( !v23 )
      {
LABEL_24:
        if ( hKey )
          RegCloseKey(hKey);
        return v22;
      }
      v24 = LocalSize(v23);
      for ( k = v23; v24; --v24 )
        *k++ = 0;
LABEL_23:
      LocalFree(v23);
      goto LABEL_24;
    }
    LogLevelW(4u, L"Opening key for read only.");
  }
  v26 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, a4, &cbMaxValueNameLen, cbMaxValueLen, 0, 0);
  if ( v26 )
  {
    v22 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x95,
            (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\securitydescriptorprotector.cpp",
            (const char *)v26,
            phkResultb);
    std::wstring::~wstring(lpSubKey);
    v23 = hMem;
    hMem = 0;
    if ( !v23 )
      goto LABEL_24;
    v27 = LocalSize(v23);
    for ( m = v23; v27; --v27 )
      *m++ = 0;
    goto LABEL_23;
  }
  LogLevelW(4u, L"Found %d security descriptors to restore.", *a4);
  v32 = LocalAlloc(0x40u, 2LL * ++cbMaxValueNameLen);
  v178 = v32;
  if ( !v32 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9B,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\securitydescriptorprotector.cpp",
      (const char *)0x8007000ELL,
      phkResultb);
    std::wstring::~wstring(lpSubKey);
    v33 = hMem;
    hMem = 0;
    if ( v33 )
    {
      v34 = LocalSize(v33);
      for ( n = v33; v34; --v34 )
        *n++ = 0;
      LocalFree(v33);
    }
LABEL_56:
    if ( hKey )
      RegCloseKey(hKey);
    return 2147942414LL;
  }
  ++cbMaxValueLen[0];
  v36 = (BYTE *)LocalAlloc(0x40u, 2LL * cbMaxValueLen[0]);
  v179 = v36;
  if ( !v36 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9F,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\securitydescriptorprotector.cpp",
      (const char *)0x8007000ELL,
      phkResultb);
    std::wstring::~wstring(lpSubKey);
    v37 = hMem;
    hMem = 0;
    if ( v37 )
    {
      v38 = LocalSize(v37);
      for ( ii = v37; v38; --v38 )
        *ii++ = 0;
      LocalFree(v37);
    }
    v40 = LocalSize(v32);
    for ( jj = v32; v40; --v40 )
      *jj++ = 0;
    LocalFree(v32);
    goto LABEL_56;
  }
  cchValueName = cbMaxValueNameLen;
  cbData = cbMaxValueLen[0];
  v42 = 1;
  v43 = 0;
  while ( 1 )
  {
    dwIndex = v42;
    v67 = RegEnumValueW(hKey, v43, (LPWSTR)v32, &cchValueName, 0, 0, v36, &cbData);
    if ( v67 == 259 )
    {
      std::wstring::~wstring(lpSubKey);
      v68 = hMem;
      hMem = 0;
      if ( v68 )
      {
        v69 = LocalSize(v68);
        for ( kk = v68; v69; --v69 )
          *kk++ = 0;
        LocalFree(v68);
      }
      if ( v7 )
      {
        v71 = LocalSize(v7);
        for ( mm = v7; v71; --v71 )
          *mm++ = 0;
        LocalFree(v7);
      }
      if ( v6 )
      {
        v73 = LocalSize(v6);
        for ( nn = v6; v73; --v73 )
          *nn++ = 0;
        LocalFree(v6);
      }
      v75 = LocalSize(v36);
      for ( i1 = v36; v75; --v75 )
        *i1++ = 0;
      LocalFree(v36);
      v77 = LocalSize(v32);
      for ( i2 = v32; v77; --v77 )
        *i2++ = 0;
      LocalFree(v32);
      goto LABEL_123;
    }
    if ( v67 )
      break;
    cchValueName = cbMaxValueNameLen;
    cbData = cbMaxValueLen[0];
    hObject[0] = 0;
    hObject[1] = 0;
    v44 = WaasMedic::CAutoThreadPrivilegeHelper::EnablePrivilege(
            (WaasMedic::CAutoThreadPrivilegeHelper *)hObject,
            L"SeTakeOwnershipPrivilege");
    v45 = v44;
    if ( v44 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB6,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\securitydescriptorprotector.cpp",
        (const char *)(unsigned int)v44,
        (int)phkResultc);
      if ( LOBYTE(hObject[1]) )
      {
        if ( RevertToSelf() )
        {
          LOBYTE(hObject[1]) = 0;
        }
        else
        {
          v139 = GetLastError();
          LogLevelW(2u, L"Failed to revert the thread token: 0%x08X", v139);
        }
      }
      if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(hObject[0]);
      std::wstring::~wstring(lpSubKey);
      v140 = hMem;
      hMem = 0;
      if ( v140 )
      {
        v141 = LocalSize(v140);
        for ( i3 = v140; v141; --v141 )
          *i3++ = 0;
        LocalFree(v140);
      }
      if ( v7 )
      {
        v143 = LocalSize(v7);
        for ( i4 = v7; v143; --v143 )
          *i4++ = 0;
        LocalFree(v7);
      }
      if ( v6 )
      {
        v145 = LocalSize(v6);
        for ( i5 = v6; v145; --v145 )
          *i5++ = 0;
        LocalFree(v6);
      }
      v147 = LocalSize(v36);
      for ( i6 = v36; v147; --v147 )
        *i6++ = 0;
      LocalFree(v36);
      v149 = LocalSize(v32);
      for ( i7 = v32; v149; --v149 )
        *i7++ = 0;
      goto LABEL_282;
    }
    v46 = WaasMedic::CAutoThreadPrivilegeHelper::EnablePrivilege(
            (WaasMedic::CAutoThreadPrivilegeHelper *)hObject,
            L"SeSecurityPrivilege");
    v45 = v46;
    if ( v46 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB7,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\securitydescriptorprotector.cpp",
        (const char *)(unsigned int)v46,
        (int)phkResultc);
      if ( LOBYTE(hObject[1]) )
      {
        if ( RevertToSelf() )
        {
          LOBYTE(hObject[1]) = 0;
        }
        else
        {
          v127 = GetLastError();
          LogLevelW(2u, L"Failed to revert the thread token: 0%x08X", v127);
        }
      }
      if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(hObject[0]);
      std::wstring::~wstring(lpSubKey);
      v128 = hMem;
      hMem = 0;
      if ( v128 )
      {
        v129 = LocalSize(v128);
        for ( i8 = v128; v129; --v129 )
          *i8++ = 0;
        LocalFree(v128);
      }
      if ( v7 )
      {
        v131 = LocalSize(v7);
        for ( i9 = v7; v131; --v131 )
          *i9++ = 0;
        LocalFree(v7);
      }
      if ( v6 )
      {
        v133 = LocalSize(v6);
        for ( i10 = v6; v133; --v133 )
          *i10++ = 0;
        LocalFree(v6);
      }
      v135 = LocalSize(v36);
      for ( i11 = v36; v135; --v135 )
        *i11++ = 0;
      LocalFree(v36);
      v137 = LocalSize(v32);
      for ( i12 = v32; v137; --v137 )
        *i12++ = 0;
      goto LABEL_282;
    }
    v47 = WaasMedic::CAutoThreadPrivilegeHelper::EnablePrivilege(
            (WaasMedic::CAutoThreadPrivilegeHelper *)hObject,
            L"SeRestorePrivilege");
    v45 = v47;
    if ( v47 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB8,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\securitydescriptorprotector.cpp",
        (const char *)(unsigned int)v47,
        (int)phkResultc);
      if ( LOBYTE(hObject[1]) )
      {
        if ( RevertToSelf() )
        {
          LOBYTE(hObject[1]) = 0;
        }
        else
        {
          v115 = GetLastError();
          LogLevelW(2u, L"Failed to revert the thread token: 0%x08X", v115);
        }
      }
      if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(hObject[0]);
      std::wstring::~wstring(lpSubKey);
      v116 = hMem;
      hMem = 0;
      if ( v116 )
      {
        v117 = LocalSize(v116);
        for ( i13 = v116; v117; --v117 )
          *i13++ = 0;
        LocalFree(v116);
      }
      if ( v7 )
      {
        v119 = LocalSize(v7);
        for ( i14 = v7; v119; --v119 )
          *i14++ = 0;
        LocalFree(v7);
      }
      if ( v6 )
      {
        v121 = LocalSize(v6);
        for ( i15 = v6; v121; --v121 )
          *i15++ = 0;
        LocalFree(v6);
      }
      v123 = LocalSize(v36);
      for ( i16 = v36; v123; --v123 )
        *i16++ = 0;
      LocalFree(v36);
      v125 = LocalSize(v32);
      for ( i17 = v32; v125; --v125 )
        *i17++ = 0;
      goto LABEL_282;
    }
    v48 = WaasMedic::CAutoThreadPrivilegeHelper::EnablePrivilege(
            (WaasMedic::CAutoThreadPrivilegeHelper *)hObject,
            L"SeBackupPrivilege");
    v45 = v48;
    if ( v48 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB9,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\securitydescriptorprotector.cpp",
        (const char *)(unsigned int)v48,
        (int)phkResultc);
      if ( LOBYTE(hObject[1]) )
      {
        if ( RevertToSelf() )
        {
          LOBYTE(hObject[1]) = 0;
        }
        else
        {
          v103 = GetLastError();
          LogLevelW(2u, L"Failed to revert the thread token: 0%x08X", v103);
        }
      }
      if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(hObject[0]);
      std::wstring::~wstring(lpSubKey);
      v104 = hMem;
      hMem = 0;
      if ( v104 )
      {
        v105 = LocalSize(v104);
        for ( i18 = v104; v105; --v105 )
          *i18++ = 0;
        LocalFree(v104);
      }
      if ( v7 )
      {
        v107 = LocalSize(v7);
        for ( i19 = v7; v107; --v107 )
          *i19++ = 0;
        LocalFree(v7);
      }
      if ( v6 )
      {
        v109 = LocalSize(v6);
        for ( i20 = v6; v109; --v109 )
          *i20++ = 0;
        LocalFree(v6);
      }
      v111 = LocalSize(v36);
      for ( i21 = v36; v111; --v111 )
        *i21++ = 0;
      LocalFree(v36);
      v113 = LocalSize(v32);
      for ( i22 = v32; v113; --v113 )
        *i22++ = 0;
      goto LABEL_282;
    }
    v176 = 0;
    *(_OWORD *)StringSecurityDescriptor = 0;
    v186 = 0;
    v49 = -1;
    do
      ++v49;
    while ( *((_WORD *)v32 + v49) );
    std::wstring::_Construct<1,unsigned short const *>(StringSecurityDescriptor, v32, v49);
    v45 = WaasMedic::Base64StringToBuffer((LPCWSTR)StringSecurityDescriptor);
    std::wstring::~wstring(StringSecurityDescriptor);
    if ( v45 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBD,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\securitydescriptorprotector.cpp",
        (const char *)(unsigned int)v45,
        (int)phkResultc);
      if ( LOBYTE(hObject[1]) )
      {
        if ( RevertToSelf() )
        {
          LOBYTE(hObject[1]) = 0;
        }
        else
        {
          v91 = GetLastError();
          LogLevelW(2u, L"Failed to revert the thread token: 0%x08X", v91);
        }
      }
      if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(hObject[0]);
      std::wstring::~wstring(lpSubKey);
      v92 = hMem;
      hMem = 0;
      if ( v92 )
      {
        v93 = LocalSize(v92);
        for ( i23 = v92; v93; --v93 )
          *i23++ = 0;
        LocalFree(v92);
      }
      if ( v7 )
      {
        v95 = LocalSize(v7);
        for ( i24 = v7; v95; --v95 )
          *i24++ = 0;
        LocalFree(v7);
      }
      if ( v6 )
      {
        v97 = LocalSize(v6);
        for ( i25 = v6; v97; --v97 )
          *i25++ = 0;
        LocalFree(v6);
      }
      v99 = LocalSize(v36);
      for ( i26 = v36; v99; --v99 )
        *i26++ = 0;
      LocalFree(v36);
      v101 = LocalSize(v32);
      for ( i27 = v32; v101; --v101 )
        *i27++ = 0;
      goto LABEL_282;
    }
    v50 = v6;
    v6 = v176;
    v180 = v176;
    if ( v50 )
    {
      v51 = LocalSize(v50);
      for ( i28 = v50; v51; --v51 )
        *i28++ = 0;
      LocalFree(v50);
    }
    v176 = 0;
    *(_OWORD *)StringSecurityDescriptor = 0;
    v186 = 0;
    v53 = -1;
    do
      ++v53;
    while ( *(_WORD *)&v36[2 * v53] );
    std::wstring::_Construct<1,unsigned short const *>(StringSecurityDescriptor, v36, v53);
    v45 = WaasMedic::Base64StringToBuffer((LPCWSTR)StringSecurityDescriptor);
    std::wstring::~wstring(StringSecurityDescriptor);
    if ( v45 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC2,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\securitydescriptorprotector.cpp",
        (const char *)(unsigned int)v45,
        (int)phkResultc);
      if ( LOBYTE(hObject[1]) )
      {
        if ( RevertToSelf() )
        {
          LOBYTE(hObject[1]) = 0;
        }
        else
        {
          v79 = GetLastError();
          LogLevelW(2u, L"Failed to revert the thread token: 0%x08X", v79);
        }
      }
      if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(hObject[0]);
      std::wstring::~wstring(lpSubKey);
      v80 = hMem;
      hMem = 0;
      if ( v80 )
      {
        v81 = LocalSize(v80);
        for ( i29 = v80; v81; --v81 )
          *i29++ = 0;
        LocalFree(v80);
      }
      if ( v7 )
      {
        v83 = LocalSize(v7);
        for ( i30 = v7; v83; --v83 )
          *i30++ = 0;
        LocalFree(v7);
      }
      if ( v6 )
      {
        v85 = LocalSize(v6);
        for ( i31 = v6; v85; --v85 )
          *i31++ = 0;
        LocalFree(v6);
      }
      v87 = LocalSize(v36);
      for ( i32 = v36; v87; --v87 )
        *i32++ = 0;
      LocalFree(v36);
      v89 = LocalSize(v32);
      for ( i33 = v32; v89; --v89 )
        *i33++ = 0;
      goto LABEL_282;
    }
    v54 = v7;
    v7 = v176;
    v181 = v176;
    if ( v54 )
    {
      v55 = LocalSize(v54);
      for ( i34 = v54; v55; --v55 )
        *i34++ = 0;
      LocalFree(v54);
    }
    v57 = hMem;
    hMem = 0;
    if ( v57 )
    {
      v58 = LocalSize(v57);
      for ( i35 = v57; v58; --v58 )
        *i35++ = 0;
      LocalFree(v57);
    }
    StringSecurityDescriptor[0] = (LPWSTR)&hMem;
    StringSecurityDescriptor[1] = 0;
    LOBYTE(v186) = 1;
    SecurityDescriptorStringFromFile = WaasMedic::CProtectionUtil::GetSecurityDescriptorStringFromFile(
                                         (LPCWSTR)v6,
                                         &StringSecurityDescriptor[1]);
    LODWORD(v176) = SecurityDescriptorStringFromFile;
    v61 = (unsigned int)SecurityDescriptorStringFromFile >> 31;
    if ( (_BYTE)v186 )
    {
      v62 = *(void **)StringSecurityDescriptor[0];
      *(_QWORD *)StringSecurityDescriptor[0] = StringSecurityDescriptor[1];
      if ( v62 )
      {
        v63 = LocalSize(v62);
        for ( i36 = v62; v63; --v63 )
          *i36++ = 0;
        LocalFree(v62);
        SecurityDescriptorStringFromFile = (int)v176;
      }
    }
    if ( (_BYTE)v61 )
    {
      v65 = L"Failed to get security descriptor %s from the folder %s. Error code: 0x%08x";
      goto LABEL_95;
    }
    if ( (unsigned int)_o__wcsicmp(v7, hMem) )
    {
      *v182 = 1;
      if ( v171 )
      {
        cbMaxValueLen[1] = 65793;
        SecurityDescriptorStringFromFile = WaasMedic::CProtectionUtil::ApplySecurityDescriptorToFile(v6, v7, 65793);
        if ( SecurityDescriptorStringFromFile < 0 )
        {
          v65 = L"Failed to apply security descriptor %s to the folder %s. Error code: 0x%08x";
LABEL_95:
          LODWORD(phkResultc) = SecurityDescriptorStringFromFile;
          LogLevelW(2u, v65, v7, v6, phkResultc);
          if ( !LOBYTE(hObject[1]) )
            goto LABEL_102;
          if ( RevertToSelf() )
            goto LABEL_100;
          goto LABEL_101;
        }
      }
    }
    if ( !LOBYTE(hObject[1]) )
      goto LABEL_102;
    if ( RevertToSelf() )
    {
LABEL_100:
      LOBYTE(hObject[1]) = 0;
      goto LABEL_102;
    }
LABEL_101:
    v66 = GetLastError();
    LogLevelW(2u, L"Failed to revert the thread token: 0%x08X", v66);
LABEL_102:
    if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hObject[0]);
    v43 = dwIndex;
    v42 = dwIndex + 1;
  }
  v151 = lpSubKey;
  if ( si128.m128i_i64[1] > 7uLL )
    v151 = (LPCWSTR *)lpSubKey[0];
  LODWORD(lpcbMaxClassLen) = v42 - 1;
  v45 = wil::details::in1diag3::Return_Win32Msg(
          retaddr,
          (void *)0xAF,
          (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\securitydescriptorprotector.cpp",
          (const char *)v67,
          (unsigned int)"Could not enumerate the values under %ws, index = %u.",
          (const char *)v151,
          lpcbMaxClassLen);
  std::wstring::~wstring(lpSubKey);
  v152 = hMem;
  hMem = 0;
  if ( v152 )
  {
    v153 = LocalSize(v152);
    for ( i37 = v152; v153; --v153 )
      *i37++ = 0;
    LocalFree(v152);
  }
  if ( v7 )
  {
    v155 = LocalSize(v7);
    for ( i38 = v7; v155; --v155 )
      *i38++ = 0;
    LocalFree(v7);
  }
  if ( v6 )
  {
    v157 = LocalSize(v6);
    for ( i39 = v6; v157; --v157 )
      *i39++ = 0;
    LocalFree(v6);
  }
  v159 = LocalSize(v36);
  for ( i40 = v36; v159; --v159 )
    *i40++ = 0;
  LocalFree(v36);
  v161 = LocalSize(v32);
  for ( i41 = v32; v161; --v161 )
    *i41++ = 0;
LABEL_282:
  LocalFree(v32);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v45;
}

```

## disassembly

```asm
0x18005b214  mov     [rsp-8+arg_8], rbx
0x18005b219  push    rbp
0x18005b21a  push    rsi
0x18005b21b  push    rdi
0x18005b21c  push    r12
0x18005b21e  push    r13
0x18005b220  push    r14
0x18005b222  push    r15
0x18005b224  lea     rbp, [rsp-20h]
0x18005b229  sub     rsp, 120h
0x18005b230  mov     rax, cs:__security_cookie
0x18005b237  xor     rax, rsp
0x18005b23a  mov     [rbp+50h+var_40], rax
0x18005b23e  mov     r12, r9
0x18005b241  mov     rbx, r8
0x18005b244  mov     [rbp+50h+var_88], rbx
0x18005b248  mov     [rbp+50h+var_D0], dl
0x18005b24b  xor     r13d, r13d
0x18005b24e  mov     [rsp+150h+hKey], r13
0x18005b253  mov     [rbp+50h+cbMaxValueNameLen], r13d
0x18005b257  mov     [rbp+50h+cbMaxValueLen], r13d
0x18005b25b  mov     [rbp+50h+var_A8], r13
0x18005b25f  mov     [rbp+50h+var_A0], r13
0x18005b263  mov     r14d, r13d
0x18005b266  mov     [rbp+50h+var_98], r13
0x18005b26a  mov     esi, r13d
0x18005b26d  mov     [rbp+50h+var_90], r13
0x18005b271  mov     [rsp+150h+hMem], r13
0x18005b276  xorps   xmm0, xmm0
0x18005b279  movups  xmmword ptr [rbp+50h+lpSubKey], xmm0
0x18005b27d  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18005b285  movdqu  [rbp+50h+var_70], xmm1
0x18005b28a  mov     word ptr [rbp+50h+lpSubKey], r13w
0x18005b28f  lea     rdx, [rbp+50h+lpSubKey]
0x18005b293  call    ?GetSecurityDescriptorStore@SecurityDescriptorProtector@WaasMedic@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WaasMedic::SecurityDescriptorProtector::GetSecurityDescriptorStore(std::wstring &)
0x18005b298  mov     r15d, eax
0x18005b29b  test    eax, eax
0x18005b29d  jns     short loc_18005B312
0x18005b29f  mov     rcx, [rbp+58h]; this
0x18005b2a3  mov     r9d, eax; char *
0x18005b2a6  lea     r8, aOnecoreEnduser_45; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18005b2ad  lea     edx, [r13+69h]; void *
0x18005b2b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b2b6  nop
0x18005b2b7  lea     rcx, [rbp+50h+lpSubKey]; void *
0x18005b2bb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005b2c0  nop
0x18005b2c1  mov     rbx, [rsp+150h+hMem]
0x18005b2c6  mov     [rsp+150h+hMem], r13
0x18005b2cb  test    rbx, rbx
0x18005b2ce  jz      short loc_18005B2FA
0x18005b2d0  mov     rcx, rbx; hMem
0x18005b2d3  call    cs:__imp_LocalSize
0x18005b2d9  mov     rcx, rbx
0x18005b2dc  test    rax, rax
0x18005b2df  jz      short loc_18005B2F0
0x18005b2e1  lea     edi, [r13+1]
0x18005b2e5  mov     [rcx], r13b
0x18005b2e8  add     rcx, rdi
0x18005b2eb  sub     rax, rdi
0x18005b2ee  jnz     short loc_18005B2E5
0x18005b2f0  mov     rcx, rbx; hMem
0x18005b2f3  call    cs:__imp_LocalFree
0x18005b2f9  nop
0x18005b2fa  mov     rcx, [rsp+150h+hKey]; hKey
0x18005b2ff  test    rcx, rcx
0x18005b302  jz      short loc_18005B30A
0x18005b304  call    cs:__imp_RegCloseKey
0x18005b30a  mov     eax, r15d
0x18005b30d  jmp     loc_18005BBA7
0x18005b312  mov     [rbx], r13b
0x18005b315  mov     [r12], r13d
0x18005b319  mov     rdi, [rsp+150h+hKey]
0x18005b31e  test    rdi, rdi
0x18005b321  jz      short loc_18005B33C
0x18005b323  call    cs:__imp_GetLastError
0x18005b329  mov     ebx, eax
0x18005b32b  mov     rcx, rdi; hKey
0x18005b32e  call    cs:__imp_RegCloseKey
0x18005b334  mov     ecx, ebx; dwErrCode
0x18005b336  call    cs:__imp_SetLastError
0x18005b33c  mov     [rsp+150h+hKey], r13
0x18005b341  lea     rdx, [rbp+50h+lpSubKey]
0x18005b345  cmp     qword ptr [rbp+50h+var_70+8], 7
0x18005b34a  cmova   rdx, [rbp+50h+lpSubKey]; lpSubKey
0x18005b34f  lea     rax, [rsp+150h+hKey]
0x18005b354  mov     [rsp+150h+phkResult], rax; phkResult
0x18005b359  mov     r9d, 3; samDesired
0x18005b35f  xor     r8d, r8d; ulOptions
0x18005b362  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005b369  call    cs:__imp_RegOpenKeyExW
0x18005b36f  mov     ebx, eax
0x18005b371  mov     edi, 1
0x18005b376  test    eax, eax
0x18005b378  jz      loc_18005B4B8
0x18005b37e  cmp     eax, 2
0x18005b381  jnz     short loc_18005B3D7
0x18005b383  lea     rdx, aNoSecurityDesc; "No security descriptors stored. Skippin"...
0x18005b38a  lea     ecx, [rax+2]; unsigned __int8
0x18005b38d  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005b392  nop
0x18005b393  lea     rcx, [rbp+50h+lpSubKey]; void *
0x18005b397  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005b39c  nop
0x18005b39d  mov     rbx, [rsp+150h+hMem]
0x18005b3a2  mov     [rsp+150h+hMem], r13
0x18005b3a7  test    rbx, rbx
0x18005b3aa  jz      short loc_18005B3D2
0x18005b3ac  mov     rcx, rbx; hMem
0x18005b3af  call    cs:__imp_LocalSize
0x18005b3b5  mov     rcx, rbx
0x18005b3b8  test    rax, rax
0x18005b3bb  jz      short loc_18005B3C8
0x18005b3bd  mov     [rcx], r13b
0x18005b3c0  add     rcx, rdi
0x18005b3c3  sub     rax, rdi
0x18005b3c6  jnz     short loc_18005B3BD
0x18005b3c8  mov     rcx, rbx; hMem
0x18005b3cb  call    cs:__imp_LocalFree
0x18005b3d1  nop
0x18005b3d2  jmp     loc_18005BB95
0x18005b3d7  cmp     eax, 5
0x18005b3da  jnz     loc_18005B55F
0x18005b3e0  mov     r15, [rsp+150h+hKey]
0x18005b3e5  test    r15, r15
0x18005b3e8  jz      short loc_18005B403
0x18005b3ea  call    cs:__imp_GetLastError
0x18005b3f0  mov     ebx, eax
0x18005b3f2  mov     rcx, r15; hKey
0x18005b3f5  call    cs:__imp_RegCloseKey
0x18005b3fb  mov     ecx, ebx; dwErrCode
0x18005b3fd  call    cs:__imp_SetLastError
0x18005b403  mov     [rsp+150h+hKey], r13
0x18005b408  lea     rdx, [rbp+50h+lpSubKey]
0x18005b40c  cmp     qword ptr [rbp+50h+var_70+8], 7
0x18005b411  cmova   rdx, [rbp+50h+lpSubKey]; lpSubKey
0x18005b416  lea     rax, [rsp+150h+hKey]
0x18005b41b  mov     [rsp+150h+phkResult], rax; unsigned int
0x18005b420  mov     r9d, edi; samDesired
0x18005b423  xor     r8d, r8d; ulOptions
0x18005b426  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005b42d  call    cs:__imp_RegOpenKeyExW
0x18005b433  test    eax, eax
0x18005b435  jz      short loc_18005B4A7
0x18005b437  mov     rcx, [rbp+58h]; this
0x18005b43b  mov     r9d, eax; char *
0x18005b43e  lea     r8, aOnecoreEnduser_45; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18005b445  mov     edx, 7Fh; void *
0x18005b44a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005b44f  mov     esi, eax
0x18005b451  lea     rcx, [rbp+50h+lpSubKey]; void *
0x18005b455  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005b45a  nop
0x18005b45b  mov     rbx, [rsp+150h+hMem]
0x18005b460  mov     [rsp+150h+hMem], r13
0x18005b465  test    rbx, rbx
0x18005b468  jz      short loc_18005B490
0x18005b46a  mov     rcx, rbx; hMem
0x18005b46d  call    cs:__imp_LocalSize
0x18005b473  mov     rcx, rbx
0x18005b476  test    rax, rax
0x18005b479  jz      short loc_18005B486
0x18005b47b  mov     [rcx], r13b
0x18005b47e  add     rcx, rdi
0x18005b481  sub     rax, rdi
0x18005b484  jnz     short loc_18005B47B
0x18005b486  mov     rcx, rbx; hMem
0x18005b489  call    cs:__imp_LocalFree
0x18005b48f  nop
0x18005b490  mov     rcx, [rsp+150h+hKey]; hKey
0x18005b495  test    rcx, rcx
0x18005b498  jz      short loc_18005B4A0
0x18005b49a  call    cs:__imp_RegCloseKey
0x18005b4a0  mov     eax, esi
0x18005b4a2  jmp     loc_18005BBA7
0x18005b4a7  lea     rdx, aOpeningKeyForR; "Opening key for read only."
0x18005b4ae  mov     ecx, 4; unsigned __int8
0x18005b4b3  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005b4b8  mov     [rsp+150h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18005b4bd  mov     [rsp+150h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18005b4c2  lea     rax, [rbp+50h+cbMaxValueLen]
0x18005b4c6  mov     [rsp+150h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18005b4cb  lea     rax, [rbp+50h+cbMaxValueNameLen]
0x18005b4cf  mov     [rsp+150h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18005b4d4  mov     [rsp+150h+lpcValues], r12; lpcValues
0x18005b4d9  mov     [rsp+150h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18005b4de  mov     [rsp+150h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x18005b4e3  mov     [rsp+150h+phkResult], r13; int
0x18005b4e8  xor     r9d, r9d; lpReserved
0x18005b4eb  xor     r8d, r8d; lpcchClass
0x18005b4ee  xor     edx, edx; lpClass
0x18005b4f0  mov     rcx, [rsp+150h+hKey]; hKey
0x18005b4f5  call    cs:__imp_RegQueryInfoKeyW
0x18005b4fb  test    eax, eax
0x18005b4fd  jz      loc_18005B5DC
0x18005b503  mov     rcx, [rbp+58h]; this
0x18005b507  mov     r9d, eax; char *
0x18005b50a  lea     r8, aOnecoreEnduser_45; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18005b511  mov     edx, 95h; void *
0x18005b516  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005b51b  mov     esi, eax
0x18005b51d  lea     rcx, [rbp+50h+lpSubKey]; void *
0x18005b521  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005b526  nop
0x18005b527  mov     rbx, [rsp+150h+hMem]
0x18005b52c  mov     [rsp+150h+hMem], r13
0x18005b531  test    rbx, rbx
0x18005b534  jz      loc_18005B490
0x18005b53a  mov     rcx, rbx; hMem
0x18005b53d  call    cs:__imp_LocalSize
0x18005b543  mov     rcx, rbx
0x18005b546  test    rax, rax
0x18005b549  jz      loc_18005B486
0x18005b54f  mov     [rcx], r13b
0x18005b552  add     rcx, rdi
0x18005b555  sub     rax, rdi
0x18005b558  jnz     short loc_18005B54F
0x18005b55a  jmp     loc_18005B486
0x18005b55f  test    eax, eax
0x18005b561  jle     short loc_18005B56C
0x18005b563  movzx   ebx, ax
0x18005b566  or      ebx, 80070000h
0x18005b56c  mov     r8d, ebx
0x18005b56f  lea     rdx, aFailedToOpenSe; "Failed to open security descriptors sto"...
0x18005b576  mov     ecx, 2; unsigned __int8
0x18005b57b  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005b580  nop
0x18005b581  lea     rcx, [rbp+50h+lpSubKey]; void *
0x18005b585  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005b58a  nop
0x18005b58b  mov     rsi, [rsp+150h+hMem]
0x18005b590  mov     [rsp+150h+hMem], r13
0x18005b595  test    rsi, rsi
0x18005b598  jz      short loc_18005B5C5
0x18005b59a  mov     rcx, rsi; hMem
0x18005b59d  call    cs:__imp_LocalSize
0x18005b5a3  mov     rcx, rsi
0x18005b5a6  test    rax, rax
0x18005b5a9  jz      short loc_18005B5BB
0x18005b5ab  mov     edi, 1
0x18005b5b0  mov     [rcx], r13b
0x18005b5b3  add     rcx, rdi
0x18005b5b6  sub     rax, rdi
0x18005b5b9  jnz     short loc_18005B5B0
0x18005b5bb  mov     rcx, rsi; hMem
0x18005b5be  call    cs:__imp_LocalFree
0x18005b5c4  nop
0x18005b5c5  mov     rcx, [rsp+150h+hKey]; hKey
0x18005b5ca  test    rcx, rcx
0x18005b5cd  jz      short loc_18005B5D5
0x18005b5cf  call    cs:__imp_RegCloseKey
0x18005b5d5  mov     eax, ebx
0x18005b5d7  jmp     loc_18005BBA7
0x18005b5dc  mov     r8d, [r12]
0x18005b5e0  lea     rdx, aFoundDSecurity; "Found %d security descriptors to restor"...
0x18005b5e7  mov     ecx, 4; unsigned __int8
0x18005b5ec  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005b5f1  mov     eax, [rbp+50h+cbMaxValueNameLen]
0x18005b5f4  add     eax, edi
0x18005b5f6  mov     [rbp+50h+cbMaxValueNameLen], eax
0x18005b5f9  mov     edx, eax
0x18005b5fb  add     rdx, rdx; uBytes
0x18005b5fe  mov     r15d, 40h ; '@'
0x18005b604  mov     ecx, r15d; uFlags
0x18005b607  call    cs:__imp_LocalAlloc
0x18005b60d  mov     rbx, rax
0x18005b610  mov     [rbp+50h+var_A8], rax
0x18005b614  test    rax, rax
0x18005b617  jnz     short loc_18005B678
0x18005b619  mov     rcx, [rbp+58h]; this
0x18005b61d  mov     r9d, 8007000Eh; char *
0x18005b623  lea     r8, aOnecoreEnduser_45; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18005b62a  lea     edx, [r15+5Bh]; void *
0x18005b62e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b633  nop
0x18005b634  lea     rcx, [rbp+50h+lpSubKey]; void *
0x18005b638  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005b63d  nop
0x18005b63e  mov     rbx, [rsp+150h+hMem]
0x18005b643  mov     [rsp+150h+hMem], r13
0x18005b648  test    rbx, rbx
0x18005b64b  jz      short loc_18005B673
0x18005b64d  mov     rcx, rbx; hMem
0x18005b650  call    cs:__imp_LocalSize
0x18005b656  mov     rcx, rbx
0x18005b659  test    rax, rax
0x18005b65c  jz      short loc_18005B669
0x18005b65e  mov     [rcx], r13b
0x18005b661  add     rcx, rdi
0x18005b664  sub     rax, rdi
0x18005b667  jnz     short loc_18005B65E
0x18005b669  mov     rcx, rbx; hMem
0x18005b66c  call    cs:__imp_LocalFree
0x18005b672  nop
0x18005b673  jmp     loc_18005B71F
0x18005b678  mov     eax, [rbp+50h+cbMaxValueLen]
0x18005b67b  add     eax, edi
0x18005b67d  mov     [rbp+50h+cbMaxValueLen], eax
0x18005b680  mov     edx, eax
0x18005b682  add     rdx, rdx; uBytes
  ... truncated ...
```
