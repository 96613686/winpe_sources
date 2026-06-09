# CSetupOneSetting::InitializeAndQuery(ushort const *,ushort const *)

- ea: `0x180042554`
- end: `0x180043a03`
- name: `?InitializeAndQuery@CSetupOneSetting@@QEAAJPEBG0@Z`
- size: `5295`
- prototype: `__int64 __fastcall(CSetupOneSetting *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180041400`

## callees

- `0x180001914`
- `0x180009e04`
- `0x18001c5bc`
- `0x18003b990`
- `0x1800406c0`
- `0x180040a3c`
- `0x180040c7c`
- `0x180042554`
- `0x180043c34`
- `0x180044ba0`
- `0x180046b54`
- `0x180047f2c`
- `0x18004f60c`
- `0x1800502c2`
- `0x180050300`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004264d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004264d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180042683`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180042683`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042665`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042665`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004282a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004288d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042cc1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042ead`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800432c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800434ab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004282a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004288d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042cc1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042ead`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800432c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800434ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004284a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004297c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042db5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042f95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800433b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800434e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004284a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004297c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042db5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042f95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800433b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800434e9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800428cd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004293a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042d01`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042d70`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042ee9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042f54`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180043305`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180043370`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800434dd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800428cd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004293a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042d01`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042d70`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042ee9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042f54`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180043305`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180043370`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800434dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800428f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180042953`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180042bb0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180042d2a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180042d8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180042f12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180042f70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004332e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004338c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800436d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800436fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004382f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800438fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800439ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800428f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180042953`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180042bb0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180042d2a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180042d8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180042f12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180042f70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004332e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004338c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800436d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800436fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004382f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800438fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800439ca`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180042904`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180042d3b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180042f23`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004333f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180042904`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180042d3b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180042f23`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004333f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180042961`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180042bbe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180042d9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180042f7e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004339a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800436e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180043708`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004383d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004390a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800439d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180042961`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180042bbe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180042d9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180042f7e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004339a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800436e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180043708`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004383d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004390a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800439d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042852`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004285f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042984`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042dbd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042f9d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800433b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004347e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800434f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004357f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004377f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004384a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043917`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042852`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004285f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042984`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042dbd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042f9d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800433b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004347e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800434f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004357f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004377f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004384a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043917`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004269f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042739`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800427a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042970`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800429ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042a73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042b33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042c32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042da9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042e05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042f89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042fe7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004307f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043097`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800430af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043140`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043158`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043170`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800431e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800433a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043402`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800434ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043585`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043611`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043670`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043718`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043788`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800437a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800437b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043853`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004386b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043883`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043921`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043939`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043951`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004269f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042739`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800427a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042970`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800429ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042a73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042b33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042c32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042da9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042e05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042f89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042fe7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004307f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043097`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800430af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043140`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043158`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043170`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800431e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800433a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043402`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800434ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043585`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043611`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043670`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043718`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043788`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800437a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800437b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043853`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004386b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043883`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043921`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043939`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043951`
- `WDSCORE!CurrentIP` at `0x1800426a7`
- `WDSCORE!CurrentIP` at `0x180042741`

## string_xrefs

- `0x18004263d`: `ntdll.dll`
- `0x18004350d`: `settings-win-ppe.data.microsoft.com`
- `0x180043571`: `settings-win-ppe.data.microsoft.com`
- `0x180043962`: `Onesettings: Failed to get DeviceId from registry: 0x%x`
- `0x180043894`: `Onesettings: Failed to get InstallationType from registry: 0x%x`
- `0x180042cf7`: `InstallationType`
- `0x180042d50`: `InstallationType`
- `0x180042de9`: `platformInstallationType`
- `0x180042e16`: `platformInstallationType`
- `0x1800437c9`: `Onesettings: Failed to get EditionId from registry: 0x%x`
- `0x180043593`: `settings-win.data.microsoft.com`
- `0x1800435f7`: `settings-win.data.microsoft.com`

## pseudocode

```c
// Hidden C++ exception states: #wind=30
__int64 __fastcall CSetupOneSetting::InitializeAndQuery(
        CSetupOneSetting *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  void *v3; // rdi
  ULONGLONG v5; // rax
  ULONGLONG v6; // rax
  ULONGLONG v7; // rax
  char IsWin10TelemetryTypeAllowed; // bl
  HMODULE Library; // rax
  HMODULE v10; // rdi
  FARPROC ProcAddress; // rax
  signed int AppVersionInfo; // esi
  DWORD v13; // edi
  __int64 v14; // rbx
  struct tagLOG_PARTIAL_MSG *v15; // rax
  OneCore::Base::Telemetry::OneSettingsQuery *v16; // rax
  const unsigned __int16 *v17; // rdx
  const unsigned __int16 *v18; // r8
  const unsigned __int16 *v19; // r9
  OneCore::Base::Telemetry::OneSettingsQuery *v20; // rax
  DWORD LastError; // edi
  __int64 v22; // rbx
  struct tagLOG_PARTIAL_MSG *v23; // rax
  DWORD v24; // edi
  __int64 v25; // rbx
  struct tagLOG_PARTIAL_MSG *v26; // rax
  __int64 v27; // r14
  LSTATUS v28; // eax
  DWORD v29; // ebx
  DWORD v30; // ebx
  HANDLE ProcessHeap; // rax
  _WORD *v32; // rax
  HANDLE v33; // rax
  __int64 v34; // rax
  DWORD v35; // edi
  __int64 v36; // rbx
  struct tagLOG_PARTIAL_MSG *v37; // rax
  void *v38; // rbx
  DWORD v39; // edi
  __int64 v40; // rbx
  struct tagLOG_PARTIAL_MSG *v41; // rax
  __int64 v42; // rbx
  __int64 v43; // rax
  DWORD v44; // edi
  __int64 v45; // rbx
  struct tagLOG_PARTIAL_MSG *v46; // rax
  void *v47; // rbx
  HANDLE v48; // rax
  __int64 v49; // rax
  DWORD v50; // edi
  __int64 v51; // rbx
  struct tagLOG_PARTIAL_MSG *v52; // rax
  LSTATUS v53; // eax
  BYTE *v54; // r12
  DWORD v55; // ebx
  DWORD v56; // ebx
  HANDLE v57; // rax
  BYTE *v58; // rax
  HANDLE v59; // rax
  __int64 v60; // rax
  DWORD v61; // edi
  __int64 v62; // rbx
  struct tagLOG_PARTIAL_MSG *v63; // rax
  LSTATUS v64; // eax
  BYTE *v65; // r13
  DWORD v66; // ebx
  DWORD v67; // ebx
  HANDLE v68; // rax
  BYTE *v69; // rax
  HANDLE v70; // rax
  __int64 v71; // rax
  DWORD v72; // edi
  __int64 v73; // rbx
  struct tagLOG_PARTIAL_MSG *v74; // rax
  signed int v75; // eax
  bool v76; // sf
  signed int v77; // eax
  DWORD v78; // edi
  __int64 v79; // rbx
  struct tagLOG_PARTIAL_MSG *v80; // rax
  signed int v81; // eax
  bool v82; // sf
  signed int v83; // eax
  DWORD v84; // edi
  __int64 v85; // rbx
  struct tagLOG_PARTIAL_MSG *v86; // rax
  DWORD v87; // edi
  __int64 v88; // rbx
  struct tagLOG_PARTIAL_MSG *v89; // rax
  __int64 v90; // rax
  LSTATUS v91; // eax
  BYTE *v92; // r12
  DWORD v93; // ebx
  DWORD v94; // ebx
  HANDLE v95; // rax
  BYTE *v96; // rax
  HANDLE v97; // rax
  DWORD v98; // edi
  __int64 v99; // rbx
  struct tagLOG_PARTIAL_MSG *v100; // rax
  LSTATUS Value; // ebx
  DWORD v102; // edi
  __int64 v103; // rbx
  struct tagLOG_PARTIAL_MSG *v104; // rax
  bool v105; // r8
  const unsigned __int16 *v106; // r9
  wchar_t *v107; // rdx
  DWORD v108; // edi
  __int64 v109; // rbx
  struct tagLOG_PARTIAL_MSG *v110; // rax
  CSetupOneSetting *v111; // rbx
  DWORD v112; // edi
  __int64 v113; // rbx
  struct tagLOG_PARTIAL_MSG *v114; // rax
  DWORD v115; // edi
  __int64 v116; // rbx
  struct tagLOG_PARTIAL_MSG *v117; // rax
  HANDLE v118; // rax
  unsigned __int16 *v119; // rbx
  HANDLE v120; // rax
  DWORD v121; // edi
  __int64 v122; // rbx
  struct tagLOG_PARTIAL_MSG *v123; // rax
  signed int v124; // eax
  bool v125; // sf
  signed int v126; // eax
  DWORD v127; // edi
  __int64 v128; // rbx
  struct tagLOG_PARTIAL_MSG *v129; // rax
  HANDLE v130; // rax
  signed int v131; // eax
  bool v132; // sf
  signed int v133; // eax
  DWORD v134; // edi
  __int64 v135; // rbx
  struct tagLOG_PARTIAL_MSG *v136; // rax
  HANDLE v137; // rax
  signed int v138; // eax
  bool v139; // sf
  signed int v140; // eax
  DWORD v141; // edi
  __int64 v142; // rbx
  struct tagLOG_PARTIAL_MSG *v143; // rax
  HANDLE v144; // rax
  const unsigned __int16 *phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  struct _SECURITY_ATTRIBUTES *phkResultb; // [rsp+20h] [rbp-E0h]
  LPDWORD lpcbData; // [rsp+28h] [rbp-D8h]
  DWORD v150; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v151; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD v152; // [rsp+68h] [rbp-98h] BYREF
  DWORD v153; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD cbData; // [rsp+70h] [rbp-90h] BYREF
  DWORD Type; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD v156; // [rsp+78h] [rbp-88h] BYREF
  DWORD v157; // [rsp+7Ch] [rbp-84h] BYREF
  LPVOID v158; // [rsp+80h] [rbp-80h]
  HKEY hKey; // [rsp+88h] [rbp-78h] BYREF
  DWORD pdwReturnedProductType; // [rsp+90h] [rbp-70h] BYREF
  BYTE *v161; // [rsp+98h] [rbp-68h]
  HKEY v162; // [rsp+A0h] [rbp-60h] BYREF
  HKEY v163; // [rsp+A8h] [rbp-58h] BYREF
  HKEY v164; // [rsp+B0h] [rbp-50h] BYREF
  HKEY v165; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v166; // [rsp+C0h] [rbp-40h] BYREF
  LPVOID lpMem; // [rsp+C8h] [rbp-38h] BYREF
  CSetupOneSetting *v168; // [rsp+D0h] [rbp-30h]
  _OSVERSIONINFOEXW VersionInformation; // [rsp+E0h] [rbp-20h] BYREF
  int v170; // [rsp+200h] [rbp+100h] BYREF
  DWORD dwOSMajorVersion[68]; // [rsp+204h] [rbp+104h] BYREF
  unsigned __int16 v172; // [rsp+314h] [rbp+214h]
  unsigned __int16 v173; // [rsp+316h] [rbp+216h]
  unsigned __int16 v174[48]; // [rsp+320h] [rbp+220h] BYREF

  v3 = 0;
  v168 = this;
  v150 = 0;
  v151 = 0;
  v152 = 0;
  v153 = 0;
  lpMem = 0;
  memset_0(dwOSMajorVersion, 0, 0x118u);
  pdwReturnedProductType = 0;
  v166 = 0;
  VersionInformation.dwOSVersionInfoSize = 284;
  *(_OWORD *)&VersionInformation.dwMajorVersion = 0;
  memset_0(VersionInformation.szCSDVersion, 0, sizeof(VersionInformation.szCSDVersion));
  *(_QWORD *)&VersionInformation.wServicePackMajor = 0;
  v5 = VerSetConditionMask(0, 2u, 3u);
  v6 = VerSetConditionMask(v5, 1u, 3u);
  v7 = VerSetConditionMask(v6, 0x20u, 3u);
  *(_QWORD *)&VersionInformation.dwMajorVersion = 10;
  VersionInformation.wServicePackMajor = 0;
  if ( VerifyVersionInfoW(&VersionInformation, 0x23u, v7) )
  {
    IsWin10TelemetryTypeAllowed = TelemetryPermissionsDownlevel::IsWin10TelemetryTypeAllowed();
  }
  else
  {
    IsWin10TelemetryTypeAllowed = 0;
    Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
    v10 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "WinSqmIsOptedInEx");
      if ( ProcAddress )
        IsWin10TelemetryTypeAllowed = ((unsigned int (__fastcall *)(__int64))ProcAddress)(4) == 1;
      FreeLibrary(v10);
    }
    v3 = 0;
  }
  `TelemetryPermissionsDownlevel::IsOptedIntoCore'::`2'::IsOptedIn = IsWin10TelemetryTypeAllowed;
  `TelemetryPermissionsDownlevel::IsOptedIntoCore'::`2'::AlreadyChecked = 1;
  if ( IsWin10TelemetryTypeAllowed )
  {
    v16 = (OneCore::Base::Telemetry::OneSettingsQuery *)operator new(0x750u);
    if ( v16 )
      v20 = (OneCore::Base::Telemetry::OneSettingsQuery *)OneCore::Base::Telemetry::OneSettingsQuery::OneSettingsQuery(
                                                            v16,
                                                            v17,
                                                            v18,
                                                            v19,
                                                            phkResult);
    else
      v20 = 0;
    *((_QWORD *)this + 1) = v20;
    if ( !v20 )
    {
      AppVersionInfo = -2147024882;
      LastError = GetLastError();
      v22 = CurrentIP();
      v23 = ConstructPartialMsgW(50331648, "Onesettings: Failed to initialize onesettings: 0x%x", -2147024882);
      WdsSetupLogMessageW(
        v23,
        0,
        L"D",
        0,
        313,
        L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
        L"CSetupOneSetting::InitializeAndQuery",
        v22,
        LastError,
        0,
        0);
      return (unsigned int)AppVersionInfo;
    }
    AppVersionInfo = OneCore::Base::Telemetry::OneSettingsQuery::AddParameterOsVer(v20, (bool)v17);
    if ( AppVersionInfo < 0 )
    {
      v24 = GetLastError();
      v25 = CurrentIP();
      v26 = ConstructPartialMsgW(50331648, "Onesettings: Failed to AddParameterOsVer: 0x%x", AppVersionInfo);
      WdsSetupLogMessageW(
        v26,
        0,
        L"D",
        0,
        330,
        L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
        L"CSetupOneSetting::InitializeAndQuery",
        v25,
        v24,
        0,
        0);
      return (unsigned int)AppVersionInfo;
    }
    hKey = 0;
    v27 = -1;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\MiniNT", 0, 0x20019u, &hKey) && hKey )
    {
      v158 = 0;
      RegCloseKey(hKey);
      SetLastError(0);
      goto LABEL_38;
    }
    SetLastError(0);
    v162 = 0;
    cbData = 0;
    Type = 0;
    v28 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\SQMClient", 0, 0x20019u, &v162);
    if ( v28 || !v162 )
    {
      SetLastError(v28);
      v158 = 0;
      goto LABEL_170;
    }
    v158 = 0;
    v29 = RegQueryValueExW(v162, L"MachineId", 0, &Type, 0, &cbData);
    if ( !v29 )
    {
      if ( Type - 1 > 1 )
      {
        v29 = 13;
        goto LABEL_31;
      }
      v30 = cbData;
      ProcessHeap = GetProcessHeap();
      v32 = HeapAlloc(ProcessHeap, 8u, v30);
      v158 = v32;
      v3 = v32;
      if ( v32 )
      {
        *v32 = 0;
        v29 = RegQueryValueExW(v162, L"MachineId", 0, 0, (LPBYTE)v32, &cbData);
        if ( !v29 )
        {
          if ( Type - 1 <= 1 )
            goto LABEL_31;
          v29 = 13;
        }
        v33 = GetProcessHeap();
        HeapFree(v33, 0, v3);
        v3 = 0;
        v158 = 0;
      }
      else
      {
        v29 = GetLastError();
      }
    }
LABEL_31:
    RegCloseKey(v162);
    SetLastError(v29);
    if ( v3 )
    {
      v34 = -1;
      do
        ++v34;
      while ( *((_WORD *)v3 + v34) );
      if ( v34 )
      {
        AppVersionInfo = RtlNameValueArray::Append(
                           (RtlNameValueArray *)(*((_QWORD *)this + 1) + 1656LL),
                           L"deviceid",
                           (const unsigned __int16 *)v3);
        if ( AppVersionInfo >= 0 )
        {
LABEL_38:
          AppVersionInfo = pGetAppVersionInfo(&v150, &v151, &v152, &v153, (unsigned __int16 **)&lpMem);
          if ( AppVersionInfo < 0 )
          {
            v39 = GetLastError();
            v40 = CurrentIP();
            v41 = ConstructPartialMsgW(50331648, "Onesettings: Failed to get app version info: 0x%x", AppVersionInfo);
            WdsSetupLogMessageW(
              v41,
              0,
              L"D",
              0,
              362,
              L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
              L"CSetupOneSetting::InitializeAndQuery",
              v40,
              v39,
              0,
              0);
            goto LABEL_46;
          }
          v42 = *((_QWORD *)this + 1);
          LODWORD(lpcbData) = v152;
          LODWORD(phkResulta) = v151;
          AppVersionInfo = StringCchPrintfW(v174, 0x2Cu, L"%d.%d.%d.%d", v150, phkResulta, lpcbData, v153);
          if ( AppVersionInfo < 0 )
            goto LABEL_45;
          v43 = -1;
          do
            ++v43;
          while ( v174[v43] );
          if ( !v43 )
          {
            AppVersionInfo = -2147024809;
LABEL_45:
            v44 = GetLastError();
            v45 = CurrentIP();
            v46 = ConstructPartialMsgW(50331648, "Onesettings: Failed to AddParameterAppVer: 0x%x", AppVersionInfo);
            WdsSetupLogMessageW(
              v46,
              0,
              L"D",
              0,
              369,
              L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
              L"CSetupOneSetting::InitializeAndQuery",
              v45,
              v44,
              0,
              0);
            goto LABEL_46;
          }
          AppVersionInfo = RtlNameValueArray::Append((RtlNameValueArray *)(v42 + 1656), L"appver", v174);
          if ( AppVersionInfo < 0 )
            goto LABEL_45;
          if ( lpMem )
          {
            v49 = -1;
            do
              ++v49;
            while ( *((_WORD *)lpMem + v49) );
            if ( !v49 )
            {
              AppVersionInfo = -2147024809;
LABEL_56:
              v50 = GetLastError();
              v51 = CurrentIP();
              v52 = ConstructPartialMsgW(
                      50331648,
                      "Onesettings: Failed to AddParameter(%s): 0x%x",
                      (const char *)L"appBuildLab",
                      AppVersionInfo);
              WdsSetupLogMessageW(
                v52,
                0,
                L"D",
                0,
                378,
                L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
                L"CSetupOneSetting::InitializeAndQuery",
                v51,
                v50,
                0,
                0);
              goto LABEL_46;
            }
            AppVersionInfo = RtlNameValueArray::Append(
                               (RtlNameValueArray *)(*((_QWORD *)this + 1) + 1656LL),
                               L"appBuildLab",
                               (const unsigned __int16 *)lpMem);
            if ( AppVersionInfo < 0 )
              goto LABEL_56;
          }
          v163 = 0;
          v156 = 0;
          v157 = 0;
          v53 = RegOpenKeyExW(
                  HKEY_LOCAL_MACHINE,
                  L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
                  0,
                  0x20019u,
                  &v163);
          if ( v53 || !v163 )
          {
            SetLastError(v53);
            goto LABEL_161;
          }
          v161 = 0;
          v54 = 0;
          v55 = RegQueryValueExW(v163, L"InstallationType", 0, &v157, 0, &v156);
          if ( !v55 )
          {
            if ( v157 - 1 > 1 )
            {
              v55 = 13;
              goto LABEL_68;
            }
            v56 = v156;
            v57 = GetProcessHeap();
            v58 = (BYTE *)HeapAlloc(v57, 8u, v56);
            v161 = v58;
            v54 = v58;
            if ( v58 )
            {
              *(_WORD *)v58 = 0;
              v55 = RegQueryValueExW(v163, L"InstallationType", 0, 0, v58, &v156);
              if ( !v55 )
              {
                if ( v157 - 1 <= 1 )
                  goto LABEL_68;
                v55 = 13;
              }
              v59 = GetProcessHeap();
              HeapFree(v59, 0, v54);
              v54 = 0;
              v161 = 0;
            }
            else
            {
              v55 = GetLastError();
            }
          }
LABEL_68:
          RegCloseKey(v163);
          SetLastError(v55);
          if ( v54 )
          {
            v60 = -1;
            do
              ++v60;
            while ( *(_WORD *)&v54[2 * v60] );
            if ( !v60 )
            {
              AppVersionInfo = -2147024809;
LABEL_74:
              v61 = GetLastError();
              v62 = CurrentIP();
              v63 = ConstructPartialMsgW(
                      50331648,
                      "Onesettings: Failed to AddParameter(%s): 0x%x",
                      (const char *)L"platformInstallationType",
                      AppVersionInfo);
              WdsSetupLogMessageW(
                v63,
                0,
                L"D",
                0,
                397,
                L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
                L"CSetupOneSetting::InitializeAndQuery",
                v62,
                v61,
                0,
                0);
LABEL_168:
              v137 = GetProcessHeap();
              HeapFree(v137, 0, v54);
LABEL_46:
              v47 = lpMem;
              if ( lpMem )
              {
                v48 = GetProcessHeap();
                HeapFree(v48, 0, v47);
              }
              goto LABEL_177;
            }
            AppVersionInfo = RtlNameValueArray::Append(
                               (RtlNameValueArray *)(*((_QWORD *)this + 1) + 1656LL),
                               L"platformInstallationType",
                               (const unsigned __int16 *)v54);
            if ( AppVersionInfo < 0 )
              goto LABEL_74;
            v164 = 0;
            v150 = 0;
            v151 = 0;
            v64 = RegOpenKeyExW(
                    HKEY_LOCAL_MACHINE,
                    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
                    0,
                    0x20019u,
                    &v164);
            if ( v64 || !v164 )
            {
              SetLastError(v64);
              goto LABEL_152;
            }
            v65 = 0;
            v66 = RegQueryValueExW(v164, L"EditionId", 0, &v151, 0, &v150);
            if ( !v66 )
            {
              if ( v151 - 1 > 1 )
              {
                v66 = 13;
                goto LABEL_86;
              }
              v67 = v150;
              v68 = GetProcessHeap();
              v69 = (BYTE *)HeapAlloc(v68, 8u, v67);
              v65 = v69;
              if ( v69 )
              {
                *(_WORD *)v69 = 0;
                v66 = RegQueryValueExW(v164, L"EditionId", 0, 0, v69, &v150);
                if ( !v66 )
                {
                  if ( v151 - 1 <= 1 )
                    goto LABEL_86;
                  v66 = 13;
                }
                v70 = GetProcessHeap();
                HeapFree(v70, 0, v65);
                v65 = 0;
              }
              else
              {
                v66 = GetLastError();
              }
            }
LABEL_86:
            RegCloseKey(v164);
            SetLastError(v66);
            if ( v65 )
            {
              v71 = -1;
              do
                ++v71;
              while ( *(_WORD *)&v65[2 * v71] );
              if ( !v71 )
              {
                AppVersionInfo = -2147024809;
LABEL_92:
                v72 = GetLastError();
                v73 = CurrentIP();
                v74 = ConstructPartialMsgW(
                        50331648,
                        "Onesettings: Failed to AddParameter(%s): 0x%x",
                        (const char *)L"platformEdition",
                        AppVersionInfo);
                WdsSetupLogMessageW(
                  v74,
                  0,
                  L"D",
                  0,
                  415,
                  L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
                  L"CSetupOneSetting::InitializeAndQuery",
                  v73,
                  v72,
                  0,
                  0);
LABEL_159:
                v130 = GetProcessHeap();
                HeapFree(v130, 0, v65);
                goto LABEL_168;
              }
              AppVersionInfo = RtlNameValueArray::Append(
                                 (RtlNameValueArray *)(*((_QWORD *)this + 1) + 1656LL),
                                 L"platformEdition",
                                 (const unsigned __int16 *)v65);
              if ( AppVersionInfo < 0 )
                goto LABEL_92;
              v170 = 284;
              if ( !(unsigned int)WdsGetVersionEx(&v170) )
              {
                v75 = GetLastError();
                v76 = v75 < 0;
                if ( v75 > 0 )
                  v76 = 1;
                if ( v76 )
                {
                  v77 = GetLastError();
                  AppVersionInfo = v77;
                  if ( v77 > 0 )
                    AppVersionInfo = (unsigned __int16)v77 | 0x80070000;
                }
                else
                {
                  AppVersionInfo = -2147467259;
                }
                v78 = GetLastError();
                v79 = CurrentIP();
                v80 = ConstructPartialMsgW(50331648, "Onesettings: Failed to get OS version: 0x%x", AppVersionInfo);
                WdsSetupLogMessageW(
                  v80,
                  0,
                  L"D",
                  0,
                  426,
                  L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
                  L"CSetupOneSetting::InitializeAndQuery",
                  v79,
                  v78,
                  0,
                  0);
                goto LABEL_159;
              }
              if ( !GetProductInfo(dwOSMajorVersion[0], dwOSMajorVersion[1], v172, v173, &pdwReturnedProductType) )
              {
                v81 = GetLastError();
                v82 = v81 < 0;
                if ( v81 > 0 )
                  v82 = 1;
                if ( v82 )
                {
                  v83 = GetLastError();
                  AppVersionInfo = v83;
                  if ( v83 > 0 )
                    AppVersionInfo = (unsigned __int16)v83 | 0x80070000;
                }
                else
                {
                  AppVersionInfo = -2147467259;
                }
                v84 = GetLastError();
                v85 = CurrentIP();
                v86 = ConstructPartialMsgW(50331648, "Onesettings: Failed to get OS product type: 0x%x", AppVersionInfo);
                WdsSetupLogMessageW(
                  v86,
                  0,
                  L"D",
                  0,
                  433,
                  L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
                  L"CSetupOneSetting::InitializeAndQuery",
                  v85,
                  v84,
                  0,
                  0);
                goto LABEL_159;
              }
              AppVersionInfo = StrAllocatingPrintf(&v166, L"%u", pdwReturnedProductType);
              if ( AppVersionInfo < 0 )
              {
                v87 = GetLastError();
                v88 = CurrentIP();
                v89 = ConstructPartialMsgW(50331648, "Onesettings: Failed to build SKU string: 0x%x", AppVersionInfo);
                WdsSetupLogMessageW(
                  v89,
                  0,
                  L"D",
                  0,
                  440,
                  L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
                  L"CSetupOneSetting::InitializeAndQuery",
                  v88,
                  v87,
                  0,
                  0);
                goto LABEL_147;
              }
              if ( !v166 )
                goto LABEL_149;
              v90 = -1;
              do
                ++v90;
              while ( v166[v90] );
              if ( v90 )
              {
                AppVersionInfo = RtlNameValueArray::Append(
                                   (RtlNameValueArray *)(*((_QWORD *)this + 1) + 1656LL),
                                   L"sku",
                                   v166);
                if ( AppVersionInfo >= 0 )
                {
                  v165 = 0;
                  v152 = 0;
                  v153 = 0;
                  v91 = RegOpenKeyExW(
                          HKEY_LOCAL_MACHINE,
                          L"SOFTWARE\\Microsoft\\WindowsSelfHost\\Applicability",
                          0,
                          0x20019u,
                          &v165);
                  if ( v91 || !v165 )
                  {
                    SetLastError(v91);
                    v92 = 0;
                    goto LABEL_134;
                  }
                  v92 = 0;
                  v93 = RegQueryValueExW(v165, L"Ring", 0, &v153, 0, &v152);
                  if ( !v93 )
                  {
                    if ( v153 - 1 > 1 )
                    {
                      v93 = 13;
                      goto LABEL_127;
                    }
                    v94 = v152;
                    v95 = GetProcessHeap();
                    v96 = (BYTE *)HeapAlloc(v95, 8u, v94);
                    v92 = v96;
                    if ( v96 )
                    {
                      *(_WORD *)v96 = 0;
                      v93 = RegQueryValueExW(v165, L"Ring", 0, 0, v96, &v152);
                      if ( !v93 )
                      {
                        if ( v153 - 1 <= 1 )
                          goto LABEL_127;
                        v93 = 13;
                      }
                      v97 = GetProcessHeap();
                      HeapFree(v97, 0, v92);
                      v92 = 0;
                    }
                    else
                    {
                      v93 = GetLastError();
                    }
                  }
LABEL_127:
                  RegCloseKey(v165);
                  SetLastError(v93);
                  if ( v92 )
                  {
                    do
                      ++v27;
                    while ( *(_WORD *)&v92[2 * v27] );
                    if ( !v27 )
                    {
                      AppVersionInfo = -2147024809;
LABEL_132:
                      v98 = GetLastError();
                      v99 = CurrentIP();
                      v100 = ConstructPartialMsgW(
                               50331648,
                               "Onesettings: Failed to AddParameter(%s): 0x%x",
                               (const char *)L"ring",
                               AppVersionInfo);
                      WdsSetupLogMessageW(
                        v100,
                        0,
                        L"D",
                        0,
                        464,
                        L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
                        L"CSetupOneSetting::InitializeAndQuery",
                        v99,
                        v98,
                        0,
                        0);
LABEL_145:
                      v118 = GetProcessHeap();
                      HeapFree(v118, 0, v92);
LABEL_146:
                      v54 = v161;
                      goto LABEL_147;
                    }
                    AppVersionInfo = RtlNameValueArray::Append(
                                       (RtlNameValueArray *)(*((_QWORD *)this + 1) + 1656LL),
                                       L"ring",
                                       (const unsigned __int16 *)v92);
                    if ( AppVersionInfo < 0 )
                      goto LABEL_132;
                  }
LABEL_134:
                  hKey = 0;
                  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\Setup", 0, 0x20019u, &hKey) || !hKey )
                  {
                    SetLastError(0);
                  }
                  else
                  {
                    Value = RegQueryValueExW(hKey, L"UseOneSettingsTestServer", 0, 0, 0, 0);
                    RegCloseKey(hKey);
                    SetLastError(0);
                    if ( !Value )
                    {
                      v102 = GetLastError();
                      v103 = CurrentIP();
                      v104 = ConstructPartialMsgW(
                               0x4000000,
                               "Onesettings: Querying PPE server %s",
                               (const char *)L"settings-win-ppe.data.microsoft.com");
                      WdsSetupLogMessageW(
                        v104,
                        0,
                        L"D",
                        0,
                        472,
                        L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
                        L"CSetupOneSetting::InitializeAndQuery",
                        v103,
                        v102,
                        0,
                        0);
                      v107 = (wchar_t *)L"settings-win-ppe.data.microsoft.com";
                      goto LABEL_140;
                    }
                  }
                  v108 = GetLastError();
                  v109 = CurrentIP();
                  v110 = ConstructPartialMsgW(
                           0x4000000,
                           "Onesettings: Querying Prod server %s",
                           (const char *)L"settings-win.data.microsoft.com");
                  WdsSetupLogMessageW(
                    v110,
                    0,
                    L"D",
                    0,
                    477,
                    L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
                    L"CSetupOneSetting::InitializeAndQuery",
                    v109,
                    v108,
                    0,
                    0);
                  v107 = (wchar_t *)L"settings-win.data.microsoft.com";
LABEL_140:
                  v111 = v168;
                  AppVersionInfo = OneCore::Base::Telemetry::OneSettingsQuery::Query(
                                     *((OneCore::Base::Telemetry::OneSettingsQuery **)v168 + 1),
                                     v107,
                                     v105,
                                     v106,
                                     phkResultb);
                  if ( AppVersionInfo >= 0 )
                  {
                    if ( !OneCore::Base::Telemetry::OneSettingsQuery::SettingsFresh(*((OneCore::Base::Telemetry::OneSettingsQuery **)v111
                                                                                    + 1)) )
                    {
                      AppVersionInfo = -2147221136;
                      v115 = GetLastError();
                      v116 = CurrentIP();
                      v117 = ConstructPartialMsgW(
                               50331648,
                               "Onesettings: Settings not fresh after query: 0x%x",
                               -2147221136);
                      WdsSetupLogMessageW(
                        v117,
                        0,
                        L"D",
                        0,
                        489,
                        L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
                        L"CSetupOneSetting::InitializeAndQuery",
                        v116,
                        v115,
                        0,
                        0);
                    }
                  }
                  else
                  {
                    v112 = GetLastError();
                    v113 = CurrentIP();
                    v114 = ConstructPartialMsgW(
                             50331648,
                             "Onesettings: Failed to Query Onesettings: 0x%x",
                             AppVersionInfo);
                    WdsSetupLogMessageW(
                      v114,
                      0,
                      L"D",
                      0,
                      482,
                      L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
                      L"CSetupOneSetting::InitializeAndQuery",
                      v113,
                      v112,
                      0,
                      0);
                  }
                  if ( !v92 )
                    goto LABEL_146;
                  goto LABEL_145;
                }
              }
              else
              {
LABEL_149:
                AppVersionInfo = -2147024809;
              }
              v121 = GetLastError();
              v122 = CurrentIP();
              v123 = ConstructPartialMsgW(
                       50331648,
                       "Onesettings: Failed to AddParameter(%s): 0x%x",
                       (const char *)L"sku",
                       AppVersionInfo);
              WdsSetupLogMessageW(
                v123,
                0,
                L"D",
                0,
                447,
                L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
                L"CSetupOneSetting::InitializeAndQuery",
                v122,
                v121,
                0,
                0);
LABEL_147:
              v119 = v166;
              if ( v166 )
              {
                v120 = GetProcessHeap();
                HeapFree(v120, 0, v119);
              }
              goto LABEL_159;
            }
LABEL_152:
            v124 = GetLastError();
            v125 = v124 < 0;
            if ( v124 > 0 )
              v125 = 1;
            if ( v125 )
            {
              v126 = GetLastError();
              AppVersionInfo = v126;
              if ( v126 > 0 )
                AppVersionInfo = (unsigned __int16)v126 | 0x80070000;
            }
            else
            {
              AppVersionInfo = -2147467259;
            }
            v127 = GetLastError();
            v128 = CurrentIP();
            v129 = ConstructPartialMsgW(
                     50331648,
                     "Onesettings: Failed to get EditionId from registry: 0x%x",
                     AppVersionInfo);
            WdsSetupLogMessageW(
              v129,
              0,
              L"D",
              0,
              408,
              L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
              L"CSetupOneSetting::InitializeAndQuery",
              v128,
              v127,
              0,
              0);
            goto LABEL_168;
          }
LABEL_161:
          v131 = GetLastError();
          v132 = v131 < 0;
          if ( v131 > 0 )
            v132 = 1;
          if ( v132 )
          {
            v133 = GetLastError();
            AppVersionInfo = v133;
            if ( v133 > 0 )
              AppVersionInfo = (unsigned __int16)v133 | 0x80070000;
          }
          else
          {
            AppVersionInfo = -2147467259;
          }
          v134 = GetLastError();
          v135 = CurrentIP();
          v136 = ConstructPartialMsgW(
                   50331648,
                   "Onesettings: Failed to get InstallationType from registry: 0x%x",
                   AppVersionInfo);
          WdsSetupLogMessageW(
            v136,
            0,
            L"D",
            0,
            390,
            L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
            L"CSetupOneSetting::InitializeAndQuery",
            v135,
            v134,
            0,
            0);
          goto LABEL_46;
        }
      }
      else
      {
        AppVersionInfo = -2147024809;
      }
      v35 = GetLastError();
      v36 = CurrentIP();
      v37 = ConstructPartialMsgW(50331648, "Onesettings: Failed to AddParameterDeviceId: 0x%x", AppVersionInfo);
      WdsSetupLogMessageW(
        v37,
        0,
        L"D",
        0,
        351,
        L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
        L"CSetupOneSetting::InitializeAndQuery",
        v36,
        v35,
        0,
        0);
      v38 = v158;
      goto LABEL_178;
    }
LABEL_170:
    v138 = GetLastError();
    v139 = v138 < 0;
    if ( v138 > 0 )
      v139 = 1;
    if ( v139 )
    {
      v140 = GetLastError();
      AppVersionInfo = v140;
      if ( v140 > 0 )
        AppVersionInfo = (unsigned __int16)v140 | 0x80070000;
    }
    else
    {
      AppVersionInfo = -2147467259;
    }
    v141 = GetLastError();
    v142 = CurrentIP();
    v143 = ConstructPartialMsgW(50331648, "Onesettings: Failed to get DeviceId from registry: 0x%x", AppVersionInfo);
    WdsSetupLogMessageW(
      v143,
      0,
      L"D",
      0,
      344,
      L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
      L"CSetupOneSetting::InitializeAndQuery",
      v142,
      v141,
      0,
      0);
LABEL_177:
    v38 = v158;
    if ( !v158 )
      return (unsigned int)AppVersionInfo;
LABEL_178:
    v144 = GetProcessHeap();
    HeapFree(v144, 0, v38);
    return (unsigned int)AppVersionInfo;
  }
  AppVersionInfo = 1;
  v13 = GetLastError();
  v14 = CurrentIP();
  v15 = ConstructPartialMsgW(50331648, "Onesettings: Core telemetry is not allowed; skipping");
  WdsSetupLogMessageW(
    v15,
    0,
    L"D",
    0,
    305,
    L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
    L"CSetupOneSetting::InitializeAndQuery",
    v14,
    v13,
    0,
    0);
  return (unsigned int)AppVersionInfo;
}

```

## disassembly

```asm
0x180042554  push    rbp
0x180042556  push    rbx
0x180042557  push    rsi
0x180042558  push    rdi
0x180042559  push    r12
0x18004255b  push    r13
0x18004255d  push    r14
0x18004255f  push    r15
0x180042561  lea     rbp, [rsp-298h]
0x180042569  sub     rsp, 398h
0x180042570  mov     rax, cs:__security_cookie
0x180042577  xor     rax, rsp
0x18004257a  mov     [rbp+2D0h+var_50], rax
0x180042581  xor     edi, edi
0x180042583  mov     [rbp+2D0h+var_300], rcx
0x180042587  mov     r15, rcx
0x18004258a  mov     [rsp+3D0h+var_370], edi
0x18004258e  lea     rcx, [rbp+2D0h+dwOSMajorVersion]; void *
0x180042595  mov     [rsp+3D0h+var_36C], edi
0x180042599  xor     edx, edx; Val
0x18004259b  mov     [rsp+3D0h+var_368], edi
0x18004259f  mov     r8d, 118h; Size
0x1800425a5  mov     [rsp+3D0h+var_364], edi
0x1800425a9  mov     [rbp+2D0h+lpMem], rdi
0x1800425ad  call    memset_0
0x1800425b2  xorps   xmm0, xmm0
0x1800425b5  mov     [rbp+2D0h+pdwReturnedProductType], edi
0x1800425b8  xor     edx, edx; Val
0x1800425ba  mov     [rbp+2D0h+var_310], rdi
0x1800425be  mov     r8d, 100h; Size
0x1800425c4  mov     [rbp+2D0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x1800425cb  lea     rcx, [rbp+2D0h+VersionInformation.szCSDVersion]; void *
0x1800425cf  movups  xmmword ptr [rbp+2D0h+VersionInformation.dwMajorVersion], xmm0
0x1800425d3  call    memset_0
0x1800425d8  mov     r8b, 3; Condition
0x1800425db  mov     qword ptr [rbp+2D0h+VersionInformation.wServicePackMajor], rdi
0x1800425e2  lea     edx, [rdi+2]; TypeMask
0x1800425e5  xor     ecx, ecx; ConditionMask
0x1800425e7  call    cs:__imp_VerSetConditionMask
0x1800425ed  lea     r13d, [rdi+1]
0x1800425f1  mov     r8b, 3; Condition
0x1800425f4  mov     rcx, rax; ConditionMask
0x1800425f7  mov     edx, r13d; TypeMask
0x1800425fa  call    cs:__imp_VerSetConditionMask
0x180042600  mov     r8b, 3; Condition
0x180042603  lea     edx, [rdi+20h]; TypeMask
0x180042606  mov     rcx, rax; ConditionMask
0x180042609  call    cs:__imp_VerSetConditionMask
0x18004260f  lea     edx, [rdi+23h]; dwTypeMask
0x180042612  mov     qword ptr [rbp+2D0h+VersionInformation.dwMajorVersion], 0Ah
0x18004261a  mov     r8, rax; dwlConditionMask
0x18004261d  mov     [rbp+2D0h+VersionInformation.wServicePackMajor], di
0x180042624  lea     rcx, [rbp+2D0h+VersionInformation]; lpVersionInformation
0x180042628  call    cs:__imp_VerifyVersionInfoW
0x18004262e  test    eax, eax
0x180042630  jz      short loc_18004263B
0x180042632  call    ?IsWin10TelemetryTypeAllowed@TelemetryPermissionsDownlevel@@CA_NW4TelemetryType@@@Z; TelemetryPermissionsDownlevel::IsWin10TelemetryTypeAllowed(TelemetryType)
0x180042637  mov     bl, al
0x180042639  jmp     short loc_18004268B
0x18004263b  xor     edx, edx; hFile
0x18004263d  lea     rcx, aNtdllDll_2; "ntdll.dll"
0x180042644  mov     r8d, 800h; dwFlags
0x18004264a  mov     bl, dil
0x18004264d  call    cs:__imp_LoadLibraryExW
0x180042653  mov     rdi, rax
0x180042656  test    rax, rax
0x180042659  jz      short loc_180042689
0x18004265b  lea     rdx, aWinsqmisoptedi; "WinSqmIsOptedInEx"
0x180042662  mov     rcx, rax; hModule
0x180042665  call    cs:__imp_GetProcAddress
0x18004266b  test    rax, rax
0x18004266e  jz      short loc_180042680
0x180042670  mov     ecx, 4
0x180042675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004267a  cmp     eax, r13d
0x18004267d  setz    bl
0x180042680  mov     rcx, rdi; hLibModule
0x180042683  call    cs:__imp_FreeLibrary
0x180042689  xor     edi, edi
0x18004268b  mov     cs:?IsOptedIn@?1??IsOptedIntoCore@TelemetryPermissionsDownlevel@@SA_N_N@Z@4_NA, bl; bool `TelemetryPermissionsDownlevel::IsOptedIntoCore(bool)'::`2'::IsOptedIn
0x180042691  mov     cs:?AlreadyChecked@?1??IsOptedIntoCore@TelemetryPermissionsDownlevel@@SA_N_N@Z@4_NA, r13b; bool `TelemetryPermissionsDownlevel::IsOptedIntoCore(bool)'::`2'::AlreadyChecked
0x180042698  test    bl, bl
0x18004269a  jnz     short loc_18004270F
0x18004269c  mov     esi, r13d
0x18004269f  call    cs:__imp_GetLastError
0x1800426a5  mov     edi, eax
0x1800426a7  call    cs:__imp_CurrentIP
0x1800426ad  lea     rdx, aOnesettingsCor; "Onesettings: Core telemetry is not allo"...
0x1800426b4  mov     ecx, 3000000h; unsigned int
0x1800426b9  mov     rbx, rax
0x1800426bc  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800426c1  xor     ecx, ecx
0x1800426c3  lea     r14, aCsetuponesetti; "CSetupOneSetting::InitializeAndQuery"
0x1800426ca  mov     [rsp+3D0h+var_380], ecx
0x1800426ce  lea     r15, aBaseNtsetupLib; "base\\ntsetup\\lib\\onesettings\\src\\o"...
0x1800426d5  mov     [rsp+3D0h+var_388], rcx
0x1800426da  mov     [rsp+3D0h+var_390], edi
0x1800426de  mov     [rsp+3D0h+var_398], rbx
0x1800426e3  mov     [rsp+3D0h+var_3A0], r14
0x1800426e8  mov     [rsp+3D0h+lpcbData], r15
0x1800426ed  mov     dword ptr [rsp+3D0h+phkResult], 131h
0x1800426f5  xor     r9d, r9d
0x1800426f8  lea     r8, aD; "D"
0x1800426ff  xor     edx, edx
0x180042701  mov     rcx, rax
0x180042704  call    cs:__imp_WdsSetupLogMessageW
0x18004270a  jmp     loc_1800439DE
0x18004270f  mov     ecx, 750h; Size
0x180042714  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180042719  test    rax, rax
0x18004271c  jz      short loc_180042728
0x18004271e  mov     rcx, rax; this
0x180042721  call    ??0OneSettingsQuery@Telemetry@Base@OneCore@@QEAA@PEBG000@Z; OneCore::Base::Telemetry::OneSettingsQuery::OneSettingsQuery(ushort const *,ushort const *,ushort const *,ushort const *)
0x180042726  jmp     short loc_18004272B
0x180042728  mov     rax, rdi
0x18004272b  mov     [r15+8], rax
0x18004272f  test    rax, rax
0x180042732  jnz     short loc_180042797
0x180042734  mov     esi, 8007000Eh
0x180042739  call    cs:__imp_GetLastError
0x18004273f  mov     edi, eax
0x180042741  call    cs:__imp_CurrentIP
0x180042747  mov     r8d, esi
0x18004274a  lea     rdx, aOnesettingsFai_2; "Onesettings: Failed to initialize onese"...
0x180042751  mov     ecx, 3000000h; unsigned int
0x180042756  mov     rbx, rax
0x180042759  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18004275e  xor     ecx, ecx
0x180042760  lea     r14, aCsetuponesetti; "CSetupOneSetting::InitializeAndQuery"
0x180042767  mov     [rsp+3D0h+var_380], ecx
0x18004276b  lea     r15, aBaseNtsetupLib; "base\\ntsetup\\lib\\onesettings\\src\\o"...
0x180042772  mov     [rsp+3D0h+var_388], rcx
0x180042777  mov     [rsp+3D0h+var_390], edi
0x18004277b  mov     [rsp+3D0h+var_398], rbx
0x180042780  mov     [rsp+3D0h+var_3A0], r14
0x180042785  mov     [rsp+3D0h+lpcbData], r15
0x18004278a  mov     dword ptr [rsp+3D0h+phkResult], 139h
0x180042792  jmp     loc_1800426F5
0x180042797  mov     rcx, rax; this
0x18004279a  call    ?AddParameterOsVer@OneSettingsQuery@Telemetry@Base@OneCore@@QEAAJ_N@Z; OneCore::Base::Telemetry::OneSettingsQuery::AddParameterOsVer(bool)
0x18004279f  mov     esi, eax
0x1800427a1  test    eax, eax
0x1800427a3  jns     short loc_180042803
0x1800427a5  call    cs:__imp_GetLastError
0x1800427ab  mov     edi, eax
0x1800427ad  call    cs:__imp_CurrentIP
0x1800427b3  mov     r8d, esi
0x1800427b6  lea     rdx, aOnesettingsFai_14; "Onesettings: Failed to AddParameterOsVe"...
0x1800427bd  mov     ecx, 3000000h; unsigned int
0x1800427c2  mov     rbx, rax
0x1800427c5  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800427ca  xor     ecx, ecx
0x1800427cc  lea     r14, aCsetuponesetti; "CSetupOneSetting::InitializeAndQuery"
0x1800427d3  mov     [rsp+3D0h+var_380], ecx
0x1800427d7  lea     r15, aBaseNtsetupLib; "base\\ntsetup\\lib\\onesettings\\src\\o"...
0x1800427de  mov     [rsp+3D0h+var_388], rcx
0x1800427e3  mov     [rsp+3D0h+var_390], edi
0x1800427e7  mov     [rsp+3D0h+var_398], rbx
0x1800427ec  mov     [rsp+3D0h+var_3A0], r14
0x1800427f1  mov     [rsp+3D0h+lpcbData], r15
0x1800427f6  mov     dword ptr [rsp+3D0h+phkResult], 14Ah
0x1800427fe  jmp     loc_1800426F5
0x180042803  lea     rax, [rbp+2D0h+hKey]
0x180042807  mov     [rbp+2D0h+hKey], rdi
0x18004280b  mov     r12, 0FFFFFFFF80000002h
0x180042812  mov     [rsp+3D0h+phkResult], rax; phkResult
0x180042817  mov     rcx, r12; hKey
0x18004281a  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Min"...
0x180042821  mov     r9d, 20019h; samDesired
0x180042827  xor     r8d, r8d; ulOptions
0x18004282a  call    cs:__imp_RegOpenKeyExW
0x180042830  or      r14, 0FFFFFFFFFFFFFFFFh
0x180042834  mov     esi, 0Dh
0x180042839  test    eax, eax
0x18004283b  jnz     short loc_18004285D
0x18004283d  mov     rcx, [rbp+2D0h+hKey]; hKey
0x180042841  test    rcx, rcx
0x180042844  jz      short loc_18004285D
0x180042846  mov     [rbp+2D0h+var_350], rdi
0x18004284a  call    cs:__imp_RegCloseKey
0x180042850  xor     ecx, ecx; dwErrCode
0x180042852  call    cs:__imp_SetLastError
0x180042858  jmp     loc_180042A4B
0x18004285d  xor     ecx, ecx; dwErrCode
0x18004285f  call    cs:__imp_SetLastError
0x180042865  lea     rax, [rbp+2D0h+var_330]
0x180042869  mov     [rbp+2D0h+var_330], rdi
0x18004286d  mov     r9d, 20019h; samDesired
0x180042873  mov     [rsp+3D0h+phkResult], rax; phkResult
0x180042878  xor     r8d, r8d; ulOptions
0x18004287b  mov     [rsp+3D0h+cbData], edi
0x18004287f  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\SQMClient"
0x180042886  mov     [rsp+3D0h+Type], edi
0x18004288a  mov     rcx, r12; hKey
0x18004288d  call    cs:__imp_RegOpenKeyExW
0x180042893  test    eax, eax
0x180042895  jnz     loc_180043915
0x18004289b  mov     rcx, [rbp+2D0h+var_330]; hKey
0x18004289f  test    rcx, rcx
0x1800428a2  jz      loc_180043915
0x1800428a8  lea     rax, [rsp+3D0h+cbData]
0x1800428ad  mov     [rbp+2D0h+var_350], rdi
0x1800428b1  mov     [rsp+3D0h+lpcbData], rax; lpcbData
0x1800428b6  lea     r9, [rsp+3D0h+Type]; lpType
0x1800428bb  xor     r12d, r12d
0x1800428be  lea     rdx, aMachineid; "MachineId"
0x1800428c5  xor     r8d, r8d; lpReserved
0x1800428c8  mov     [rsp+3D0h+phkResult], r12; lpData
0x1800428cd  call    cs:__imp_RegQueryValueExW
0x1800428d3  mov     ebx, eax
0x1800428d5  test    eax, eax
0x1800428d7  jnz     loc_180042978
0x1800428dd  mov     eax, [rsp+3D0h+Type]
0x1800428e1  dec     eax
0x1800428e3  cmp     eax, r13d
0x1800428e6  jbe     short loc_1800428EF
0x1800428e8  mov     ebx, esi
0x1800428ea  jmp     loc_180042978
0x1800428ef  mov     ebx, [rsp+3D0h+cbData]
0x1800428f3  call    cs:__imp_GetProcessHeap
0x1800428f9  mov     r8d, ebx; dwBytes
0x1800428fc  mov     edx, 8; dwFlags
0x180042901  mov     rcx, rax; hHeap
0x180042904  call    cs:__imp_HeapAlloc
0x18004290a  mov     [rbp+2D0h+var_350], rax
0x18004290e  mov     rdi, rax
0x180042911  test    rax, rax
0x180042914  jz      short loc_180042970
0x180042916  mov     [rax], r12w
0x18004291a  lea     rdx, aMachineid; "MachineId"
0x180042921  mov     rcx, [rbp+2D0h+var_330]; hKey
0x180042925  lea     rax, [rsp+3D0h+cbData]
0x18004292a  mov     [rsp+3D0h+lpcbData], rax; lpcbData
0x18004292f  xor     r9d, r9d; lpType
0x180042932  xor     r8d, r8d; lpReserved
0x180042935  mov     [rsp+3D0h+phkResult], rdi; lpData
0x18004293a  call    cs:__imp_RegQueryValueExW
0x180042940  mov     ebx, eax
0x180042942  test    eax, eax
0x180042944  jnz     short loc_180042953
0x180042946  mov     eax, [rsp+3D0h+Type]
0x18004294a  dec     eax
0x18004294c  cmp     eax, r13d
0x18004294f  jbe     short loc_180042978
0x180042951  mov     ebx, esi
0x180042953  call    cs:__imp_GetProcessHeap
0x180042959  mov     r8, rdi; lpMem
0x18004295c  xor     edx, edx; dwFlags
0x18004295e  mov     rcx, rax; hHeap
0x180042961  call    cs:__imp_HeapFree
0x180042967  mov     rdi, r12
0x18004296a  mov     [rbp+2D0h+var_350], r12
0x18004296e  jmp     short loc_180042978
0x180042970  call    cs:__imp_GetLastError
0x180042976  mov     ebx, eax
0x180042978  mov     rcx, [rbp+2D0h+var_330]; hKey
0x18004297c  call    cs:__imp_RegCloseKey
0x180042982  mov     ecx, ebx; dwErrCode
0x180042984  call    cs:__imp_SetLastError
0x18004298a  test    rdi, rdi
0x18004298d  jz      loc_180043921
0x180042993  mov     rax, r14
0x180042996  inc     rax
0x180042999  cmp     [rdi+rax*2], r12w
0x18004299e  jnz     short loc_180042996
0x1800429a0  test    rax, rax
0x1800429a3  jnz     short loc_1800429AC
0x1800429a5  mov     esi, 80070057h
0x1800429aa  jmp     short loc_1800429CE
0x1800429ac  mov     rcx, [r15+8]
0x1800429b0  lea     rdx, aDeviceid; "deviceid"
0x1800429b7  add     rcx, 678h; this
0x1800429be  mov     r8, rdi; unsigned __int16 *
0x1800429c1  call    ?Append@RtlNameValueArray@@QEAAJPEBG0@Z; RtlNameValueArray::Append(ushort const *,ushort const *)
0x1800429c6  xor     edi, edi
0x1800429c8  mov     esi, eax
0x1800429ca  test    eax, eax
0x1800429cc  jns     short loc_180042A44
0x1800429ce  call    cs:__imp_GetLastError
0x1800429d4  mov     edi, eax
0x1800429d6  call    cs:__imp_CurrentIP
0x1800429dc  mov     r8d, esi
0x1800429df  lea     rdx, aOnesettingsFai_8; "Onesettings: Failed to AddParameterDevi"...
0x1800429e6  mov     ecx, 3000000h; unsigned int
0x1800429eb  mov     rbx, rax
0x1800429ee  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800429f3  mov     [rsp+3D0h+var_380], r12d
0x1800429f8  lea     r14, aCsetuponesetti; "CSetupOneSetting::InitializeAndQuery"
0x1800429ff  mov     [rsp+3D0h+var_388], r12
0x180042a04  lea     r15, aBaseNtsetupLib; "base\\ntsetup\\lib\\onesettings\\src\\o"...
0x180042a0b  mov     [rsp+3D0h+var_390], edi
0x180042a0f  lea     r8, aD; "D"
0x180042a16  mov     [rsp+3D0h+var_398], rbx
0x180042a1b  xor     r9d, r9d
0x180042a1e  mov     [rsp+3D0h+var_3A0], r14
0x180042a23  xor     edx, edx
0x180042a25  mov     [rsp+3D0h+lpcbData], r15
0x180042a2a  mov     rcx, rax
0x180042a2d  mov     dword ptr [rsp+3D0h+phkResult], 15Fh
0x180042a35  call    cs:__imp_WdsSetupLogMessageW
  ... truncated ...
```
