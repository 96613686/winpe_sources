# CAudioResourceManager::CreateInternalLoopbackStream(ushort const *,__int64,bool,IStreamGroupProxy *,IBridgeStreamInstanceProxy * *)

- ea: `0x1800c1ca4`
- end: `0x1800c4305`
- name: `?CreateInternalLoopbackStream@CAudioResourceManager@@IEAAJPEBG_J_NPEAUIStreamGroupProxy@@PEAPEAUIBridgeStreamInstanceProxy@@@Z`
- size: `9825`
- prototype: `int(CAudioResourceManager *__hidden this, const unsigned __int16 *, __int64, bool, struct IStreamGroupProxy *, struct IBridgeStreamInstanceProxy **)`
- caller_count: `1`
- callee_count: `42`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800c1ab4`

## callees

- `0x180001658`
- `0x180002c28`
- `0x1800088dc`
- `0x180008df0`
- `0x180008e58`
- `0x180009714`
- `0x18000accc`
- `0x18000cae0`
- `0x18000e154`
- `0x1800126bc`
- `0x18001b3d0`
- `0x18001df60`
- `0x18001e7dc`
- `0x18001eb4c`
- `0x180025d64`
- `0x180031778`
- `0x180031b20`
- `0x1800384fc`
- `0x1800423cc`
- `0x180045068`
- `0x180046c3c`
- `0x18004a38c`
- `0x18004f78c`
- `0x180055f44`
- `0x18005b03c`
- `0x1800618c0`
- `0x1800621b0`
- `0x180062e9c`
- `0x1800632c0`
- `0x180073310`
- `0x180079324`
- `0x1800a5600`
- `0x1800a7de4`
- `0x1800a9a10`
- `0x1800b139c`
- `0x1800b724c`
- `0x1800bdf64`
- `0x1800c1ca4`
- `0x1800cf8c0`
- `0x1800d0764`
- `0x1800e2e00`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c323c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3322`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3331`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3578`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3587`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3723`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3732`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3934`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3943`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3ab5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3ac4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3ccf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3cde`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3e79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3e88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c40e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c40f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c323c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3322`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3331`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3578`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3587`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3723`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3732`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3934`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3943`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3ab5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3ac4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3ccf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3cde`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3e79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3e88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c40e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c40f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800c2dc6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800c2dc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c21d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c21f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c220e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c222a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2acf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2aeb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2b07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2b23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2cef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2d0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2d27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2d43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2f00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2f1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2f38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2f54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c302f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c304b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3067`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3083`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3168`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3184`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c31a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c31bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3393`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c33af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c33cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c33e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c35e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3605`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3621`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c363d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3794`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c37b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c37cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c37e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c39a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c39c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c39dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c39f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3b26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3b42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3b5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3b7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3d40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3d5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3d78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3d94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3eea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3f06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3f22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3f3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c416e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c418a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c41a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c41c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c21d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c21f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c220e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c222a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2acf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2aeb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2b07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2b23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2cef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2d0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2d27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2d43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2f00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2f1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2f38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2f54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c302f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c304b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3067`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3083`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3168`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3184`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c31a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c31bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3393`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c33af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c33cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c33e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c35e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3605`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3621`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c363d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3794`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c37b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c37cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c37e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c39a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c39c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c39dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c39f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3b26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3b42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3b5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3b7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3d40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3d5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3d78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3d94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3eea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3f06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3f22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3f3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c416e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c418a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c41a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c41c2`

## string_xrefs

- `0x1800c1d49`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800c1deb`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800c1fab`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800c21af`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800c2aa8`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800c2cba`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800c2ebd`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800c2fde`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800c30fb`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800c32f5`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800c354b`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800c36e8`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800c38eb`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800c3a6c`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800c3c86`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800c3e30`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=26 #try_helpers=1
__int64 __fastcall CAudioResourceManager::CreateInternalLoopbackStream(
        CAudioResourceManager *this,
        unsigned __int16 *a2,
        __int64 a3,
        char a4,
        struct IStreamGroupProxy *a5,
        struct IBridgeStreamInstanceProxy **a6)
{
  int EndpointCharacteristicsDescriptor; // eax
  unsigned int v8; // ebx
  char v10; // r14
  unsigned int v11; // r13d
  CAudioPumpDspResourceTracker *v12; // rcx
  int v13; // eax
  unsigned int v14; // ebx
  __int64 AudioPumpDspResourceTokenFromTokenList; // rax
  struct IUnknown *v16; // rdi
  BOOL v17; // r9d
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 ConnectorTypeForStream; // esi
  int v19; // eax
  unsigned int v20; // ebx
  GUID v21; // xmm6
  struct _GUID v22; // xmm7
  int v23; // ebx
  void *v24; // rcx
  struct tWAVEFORMATEX *v25; // rcx
  void *v26; // rcx
  void *v27; // rcx
  _DWORD *v28; // rdi
  _DWORD *v29; // r8
  int v30; // r8d
  int v31; // r9d
  _DWORD *v32; // r12
  _DWORD *v33; // r8
  int v34; // r8d
  int v35; // r9d
  unsigned int v36; // ecx
  _DWORD *v37; // r8
  int v38; // r8d
  int v39; // r9d
  _DWORD *v40; // r8
  int v41; // r8d
  int v42; // r9d
  unsigned int v43; // ecx
  _DWORD *v44; // r8
  int v45; // r8d
  int v46; // r9d
  _DWORD *v47; // r8
  int v48; // r8d
  int v49; // r9d
  struct tWAVEFORMATEX *v50; // r12
  _DWORD *v51; // r8
  int v52; // r8d
  int v53; // r9d
  unsigned int wFormatTag; // ecx
  _DWORD *v55; // r8
  int v56; // r8d
  int v57; // r9d
  _DWORD *v58; // r8
  int v59; // r8d
  int v60; // r9d
  _DWORD *v61; // r12
  _DWORD *v62; // r8
  int v63; // r8d
  int v64; // r9d
  unsigned int v65; // ecx
  _DWORD *v66; // r8
  int v67; // r8d
  int v68; // r9d
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 v69; // r12d
  int SharedModeEnginePeriodicity; // eax
  void *v71; // rcx
  struct tWAVEFORMATEX *v72; // rcx
  void *v73; // rcx
  void *v74; // rcx
  double v75; // xmm1_8
  int v76; // eax
  void *v77; // rcx
  struct tWAVEFORMATEX *v78; // rcx
  void *v79; // rcx
  void *v80; // rcx
  unsigned __int16 *v81; // rdi
  int v82; // eax
  CEndpointStoreCache *v83; // rcx
  int v84; // r8d
  void *v85; // rcx
  struct tWAVEFORMATEX *v86; // rcx
  void *v87; // rcx
  void *v88; // rcx
  int EndpointStore; // eax
  void *v90; // rcx
  struct tWAVEFORMATEX *v91; // rcx
  void *v92; // rcx
  void *v93; // rcx
  int CustomResourceManagerService; // eax
  void *v95; // rcx
  struct tWAVEFORMATEX *v96; // rcx
  void *v97; // rcx
  void *v98; // rcx
  struct _RTL_CRITICAL_SECTION *v99; // rbx
  __int64 v100; // rax
  struct CEndpointStore *v101; // rdi
  __int64 (__fastcall *v102)(struct IDeviceGraphManager *, CEndpointCharacteristics **, _QWORD, __int64); // rsi
  int v103; // eax
  int v104; // esi
  void *v105; // rcx
  struct tWAVEFORMATEX *v106; // rcx
  void *v107; // rcx
  void *v108; // rcx
  int *v109; // r8
  int v110; // r9d
  int v111; // ecx
  void *v112; // rcx
  struct tWAVEFORMATEX *v113; // rcx
  void *v114; // rcx
  void *v115; // rcx
  LPVOID *v116; // r14
  __int64 (__fastcall *v117)(LPVOID *, __int64 **); // rsi
  int v118; // eax
  void *v119; // rcx
  struct tWAVEFORMATEX *v120; // rcx
  void *v121; // rcx
  void *v122; // rcx
  __int64 *v123; // rcx
  void *v124; // rcx
  struct tWAVEFORMATEX *v125; // rcx
  void *v126; // rcx
  void *v127; // rcx
  void *v128; // rcx
  struct tWAVEFORMATEX *v129; // rcx
  void *v130; // rcx
  void *v131; // rcx
  int SaDeviceForSharedStream; // eax
  int v133; // ecx
  int v134; // r8d
  unsigned int v135; // edi
  void *v136; // rcx
  struct tWAVEFORMATEX *v137; // rcx
  void *v138; // rcx
  void *v139; // rcx
  int v140; // eax
  int v141; // ecx
  int v142; // r8d
  void *v143; // rcx
  struct tWAVEFORMATEX *v144; // rcx
  void *v145; // rcx
  void *v146; // rcx
  __int64 v147; // rax
  int v148; // edi
  _DWORD *v149; // rdi
  int v150; // r8d
  int v151; // r9d
  struct IBridgeStreamInstanceProxy *v152; // rax
  void *v153; // rcx
  struct tWAVEFORMATEX *v154; // rcx
  void *v155; // rcx
  void *v156; // rcx
  _DWORD *v157; // r8
  int v158; // r8d
  int v159; // r9d
  int v160; // [rsp+20h] [rbp-338h]
  int v161; // [rsp+20h] [rbp-338h]
  int v162; // [rsp+20h] [rbp-338h]
  int v163; // [rsp+20h] [rbp-338h]
  int v164; // [rsp+20h] [rbp-338h]
  LPVOID pv; // [rsp+F0h] [rbp-268h] BYREF
  LPVOID v166; // [rsp+F8h] [rbp-260h] BYREF
  struct tWAVEFORMATEX *Src; // [rsp+100h] [rbp-258h] BYREF
  LPVOID v168; // [rsp+108h] [rbp-250h] BYREF
  __int64 *v169; // [rsp+110h] [rbp-248h] BYREF
  struct IStreamGroupProxy *v170; // [rsp+118h] [rbp-240h] BYREF
  void *v171; // [rsp+120h] [rbp-238h] BYREF
  const wchar_t *v172; // [rsp+128h] [rbp-230h] BYREF
  struct IUnknown *v173; // [rsp+130h] [rbp-228h] BYREF
  __int64 v174; // [rsp+138h] [rbp-220h] BYREF
  char v175; // [rsp+140h] [rbp-218h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+148h] [rbp-210h] BYREF
  __int64 v177; // [rsp+150h] [rbp-208h] BYREF
  LPVOID *v178; // [rsp+158h] [rbp-200h] BYREF
  struct tWAVEFORMATEX *v179; // [rsp+160h] [rbp-1F8h] BYREF
  char v180; // [rsp+168h] [rbp-1F0h]
  _QWORD v181[2]; // [rsp+170h] [rbp-1E8h] BYREF
  struct _GUID Buf1; // [rsp+180h] [rbp-1D8h] BYREF
  CEndpointCharacteristics *v183[2]; // [rsp+190h] [rbp-1C8h] BYREF
  __int64 v184; // [rsp+1A0h] [rbp-1B8h]
  __int128 v185; // [rsp+1A8h] [rbp-1B0h] BYREF
  __int64 v186; // [rsp+1B8h] [rbp-1A0h]
  struct CEndpointStore *v187[2]; // [rsp+1C0h] [rbp-198h] BYREF
  struct _GUID v188; // [rsp+1D0h] [rbp-188h] BYREF
  LPCRITICAL_SECTION v189[2]; // [rsp+1E0h] [rbp-178h] BYREF
  __int64 v190; // [rsp+1F0h] [rbp-168h] BYREF
  void *p_pv; // [rsp+1F8h] [rbp-160h] BYREF
  struct tWAVEFORMATEX *v192; // [rsp+200h] [rbp-158h] BYREF
  char v193; // [rsp+208h] [rbp-150h]
  struct IStreamGroupProxy *v194; // [rsp+210h] [rbp-148h] BYREF
  unsigned __int16 *v195; // [rsp+218h] [rbp-140h]
  struct IBridgeStreamInstanceProxy **v196; // [rsp+220h] [rbp-138h]
  LPVOID *v197; // [rsp+228h] [rbp-130h] BYREF
  struct tWAVEFORMATEX *v198; // [rsp+230h] [rbp-128h] BYREF
  char v199; // [rsp+238h] [rbp-120h]
  _DWORD v200[6]; // [rsp+240h] [rbp-118h] BYREF
  __int64 v201; // [rsp+258h] [rbp-100h]
  struct _GUID v202; // [rsp+260h] [rbp-F8h]
  __int64 v203; // [rsp+270h] [rbp-E8h]
  unsigned __int16 *v204; // [rsp+278h] [rbp-E0h]
  struct tWAVEFORMATEX **p_Src; // [rsp+290h] [rbp-C8h] BYREF
  struct tWAVEFORMATEX *v206; // [rsp+298h] [rbp-C0h] BYREF
  _BYTE v207[24]; // [rsp+2A0h] [rbp-B8h]
  struct IStreamGroupProxy **v208; // [rsp+2B8h] [rbp-A0h]
  __int128 *v209; // [rsp+2C0h] [rbp-98h]
  __int64 *v210; // [rsp+2C8h] [rbp-90h]
  struct _GUID v211; // [rsp+2D0h] [rbp-88h] BYREF
  _QWORD v212[2]; // [rsp+2E0h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+358h] [rbp+0h]

  v195 = a2;
  v212[0] = this;
  v190 = a3;
  v194 = a5;
  v196 = a6;
  *(_OWORD *)v183 = 0;
  v184 = 0;
  EndpointCharacteristicsDescriptor = GetEndpointCharacteristicsDescriptor(
                                        a2,
                                        0,
                                        (struct EndpointCharacteristicsDescriptor *)v183);
  v8 = EndpointCharacteristicsDescriptor;
  if ( EndpointCharacteristicsDescriptor < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC90,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)EndpointCharacteristicsDescriptor,
      v160);
    EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)v183);
    return v8;
  }
  v10 = *((_BYTE *)v183[0] + 264);
  v175 = v10;
  if ( !a4 || (v11 = 3, !v10) )
    v11 = 2;
  v185 = 0;
  v186 = 0;
  v173 = 0;
  wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v173);
  v13 = CAudioPumpDspResourceTracker::AcquireAudioPumpDspTokenForEndpoint(
          v12,
          (struct EndpointCharacteristicsDescriptor *)v183,
          &v173);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC9C,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v13,
      v160);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v173);
    std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v185);
    EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)v183);
    return v14;
  }
  if ( *((_QWORD *)&v185 + 1) == v186 )
  {
    std::vector<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>>::_Emplace_reallocate<wil::com_ptr_t<IUnknown,wil::err_returncode_policy> const &>(
      &v185,
      *((_QWORD *)&v185 + 1),
      &v173);
  }
  else
  {
    wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>(
      *((_QWORD *)&v185 + 1),
      v173);
    *((_QWORD *)&v185 + 1) += 8LL;
  }
  v211 = GUID_00000000_0000_0000_0000_000000000000;
  v188 = GUID_00000000_0000_0000_0000_000000000000;
  Buf1 = GUID_00000000_0000_0000_0000_000000000000;
  *(GUID *)v187 = GUID_00000000_0000_0000_0000_000000000000;
  *(GUID *)v189 = GUID_00000000_0000_0000_0000_000000000000;
  AudioPumpDspResourceTokenFromTokenList = TryGetAudioPumpDspResourceTokenFromTokenList(&v178, &v185);
  v16 = *(struct IUnknown **)(AudioPumpDspResourceTokenFromTokenList + 8);
  *(_QWORD *)(AudioPumpDspResourceTokenFromTokenList + 8) = 0;
  v172 = (const wchar_t *)v16;
  AudioPumpDspResourceTokenPair::~AudioPumpDspResourceTokenPair((AudioPumpDspResourceTokenPair *)&v178);
  v17 = a4 && v10;
  ConnectorTypeForStream = GetConnectorTypeForStream(
                             (struct EndpointCharacteristicsDescriptor *)v183,
                             0x20002u,
                             AUDCLNT_SHAREMODE_SHARED,
                             v17,
                             0,
                             0,
                             v16);
  LODWORD(lpCriticalSection) = ConnectorTypeForStream;
  v19 = DeriveAudioProcessingModeConfiguration(0, 0, 0, v183);
  v20 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCBC,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v19,
      v11);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v172);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v173);
    std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v185);
    EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)v183);
    return v20;
  }
  if ( v16 )
    v21 = GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf;
  else
    v21 = v211;
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v172);
  v166 = 0;
  v168 = 0;
  Src = 0;
  pv = 0;
  p_pv = &pv;
  v192 = 0;
  v193 = 1;
  p_Src = &Src;
  v206 = 0;
  v207[0] = 1;
  v197 = &v168;
  v198 = 0;
  v199 = 1;
  v178 = &v166;
  v179 = 0;
  v180 = 1;
  v211 = v21;
  v22 = v188;
  v23 = DeriveDeviceGraphFormatsForStream(
          (struct EndpointCharacteristicsDescriptor *)v183,
          0,
          ConnectorTypeForStream,
          AUDCLNT_SHAREMODE_SHARED,
          0,
          &Buf1,
          &v188,
          &v211,
          0,
          &v179,
          &v198,
          &v206,
          &v192);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v178);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v197);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_Src);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCD2,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v23,
      v161);
    v24 = pv;
    pv = 0;
    if ( v24 )
      CoTaskMemFree(v24);
    v25 = Src;
    Src = 0;
    if ( v25 )
      CoTaskMemFree(v25);
    v26 = v168;
    v168 = 0;
    if ( v26 )
      CoTaskMemFree(v26);
    v27 = v166;
    v166 = 0;
    if ( v27 )
      CoTaskMemFree(v27);
LABEL_124:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v173);
    std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v185);
    EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)v183);
    return (unsigned int)v23;
  }
  v28 = v166;
  if ( v166 )
  {
    v36 = *(unsigned __int16 *)v166;
    if ( (_WORD)v36 == 0xFFFE )
    {
      v40 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v40 > 4u && (unsigned __int8)tlgKeywordOn(v40, 512) )
      {
        LODWORD(v169) = v28[5];
        *(_QWORD *)&Buf1.Data1 = v28 + 6;
        LODWORD(v171) = *((_DWORD *)v166 + 2);
        LODWORD(v178) = *((_DWORD *)v166 + 1);
        LOWORD(v170) = *((_WORD *)v166 + 1);
        v172 = L"WAVEFORMATEXTENSIBLE";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v41,
          (unsigned int)&unk_1801A18AC,
          v41,
          v42,
          (__int64)&v172,
          (__int64)&v170,
          (__int64)&v178,
          (__int64)&v171,
          (__int64)&Buf1,
          (__int64)&v169);
      }
    }
    else
    {
      *(_QWORD *)&v211.Data2 = *(_QWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data2;
      *(_DWORD *)&v211.Data4[4] = *(_DWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data4[4];
      v211.Data1 = v36;
      v37 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v37 > 4u && (unsigned __int8)tlgKeywordOn(v37, 512) )
      {
        *(_QWORD *)&Buf1.Data1 = &v211;
        LODWORD(v171) = *((_DWORD *)v166 + 2);
        LODWORD(v169) = *((_DWORD *)v166 + 1);
        LOWORD(v170) = *((_WORD *)v166 + 1);
        v172 = L"WAVEFORMATEX";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          v38,
          (unsigned int)&unk_1801A1950,
          v38,
          v39,
          (__int64)&v172,
          (__int64)&v170,
          (__int64)&v169,
          (__int64)&v171,
          (__int64)&Buf1);
      }
    }
  }
  else
  {
    v29 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
    if ( *v29 > 4u && (unsigned __int8)tlgKeywordOn(v29, 512) )
    {
      LODWORD(v170) = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v30,
        (unsigned int)&unk_1801A19E7,
        v30,
        v31,
        (__int64)&v170);
    }
  }
  v32 = v168;
  if ( v168 )
  {
    v43 = *(unsigned __int16 *)v168;
    if ( (_WORD)v43 == 0xFFFE )
    {
      v47 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v47 > 4u && (unsigned __int8)tlgKeywordOn(v47, 512) )
      {
        LODWORD(v178) = v32[5];
        *(_QWORD *)&Buf1.Data1 = v32 + 6;
        LODWORD(v169) = *((_DWORD *)v168 + 2);
        LODWORD(v171) = *((_DWORD *)v168 + 1);
        LOWORD(v170) = *((_WORD *)v168 + 1);
        v172 = L"WAVEFORMATEXTENSIBLE";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v48,
          (unsigned int)&unk_1801A170A,
          v48,
          v49,
          (__int64)&v172,
          (__int64)&v170,
          (__int64)&v171,
          (__int64)&v169,
          (__int64)&Buf1,
          (__int64)&v178);
      }
    }
    else
    {
      *(_QWORD *)&v211.Data2 = *(_QWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data2;
      *(_DWORD *)&v211.Data4[4] = *(_DWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data4[4];
      v211.Data1 = v43;
      v44 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v44 > 4u && (unsigned __int8)tlgKeywordOn(v44, 512) )
      {
        *(_QWORD *)&Buf1.Data1 = &v211;
        LODWORD(v178) = *((_DWORD *)v168 + 2);
        LODWORD(v169) = *((_DWORD *)v168 + 1);
        LOWORD(v170) = *((_WORD *)v168 + 1);
        v172 = L"WAVEFORMATEX";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          v45,
          (unsigned int)&unk_1801A17B1,
          v45,
          v46,
          (__int64)&v172,
          (__int64)&v170,
          (__int64)&v169,
          (__int64)&v178,
          (__int64)&Buf1);
      }
    }
  }
  else
  {
    v33 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
    if ( *v33 > 4u && (unsigned __int8)tlgKeywordOn(v33, 512) )
    {
      LODWORD(v178) = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v34,
        (unsigned int)&unk_1801A184B,
        v34,
        v35,
        (__int64)&v178);
    }
  }
  v50 = Src;
  if ( Src )
  {
    wFormatTag = Src->wFormatTag;
    if ( (_WORD)wFormatTag == 0xFFFE )
    {
      v58 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v58 > 4u && (unsigned __int8)tlgKeywordOn(v58, 512) )
      {
        LODWORD(v178) = *(_DWORD *)&v50[1].nChannels;
        *(_QWORD *)&Buf1.Data1 = (char *)v50 + 24;
        LODWORD(v169) = Src->nAvgBytesPerSec;
        LODWORD(v171) = Src->nSamplesPerSec;
        LOWORD(v170) = Src->nChannels;
        v172 = L"WAVEFORMATEXTENSIBLE";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v59,
          (unsigned int)&unk_1801A156B,
          v59,
          v60,
          (__int64)&v172,
          (__int64)&v170,
          (__int64)&v171,
          (__int64)&v169,
          (__int64)&Buf1,
          (__int64)&v178);
      }
    }
    else
    {
      *(_QWORD *)&v211.Data2 = *(_QWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data2;
      *(_DWORD *)&v211.Data4[4] = *(_DWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data4[4];
      v211.Data1 = wFormatTag;
      v55 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v55 > 4u && (unsigned __int8)tlgKeywordOn(v55, 512) )
      {
        *(_QWORD *)&Buf1.Data1 = &v211;
        LODWORD(v178) = Src->nAvgBytesPerSec;
        LODWORD(v169) = Src->nSamplesPerSec;
        LOWORD(v170) = Src->nChannels;
        v172 = L"WAVEFORMATEX";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          v56,
          (unsigned int)&unk_1801A1611,
          v56,
          v57,
          (__int64)&v172,
          (__int64)&v170,
          (__int64)&v169,
          (__int64)&v178,
          (__int64)&Buf1);
      }
    }
  }
  else
  {
    v51 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
    if ( *v51 > 4u && (unsigned __int8)tlgKeywordOn(v51, 512) )
    {
      LODWORD(v178) = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v52,
        (unsigned int)&unk_1801A16AA,
        v52,
        v53,
        (__int64)&v178);
    }
  }
  v61 = pv;
  if ( pv )
  {
    v65 = *(unsigned __int16 *)pv;
    if ( (_WORD)v65 == 0xFFFE )
    {
      v157 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v157 > 4u && (unsigned __int8)tlgKeywordOn(v157, 512) )
      {
        LODWORD(v178) = v61[5];
        *(_QWORD *)&Buf1.Data1 = v61 + 6;
        LODWORD(v169) = *((_DWORD *)pv + 2);
        LODWORD(v171) = *((_DWORD *)pv + 1);
        LOWORD(v170) = *((_WORD *)pv + 1);
        v172 = L"WAVEFORMATEXTENSIBLE";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v158,
          (unsigned int)&unk_1801A13CF,
          v158,
          v159,
          (__int64)&v172,
          (__int64)&v170,
          (__int64)&v171,
          (__int64)&v169,
          (__int64)&Buf1,
          (__int64)&v178);
      }
    }
    else
    {
      *(_QWORD *)&v211.Data2 = *(_QWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data2;
      *(_DWORD *)&v211.Data4[4] = *(_DWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data4[4];
      v211.Data1 = v65;
      v66 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v66 > 4u && (unsigned __int8)tlgKeywordOn(v66, 512) )
      {
        *(_QWORD *)&Buf1.Data1 = &v211;
        LODWORD(v178) = *((_DWORD *)pv + 2);
        LODWORD(v169) = *((_DWORD *)pv + 1);
        LOWORD(v170) = *((_WORD *)pv + 1);
        v172 = L"WAVEFORMATEX";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          v67,
          (unsigned int)&unk_1801A1474,
          v67,
          v68,
          (__int64)&v172,
          (__int64)&v170,
          (__int64)&v169,
          (__int64)&v178,
          (__int64)&Buf1);
      }
    }
  }
  else
  {
    v62 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
    if ( *v62 > 4u && (unsigned __int8)tlgKeywordOn(v62, 512) )
    {
      LODWORD(v178) = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v63,
        (unsigned int)&unk_1801A150C,
        v63,
        v64,
        (__int64)&v178);
    }
  }
  LODWORD(v170) = 0;
  v211 = v21;
  v69 = (int)lpCriticalSection;
  SharedModeEnginePeriodicity = EffectPack::GetSharedModeEnginePeriodicity(
                                  v183[1],
                                  (unsigned int)lpCriticalSection,
                                  pv,
                                  &v211);
  v23 = SharedModeEnginePeriodicity;
  if ( SharedModeEnginePeriodicity < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCDC,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)SharedModeEnginePeriodicity,
      0);
    v71 = pv;
    pv = 0;
    if ( v71 )
      CoTaskMemFree(v71);
    v72 = Src;
    Src = 0;
    if ( v72 )
      CoTaskMemFree(v72);
    v73 = v168;
    v168 = 0;
    if ( v73 )
      CoTaskMemFree(v73);
    v74 = v166;
    v166 = 0;
    if ( v74 )
      CoTaskMemFree(v74);
    goto LABEL_124;
  }
  v75 = (double)(int)v170 * 10000000.0 / (double)*((int *)pv + 1) + 0.5;
  v174 = 0;
  v211 = *(struct _GUID *)v189;
  v188 = v22;
  Buf1 = v21;
  v76 = InitializeStreamAndModeDescriptors(
          (AudioModeEffectsWatcherFactory *)v183,
          v69,
          &Buf1,
          (__int64)&v188,
          (__int64)&v211,
          0,
          0,
          (__int64)v166,
          0,
          (unsigned int)(int)v75,
          0,
          0,
          0,
          0,
          0,
          0,
          0,
          0,
          0,
          0,
          0,
          0,
          0,
          -1,
          0,
          (__int64)&v174);
  v23 = v76;
  if ( v76 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCE5,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v76,
      v162);
    std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v174);
    v77 = pv;
    pv = 0;
    if ( v77 )
      CoTaskMemFree(v77);
    v78 = Src;
    Src = 0;
    if ( v78 )
      CoTaskMemFree(v78);
    v79 = v168;
    v168 = 0;
    if ( v79 )
      CoTaskMemFree(v79);
    v80 = v166;
    v166 = 0;
    if ( v80 )
      CoTaskMemFree(v80);
    goto LABEL_124;
  }
  memset_0(v200, 0, 0x50u);
  v203 = (unsigned int)(int)v75;
  v200[0] = v11;
  v202 = v22;
  v200[2] = v69;
  v81 = v195;
  v204 = v195;
  v200[1] = 1;
  v200[4] = GetCurrentProcessId();
  v201 = v190;
  if ( v174 )
  {
    *(_DWORD *)(*(_QWORD *)(v174 + 8) + 8LL) = *((unsigned __int16 *)v166 + 8) + 18;
    *(_QWORD *)(*(_QWORD *)(v174 + 8) + 16LL) = v166;
  }
  v200[3] = v69 == eConnectorCount;
  v177 = 0;
  v211 = *(struct _GUID *)v187;
  v82 = DeriveStreamGroupParametersForStream(v183, (unsigned int)v69, v11, v203);
  v23 = v82;
  if ( v82 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCFD,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v82,
      v162);
    std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v177);
    std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v174);
    v85 = pv;
    pv = 0;
    if ( v85 )
      CoTaskMemFree(v85);
    v86 = Src;
    Src = 0;
    if ( v86 )
      CoTaskMemFree(v86);
    v87 = v168;
    v168 = 0;
    if ( v87 )
      CoTaskMemFree(v87);
    v88 = v166;
    v166 = 0;
    if ( v88 )
      CoTaskMemFree(v88);
    goto LABEL_124;
  }
  if ( (Microsoft_Windows_AudioEnableBits & 0x20) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      (_DWORD)v83,
      (unsigned int)&AudioResourceManager_StreamSettings_Derived,
      v84,
      1,
      (__int64)&v211);
  v187[0] = 0;
  EndpointStore = CEndpointStoreCache::GetEndpointStore(v83, v81, v187);
  v23 = EndpointStore;
  if ( EndpointStore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD02,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)EndpointStore,
      v162);
    wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(v187);
    std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v177);
    std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v174);
    v90 = pv;
    pv = 0;
    if ( v90 )
      CoTaskMemFree(v90);
    v91 = Src;
    Src = 0;
    if ( v91 )
      CoTaskMemFree(v91);
    v92 = v168;
    v168 = 0;
    if ( v92 )
      CoTaskMemFree(v92);
    v93 = v166;
    v166 = 0;
    if ( v93 )
      CoTaskMemFree(v93);
    goto LABEL_124;
  }
  v181[0] = 0;
  v171 = 0;
  CustomResourceManagerService = CEndpointCharacteristics::TryGetCustomResourceManagerService(
                                   v183[0],
                                   &GUID_475d74a7_6824_4b91_89be_33d893b255ed,
                                   &v171);
  v23 = CustomResourceManagerService;
  if ( CustomResourceManagerService < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD08,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)CustomResourceManagerService,
      v162);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v171);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v181);
    wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(v187);
    std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v177);
    std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v174);
    v95 = pv;
    pv = 0;
    if ( v95 )
      CoTaskMemFree(v95);
    v96 = Src;
    Src = 0;
    if ( v96 )
      CoTaskMemFree(v96);
    v97 = v168;
    v168 = 0;
    if ( v97 )
      CoTaskMemFree(v97);
    v98 = v166;
    v166 = 0;
    if ( v98 )
      CoTaskMemFree(v98);
    goto LABEL_124;
  }
  v99 = 0;
  v172 = 0;
  if ( v171 )
  {
    v100 = (*(__int64 (__fastcall **)(void *, LPCRITICAL_SECTION *))(*(_QWORD *)v171 + 104LL))(v171, &lpCriticalSection);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::operator=(
      &v172,
      v100);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    v99 = (struct _RTL_CRITICAL_SECTION *)v172;
  }
  v101 = v187[0];
  (*(void (__fastcall **)(_QWORD, LPCRITICAL_SECTION *))(**((_QWORD **)v187[0] + 13) + 128LL))(
    *((_QWORD *)v187[0] + 13),
    v189);
  v178 = 0;
  v102 = *(__int64 (__fastcall **)(struct IDeviceGraphManager *, CEndpointCharacteristics **, _QWORD, __int64))(*(_QWORD *)g_DeviceGraphManager + 48LL);
  wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v178);
  v163 = 0;
  v103 = v102(g_DeviceGraphManager, v183, *((_QWORD *)v101 + 13), v177);
  v104 = v103;
  if ( v103 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD17,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v103,
      0);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v178);
    if ( v189[0] )
      LeaveCriticalSection(v189[0]);
    if ( v99 )
      LeaveCriticalSection(v99);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v171);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v181);
    wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(v187);
    std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v177);
    std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v174);
    v105 = pv;
    pv = 0;
    if ( v105 )
      CoTaskMemFree(v105);
    v106 = Src;
    Src = 0;
    if ( v106 )
      CoTaskMemFree(v106);
    v107 = v168;
    v168 = 0;
    if ( v107 )
      CoTaskMemFree(v107);
    v108 = v166;
    v166 = 0;
    if ( v108 )
      CoTaskMemFree(v108);
LABEL_189:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v173);
    std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v185);
    EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)v183);
    return (unsigned int)v104;
  }
  p_Src = (struct tWAVEFORMATEX **)&v178;
  v206 = (struct tWAVEFORMATEX *)v200;
  *(_QWORD *)v207 = &v174;
  *(_QWORD *)&v207[8] = &v177;
  *(_QWORD *)&v207[16] = v181;
  v208 = &v194;
  v209 = &v185;
  v210 = &v190;
  v104 = lambda_cb723a5ef8b52b0dc033746828a6c36f_::operator()(&p_Src);
  v109 = (int *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
  v111 = *v109;
  if ( (unsigned int)*v109 > 4 )
  {
    v170 = v194;
    *(_QWORD *)&v188.Data1 = v190;
    *(_QWORD *)&v211.Data1 = v178;
    LODWORD(lpCriticalSection) = v104;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      (_DWORD)v109,
      (unsigned int)&unk_1801A1371,
      (_DWORD)v109,
      v110,
      (__int64)&lpCriticalSection,
      (__int64)&v211,
      (__int64)&v188,
      (__int64)&v170);
  }
  if ( v104 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD37,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v104,
      v163);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v178);
    if ( v189[0] )
      LeaveCriticalSection(v189[0]);
    if ( v99 )
      LeaveCriticalSection(v99);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v171);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v181);
    wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(v187);
    std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v177);
    std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v174);
    v112 = pv;
    pv = 0;
    if ( v112 )
      CoTaskMemFree(v112);
    v113 = Src;
    Src = 0;
    if ( v113 )
      CoTaskMemFree(v113);
    v114 = v168;
    v168 = 0;
    if ( v114 )
      CoTaskMemFree(v114);
    v115 = v166;
    v166 = 0;
    if ( v115 )
      CoTaskMemFree(v115);
    goto LABEL_189;
  }
  if ( (Microsoft_Windows_AudioEnableBits & 0x20) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      v111,
      (unsigned int)&AudioResourceManager_Stream_Created,
      (_DWORD)v109,
      1,
      (__int64)&v211);
  v169 = 0;
  v116 = v178;
  v117 = (__int64 (__fastcall *)(LPVOID *, __int64 **))*((_QWORD *)*v178 + 28);
  wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v169);
  v118 = v117(v116, &v169);
  v104 = v118;
  if ( v118 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD3D,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v118,
      v163);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v169);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v178);
    if ( v189[0] )
      LeaveCriticalSection(v189[0]);
    if ( v99 )
      LeaveCriticalSection(v99);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v171);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v181);
    wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(v187);
    std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v177);
    std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v174);
    v119 = pv;
    pv = 0;
    if ( v119 )
      CoTaskMemFree(v119);
    v120 = Src;
    Src = 0;
    if ( v120 )
      CoTaskMemFree(v120);
    v121 = v168;
    v168 = 0;
    if ( v121 )
      CoTaskMemFree(v121);
    v122 = v166;
    v166 = 0;
    if ( v122 )
      CoTaskMemFree(v122);
    goto LABEL_189;
  }
  v123 = v169;
  if ( !v169 )
  {
    lpCriticalSection = 0;
    p_pv = &lpCriticalSection;
    v192 = 0;
    v193 = 1;
    v211 = v22;
    v188 = v21;
    v104 = DeriveSaDeviceParametersForStream(
             (struct EndpointCharacteristicsDescriptor *)v183,
             AUDCLNT_SHAREMODE_SHARED,
             v69,
             &v188,
             &v211,
             (struct tWAVEFORMATEX *)pv,
             Src,
             *(_QWORD *)(v177 + 24),
             (struct SaDeviceParams **)&v192);
    wil::details::out_param_t<std::unique_ptr<SaDeviceParams>>::~out_param_t<std::unique_ptr<SaDeviceParams>>(&p_pv);
    if ( v104 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD45,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
        (const char *)(unsigned int)v104,
        v164);
      std::unique_ptr<SaDeviceParams>::~unique_ptr<SaDeviceParams>(&lpCriticalSection);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v169);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v178);
      if ( v189[0] )
        LeaveCriticalSection(v189[0]);
      if ( v99 )
        LeaveCriticalSection(v99);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v171);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v181);
      wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(v187);
      std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v177);
      std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v174);
      v124 = pv;
      pv = 0;
      if ( v124 )
        CoTaskMemFree(v124);
      v125 = Src;
      Src = 0;
      if ( v125 )
        CoTaskMemFree(v125);
      v126 = v168;
      v168 = 0;
      if ( v126 )
        CoTaskMemFree(v126);
      v127 = v166;
      v166 = 0;
      if ( v127 )
        CoTaskMemFree(v127);
      goto LABEL_189;
    }
    if ( CEndpointCharacteristics::DoesExclusiveModeOverrideShared(v183[0])
      && _InterlockedCompareExchange((volatile signed __int32 *)(*((_QWORD *)v101 + 12) + 276LL), 0, 0) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD4E,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
        (const char *)0x887C005CLL,
        v164);
      std::unique_ptr<SaDeviceParams>::~unique_ptr<SaDeviceParams>(&lpCriticalSection);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v169);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v178);
      if ( v189[0] )
        LeaveCriticalSection(v189[0]);
      if ( v99 )
        LeaveCriticalSection(v99);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v171);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v181);
      wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(v187);
      std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v177);
      std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v174);
      v128 = pv;
      pv = 0;
      if ( v128 )
        CoTaskMemFree(v128);
      v129 = Src;
      Src = 0;
      if ( v129 )
        CoTaskMemFree(v129);
      v130 = v168;
      v168 = 0;
      if ( v130 )
        CoTaskMemFree(v130);
      v131 = v166;
      v166 = 0;
      if ( v131 )
        CoTaskMemFree(v131);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v173);
      std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v185);
      EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)v183);
      return 2289827932LL;
    }
    *(_WORD *)((char *)&v206 + 5) = 0;
    HIBYTE(v206) = 0;
    *(_DWORD *)&v207[20] = 0;
    BYTE4(v206) = 1;
    LODWORD(v206) = 0;
    p_Src = 0;
    *(GUID *)&v207[4] = v21;
    *(_DWORD *)v207 = v69;
    wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v169);
    SaDeviceForSharedStream = CAudioResourceManager::GetSaDeviceForSharedStream(v212[0], v183, v171, lpCriticalSection);
    v135 = SaDeviceForSharedStream;
    if ( SaDeviceForSharedStream < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD5C,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
        (const char *)(unsigned int)SaDeviceForSharedStream,
        131074);
      std::unique_ptr<SaDeviceParams>::~unique_ptr<SaDeviceParams>(&lpCriticalSection);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v169);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v178);
      if ( v189[0] )
        LeaveCriticalSection(v189[0]);
      if ( v99 )
        LeaveCriticalSection(v99);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v171);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v181);
      wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(v187);
      std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v177);
      std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v174);
      v136 = pv;
      pv = 0;
      if ( v136 )
        CoTaskMemFree(v136);
      v137 = Src;
      Src = 0;
      if ( v137 )
        CoTaskMemFree(v137);
      v138 = v168;
      v168 = 0;
      if ( v138 )
        CoTaskMemFree(v138);
      v139 = v166;
      v166 = 0;
      if ( v139 )
        CoTaskMemFree(v139);
LABEL_218:
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v173);
      std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v185);
      EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)v183);
      return v135;
    }
    if ( (Microsoft_Windows_AudioEnableBits & 0x20) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(
        v133,
        (unsigned int)&AudioResourceManager_SaDevice_Created,
        v134,
        1,
        (__int64)v212);
    v140 = (*(__int64 (__fastcall **)(struct IDeviceGraphManager *, LPVOID *, __int64 *, __int64))(*(_QWORD *)g_DeviceGraphManager
                                                                                                 + 32LL))(
             g_DeviceGraphManager,
             v178,
             v169,
             1);
    v135 = v140;
    if ( v140 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD68,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
        (const char *)(unsigned int)v140,
        0);
      std::unique_ptr<SaDeviceParams>::~unique_ptr<SaDeviceParams>(&lpCriticalSection);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v169);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v178);
      if ( v189[0] )
        LeaveCriticalSection(v189[0]);
      if ( v99 )
        LeaveCriticalSection(v99);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v171);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v181);
      wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(v187);
      std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v177);
      std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v174);
      v143 = pv;
      pv = 0;
      if ( v143 )
        CoTaskMemFree(v143);
      v144 = Src;
      Src = 0;
      if ( v144 )
        CoTaskMemFree(v144);
      v145 = v168;
      v168 = 0;
      if ( v145 )
        CoTaskMemFree(v145);
      v146 = v166;
      v166 = 0;
      if ( v146 )
        CoTaskMemFree(v146);
      goto LABEL_218;
    }
    if ( (Microsoft_Windows_AudioEnableBits & 0x20) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(
        v141,
        (unsigned int)&AudioResourceManager_SaDevice_Connected,
        v142,
        1,
        (__int64)v212);
    std::unique_ptr<SaDeviceParams>::~unique_ptr<SaDeviceParams>(&lpCriticalSection);
    v123 = v169;
  }
  *(_QWORD *)&Buf1.Data1 = 0;
  v147 = *v123;
  p_pv = &Buf1;
  v192 = 0;
  v193 = 1;
  v148 = (*(__int64 (__fastcall **)(__int64 *, struct tWAVEFORMATEX **))(v147 + 120))(v123, &v192);
  wil::details::out_param_t<std::unique_ptr<SaDeviceParams>>::~out_param_t<std::unique_ptr<SaDeviceParams>>(&p_pv);
  if ( v148 >= 0 )
  {
    v149 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
    if ( *v149 > 4u )
    {
      v212[0] = (*(__int64 (__fastcall **)(struct IStreamGroupProxy *))(*(_QWORD *)v194 + 152LL))(v194);
      LOBYTE(v170) = v175;
      *(_QWORD *)&v211.Data1 = v195;
      *(_QWORD *)&v188.Data1 = v190;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v149,
        (unsigned int)&unk_1801A12FD,
        v150,
        v151,
        (__int64)&v188,
        (__int64)&v211,
        (__int64)&v170,
        (__int64)v212);
    }
  }
  std::unique_ptr<SaDeviceParams>::~unique_ptr<SaDeviceParams>(&Buf1);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v169);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v178);
  if ( v189[0] )
    LeaveCriticalSection(v189[0]);
  if ( v99 )
    LeaveCriticalSection(v99);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v171);
  v152 = (struct IBridgeStreamInstanceProxy *)v181[0];
  v181[0] = 0;
  *v196 = v152;
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v181);
  wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(v187);
  std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v177);
  std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v174);
  v153 = pv;
  pv = 0;
  if ( v153 )
    CoTaskMemFree(v153);
  v154 = Src;
  Src = 0;
  if ( v154 )
    CoTaskMemFree(v154);
  v155 = v168;
  v168 = 0;
  if ( v155 )
    CoTaskMemFree(v155);
  v156 = v166;
  v166 = 0;
  if ( v156 )
    CoTaskMemFree(v156);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v173);
  std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v185);
  EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)v183);
  return 0;
}

```

## disassembly

```asm
0x1800c1ca4  mov     r11, rsp
0x1800c1ca7  push    rbx
0x1800c1ca8  push    rsi
0x1800c1ca9  push    rdi
0x1800c1caa  push    r12
0x1800c1cac  push    r13
0x1800c1cae  push    r14
0x1800c1cb0  push    r15
0x1800c1cb2  sub     rsp, 320h
0x1800c1cb9  movaps  xmmword ptr [r11-48h], xmm6
0x1800c1cbe  movaps  xmmword ptr [r11-58h], xmm7
0x1800c1cc3  mov     rax, cs:__security_cookie
0x1800c1cca  xor     rax, rsp
0x1800c1ccd  mov     [rsp+358h+var_68], rax
0x1800c1cd5  mov     sil, r9b
0x1800c1cd8  mov     r9, rdx
0x1800c1cdb  mov     [rsp+358h+var_140], rdx
0x1800c1ce3  mov     [rsp+358h+var_78], rcx
0x1800c1ceb  mov     [r11-168h], r8
0x1800c1cf2  mov     rax, [rsp+358h+arg_20]
0x1800c1cfa  mov     [r11-148h], rax
0x1800c1d01  mov     rax, [rsp+358h+arg_28]
0x1800c1d09  mov     [rsp+358h+var_138], rax
0x1800c1d11  xorps   xmm0, xmm0
0x1800c1d14  movdqu  xmmword ptr [rsp+358h+var_1C8], xmm0
0x1800c1d1d  xor     r12d, r12d
0x1800c1d20  mov     [r11-1B8h], r12
0x1800c1d27  lea     r8, [r11-1C8h]; struct EndpointCharacteristicsDescriptor *
0x1800c1d2e  xor     edx, edx; int
0x1800c1d30  mov     rcx, r9; unsigned __int16 *
0x1800c1d33  call    ?GetEndpointCharacteristicsDescriptor@@YAJPEBGHPEAUEndpointCharacteristicsDescriptor@@@Z; GetEndpointCharacteristicsDescriptor(ushort const *,int,EndpointCharacteristicsDescriptor *)
0x1800c1d38  mov     ebx, eax
0x1800c1d3a  test    eax, eax
0x1800c1d3c  jns     short loc_1800C1D6F
0x1800c1d3e  mov     rcx, [rsp+358h]; this
0x1800c1d46  mov     r9d, eax; char *
0x1800c1d49  lea     r8, aAvcoreAudiocor_74; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800c1d50  mov     edx, 0C90h; void *
0x1800c1d55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1d5a  nop
0x1800c1d5b  lea     rcx, [rsp+358h+var_1C8]; this
0x1800c1d63  call    ??1EndpointCharacteristicsDescriptor@@QEAA@XZ; EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor(void)
0x1800c1d68  mov     eax, ebx
0x1800c1d6a  jmp     loc_1800C41FD
0x1800c1d6f  mov     rax, [rsp+358h+var_1C8]
0x1800c1d77  mov     r14b, [rax+108h]
0x1800c1d7e  mov     [rsp+358h+var_218], r14b
0x1800c1d86  test    sil, sil
0x1800c1d89  jz      short loc_1800C1D96
0x1800c1d8b  test    r14b, r14b
0x1800c1d8e  mov     r13d, 3
0x1800c1d94  jnz     short loc_1800C1D9C
0x1800c1d96  mov     r13d, 2
0x1800c1d9c  xorps   xmm0, xmm0
0x1800c1d9f  movdqu  [rsp+358h+var_1B0], xmm0
0x1800c1da8  mov     [rsp+358h+var_1A0], r12
0x1800c1db0  mov     [rsp+358h+var_228], r12
0x1800c1db8  lea     rcx, [rsp+358h+var_228]
0x1800c1dc0  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x1800c1dc5  lea     r8, [rsp+358h+var_228]; struct IUnknown **
0x1800c1dcd  lea     rdx, [rsp+358h+var_1C8]; struct EndpointCharacteristicsDescriptor *
0x1800c1dd5  call    ?AcquireAudioPumpDspTokenForEndpoint@CAudioPumpDspResourceTracker@@QEAAJPEAUEndpointCharacteristicsDescriptor@@PEAPEAUIUnknown@@@Z; CAudioPumpDspResourceTracker::AcquireAudioPumpDspTokenForEndpoint(EndpointCharacteristicsDescriptor *,IUnknown * *)
0x1800c1dda  mov     ebx, eax
0x1800c1ddc  test    eax, eax
0x1800c1dde  jns     short loc_1800C1E2D
0x1800c1de0  mov     rcx, [rsp+358h]; this
0x1800c1de8  mov     r9d, eax; char *
0x1800c1deb  lea     r8, aAvcoreAudiocor_74; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800c1df2  mov     edx, 0C9Ch; void *
0x1800c1df7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1dfc  nop
0x1800c1dfd  lea     rcx, [rsp+358h+var_228]
0x1800c1e05  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800c1e0a  nop
0x1800c1e0b  lea     rcx, [rsp+358h+var_1B0]
0x1800c1e13  call    ??1?$vector@V?$com_ptr_t@VCAudioStream@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VCAudioStream@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(void)
0x1800c1e18  nop
0x1800c1e19  lea     rcx, [rsp+358h+var_1C8]; this
0x1800c1e21  call    ??1EndpointCharacteristicsDescriptor@@QEAA@XZ; EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor(void)
0x1800c1e26  mov     eax, ebx
0x1800c1e28  jmp     loc_1800C41FD
0x1800c1e2d  mov     rax, qword ptr [rsp+358h+var_1B0+8]
0x1800c1e35  cmp     rax, [rsp+358h+var_1A0]
0x1800c1e3d  jz      short loc_1800C1E5A
0x1800c1e3f  mov     rdx, [rsp+358h+var_228]
0x1800c1e47  mov     rcx, rax
0x1800c1e4a  call    ??0?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAVCEndpointCharacteristics@@@Z; wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>(CEndpointCharacteristics *)
0x1800c1e4f  add     qword ptr [rsp+358h+var_1B0+8], 8
0x1800c1e58  jmp     short loc_1800C1E72
0x1800c1e5a  lea     r8, [rsp+358h+var_228]
0x1800c1e62  mov     rdx, rax
0x1800c1e65  lea     rcx, [rsp+358h+var_1B0]
0x1800c1e6d  call    ??$_Emplace_reallocate@AEBV?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@@?$vector@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@AEAAPEAV?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAV23@AEBV23@@Z; std::vector<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>>::_Emplace_reallocate<wil::com_ptr_t<IUnknown,wil::err_returncode_policy> const &>(wil::com_ptr_t<IUnknown,wil::err_returncode_policy> * const,wil::com_ptr_t<IUnknown,wil::err_returncode_policy> const &)
0x1800c1e72  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800c1e79  movdqu  xmmword ptr [rsp+358h+var_88.Data1], xmm0
0x1800c1e82  movdqu  xmmword ptr [rsp+358h+var_188.Data1], xmm0
0x1800c1e8b  movdqu  xmmword ptr [rsp+358h+Buf1.Data1], xmm0
0x1800c1e94  movdqu  xmmword ptr [rsp+358h+var_198], xmm0
0x1800c1e9d  movdqu  xmmword ptr [rsp+358h+var_178], xmm0
0x1800c1ea6  lea     rdx, [rsp+358h+var_1B0]
0x1800c1eae  lea     rcx, [rsp+358h+var_200]
0x1800c1eb6  call    ?TryGetAudioPumpDspResourceTokenFromTokenList@@YA?AUAudioPumpDspResourceTokenPair@@AEBV?$vector@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@@Z; TryGetAudioPumpDspResourceTokenFromTokenList(std::vector<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>> const &)
0x1800c1ebb  mov     rdi, [rax+8]
0x1800c1ebf  mov     [rax+8], r12
0x1800c1ec3  mov     [rsp+358h+var_230], rdi
0x1800c1ecb  lea     rcx, [rsp+358h+var_200]; this
0x1800c1ed3  call    ??1AudioPumpDspResourceTokenPair@@QEAA@XZ; AudioPumpDspResourceTokenPair::~AudioPumpDspResourceTokenPair(void)
0x1800c1ed8  test    sil, sil
0x1800c1edb  jz      short loc_1800C1EED
0x1800c1edd  test    r14b, r14b
0x1800c1ee0  jz      short loc_1800C1EED
0x1800c1ee2  mov     r15d, 1
0x1800c1ee8  mov     r9d, r15d
0x1800c1eeb  jmp     short loc_1800C1EF6
0x1800c1eed  mov     r9d, r12d; int
0x1800c1ef0  mov     r15d, 1
0x1800c1ef6  mov     [rsp+358h+Src], rdi; struct IUnknown *
0x1800c1efb  mov     [rsp+358h+var_330], r12; struct IProcessSubmixProxy *
0x1800c1f00  mov     qword ptr [rsp+358h+var_338], r12; struct tWAVEFORMATEX *
0x1800c1f05  xor     r8d, r8d; enum _AUDCLNT_SHAREMODE
0x1800c1f08  mov     edx, 20002h; unsigned int
0x1800c1f0d  lea     rcx, [rsp+358h+var_1C8]; struct EndpointCharacteristicsDescriptor *
0x1800c1f15  call    ?GetConnectorTypeForStream@@YA?AW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUEndpointCharacteristicsDescriptor@@KW4_AUDCLNT_SHAREMODE@@HPEBUtWAVEFORMATEX@@PEAUIProcessSubmixProxy@@PEAUIUnknown@@@Z; GetConnectorTypeForStream(EndpointCharacteristicsDescriptor *,ulong,_AUDCLNT_SHAREMODE,int,tWAVEFORMATEX const *,IProcessSubmixProxy *,IUnknown *)
0x1800c1f1a  mov     esi, eax
0x1800c1f1c  mov     dword ptr [rsp+358h+lpCriticalSection], eax
0x1800c1f23  lea     rax, [rsp+358h+var_178]
0x1800c1f2b  mov     [rsp+358h+var_2E0], rax
0x1800c1f30  lea     rax, [rsp+358h+var_198]
0x1800c1f38  mov     [rsp+358h+var_2E8], rax
0x1800c1f3d  lea     rax, [rsp+358h+Buf1]
0x1800c1f45  mov     [rsp+358h+var_2F0], rax
0x1800c1f4a  lea     rax, [rsp+358h+var_188]
0x1800c1f52  mov     [rsp+358h+var_2F8], rax
0x1800c1f57  lea     rax, [rsp+358h+var_88]
0x1800c1f5f  mov     [rsp+358h+var_300], rax
0x1800c1f64  mov     [rsp+358h+var_308], r12
0x1800c1f69  mov     dword ptr [rsp+358h+var_310], r12d
0x1800c1f6e  mov     dword ptr [rsp+358h+var_318], r12d
0x1800c1f73  mov     [rsp+358h+var_320], r12
0x1800c1f78  mov     dword ptr [rsp+358h+Src], esi
0x1800c1f7c  mov     dword ptr [rsp+358h+var_330], r12d
0x1800c1f81  mov     [rsp+358h+var_338], r13d; int
0x1800c1f86  lea     r9, [rsp+358h+var_1C8]
0x1800c1f8e  xor     r8d, r8d
0x1800c1f91  xor     edx, edx
0x1800c1f93  xor     ecx, ecx
0x1800c1f95  call    ?DeriveAudioProcessingModeConfiguration@@YAJKHHPEAUEndpointCharacteristicsDescriptor@@W4SYSTEM_AUDIO_STREAM_TYPE@@W4_AUDCLNT_SHAREMODE@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUIProcessSubmixProxy@@HHPEBUtWAVEFORMATEX@@PEAU_GUID@@6666@Z; DeriveAudioProcessingModeConfiguration(ulong,int,int,EndpointCharacteristicsDescriptor *,SYSTEM_AUDIO_STREAM_TYPE,_AUDCLNT_SHAREMODE,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,IProcessSubmixProxy *,int,int,tWAVEFORMATEX const *,_GUID *,_GUID *,_GUID *,_GUID *,_GUID *)
0x1800c1f9a  mov     ebx, eax
0x1800c1f9c  test    eax, eax
0x1800c1f9e  jns     short loc_1800C1FFB
0x1800c1fa0  mov     rcx, [rsp+358h]; this
0x1800c1fa8  mov     r9d, eax; char *
0x1800c1fab  lea     r8, aAvcoreAudiocor_74; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800c1fb2  mov     edx, 0CBCh; void *
0x1800c1fb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1fbc  nop
0x1800c1fbd  lea     rcx, [rsp+358h+var_230]
0x1800c1fc5  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800c1fca  nop
0x1800c1fcb  lea     rcx, [rsp+358h+var_228]
0x1800c1fd3  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800c1fd8  nop
0x1800c1fd9  lea     rcx, [rsp+358h+var_1B0]
0x1800c1fe1  call    ??1?$vector@V?$com_ptr_t@VCAudioStream@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VCAudioStream@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(void)
0x1800c1fe6  nop
0x1800c1fe7  lea     rcx, [rsp+358h+var_1C8]; this
0x1800c1fef  call    ??1EndpointCharacteristicsDescriptor@@QEAA@XZ; EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor(void)
0x1800c1ff4  mov     eax, ebx
0x1800c1ff6  jmp     loc_1800C41FD
0x1800c1ffb  test    rdi, rdi
0x1800c1ffe  jz      short loc_1800C2009
0x1800c2000  movaps  xmm6, xmmword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1
0x1800c2007  jmp     short loc_1800C2011
0x1800c2009  movaps  xmm6, xmmword ptr [rsp+358h+var_88.Data1]
0x1800c2011  lea     rcx, [rsp+358h+var_230]
0x1800c2019  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800c201e  mov     [rsp+358h+var_260], r12
0x1800c2026  mov     [rsp+358h+var_250], r12
0x1800c202e  mov     [rsp+358h+var_258], r12
0x1800c2036  mov     [rsp+358h+pv], r12
0x1800c203e  lea     rax, [rsp+358h+pv]
0x1800c2046  mov     [rsp+358h+var_160], rax
0x1800c204e  mov     [rsp+358h+var_158], r12
0x1800c2056  mov     [rsp+358h+var_150], r15b
0x1800c205e  lea     rax, [rsp+358h+var_258]
0x1800c2066  mov     [rsp+358h+var_C8], rax
0x1800c206e  mov     [rsp+358h+var_C0], r12
0x1800c2076  mov     byte ptr [rsp+358h+var_B8], r15b
0x1800c207e  lea     rax, [rsp+358h+var_250]
0x1800c2086  mov     [rsp+358h+var_130], rax
0x1800c208e  mov     [rsp+358h+var_128], r12
0x1800c2096  mov     [rsp+358h+var_120], r15b
0x1800c209e  lea     rax, [rsp+358h+var_260]
0x1800c20a6  mov     [rsp+358h+var_200], rax
0x1800c20ae  mov     [rsp+358h+var_1F8], r12
0x1800c20b6  mov     [rsp+358h+var_1F0], r15b
0x1800c20be  movdqa  xmmword ptr [rsp+358h+var_88.Data1], xmm6
0x1800c20c7  movaps  xmm7, xmmword ptr [rsp+358h+var_188.Data1]
0x1800c20cf  movdqa  xmmword ptr [rsp+358h+var_188.Data1], xmm7
0x1800c20d8  movaps  xmm0, xmmword ptr [rsp+358h+Buf1.Data1]
0x1800c20e0  movdqa  xmmword ptr [rsp+358h+Buf1.Data1], xmm0
0x1800c20e9  lea     rax, [rsp+358h+var_158]
0x1800c20f1  mov     [rsp+358h+var_2F8], rax; struct tWAVEFORMATEX **
0x1800c20f6  lea     rax, [rsp+358h+var_C0]
0x1800c20fe  mov     [rsp+358h+var_300], rax; struct tWAVEFORMATEX **
0x1800c2103  lea     rax, [rsp+358h+var_128]
0x1800c210b  mov     [rsp+358h+var_308], rax; struct tWAVEFORMATEX **
0x1800c2110  lea     rax, [rsp+358h+var_1F8]
0x1800c2118  mov     [rsp+358h+var_310], rax; struct tWAVEFORMATEX **
0x1800c211d  mov     [rsp+358h+var_318], r12; struct tWAVEFORMATEX *
0x1800c2122  lea     rax, [rsp+358h+var_88]
0x1800c212a  mov     [rsp+358h+var_320], rax; struct _GUID *
0x1800c212f  lea     rax, [rsp+358h+var_188]
0x1800c2137  mov     [rsp+358h+Src], rax; struct _GUID *
0x1800c213c  lea     rax, [rsp+358h+Buf1]
0x1800c2144  mov     [rsp+358h+var_330], rax; struct _GUID *
0x1800c2149  mov     [rsp+358h+var_338], r12d; int
0x1800c214e  xor     r9d, r9d; enum _AUDCLNT_SHAREMODE
0x1800c2151  mov     r8d, esi; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x1800c2154  xor     edx, edx; bool
0x1800c2156  lea     rcx, [rsp+358h+var_1C8]; struct EndpointCharacteristicsDescriptor *
0x1800c215e  call    ?DeriveDeviceGraphFormatsForStream@@YAJPEAUEndpointCharacteristicsDescriptor@@_NW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@W4_AUDCLNT_SHAREMODE@@KU_GUID@@44PEAUtWAVEFORMATEX@@PEAPEAU5@666@Z; DeriveDeviceGraphFormatsForStream(EndpointCharacteristicsDescriptor *,bool,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_AUDCLNT_SHAREMODE,ulong,_GUID,_GUID,_GUID,tWAVEFORMATEX *,tWAVEFORMATEX * *,tWAVEFORMATEX * *,tWAVEFORMATEX * *,tWAVEFORMATEX * *)
0x1800c2163  mov     ebx, eax
0x1800c2165  lea     rcx, [rsp+358h+var_200]
0x1800c216d  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800c2172  nop
0x1800c2173  lea     rcx, [rsp+358h+var_130]
0x1800c217b  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800c2180  nop
0x1800c2181  lea     rcx, [rsp+358h+var_C8]
0x1800c2189  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800c218e  nop
0x1800c218f  lea     rcx, [rsp+358h+var_160]
0x1800c2197  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800c219c  test    ebx, ebx
0x1800c219e  jns     loc_1800C2261
0x1800c21a4  mov     rcx, [rsp+358h]; this
0x1800c21ac  mov     r9d, ebx; char *
0x1800c21af  lea     r8, aAvcoreAudiocor_74; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800c21b6  mov     edx, 0CD2h; void *
0x1800c21bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c21c0  nop
0x1800c21c1  mov     rcx, [rsp+358h+pv]; pv
0x1800c21c9  mov     [rsp+358h+pv], r12
0x1800c21d1  test    rcx, rcx
0x1800c21d4  jz      short loc_1800C21DD
0x1800c21d6  call    cs:__imp_CoTaskMemFree
0x1800c21dc  nop
0x1800c21dd  mov     rcx, [rsp+358h+var_258]; pv
0x1800c21e5  mov     [rsp+358h+var_258], r12
0x1800c21ed  test    rcx, rcx
0x1800c21f0  jz      short loc_1800C21F9
0x1800c21f2  call    cs:__imp_CoTaskMemFree
0x1800c21f8  nop
0x1800c21f9  mov     rcx, [rsp+358h+var_250]; pv
0x1800c2201  mov     [rsp+358h+var_250], r12
0x1800c2209  test    rcx, rcx
0x1800c220c  jz      short loc_1800C2215
0x1800c220e  call    cs:__imp_CoTaskMemFree
0x1800c2214  nop
0x1800c2215  mov     rcx, [rsp+358h+var_260]; pv
0x1800c221d  mov     [rsp+358h+var_260], r12
0x1800c2225  test    rcx, rcx
0x1800c2228  jz      short loc_1800C2231
0x1800c222a  call    cs:__imp_CoTaskMemFree
0x1800c2230  nop
0x1800c2231  lea     rcx, [rsp+358h+var_228]
0x1800c2239  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800c223e  nop
0x1800c223f  lea     rcx, [rsp+358h+var_1B0]
0x1800c2247  call    ??1?$vector@V?$com_ptr_t@VCAudioStream@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VCAudioStream@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(void)
0x1800c224c  nop
0x1800c224d  lea     rcx, [rsp+358h+var_1C8]; this
0x1800c2255  call    ??1EndpointCharacteristicsDescriptor@@QEAA@XZ; EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor(void)
0x1800c225a  mov     eax, ebx
0x1800c225c  jmp     loc_1800C41FD
0x1800c2261  mov     rdi, [rsp+358h+var_260]
0x1800c2269  test    rdi, rdi
0x1800c226c  jnz     loc_1800C2330
0x1800c2272  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800c2277  mov     r8, [rax+8]
0x1800c227b  mov     eax, [r8]
0x1800c227e  mov     ebx, 200h
0x1800c2283  cmp     eax, 4
0x1800c2286  jbe     short loc_1800C22BA
0x1800c2288  mov     edx, ebx
0x1800c228a  mov     rcx, r8
0x1800c228d  call    _tlgKeywordOn
0x1800c2292  test    al, al
0x1800c2294  jz      short loc_1800C22BA
0x1800c2296  mov     dword ptr [rsp+358h+var_240], r12d
0x1800c229e  lea     rax, [rsp+358h+var_240]
0x1800c22a6  mov     qword ptr [rsp+358h+var_338], rax
0x1800c22ab  lea     rdx, unk_1801A19E7
0x1800c22b2  mov     rcx, r8
0x1800c22b5  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800c22ba  mov     r14d, 0FFFEh
0x1800c22c0  lea     rdi, aWaveformatexte; "WAVEFORMATEXTENSIBLE"
0x1800c22c7  lea     rsi, aWaveformatex; "WAVEFORMATEX"
0x1800c22ce  mov     r12, [rsp+358h+var_250]
  ... truncated ...
```
