# WsbkInstall(ushort const *,ushort const *,ushort const *,int,int,int,ushort const * * const,ulong)

- ea: `0x18004acc8`
- end: `0x18004c179`
- name: `?WsbkInstall@@YAJPEBG00HHHQEAPEBGK@Z`
- size: `5297`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, __int64, int, int, const unsigned __int16 **const)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800170f0`

## callees

- `0x180009e04`
- `0x18003b094`
- `0x18003b7f4`
- `0x18003bb74`
- `0x18003cd7c`
- `0x18003e128`
- `0x18003e794`
- `0x18003e8f0`
- `0x180049110`
- `0x18004a9d4`
- `0x18004acc8`
- `0x18004d980`
- `0x18004da60`
- `0x18004e288`
- `0x180050300`

## import_xrefs

- `msvcrt!wcstoul` at `0x18004b782`
- `msvcrt!wcstoul` at `0x18004b782`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004b6b4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004b817`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004b962`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004ba64`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004b6b4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004b817`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004b962`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004ba64`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18004b109`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18004bea7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18004b109`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18004bea7`
- `api-ms-win-core-registry-l1-1-0!RegRestoreKeyW` at `0x18004b33d`
- `api-ms-win-core-registry-l1-1-0!RegRestoreKeyW` at `0x18004b33d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004bade`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004bb5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004c09b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004c0aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004bade`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004bb5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004c09b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004c0aa`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004b1ca`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004b459`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004b1ca`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004b459`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004b4d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004b60b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c065`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c07e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c0b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c0d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c0f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c10d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c12a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004b4d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004b60b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c065`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c07e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c0b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c0d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c0f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c10d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c12a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004b4e6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004b619`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c073`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c08c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c0c7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c0e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c0fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c11b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c138`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004b4e6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004b619`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c073`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c08c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c0c7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c0e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c0fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c11b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c138`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ad83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ad9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004adb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ae42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ae5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ae75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b008`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b020`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b065`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b077`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b127`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b1e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b25d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b271`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b28a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b357`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b46f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b706`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b795`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b833`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b8d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b974`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ba7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004baf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bb70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bbdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bc41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bc9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bcb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bd9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004be1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bec8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bf62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bf83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ad83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ad9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004adb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ae42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ae5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ae75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b008`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b020`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b065`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b077`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b127`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b1e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b25d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b271`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b28a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b357`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b46f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b706`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b795`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b833`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b8d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b974`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ba7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004baf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bb70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bbdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bc41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bc9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bcb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bd9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004be1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bec8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bf62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bf83`
- `ntdll!RtlAllocateHeap` at `0x18004af1c`
- `ntdll!RtlAllocateHeap` at `0x18004b54d`
- `ntdll!RtlAllocateHeap` at `0x18004af1c`
- `ntdll!RtlAllocateHeap` at `0x18004b54d`
- `ntdll!RtlFreeHeap` at `0x18004aff3`
- `ntdll!RtlFreeHeap` at `0x18004b660`
- `ntdll!RtlFreeHeap` at `0x18004bd54`
- `ntdll!RtlFreeHeap` at `0x18004c056`
- `ntdll!RtlFreeHeap` at `0x18004aff3`
- `ntdll!RtlFreeHeap` at `0x18004b660`
- `ntdll!RtlFreeHeap` at `0x18004bd54`
- `ntdll!RtlFreeHeap` at `0x18004c056`
- `WDSCORE!CurrentIP` at `0x18004adbe`
- `WDSCORE!CurrentIP` at `0x18004ae7d`
- `WDSCORE!CurrentIP` at `0x18004b07f`
- `WDSCORE!CurrentIP` at `0x18004b12f`
- `WDSCORE!CurrentIP` at `0x18004b1e8`
- `WDSCORE!CurrentIP` at `0x18004b292`
- `WDSCORE!CurrentIP` at `0x18004b35f`
- `WDSCORE!CurrentIP` at `0x18004b477`
- `WDSCORE!CurrentIP` at `0x18004b70e`
- `WDSCORE!CurrentIP` at `0x18004b79d`
- `WDSCORE!CurrentIP` at `0x18004b83b`
- `WDSCORE!CurrentIP` at `0x18004b8d8`
- `WDSCORE!CurrentIP` at `0x18004b97c`
- `WDSCORE!CurrentIP` at `0x18004ba84`
- `WDSCORE!CurrentIP` at `0x18004bafc`
- `WDSCORE!CurrentIP` at `0x18004bb78`
- `WDSCORE!CurrentIP` at `0x18004bbe4`
- `WDSCORE!CurrentIP` at `0x18004bc49`
- `WDSCORE!CurrentIP` at `0x18004bcb9`
- `WDSCORE!CurrentIP` at `0x18004bda4`
- `WDSCORE!CurrentIP` at `0x18004be24`
- `WDSCORE!CurrentIP` at `0x18004bed0`
- `WDSCORE!CurrentIP` at `0x18004bf8b`
- `WDSCORE!CurrentIP` at `0x18004adbe`
- `WDSCORE!CurrentIP` at `0x18004ae7d`
- `WDSCORE!CurrentIP` at `0x18004b07f`
- `WDSCORE!CurrentIP` at `0x18004b12f`
- `WDSCORE!CurrentIP` at `0x18004b1e8`
- `WDSCORE!CurrentIP` at `0x18004b292`
- `WDSCORE!CurrentIP` at `0x18004b35f`
- `WDSCORE!CurrentIP` at `0x18004b477`
- `WDSCORE!CurrentIP` at `0x18004b70e`
- `WDSCORE!CurrentIP` at `0x18004b79d`
- `WDSCORE!CurrentIP` at `0x18004b83b`
- `WDSCORE!CurrentIP` at `0x18004b8d8`
- `WDSCORE!CurrentIP` at `0x18004b97c`
- `WDSCORE!CurrentIP` at `0x18004ba84`
- `WDSCORE!CurrentIP` at `0x18004bafc`
- `WDSCORE!CurrentIP` at `0x18004bb78`
- `WDSCORE!CurrentIP` at `0x18004bbe4`
- `WDSCORE!CurrentIP` at `0x18004bc49`
- `WDSCORE!CurrentIP` at `0x18004bcb9`
- `WDSCORE!CurrentIP` at `0x18004bda4`
- `WDSCORE!CurrentIP` at `0x18004be24`
- `WDSCORE!CurrentIP` at `0x18004bed0`
- `WDSCORE!CurrentIP` at `0x18004bf8b`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004ae1e`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004b192`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004b2f2`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004b3c2`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004b772`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004b7ef`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004b897`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004b930`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004ba32`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004bd1c`

## string_xrefs

- `0x18004b309`: `SeBackupPrivilege`
- `0x18004b415`: `SeBackupPrivilege`
- `0x18004c01c`: `SeBackupPrivilege`
- `0x18004b31f`: `SeRestorePrivilege`
- `0x18004b3ef`: `SeRestorePrivilege`
- `0x18004c001`: `SeRestorePrivilege`
- `0x18004ad47`: `%WINDIR%\System32\drivers`
- `0x18004ade6`: `WsbkInstall`
- `0x18004aea5`: `WsbkInstall`
- `0x18004b0ae`: `WsbkInstall`
- `0x18004b15a`: `WsbkInstall`
- `0x18004b213`: `WsbkInstall`
- `0x18004b2ca`: `WsbkInstall`
- `0x18004b39a`: `WsbkInstall`
- `0x18004b4a2`: `WsbkInstall`
- `0x18004b72e`: `WsbkInstall`
- `0x18004b863`: `WsbkInstall`
- `0x18004b8b5`: `WsbkInstall`
- `0x18004b9a2`: `WsbkInstall`
- `0x18004b9f2`: `WsbkInstall`
- `0x18004baac`: `WsbkInstall`
- `0x18004bb24`: `WsbkInstall`
- `0x18004bba0`: `WsbkInstall`
- `0x18004bc0f`: `WsbkInstall`
- `0x18004bc74`: `WsbkInstall`
- `0x18004bce4`: `WsbkInstall`
- `0x18004bde4`: `WsbkInstall`
- `0x18004be5c`: `WsbkInstall`
- `0x18004bef2`: `WsbkInstall`
- `0x18004bf3d`: `WsbkInstall`
- `0x18004adc7`: `WsbkInstall: Failed to build drivers directory path; hr = 0x%x`
- `0x18004ae29`: `%WINDIR%\System32\WinSetupBak.sys`
- `0x18004be2d`: `WsbkInstall: Failed to build driver file destination path; hr = 0x%x`
- `0x18004b08f`: `WsbkInstall: Failed to copy driver file %s -> %s; hr = 0x%x`
- `0x18004ae86`: `WsbkInstall: Failed to build default driver file path; hr = 0x%x`
- `0x18004b1f1`: `WsbkInstall: Failed to create service key %s; hr = 0x%x`
- `0x18004b138`: `WsbkInstall: Failed to delete service key %s; hr = 0x%x`
- `0x18004b241`: `%WINDIR%\System32\WinSetupBak.hiv`
- `0x18004b368`: `WsbkInstall: Failed to restore service registry hive %s; hr = 0x%x`
- `0x18004b29b`: `WsbkInstall: Failed to build default service registry hive file path; hr = 0x%x`
- `0x18004bdad`: `WsbkInstall: Failed to build volume root path for %s; hr = 0x%x`
- `0x18004b480`: `WsbkInstall: Failed to create Parameters key under %s; hr = 0x%x`
- `0x18004bc52`: `WsbkInstall: Failed to get stable path for %s; hr = 0x%x`
- `0x18004bcc2`: `WsbkInstall: Failed to form NT path for %s; hr = 0x%x`
- `0x18004bbed`: `WsbkInstall: Failed to set registry value for volume %s; hr = 0x%x`
- `0x18004b8de`: `WsbkInstall: Restore mode detected`
- `0x18004b844`: `WsbkInstall: Failed to set registry value for verbose; hr = 0x%x`
- `0x18004b9dc`: `WsbkInstall: VSS backup mode detected`
- `0x18004b98c`: `WsbkInstall: Failed to set registry value for restore mode; hr = 0x%x`
- `0x18004ba8d`: `WsbkInstall: Failed to set registry value for VSS backup mode; hr = 0x%x`
- `0x18004bb81`: `WsbkInstall: Failed to close service key; hr = 0x%x`
- `0x18004bb05`: `WsbkInstall: Failed to close parameters key; hr = 0x%x`
- `0x18004bf94`: `WsbkInstall: Failed to clean up driver file %s; hr = 0x%x`
- `0x18004bed9`: `WsbkInstall: Failed to clean up service key %s; hr = 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=30
__int64 __fastcall WsbkInstall(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        int a5,
        int a6,
        const unsigned __int16 **const a7)
{
  int v7; // edi
  char *v8; // r12
  STRSAFE_LPWSTR v9; // r14
  signed int LastError; // eax
  bool v11; // sf
  signed int v12; // eax
  int v13; // esi
  DWORD v14; // edi
  __int64 v15; // rbx
  struct tagLOG_PARTIAL_MSG *v16; // rax
  signed int v17; // eax
  bool v18; // sf
  signed int v19; // eax
  DWORD v20; // edi
  __int64 v21; // rbx
  struct tagLOG_PARTIAL_MSG *v22; // rax
  __int64 v23; // rbx
  HRESULT v24; // eax
  unsigned __int16 v25; // bx
  HRESULT v26; // eax
  HRESULT v27; // eax
  signed int v28; // eax
  bool v29; // sf
  signed int v30; // eax
  const char *v31; // r15
  signed int v32; // eax
  DWORD v33; // edi
  __int64 v34; // rbx
  struct tagLOG_PARTIAL_MSG *v35; // rax
  int ServiceKeyName; // eax
  const char *v37; // r15
  int v38; // eax
  DWORD v39; // edi
  __int64 v40; // rbx
  struct tagLOG_PARTIAL_MSG *v41; // rax
  LSTATUS v42; // eax
  DWORD v43; // edi
  __int64 v44; // rbx
  struct tagLOG_PARTIAL_MSG *v45; // rax
  const WCHAR *v46; // rbx
  signed int v47; // eax
  bool v48; // sf
  signed int v49; // eax
  DWORD v50; // edi
  __int64 v51; // rbx
  struct tagLOG_PARTIAL_MSG *v52; // rax
  int v53; // edi
  bool v54; // sf
  DWORD v55; // edi
  __int64 v56; // rbx
  struct tagLOG_PARTIAL_MSG *v57; // rax
  int v58; // edi
  LSTATUS v59; // eax
  DWORD v60; // edi
  __int64 v61; // rbx
  struct tagLOG_PARTIAL_MSG *v62; // rax
  unsigned int v63; // r12d
  HANDLE ProcessHeap; // rax
  const wchar_t *v65; // rsi
  __int64 v66; // rbx
  HRESULT v67; // eax
  unsigned __int16 v68; // bx
  HRESULT v69; // eax
  HRESULT v70; // eax
  void *v71; // rbx
  HANDLE v72; // rax
  const WCHAR *v73; // r15
  unsigned __int16 **v74; // r8
  int StablePathWithFallback; // eax
  WCHAR *v76; // r15
  LSTATUS v77; // eax
  DWORD v78; // edi
  __int64 v79; // rbx
  struct tagLOG_PARTIAL_MSG *v80; // rax
  DWORD v81; // edi
  __int64 v82; // rbx
  struct tagLOG_PARTIAL_MSG *v83; // rax
  LSTATUS v84; // eax
  DWORD v85; // edi
  __int64 v86; // rbx
  struct tagLOG_PARTIAL_MSG *v87; // rax
  DWORD v88; // edi
  __int64 v89; // rbx
  struct tagLOG_PARTIAL_MSG *v90; // rax
  LSTATUS v91; // eax
  DWORD v92; // edi
  __int64 v93; // rbx
  struct tagLOG_PARTIAL_MSG *v94; // rax
  LSTATUS v95; // eax
  DWORD v96; // edi
  __int64 v97; // rbx
  LSTATUS v98; // eax
  DWORD v99; // edi
  __int64 v100; // rbx
  LSTATUS v101; // eax
  DWORD v102; // edi
  __int64 v103; // rbx
  DWORD v104; // edi
  __int64 v105; // rbx
  DWORD v106; // edi
  __int64 v107; // rbx
  struct tagLOG_PARTIAL_MSG *v108; // rax
  signed int v109; // eax
  DWORD v110; // edi
  __int64 v111; // rbx
  struct tagLOG_PARTIAL_MSG *v112; // rax
  DWORD v113; // edi
  __int64 v114; // rbx
  struct tagLOG_PARTIAL_MSG *v115; // rax
  DWORD v116; // edi
  __int64 v117; // rbx
  struct tagLOG_PARTIAL_MSG *v118; // rax
  int v119; // eax
  int v120; // r14d
  DWORD v121; // edi
  __int64 v122; // rbx
  struct tagLOG_PARTIAL_MSG *v123; // rax
  signed int v124; // eax
  int v125; // r14d
  DWORD v126; // edi
  __int64 v127; // rbx
  struct tagLOG_PARTIAL_MSG *v128; // rax
  void *v129; // rbx
  HANDLE v130; // rax
  HANDLE v131; // rax
  void *v132; // rbx
  HANDLE v133; // rax
  WCHAR *v134; // rbx
  HANDLE v135; // rax
  HANDLE v136; // rax
  WCHAR *v137; // rbx
  HANDLE v138; // rax
  void *v139; // rbx
  HANDLE v140; // rax
  int ppszDestEnd; // [rsp+20h] [rbp-E0h]
  DWORD lpSecurityAttributes; // [rsp+30h] [rbp-D0h]
  DWORD lpSecurityAttributesa; // [rsp+30h] [rbp-D0h]
  DWORD lpSecurityAttributesb; // [rsp+30h] [rbp-D0h]
  PHKEY phkResult; // [rsp+38h] [rbp-C8h]
  DWORD lpdwDisposition; // [rsp+40h] [rbp-C0h]
  LPCWSTR lpSubKey; // [rsp+60h] [rbp-A0h] BYREF
  STRSAFE_LPWSTR v149; // [rsp+68h] [rbp-98h]
  __int64 v150; // [rsp+70h] [rbp-90h] BYREF
  LPVOID Heap; // [rsp+78h] [rbp-88h]
  int v152; // [rsp+80h] [rbp-80h]
  struct _UNICODE_STRING P; // [rsp+88h] [rbp-78h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+98h] [rbp-68h] BYREF
  HKEY v155; // [rsp+A0h] [rbp-60h] BYREF
  int v156; // [rsp+A8h] [rbp-58h]
  __int64 v157; // [rsp+ACh] [rbp-54h]
  HKEY hKey; // [rsp+B8h] [rbp-48h] BYREF
  BYTE v159[8]; // [rsp+C0h] [rbp-40h] BYREF
  LPVOID lpMem; // [rsp+C8h] [rbp-38h]
  LPCWSTR lpExistingFileName; // [rsp+D0h] [rbp-30h]
  LPVOID v162; // [rsp+D8h] [rbp-28h]
  LPVOID Expand; // [rsp+E0h] [rbp-20h]
  __int128 v164; // [rsp+E8h] [rbp-18h] BYREF
  char v165; // [rsp+F8h] [rbp-8h]
  int v166; // [rsp+F9h] [rbp-7h]
  __int16 v167; // [rsp+FDh] [rbp-3h]
  char v168; // [rsp+FFh] [rbp-1h]
  __int128 v169; // [rsp+100h] [rbp+0h]
  WCHAR Buffer[4]; // [rsp+110h] [rbp+10h] BYREF
  __int16 v171; // [rsp+118h] [rbp+18h]

  v7 = 0;
  *(_QWORD *)Buffer = a7;
  v157 = 0;
  v150 = 0;
  v166 = 0;
  v167 = 0;
  v168 = 0;
  v165 = 0;
  lpSubKey = 0;
  hKey = 0;
  v155 = 0;
  *(_QWORD *)&P.Length = 0;
  *(_DWORD *)v159 = 0;
  v164 = 0;
  v169 = 0;
  if ( !a7 )
  {
    CSystemHive::Unload((CSystemHive *)&v164);
    return 2147942487LL;
  }
  v162 = 0;
  v8 = 0;
  v149 = 0;
  v9 = 0;
  lpMem = 0;
  v152 = 0;
  v156 = 0;
  Expand = (LPVOID)AllocateExpand(L"%WINDIR%\\System32\\drivers");
  if ( !Expand )
  {
    lpExistingFileName = 0;
    LastError = GetLastError();
    v11 = LastError < 0;
    if ( LastError > 0 )
      v11 = 1;
    if ( v11 )
    {
      v12 = GetLastError();
      v13 = v12;
      if ( v12 > 0 )
        v13 = (unsigned __int16)v12 | 0x80070000;
    }
    else
    {
      v13 = -2147467259;
    }
    v14 = GetLastError();
    v15 = CurrentIP();
    v16 = ConstructPartialMsgW(0x2000000u, "WsbkInstall: Failed to build drivers directory path; hr = 0x%x", v13);
    WdsSetupLogMessageW(
      v16,
      0,
      L"D",
      0,
      3403,
      L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
      L"WsbkInstall",
      v15,
      v14,
      0,
      0);
LABEL_133:
    v37 = (const char *)lpSubKey;
    goto LABEL_134;
  }
  lpExistingFileName = (LPCWSTR)AllocateExpand(L"%WINDIR%\\System32\\WinSetupBak.sys");
  if ( !lpExistingFileName )
  {
    v17 = GetLastError();
    v18 = v17 < 0;
    if ( v17 > 0 )
      v18 = 1;
    if ( v18 )
    {
      v19 = GetLastError();
      v13 = v19;
      if ( v19 > 0 )
        v13 = (unsigned __int16)v19 | 0x80070000;
    }
    else
    {
      v13 = -2147467259;
    }
    v20 = GetLastError();
    v21 = CurrentIP();
    v22 = ConstructPartialMsgW(0x2000000u, "WsbkInstall: Failed to build default driver file path; hr = 0x%x", v13);
    WdsSetupLogMessageW(
      v22,
      0,
      L"D",
      0,
      3446,
      L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
      L"WsbkInstall",
      v21,
      v20,
      0,
      0);
    goto LABEL_133;
  }
  v23 = -1;
  pszDest = 0;
  P.Buffer = 0;
  do
    ++v23;
  while ( *((_WORD *)Expand + v23) );
  if ( (_DWORD)v23 && *((_WORD *)Expand + (unsigned int)(v23 - 1)) != 92 )
    v7 = 1;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * (unsigned int)(v23 + v7 + 16));
  v8 = (char *)Heap;
  if ( !Heap )
  {
    NtCurrentTeb()->LastErrorValue = 8;
    goto LABEL_31;
  }
  v24 = StringCchCopyNExW(
          (STRSAFE_LPWSTR)Heap,
          (unsigned int)(v23 + v7 + 16),
          (STRSAFE_PCNZWCH)Expand,
          (unsigned int)v23,
          &pszDest,
          (size_t *)&P.Buffer,
          lpSecurityAttributes);
  v25 = v24;
  if ( v24 < 0
    || v7
    && (v26 = StringCchCopyNExW(
                pszDest,
                (size_t)P.Buffer,
                L"\\",
                1u,
                &pszDest,
                (size_t *)&P.Buffer,
                lpSecurityAttributesa),
        v25 = v26,
        v26 < 0)
    || (v27 = StringCchCopyNW(pszDest, (size_t)P.Buffer, L"WinSetupBak.sys", 0xFu), v25 = v27, v27 < 0) )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
    NtCurrentTeb()->LastErrorValue = v25;
LABEL_31:
    v28 = GetLastError();
    v29 = v28 < 0;
    if ( v28 > 0 )
      v29 = 1;
    if ( v29 )
    {
      v30 = GetLastError();
      v13 = v30;
      if ( v30 > 0 )
        v13 = (unsigned __int16)v30 | 0x80070000;
      Heap = 0;
      v8 = 0;
      if ( v13 >= 0 )
        goto LABEL_37;
    }
    else
    {
      v13 = -2147467259;
    }
    v116 = GetLastError();
    v117 = CurrentIP();
    v118 = ConstructPartialMsgW(0x2000000u, "WsbkInstall: Failed to build driver file destination path; hr = 0x%x", v13);
    WdsSetupLogMessageW(
      v118,
      0,
      L"D",
      0,
      3453,
      L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
      L"WsbkInstall",
      v117,
      v116,
      0,
      0);
    v8 = 0;
LABEL_143:
    v37 = (const char *)lpSubKey;
    goto LABEL_144;
  }
  NtCurrentTeb()->LastErrorValue = 0;
LABEL_37:
  v31 = (const char *)lpExistingFileName;
  if ( !CopyFileExW(lpExistingFileName, (LPCWSTR)v8, 0, 0, 0, 0) )
  {
    v32 = GetLastError();
    v13 = v32;
    if ( v32 > 0 )
      v13 = (unsigned __int16)v32 | 0x80070000;
    v33 = GetLastError();
    v34 = CurrentIP();
    v35 = ConstructPartialMsgW(0x2000000u, "WsbkInstall: Failed to copy driver file %s -> %s; hr = 0x%x", v31, v8, v13);
    WdsSetupLogMessageW(
      v35,
      0,
      L"D",
      0,
      3461,
      L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
      L"WsbkInstall",
      v34,
      v33,
      0,
      0);
    goto LABEL_133;
  }
  ServiceKeyName = WsbkGetServiceKeyName(L"SYSTEM", &lpSubKey);
  v37 = (const char *)lpSubKey;
  v13 = ServiceKeyName;
  if ( ServiceKeyName < 0 )
    goto LABEL_144;
  v38 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, lpSubKey);
  if ( v38 > 0 )
    v38 = (unsigned __int16)v38 | 0x80070000;
  v13 = 0;
  if ( v38 != -2147024894 )
    v13 = v38;
  if ( v13 < 0 )
  {
    v39 = GetLastError();
    v40 = CurrentIP();
    v41 = ConstructPartialMsgW(0x2000000u, "WsbkInstall: Failed to delete service key %s; hr = 0x%x", v37, v13);
    WdsSetupLogMessageW(
      v41,
      0,
      L"D",
      0,
      3497,
      L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
      L"WsbkInstall",
      v40,
      v39,
      0,
      0);
    goto LABEL_144;
  }
  v42 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)v37, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  v13 = v42;
  if ( v42 > 0 )
    v13 = (unsigned __int16)v42 | 0x80070000;
  if ( v13 < 0 )
  {
    v43 = GetLastError();
    v44 = CurrentIP();
    v45 = ConstructPartialMsgW(0x2000000u, "WsbkInstall: Failed to create service key %s; hr = 0x%x", v37, v13);
    WdsSetupLogMessageW(
      v45,
      0,
      L"D",
      0,
      3513,
      L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
      L"WsbkInstall",
      v44,
      v43,
      0,
      0);
    goto LABEL_144;
  }
  v162 = (LPVOID)AllocateExpand(L"%WINDIR%\\System32\\WinSetupBak.hiv");
  v46 = (const WCHAR *)v162;
  if ( !v162 )
  {
    v47 = GetLastError();
    v48 = v47 < 0;
    if ( v47 > 0 )
      v48 = 1;
    if ( v48 )
    {
      v49 = GetLastError();
      v13 = v49;
      if ( v49 > 0 )
        v13 = (unsigned __int16)v49 | 0x80070000;
    }
    else
    {
      v13 = -2147467259;
    }
    v50 = GetLastError();
    v51 = CurrentIP();
    v52 = ConstructPartialMsgW(
            0x2000000u,
            "WsbkInstall: Failed to build default service registry hive file path; hr = 0x%x",
            v13);
    WdsSetupLogMessageW(
      v52,
      0,
      L"D",
      0,
      3533,
      L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
      L"WsbkInstall",
      v51,
      v50,
      0,
      0);
LABEL_134:
    if ( v13 >= 0 )
    {
LABEL_159:
      if ( v156 == 1 && !(_DWORD)v157 )
        EnablePrivilegeEx(L"SeRestorePrivilege");
      if ( v152 == 1 && !HIDWORD(v157) )
        EnablePrivilegeEx(L"SeBackupPrivilege");
      v9 = v149;
      v76 = *(WCHAR **)&P.Length;
      goto LABEL_166;
    }
LABEL_144:
    if ( v37 )
    {
      v119 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, (LPCWSTR)v37);
      if ( v119 > 0 )
        v119 = (unsigned __int16)v119 | 0x80070000;
      v120 = 0;
      if ( v119 != -2147024894 )
        v120 = v119;
      if ( v120 < 0 )
      {
        v121 = GetLastError();
        v122 = CurrentIP();
        v123 = ConstructPartialMsgW(0x2000000u, "WsbkInstall: Failed to clean up service key %s; hr = 0x%x", v37, v120);
        WdsSetupLogMessageW(
          v123,
          0,
          L"D",
          0,
          3766,
          L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
          L"WsbkInstall",
          v122,
          v121,
          0,
          0);
      }
    }
    if ( v8 && !DeleteFileEx2((__int64)v8, 64) )
    {
      v124 = GetLastError();
      if ( v124 > 0 )
        v124 = (unsigned __int16)v124 | 0x80070000;
      v125 = 0;
      if ( v124 != -2147024894 )
        v125 = v124;
      if ( v125 < 0 )
      {
        v126 = GetLastError();
        v127 = CurrentIP();
        v128 = ConstructPartialMsgW(0x2000000u, "WsbkInstall: Failed to clean up driver file %s; hr = 0x%x", v8, v125);
        WdsSetupLogMessageW(
          v128,
          0,
          L"D",
          0,
          3783,
          L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
          L"WsbkInstall",
          v127,
          v126,
          0,
          0);
      }
    }
    goto LABEL_159;
  }
  v152 = EnablePrivilegeEx(L"SeBackupPrivilege");
  v156 = EnablePrivilegeEx(L"SeRestorePrivilege");
  v53 = v156;
  v13 = RegRestoreKeyW(hKey, v46, 8u);
  v54 = v13 < 0;
  if ( v13 > 0 )
  {
    v13 = (unsigned __int16)v13 | 0x80070000;
    v54 = v13 < 0;
  }
  if ( v54 )
  {
    v55 = GetLastError();
    v56 = CurrentIP();
    v57 = ConstructPartialMsgW(0x2000000u, "WsbkInstall: Failed to restore service registry hive %s; hr = 0x%x", 0, v13);
    WdsSetupLogMessageW(
      v57,
      0,
      L"D",
      0,
      3544,
      L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
      L"WsbkInstall",
      v56,
      v55,
      0,
      0);
    v157 = v150;
    goto LABEL_144;
  }
  if ( v53 == 1 )
  {
    v58 = 0;
    if ( !(_DWORD)v150 )
      EnablePrivilegeEx(L"SeRestorePrivilege");
  }
  else
  {
    v58 = 0;
  }
  v156 = 0;
  LODWORD(v157) = 0;
  if ( v152 == 1 && !HIDWORD(v150) )
    EnablePrivilegeEx(L"SeBackupPrivilege");
  v152 = 0;
  HIDWORD(v157) = 0;
  v59 = RegCreateKeyExW(hKey, L"Parameters", 0, 0, 0, 0xF003Fu, 0, &v155, 0);
  v13 = v59;
  if ( v59 > 0 )
    v13 = (unsigned __int16)v59 | 0x80070000;
  if ( v13 < 0 )
  {
    v60 = GetLastError();
    v61 = CurrentIP();
    v62 = ConstructPartialMsgW(0x2000000u, "WsbkInstall: Failed to create Parameters key under %s; hr = 0x%x", v37, v13);
    WdsSetupLogMessageW(
      v62,
      0,
      L"D",
      0,
      3591,
      L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
      L"WsbkInstall",
      v61,
      v60,
      0,
      0);
    goto LABEL_144;
  }
  v63 = 0;
  do
  {
    if ( v9 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v9);
    }
    P.Buffer = 0;
    pszDest = 0;
    v65 = *(const wchar_t **)(*(_QWORD *)Buffer + 8LL * v63);
    if ( !v65 )
    {
      NtCurrentTeb()->LastErrorValue = 87;
LABEL_139:
      v149 = 0;
      goto LABEL_140;
    }
    v66 = -1;
    do
      ++v66;
    while ( v65[v66] );
    if ( (_DWORD)v66 && v65[(unsigned int)(v66 - 1)] != 92 )
      v58 = 1;
    v149 = (STRSAFE_LPWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * (unsigned int)(v66 + v58 + 1));
    if ( !v149 )
    {
      v149 = 0;
      NtCurrentTeb()->LastErrorValue = 8;
LABEL_140:
      v13 = -2147024882;
      v113 = GetLastError();
      v114 = CurrentIP();
      v115 = ConstructPartialMsgW(
               0x2000000u,
               "WsbkInstall: Failed to build volume root path for %s; hr = 0x%x",
               *(const char **)(*(_QWORD *)Buffer + 8LL * v63),
               -2147024882);
      WdsSetupLogMessageW(
        v115,
        0,
        L"D",
        0,
        3602,
        L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
        L"WsbkInstall",
        v114,
        v113,
        0,
        0);
      goto LABEL_108;
    }
    v9 = v149;
    v67 = StringCchCopyNExW(
            v149,
            (unsigned int)(v66 + v58 + 1),
            v65,
            (unsigned int)v66,
            &P.Buffer,
            (size_t *)&pszDest,
            lpSecurityAttributesb);
    v68 = v67;
    if ( v67 < 0 )
      goto LABEL_136;
    if ( v58 )
    {
      v69 = StringCchCopyNExW(
              P.Buffer,
              (size_t)pszDest,
              L"\\",
              1u,
              &P.Buffer,
              (size_t *)&pszDest,
              lpSecurityAttributesb);
      v58 = 0;
      v68 = v69;
      if ( v69 < 0 )
        goto LABEL_136;
    }
    else
    {
      v58 = 0;
    }
    v70 = StringCchCopyNW(P.Buffer, (size_t)pszDest, &Format, 0);
    v68 = v70;
    if ( v70 < 0 )
    {
LABEL_136:
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
      NtCurrentTeb()->LastErrorValue = v68;
      goto LABEL_139;
    }
    v71 = lpMem;
    NtCurrentTeb()->LastErrorValue = 0;
    if ( v71 )
    {
      v72 = GetProcessHeap();
      HeapFree(v72, 0, v71);
    }
    lpMem = (LPVOID)FormFinalPathNameEx(v9, 2);
    v73 = (const WCHAR *)lpMem;
    if ( !lpMem )
    {
      v109 = GetLastError();
      v13 = v109;
      if ( v109 > 0 )
        v13 = (unsigned __int16)v109 | 0x80070000;
      v110 = GetLastError();
      v111 = CurrentIP();
      v112 = ConstructPartialMsgW(
               0x2000000u,
               "WsbkInstall: Failed to form NT path for %s; hr = 0x%x",
               (const char *)v9,
               v13);
      WdsSetupLogMessageW(
        v112,
        0,
        L"D",
        0,
        3611,
        L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
        L"WsbkInstall",
        v111,
        v110,
        0,
        0);
LABEL_132:
      v8 = (char *)Heap;
      v149 = v9;
      goto LABEL_133;
    }
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue>::GetImpl'::`2'::impl);
    v74 = *(unsigned __int16 ***)&P.Length;
    if ( *(_QWORD *)&P.Length )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *(PVOID *)&P.Length);
      *(_QWORD *)&P.Length = 0;
    }
    StablePathWithFallback = DriverUtil::GetStablePathWithFallback(v73, &P, v74);
    if ( StablePathWithFallback < 0 )
    {
      v13 = StablePathWithFallback | 0x10000000;
      v106 = GetLastError();
      v107 = CurrentIP();
      v108 = ConstructPartialMsgW(
               0x2000000u,
               "WsbkInstall: Failed to get stable path for %s; hr = 0x%x",
               (const char *)v73,
               v13);
      WdsSetupLogMessageW(
        v108,
        0,
        L"D",
        0,
        3627,
        L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
        L"WsbkInstall",
        v107,
        v106,
        0,
        0);
      goto LABEL_132;
    }
    v76 = *(WCHAR **)&P.Length;
    StrRTrm(*(_QWORD *)&P.Length);
    HIDWORD(v150) = 1;
    v77 = RegSetValueExW(v155, v76, 0, 4u, (const BYTE *)&v150 + 4, 4u);
    v13 = v77;
    if ( v77 > 0 )
      v13 = (unsigned __int16)v77 | 0x80070000;
    if ( v13 < 0 )
    {
      v104 = GetLastError();
      v105 = CurrentIP();
      v87 = ConstructPartialMsgW(
              0x2000000u,
              "WsbkInstall: Failed to set registry value for volume %s; hr = 0x%x",
              (const char *)v76,
              v13);
      lpdwDisposition = v104;
      phkResult = (PHKEY)v105;
      ppszDestEnd = 3642;
LABEL_107:
      WdsSetupLogMessageW(
        v87,
        0,
        L"D",
        0,
        ppszDestEnd,
        L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
        L"WsbkInstall",
        phkResult,
        lpdwDisposition,
        0,
        0);
      v149 = v9;
LABEL_108:
      v8 = (char *)Heap;
      goto LABEL_143;
    }
    ++v63;
  }
  while ( !v63 );
  *(_QWORD *)Buffer = 0;
  v171 = 0;
  if ( GetEnvironmentVariableW(L"WINSETUPBAK_VERBOSE", Buffer, 5u) )
  {
    v78 = GetLastError();
    v79 = CurrentIP();
    v80 = ConstructPartialMsgW(0x4000000u, "WINSETUPBAK_VERBOSE = %s", (const char *)Buffer);
    WdsSetupLogMessageW(
      v80,
      0,
      L"D",
      0,
      3652,
      L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
      L"WsbkInstall",
      v79,
      v78,
      0,
      0);
    *(_DWORD *)v159 = wcstoul(Buffer, 0, 10);
    if ( *(_DWORD *)v159 )
    {
      v81 = GetLastError();
      v82 = CurrentIP();
      v83 = ConstructPartialMsgW(0x4000000u, "Will enable verbose logging per environment variable");
      WdsSetupLogMessageW(
        v83,
        0,
        L"D",
        0,
        3656,
        L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
        L"WsbkInstall",
        v82,
        v81,
        0,
        0);
      v84 = RegSetValueExW(v155, L"Verbose", 0, 4u, v159, 4u);
      v13 = v84;
      if ( v84 > 0 )
        v13 = (unsigned __int16)v84 | 0x80070000;
      if ( v13 < 0 )
      {
        v85 = GetLastError();
        v86 = CurrentIP();
        v87 = ConstructPartialMsgW(0x2000000u, "WsbkInstall: Failed to set registry value for verbose; hr = 0x%x", v13);
        lpdwDisposition = v85;
        phkResult = (PHKEY)v86;
        ppszDestEnd = 3666;
        goto LABEL_107;
      }
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::GetImpl'::`2'::impl) )
  {
    v88 = GetLastError();
    v89 = CurrentIP();
    v90 = ConstructPartialMsgW(0x4000000u, "WsbkInstall: Restore mode detected");
    WdsSetupLogMessageW(
      v90,
      0,
      L"D",
      0,
      3678,
      L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
      L"WsbkInstall",
      v89,
      v88,
      0,
      0);
    LODWORD(v150) = 1;
    v91 = RegSetValueExW(v155, L"RestoreMode", 0, 4u, (const BYTE *)&v150, 4u);
    v13 = v91;
    if ( v91 > 0 )
      v13 = (unsigned __int16)v91 | 0x80070000;
    v92 = GetLastError();
    v93 = CurrentIP();
    if ( v13 < 0 )
    {
      v87 = ConstructPartialMsgW(
              0x2000000u,
              "WsbkInstall: Failed to set registry value for restore mode; hr = 0x%x",
              v13);
      lpdwDisposition = v92;
      phkResult = (PHKEY)v93;
      ppszDestEnd = 3689;
      goto LABEL_107;
    }
    v94 = ConstructPartialMsgW(0x4000000u, "WsbkInstall: VSS backup mode detected");
    WdsSetupLogMessageW(
      v94,
      0,
      L"D",
      0,
      3696,
      L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
      L"WsbkInstall",
      v93,
      v92,
      0,
      0);
    LODWORD(v150) = 1;
    v95 = RegSetValueExW(v155, L"BackupIsVSS", 0, 4u, (const BYTE *)&v150, 4u);
    v13 = v95;
    if ( v95 > 0 )
      v13 = (unsigned __int16)v95 | 0x80070000;
    if ( v13 < 0 )
    {
      v96 = GetLastError();
      v97 = CurrentIP();
      v87 = ConstructPartialMsgW(
              0x2000000u,
              "WsbkInstall: Failed to set registry value for VSS backup mode; hr = 0x%x",
              v13);
      lpdwDisposition = v96;
      phkResult = (PHKEY)v97;
      ppszDestEnd = 3707;
      goto LABEL_107;
    }
  }
  v98 = RegCloseKey(v155);
  v13 = v98;
  if ( v98 > 0 )
    v13 = (unsigned __int16)v98 | 0x80070000;
  if ( v13 < 0 )
  {
    v99 = GetLastError();
    v100 = CurrentIP();
    v87 = ConstructPartialMsgW(0x2000000u, "WsbkInstall: Failed to close parameters key; hr = 0x%x", v13);
    lpdwDisposition = v99;
    phkResult = (PHKEY)v100;
    ppszDestEnd = 3720;
    goto LABEL_107;
  }
  v155 = 0;
  v101 = RegCloseKey(hKey);
  v13 = v101;
  if ( v101 > 0 )
    v13 = (unsigned __int16)v101 | 0x80070000;
  if ( v13 < 0 )
  {
    v102 = GetLastError();
    v103 = CurrentIP();
    v87 = ConstructPartialMsgW(0x2000000u, "WsbkInstall: Failed to close service key; hr = 0x%x", v13);
    lpdwDisposition = v102;
    phkResult = (PHKEY)v103;
    ppszDestEnd = 3728;
    goto LABEL_107;
  }
  v8 = (char *)Heap;
  hKey = 0;
LABEL_166:
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SetupPlatform_WinSetupBootVolumeIssue>::GetImpl'::`2'::impl);
  if ( v76 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v76);
  v129 = lpMem;
  if ( lpMem )
  {
    v130 = GetProcessHeap();
    HeapFree(v130, 0, v129);
  }
  if ( v9 )
  {
    v131 = GetProcessHeap();
    HeapFree(v131, 0, v9);
  }
  if ( v155 )
    RegCloseKey(v155);
  if ( hKey )
    RegCloseKey(hKey);
  v132 = v162;
  if ( v162 )
  {
    v133 = GetProcessHeap();
    HeapFree(v133, 0, v132);
  }
  v134 = (WCHAR *)lpSubKey;
  if ( lpSubKey )
  {
    v135 = GetProcessHeap();
    HeapFree(v135, 0, v134);
  }
  if ( v8 )
  {
    v136 = GetProcessHeap();
    HeapFree(v136, 0, v8);
  }
  v137 = (WCHAR *)lpExistingFileName;
  if ( lpExistingFileName )
  {
    v138 = GetProcessHeap();
    HeapFree(v138, 0, v137);
  }
  v139 = Expand;
  if ( Expand )
  {
    v140 = GetProcessHeap();
    HeapFree(v140, 0, v139);
  }
  CSystemHive::Unload((CSystemHive *)&v164);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18004acc8  push    rbp
0x18004acca  push    rbx
0x18004accb  push    rsi
0x18004accc  push    rdi
0x18004accd  push    r12
0x18004accf  push    r13
0x18004acd1  push    r14
0x18004acd3  push    r15
0x18004acd5  lea     rbp, [rsp-38h]
0x18004acda  sub     rsp, 138h
0x18004ace1  mov     rax, cs:__security_cookie
0x18004ace8  xor     rax, rsp
0x18004aceb  mov     [rbp+70h+var_50], rax
0x18004acef  mov     rcx, [rbp+70h+arg_30]
0x18004acf6  xor     edi, edi
0x18004acf8  mov     qword ptr [rbp+70h+Buffer], rcx
0x18004acfc  mov     eax, edi
0x18004acfe  mov     dword ptr [rbp+70h+var_C4+4], eax
0x18004ad01  xorps   xmm0, xmm0
0x18004ad04  mov     dword ptr [rsp+170h+var_100+4], eax
0x18004ad08  xorps   xmm1, xmm1
0x18004ad0b  mov     dword ptr [rbp+70h+var_C4], eax
0x18004ad0e  mov     dword ptr [rsp+170h+var_100], eax
0x18004ad12  mov     [rbp+70h+var_77], edi
0x18004ad15  mov     [rbp+70h+var_73], di
0x18004ad19  mov     [rbp+70h+var_71], dil
0x18004ad1d  mov     [rbp+70h+var_78], dil
0x18004ad21  mov     [rsp+170h+lpSubKey], rdi
0x18004ad26  mov     [rbp+70h+hKey], rdi
0x18004ad2a  mov     [rbp+70h+var_D0], rdi
0x18004ad2e  mov     [rbp+70h+P], rdi
0x18004ad32  mov     dword ptr [rbp+70h+var_B0], edi
0x18004ad35  movups  [rbp+70h+var_88], xmm0
0x18004ad39  movdqu  [rbp+70h+var_70], xmm1
0x18004ad3e  test    rcx, rcx
0x18004ad41  jz      loc_18004C14B
0x18004ad47  lea     rcx, Src; "%WINDIR%\\System32\\drivers"
0x18004ad4e  mov     [rbp+70h+var_98], rdi
0x18004ad52  mov     r12d, edi
0x18004ad55  mov     [rsp+170h+var_108], rdi
0x18004ad5a  mov     r14d, edi
0x18004ad5d  mov     [rbp+70h+lpMem], rdi
0x18004ad61  mov     [rbp+70h+var_F0], edi
0x18004ad64  mov     [rbp+70h+var_C8], edi
0x18004ad67  call    AllocateExpand
0x18004ad6c  mov     [rbp+70h+var_90], rax
0x18004ad70  mov     r15, rax
0x18004ad73  lea     esi, [rdi+1]
0x18004ad76  test    rax, rax
0x18004ad79  jnz     loc_18004AE29
0x18004ad7f  mov     [rbp+70h+lpExistingFileName], rdi
0x18004ad83  call    cs:__imp_GetLastError
0x18004ad89  mov     r13d, 80070000h
0x18004ad8f  test    eax, eax
0x18004ad91  jle     short loc_18004AD9B
0x18004ad93  movzx   eax, ax
0x18004ad96  or      eax, r13d
0x18004ad99  test    eax, eax
0x18004ad9b  jns     short loc_18004ADB1
0x18004ad9d  call    cs:__imp_GetLastError
0x18004ada3  mov     esi, eax
0x18004ada5  test    eax, eax
0x18004ada7  jle     short loc_18004ADB6
0x18004ada9  movzx   esi, ax
0x18004adac  or      esi, r13d
0x18004adaf  jmp     short loc_18004ADB6
0x18004adb1  mov     esi, 80004005h
0x18004adb6  call    cs:__imp_GetLastError
0x18004adbc  mov     edi, eax
0x18004adbe  call    cs:__imp_CurrentIP
0x18004adc4  mov     r8d, esi
0x18004adc7  lea     rdx, aWsbkinstallFai_7; "WsbkInstall: Failed to build drivers di"...
0x18004adce  mov     ecx, 2000000h; unsigned int
0x18004add3  mov     rbx, rax
0x18004add6  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18004addb  xor     ecx, ecx
0x18004addd  mov     [rsp+170h+var_120], ecx
0x18004ade1  mov     [rsp+170h+var_128], rcx
0x18004ade6  lea     rcx, aWsbkinstall; "WsbkInstall"
0x18004aded  mov     dword ptr [rsp+170h+lpdwDisposition], edi
0x18004adf1  mov     [rsp+170h+phkResult], rbx
0x18004adf6  mov     [rsp+170h+lpSecurityAttributes], rcx
0x18004adfb  lea     rcx, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\deploymen"...
0x18004ae02  mov     [rsp+170h+pcchRemaining], rcx
0x18004ae07  mov     dword ptr [rsp+170h+ppszDestEnd], 0D4Bh
0x18004ae0f  xor     r9d, r9d
0x18004ae12  lea     r8, aD; "D"
0x18004ae19  xor     edx, edx
0x18004ae1b  mov     rcx, rax
0x18004ae1e  call    cs:__imp_WdsSetupLogMessageW
0x18004ae24  jmp     loc_18004BD2C
0x18004ae29  lea     rcx, aWindirSystem32_1; "%WINDIR%\\System32\\WinSetupBak.sys"
0x18004ae30  call    AllocateExpand
0x18004ae35  mov     [rbp+70h+lpExistingFileName], rax
0x18004ae39  test    rax, rax
0x18004ae3c  jnz     loc_18004AED3
0x18004ae42  call    cs:__imp_GetLastError
0x18004ae48  mov     r13d, 80070000h
0x18004ae4e  test    eax, eax
0x18004ae50  jle     short loc_18004AE5A
0x18004ae52  movzx   eax, ax
0x18004ae55  or      eax, r13d
0x18004ae58  test    eax, eax
0x18004ae5a  jns     short loc_18004AE70
0x18004ae5c  call    cs:__imp_GetLastError
0x18004ae62  mov     esi, eax
0x18004ae64  test    eax, eax
0x18004ae66  jle     short loc_18004AE75
0x18004ae68  movzx   esi, ax
0x18004ae6b  or      esi, r13d
0x18004ae6e  jmp     short loc_18004AE75
0x18004ae70  mov     esi, 80004005h
0x18004ae75  call    cs:__imp_GetLastError
0x18004ae7b  mov     edi, eax
0x18004ae7d  call    cs:__imp_CurrentIP
0x18004ae83  mov     r8d, esi
0x18004ae86  lea     rdx, aWsbkinstallFai_5; "WsbkInstall: Failed to build default dr"...
0x18004ae8d  mov     ecx, 2000000h; unsigned int
0x18004ae92  mov     rbx, rax
0x18004ae95  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18004ae9a  xor     ecx, ecx
0x18004ae9c  mov     [rsp+170h+var_120], ecx
0x18004aea0  mov     [rsp+170h+var_128], rcx
0x18004aea5  lea     rcx, aWsbkinstall; "WsbkInstall"
0x18004aeac  mov     dword ptr [rsp+170h+lpdwDisposition], edi
0x18004aeb0  mov     [rsp+170h+phkResult], rbx
0x18004aeb5  mov     [rsp+170h+lpSecurityAttributes], rcx
0x18004aeba  lea     rcx, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\deploymen"...
0x18004aec1  mov     [rsp+170h+pcchRemaining], rcx
0x18004aec6  mov     dword ptr [rsp+170h+ppszDestEnd], 0D76h
0x18004aece  jmp     loc_18004AE0F
0x18004aed3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004aed7  mov     [rbp+70h+pszDest], rdi
0x18004aedb  xor     eax, eax
0x18004aedd  mov     [rbp+70h+cchDest], rdi
0x18004aee1  inc     rbx
0x18004aee4  cmp     [r15+rbx*2], ax
0x18004aee9  jnz     short loc_18004AEE1
0x18004aeeb  mov     edx, 5Ch ; '\'
0x18004aef0  test    ebx, ebx
0x18004aef2  jz      short loc_18004AEFF
0x18004aef4  lea     eax, [rbx-1]
0x18004aef7  cmp     dx, [r15+rax*2]
0x18004aefc  cmovnz  edi, esi
0x18004aeff  mov     rcx, gs:60h
0x18004af08  lea     eax, [rdi+10h]
0x18004af0b  add     eax, ebx
0x18004af0d  mov     edx, 8; Flags
0x18004af12  mov     esi, eax
0x18004af14  mov     rcx, [rcx+30h]; HeapHandle
0x18004af18  lea     r8, [rax+rax]; Size
0x18004af1c  call    cs:__imp_RtlAllocateHeap
0x18004af22  mov     [rsp+170h+var_F8], rax
0x18004af27  mov     r12, rax
0x18004af2a  mov     r13d, 80070000h
0x18004af30  test    rax, rax
0x18004af33  jnz     short loc_18004AF4C
0x18004af35  mov     rax, gs:30h
0x18004af3e  xor     edi, edi
0x18004af40  mov     dword ptr [rax+68h], 8
0x18004af47  jmp     loc_18004B008
0x18004af4c  lea     rax, [rbp+70h+cchDest]
0x18004af50  mov     r9d, ebx; cchToCopy
0x18004af53  mov     [rsp+170h+pcchRemaining], rax; pcchRemaining
0x18004af58  mov     r8, r15; pszSrc
0x18004af5b  lea     rax, [rbp+70h+pszDest]
0x18004af5f  mov     rdx, rsi; cchDest
0x18004af62  mov     rcx, r12; pszDest
0x18004af65  mov     [rsp+170h+ppszDestEnd], rax; ppszDestEnd
0x18004af6a  call    StringCchCopyNExW
0x18004af6f  mov     ebx, eax
0x18004af71  test    eax, eax
0x18004af73  js      short loc_18004AFDF
0x18004af75  test    edi, edi
0x18004af77  jz      short loc_18004AFAF
0x18004af79  mov     rdx, [rbp+70h+cchDest]; cchDest
0x18004af7d  lea     rax, [rbp+70h+cchDest]
0x18004af81  mov     rcx, [rbp+70h+pszDest]; pszDest
0x18004af85  lea     r8, pszSrc; "\\"
0x18004af8c  mov     [rsp+170h+pcchRemaining], rax; pcchRemaining
0x18004af91  mov     r9d, 1; cchToCopy
0x18004af97  lea     rax, [rbp+70h+pszDest]
0x18004af9b  mov     [rsp+170h+ppszDestEnd], rax; ppszDestEnd
0x18004afa0  call    StringCchCopyNExW
0x18004afa5  xor     edi, edi
0x18004afa7  mov     ebx, eax
0x18004afa9  test    eax, eax
0x18004afab  jns     short loc_18004AFB1
0x18004afad  jmp     short loc_18004AFE1
0x18004afaf  xor     edi, edi
0x18004afb1  mov     rdx, [rbp+70h+cchDest]; cchDest
0x18004afb5  lea     r8, aWinsetupbakSys; "WinSetupBak.sys"
0x18004afbc  mov     rcx, [rbp+70h+pszDest]; pszDest
0x18004afc0  mov     r9d, 0Fh; cchToCopy
0x18004afc6  call    StringCchCopyNW
0x18004afcb  mov     ebx, eax
0x18004afcd  test    eax, eax
0x18004afcf  js      short loc_18004AFE1
0x18004afd1  mov     rax, gs:30h
0x18004afda  mov     [rax+68h], edi
0x18004afdd  jmp     short loc_18004B042
0x18004afdf  xor     edi, edi
0x18004afe1  mov     rcx, gs:60h
0x18004afea  mov     r8, r12; P
0x18004afed  xor     edx, edx; Flags
0x18004afef  mov     rcx, [rcx+30h]; HeapHandle
0x18004aff3  call    cs:__imp_RtlFreeHeap
0x18004aff9  mov     rax, gs:30h
0x18004b002  movzx   ecx, bx
0x18004b005  mov     [rax+68h], ecx
0x18004b008  call    cs:__imp_GetLastError
0x18004b00e  test    eax, eax
0x18004b010  jle     short loc_18004B01A
0x18004b012  movzx   eax, ax
0x18004b015  or      eax, r13d
0x18004b018  test    eax, eax
0x18004b01a  jns     loc_18004BE17
0x18004b020  call    cs:__imp_GetLastError
0x18004b026  mov     esi, eax
0x18004b028  test    eax, eax
0x18004b02a  jle     short loc_18004B032
0x18004b02c  movzx   esi, ax
0x18004b02f  or      esi, r13d
0x18004b032  mov     [rsp+170h+var_F8], rdi
0x18004b037  mov     r12, rdi
0x18004b03a  test    esi, esi
0x18004b03c  js      loc_18004BE1C
0x18004b042  mov     r15, [rbp+70h+lpExistingFileName]
0x18004b046  xor     r9d, r9d; lpData
0x18004b049  mov     rcx, r15; lpExistingFileName
0x18004b04c  mov     dword ptr [rsp+170h+pcchRemaining], edi; dwCopyFlags
0x18004b050  xor     r8d, r8d; lpProgressRoutine
0x18004b053  mov     [rsp+170h+ppszDestEnd], rdi; pbCancel
0x18004b058  mov     rdx, r12; lpNewFileName
0x18004b05b  call    cs:__imp_CopyFileExW
0x18004b061  test    eax, eax
0x18004b063  jnz     short loc_18004B0DC
0x18004b065  call    cs:__imp_GetLastError
0x18004b06b  mov     esi, eax
0x18004b06d  test    eax, eax
0x18004b06f  jle     short loc_18004B077
0x18004b071  movzx   esi, ax
0x18004b074  or      esi, r13d
0x18004b077  call    cs:__imp_GetLastError
0x18004b07d  mov     edi, eax
0x18004b07f  call    cs:__imp_CurrentIP
0x18004b085  mov     r9, r12
0x18004b088  mov     dword ptr [rsp+170h+ppszDestEnd], esi
0x18004b08c  mov     r8, r15
0x18004b08f  lea     rdx, aWsbkinstallFai_13; "WsbkInstall: Failed to copy driver file"...
0x18004b096  mov     ecx, 2000000h; unsigned int
0x18004b09b  mov     rbx, rax
0x18004b09e  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18004b0a3  xor     ecx, ecx
0x18004b0a5  mov     [rsp+170h+var_120], ecx
0x18004b0a9  mov     [rsp+170h+var_128], rcx
0x18004b0ae  lea     rcx, aWsbkinstall; "WsbkInstall"
0x18004b0b5  mov     dword ptr [rsp+170h+lpdwDisposition], edi
0x18004b0b9  mov     [rsp+170h+phkResult], rbx
0x18004b0be  mov     [rsp+170h+lpSecurityAttributes], rcx
0x18004b0c3  lea     rcx, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\deploymen"...
0x18004b0ca  mov     [rsp+170h+pcchRemaining], rcx
0x18004b0cf  mov     dword ptr [rsp+170h+ppszDestEnd], 0D85h
0x18004b0d7  jmp     loc_18004AE0F
0x18004b0dc  lea     rdx, [rsp+170h+lpSubKey]
0x18004b0e1  lea     rcx, aSystem; "SYSTEM"
0x18004b0e8  call    WsbkGetServiceKeyName
0x18004b0ed  mov     r15, [rsp+170h+lpSubKey]
0x18004b0f2  mov     esi, eax
0x18004b0f4  test    eax, eax
0x18004b0f6  js      loc_18004BE94
0x18004b0fc  mov     rbx, 0FFFFFFFF80000002h
0x18004b103  mov     rdx, r15; lpSubKey
0x18004b106  mov     rcx, rbx; hKey
0x18004b109  call    cs:__imp_RegDeleteTreeW
0x18004b10f  test    eax, eax
0x18004b111  jle     short loc_18004B119
0x18004b113  movzx   eax, ax
0x18004b116  or      eax, r13d
0x18004b119  cmp     eax, 80070002h
0x18004b11e  mov     esi, edi
0x18004b120  cmovnz  esi, eax
0x18004b123  test    esi, esi
0x18004b125  jns     short loc_18004B19F
0x18004b127  call    cs:__imp_GetLastError
0x18004b12d  mov     edi, eax
0x18004b12f  call    cs:__imp_CurrentIP
0x18004b135  mov     r9d, esi
0x18004b138  lea     rdx, aWsbkinstallFai_11; "WsbkInstall: Failed to delete service k"...
0x18004b13f  mov     r8, r15
0x18004b142  mov     ecx, 2000000h; unsigned int
0x18004b147  mov     rbx, rax
0x18004b14a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18004b14f  xor     ecx, ecx
0x18004b151  mov     [rsp+170h+var_120], ecx
0x18004b155  mov     [rsp+170h+var_128], rcx
0x18004b15a  lea     rcx, aWsbkinstall; "WsbkInstall"
0x18004b161  mov     dword ptr [rsp+170h+lpdwDisposition], edi
0x18004b165  mov     [rsp+170h+phkResult], rbx
0x18004b16a  mov     [rsp+170h+lpSecurityAttributes], rcx
  ... truncated ...
```
