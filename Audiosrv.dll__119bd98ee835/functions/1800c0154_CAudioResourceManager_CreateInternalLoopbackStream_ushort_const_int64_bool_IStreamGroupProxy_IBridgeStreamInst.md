# CAudioResourceManager::CreateInternalLoopbackStream(ushort const *,__int64,bool,IStreamGroupProxy *,IBridgeStreamInstanceProxy * *)

- ea: `0x1800c0154`
- end: `0x1800c27bc`
- name: `?CreateInternalLoopbackStream@CAudioResourceManager@@IEAAJPEBG_J_NPEAUIStreamGroupProxy@@PEAPEAUIBridgeStreamInstanceProxy@@@Z`
- size: `9832`
- prototype: `int(CAudioResourceManager *__hidden this, const unsigned __int16 *, __int64, bool, struct IStreamGroupProxy *, struct IBridgeStreamInstanceProxy **)`
- caller_count: `1`
- callee_count: `42`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800bff64`

## callees

- `0x180001658`
- `0x180002e34`
- `0x180008a2c`
- `0x180008f40`
- `0x180008fa8`
- `0x180009864`
- `0x18000ae1c`
- `0x18000cc30`
- `0x18000e2a4`
- `0x18001280c`
- `0x18001b520`
- `0x18001e0b0`
- `0x18001e92c`
- `0x18001ec9c`
- `0x180025eb4`
- `0x1800318d8`
- `0x180031c80`
- `0x18003865c`
- `0x1800424ec`
- `0x180044bd8`
- `0x1800467ac`
- `0x180049efc`
- `0x18004f2fc`
- `0x180055ab4`
- `0x18005abac`
- `0x180061430`
- `0x180061d20`
- `0x180062a0c`
- `0x180062e30`
- `0x180072e10`
- `0x180078e2c`
- `0x1800a4da0`
- `0x1800a6b34`
- `0x1800af6ac`
- `0x1800b571c`
- `0x1800bc414`
- `0x1800c0154`
- `0x1800cd8d0`
- `0x1800ce774`
- `0x1800df5dc`
- `0x1800e2684`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c16f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c17d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c17e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c1a2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c1a3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c1bda`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c1be9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c1deb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c1dfa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c1f6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c1f7b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c2186`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c2195`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c2330`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c233f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c259a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c25a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c16f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c17d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c17e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c1a2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c1a3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c1bda`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c1be9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c1deb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c1dfa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c1f6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c1f7b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c2186`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c2195`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c2330`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c233f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c259a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c25a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800c127d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800c127d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c068d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c06a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c06c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c06e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0f86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0fa2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0fbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0fda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c11a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c11c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c11de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c11fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c13b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c13d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c13ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c140b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c14e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1502`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c151e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c153a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c161f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c163b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1657`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1673`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c184a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1866`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1882`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c189e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1aa0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1abc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1ad8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1af4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1c4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1c67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1c83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1c9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1e5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1e78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1e94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1eb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1fdd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1ff9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2015`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2031`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c21f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2213`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c222f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c224b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c23a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c23bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c23d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c23f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2625`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2641`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c265d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2679`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c068d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c06a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c06c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c06e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0f86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0fa2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0fbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0fda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c11a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c11c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c11de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c11fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c13b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c13d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c13ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c140b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c14e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1502`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c151e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c153a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c161f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c163b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1657`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1673`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c184a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1866`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1882`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c189e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1aa0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1abc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1ad8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1af4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1c4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1c67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1c83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1c9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1e5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1e78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1e94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1eb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1fdd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1ff9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2015`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2031`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c21f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2213`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c222f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c224b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c23a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c23bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c23d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c23f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2625`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2641`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c265d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2679`

## string_xrefs

- `0x1800c01f9`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800c02a2`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800c0462`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800c0666`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800c0f5f`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800c1171`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800c1374`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800c1495`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800c15b2`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800c17ac`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800c1a02`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800c1b9f`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800c1da2`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800c1f23`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800c213d`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800c22e7`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`

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
  int v12; // eax
  unsigned int v13; // ebx
  __int64 AudioPumpDspResourceTokenFromTokenList; // rax
  struct IUnknown *v15; // rdi
  BOOL v16; // r9d
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 ConnectorTypeForStream; // esi
  int v18; // eax
  unsigned int v19; // ebx
  GUID v20; // xmm6
  struct _GUID v21; // xmm7
  int v22; // ebx
  void *v23; // rcx
  struct tWAVEFORMATEX *v24; // rcx
  void *v25; // rcx
  void *v26; // rcx
  _DWORD *v27; // rdi
  _DWORD *v28; // r8
  int v29; // r8d
  int v30; // r9d
  _DWORD *v31; // r12
  _DWORD *v32; // r8
  int v33; // r8d
  int v34; // r9d
  unsigned int v35; // ecx
  _DWORD *v36; // r8
  int v37; // r8d
  int v38; // r9d
  _DWORD *v39; // r8
  int v40; // r8d
  int v41; // r9d
  unsigned int v42; // ecx
  _DWORD *v43; // r8
  int v44; // r8d
  int v45; // r9d
  _DWORD *v46; // r8
  int v47; // r8d
  int v48; // r9d
  struct tWAVEFORMATEX *v49; // r12
  _DWORD *v50; // r8
  int v51; // r8d
  int v52; // r9d
  unsigned int wFormatTag; // ecx
  _DWORD *v54; // r8
  int v55; // r8d
  int v56; // r9d
  _DWORD *v57; // r8
  int v58; // r8d
  int v59; // r9d
  _DWORD *v60; // r12
  _DWORD *v61; // r8
  int v62; // r8d
  int v63; // r9d
  unsigned int v64; // ecx
  _DWORD *v65; // r8
  int v66; // r8d
  int v67; // r9d
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 v68; // r12d
  int SharedModeEnginePeriodicity; // eax
  void *v70; // rcx
  struct tWAVEFORMATEX *v71; // rcx
  void *v72; // rcx
  void *v73; // rcx
  double v74; // xmm1_8
  int v75; // eax
  void *v76; // rcx
  struct tWAVEFORMATEX *v77; // rcx
  void *v78; // rcx
  void *v79; // rcx
  unsigned __int16 *v80; // rdi
  int v81; // eax
  CEndpointStoreCache *v82; // rcx
  int v83; // r8d
  void *v84; // rcx
  struct tWAVEFORMATEX *v85; // rcx
  void *v86; // rcx
  void *v87; // rcx
  int EndpointStore; // eax
  void *v89; // rcx
  struct tWAVEFORMATEX *v90; // rcx
  void *v91; // rcx
  void *v92; // rcx
  int CustomResourceManagerService; // eax
  void *v94; // rcx
  struct tWAVEFORMATEX *v95; // rcx
  void *v96; // rcx
  void *v97; // rcx
  struct _RTL_CRITICAL_SECTION *v98; // rbx
  __int64 v99; // rax
  struct CEndpointStore *v100; // rdi
  __int64 (__fastcall *v101)(struct IDeviceGraphManager *, CEndpointCharacteristics **, _QWORD, __int64); // rsi
  int v102; // eax
  int v103; // esi
  void *v104; // rcx
  struct tWAVEFORMATEX *v105; // rcx
  void *v106; // rcx
  void *v107; // rcx
  int *v108; // r8
  int v109; // r9d
  int v110; // ecx
  void *v111; // rcx
  struct tWAVEFORMATEX *v112; // rcx
  void *v113; // rcx
  void *v114; // rcx
  LPVOID *v115; // r14
  __int64 (__fastcall *v116)(LPVOID *, __int64 **); // rsi
  int v117; // eax
  void *v118; // rcx
  struct tWAVEFORMATEX *v119; // rcx
  void *v120; // rcx
  void *v121; // rcx
  __int64 *v122; // rcx
  void *v123; // rcx
  struct tWAVEFORMATEX *v124; // rcx
  void *v125; // rcx
  void *v126; // rcx
  void *v127; // rcx
  struct tWAVEFORMATEX *v128; // rcx
  void *v129; // rcx
  void *v130; // rcx
  int SaDeviceForSharedStream; // eax
  int v132; // ecx
  int v133; // r8d
  unsigned int v134; // edi
  void *v135; // rcx
  struct tWAVEFORMATEX *v136; // rcx
  void *v137; // rcx
  void *v138; // rcx
  int v139; // eax
  int v140; // ecx
  int v141; // r8d
  void *v142; // rcx
  struct tWAVEFORMATEX *v143; // rcx
  void *v144; // rcx
  void *v145; // rcx
  __int64 v146; // rax
  int v147; // edi
  _DWORD *v148; // rdi
  int v149; // r8d
  int v150; // r9d
  struct IBridgeStreamInstanceProxy *v151; // rax
  void *v152; // rcx
  struct tWAVEFORMATEX *v153; // rcx
  void *v154; // rcx
  void *v155; // rcx
  _DWORD *v156; // r8
  int v157; // r8d
  int v158; // r9d
  int v159; // [rsp+20h] [rbp-338h]
  int v160; // [rsp+20h] [rbp-338h]
  int v161; // [rsp+20h] [rbp-338h]
  int v162; // [rsp+20h] [rbp-338h]
  int v163; // [rsp+20h] [rbp-338h]
  LPVOID pv; // [rsp+F0h] [rbp-268h] BYREF
  LPVOID v165; // [rsp+F8h] [rbp-260h] BYREF
  struct tWAVEFORMATEX *Src; // [rsp+100h] [rbp-258h] BYREF
  LPVOID v167; // [rsp+108h] [rbp-250h] BYREF
  __int64 *v168; // [rsp+110h] [rbp-248h] BYREF
  struct IStreamGroupProxy *v169; // [rsp+118h] [rbp-240h] BYREF
  void *v170; // [rsp+120h] [rbp-238h] BYREF
  const wchar_t *v171; // [rsp+128h] [rbp-230h] BYREF
  struct IUnknown *v172; // [rsp+130h] [rbp-228h] BYREF
  __int64 v173; // [rsp+138h] [rbp-220h] BYREF
  char v174; // [rsp+140h] [rbp-218h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+148h] [rbp-210h] BYREF
  __int64 v176; // [rsp+150h] [rbp-208h] BYREF
  LPVOID *v177; // [rsp+158h] [rbp-200h] BYREF
  struct tWAVEFORMATEX *v178; // [rsp+160h] [rbp-1F8h] BYREF
  char v179; // [rsp+168h] [rbp-1F0h]
  _QWORD v180[2]; // [rsp+170h] [rbp-1E8h] BYREF
  struct _GUID Buf1; // [rsp+180h] [rbp-1D8h] BYREF
  CEndpointCharacteristics *v182[2]; // [rsp+190h] [rbp-1C8h] BYREF
  __int64 v183; // [rsp+1A0h] [rbp-1B8h]
  __int128 v184; // [rsp+1A8h] [rbp-1B0h] BYREF
  __int64 v185; // [rsp+1B8h] [rbp-1A0h]
  struct CEndpointStore *v186[2]; // [rsp+1C0h] [rbp-198h] BYREF
  struct _GUID v187; // [rsp+1D0h] [rbp-188h] BYREF
  LPCRITICAL_SECTION v188[2]; // [rsp+1E0h] [rbp-178h] BYREF
  __int64 v189; // [rsp+1F0h] [rbp-168h] BYREF
  void *p_pv; // [rsp+1F8h] [rbp-160h] BYREF
  struct tWAVEFORMATEX *v191; // [rsp+200h] [rbp-158h] BYREF
  char v192; // [rsp+208h] [rbp-150h]
  struct IStreamGroupProxy *v193; // [rsp+210h] [rbp-148h] BYREF
  unsigned __int16 *v194; // [rsp+218h] [rbp-140h]
  struct IBridgeStreamInstanceProxy **v195; // [rsp+220h] [rbp-138h]
  LPVOID *v196; // [rsp+228h] [rbp-130h] BYREF
  struct tWAVEFORMATEX *v197; // [rsp+230h] [rbp-128h] BYREF
  char v198; // [rsp+238h] [rbp-120h]
  _DWORD v199[6]; // [rsp+240h] [rbp-118h] BYREF
  __int64 v200; // [rsp+258h] [rbp-100h]
  struct _GUID v201; // [rsp+260h] [rbp-F8h]
  __int64 v202; // [rsp+270h] [rbp-E8h]
  unsigned __int16 *v203; // [rsp+278h] [rbp-E0h]
  struct tWAVEFORMATEX **p_Src; // [rsp+290h] [rbp-C8h] BYREF
  struct tWAVEFORMATEX *v205; // [rsp+298h] [rbp-C0h] BYREF
  _BYTE v206[24]; // [rsp+2A0h] [rbp-B8h]
  struct IStreamGroupProxy **v207; // [rsp+2B8h] [rbp-A0h]
  __int128 *v208; // [rsp+2C0h] [rbp-98h]
  __int64 *v209; // [rsp+2C8h] [rbp-90h]
  struct _GUID v210; // [rsp+2D0h] [rbp-88h] BYREF
  _QWORD v211[2]; // [rsp+2E0h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+358h] [rbp+0h]

  v194 = a2;
  v211[0] = this;
  v189 = a3;
  v193 = a5;
  v195 = a6;
  *(_OWORD *)v182 = 0;
  v183 = 0;
  EndpointCharacteristicsDescriptor = GetEndpointCharacteristicsDescriptor(
                                        a2,
                                        0,
                                        (struct EndpointCharacteristicsDescriptor *)v182);
  v8 = EndpointCharacteristicsDescriptor;
  if ( EndpointCharacteristicsDescriptor < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC90,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)EndpointCharacteristicsDescriptor,
      v159);
    EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)v182);
    return v8;
  }
  v10 = *((_BYTE *)v182[0] + 264);
  v174 = v10;
  if ( !a4 || (v11 = 3, !v10) )
    v11 = 2;
  v184 = 0;
  v185 = 0;
  v172 = 0;
  wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v172);
  v12 = CAudioPumpDspResourceTracker::AcquireAudioPumpDspTokenForEndpoint(
          s_DspResourceTracker,
          (struct EndpointCharacteristicsDescriptor *)v182,
          &v172);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC9C,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v12,
      v159);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v172);
    std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v184);
    EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)v182);
    return v13;
  }
  if ( *((_QWORD *)&v184 + 1) == v185 )
  {
    std::vector<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>>::_Emplace_reallocate<wil::com_ptr_t<IUnknown,wil::err_returncode_policy> const &>(
      &v184,
      *((_QWORD *)&v184 + 1),
      &v172);
  }
  else
  {
    wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>(
      *((_QWORD *)&v184 + 1),
      v172);
    *((_QWORD *)&v184 + 1) += 8LL;
  }
  v210 = GUID_00000000_0000_0000_0000_000000000000;
  v187 = GUID_00000000_0000_0000_0000_000000000000;
  Buf1 = GUID_00000000_0000_0000_0000_000000000000;
  *(GUID *)v186 = GUID_00000000_0000_0000_0000_000000000000;
  *(GUID *)v188 = GUID_00000000_0000_0000_0000_000000000000;
  AudioPumpDspResourceTokenFromTokenList = TryGetAudioPumpDspResourceTokenFromTokenList(&v177, &v184);
  v15 = *(struct IUnknown **)(AudioPumpDspResourceTokenFromTokenList + 8);
  *(_QWORD *)(AudioPumpDspResourceTokenFromTokenList + 8) = 0;
  v171 = (const wchar_t *)v15;
  AudioPumpDspResourceTokenPair::~AudioPumpDspResourceTokenPair((AudioPumpDspResourceTokenPair *)&v177);
  v16 = a4 && v10;
  ConnectorTypeForStream = GetConnectorTypeForStream(
                             (struct EndpointCharacteristicsDescriptor *)v182,
                             0x20002u,
                             AUDCLNT_SHAREMODE_SHARED,
                             v16,
                             0,
                             0,
                             v15);
  LODWORD(lpCriticalSection) = ConnectorTypeForStream;
  v18 = DeriveAudioProcessingModeConfiguration(0, 0, 0, v182);
  v19 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCBC,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v18,
      v11);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v171);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v172);
    std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v184);
    EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)v182);
    return v19;
  }
  if ( v15 )
    v20 = GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf;
  else
    v20 = v210;
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v171);
  v165 = 0;
  v167 = 0;
  Src = 0;
  pv = 0;
  p_pv = &pv;
  v191 = 0;
  v192 = 1;
  p_Src = &Src;
  v205 = 0;
  v206[0] = 1;
  v196 = &v167;
  v197 = 0;
  v198 = 1;
  v177 = &v165;
  v178 = 0;
  v179 = 1;
  v210 = v20;
  v21 = v187;
  v22 = DeriveDeviceGraphFormatsForStream(
          (struct EndpointCharacteristicsDescriptor *)v182,
          0,
          ConnectorTypeForStream,
          AUDCLNT_SHAREMODE_SHARED,
          0,
          &Buf1,
          &v187,
          &v210,
          0,
          &v178,
          &v197,
          &v205,
          &v191);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v177);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v196);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_Src);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCD2,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v22,
      v160);
    v23 = pv;
    pv = 0;
    if ( v23 )
      CoTaskMemFree(v23);
    v24 = Src;
    Src = 0;
    if ( v24 )
      CoTaskMemFree(v24);
    v25 = v167;
    v167 = 0;
    if ( v25 )
      CoTaskMemFree(v25);
    v26 = v165;
    v165 = 0;
    if ( v26 )
      CoTaskMemFree(v26);
LABEL_124:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v172);
    std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v184);
    EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)v182);
    return (unsigned int)v22;
  }
  v27 = v165;
  if ( v165 )
  {
    v35 = *(unsigned __int16 *)v165;
    if ( (_WORD)v35 == 0xFFFE )
    {
      v39 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v39 > 4u && (unsigned __int8)tlgKeywordOn(v39, 512) )
      {
        LODWORD(v168) = v27[5];
        *(_QWORD *)&Buf1.Data1 = v27 + 6;
        LODWORD(v170) = *((_DWORD *)v165 + 2);
        LODWORD(v177) = *((_DWORD *)v165 + 1);
        LOWORD(v169) = *((_WORD *)v165 + 1);
        v171 = L"WAVEFORMATEXTENSIBLE";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v40,
          (unsigned int)&byte_1801A2AEF,
          v40,
          v41,
          (__int64)&v171,
          (__int64)&v169,
          (__int64)&v177,
          (__int64)&v170,
          (__int64)&Buf1,
          (__int64)&v168);
      }
    }
    else
    {
      *(_QWORD *)&v210.Data2 = *(_QWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data2;
      *(_DWORD *)&v210.Data4[4] = *(_DWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data4[4];
      v210.Data1 = v35;
      v36 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v36 > 4u && (unsigned __int8)tlgKeywordOn(v36, 512) )
      {
        *(_QWORD *)&Buf1.Data1 = &v210;
        LODWORD(v170) = *((_DWORD *)v165 + 2);
        LODWORD(v168) = *((_DWORD *)v165 + 1);
        LOWORD(v169) = *((_WORD *)v165 + 1);
        v171 = L"WAVEFORMATEX";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          v37,
          (unsigned int)byte_1801A2B93,
          v37,
          v38,
          (__int64)&v171,
          (__int64)&v169,
          (__int64)&v168,
          (__int64)&v170,
          (__int64)&Buf1);
      }
    }
  }
  else
  {
    v28 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
    if ( *v28 > 4u && (unsigned __int8)tlgKeywordOn(v28, 512) )
    {
      LODWORD(v169) = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v29,
        (unsigned int)word_1801A2C2A,
        v29,
        v30,
        (__int64)&v169);
    }
  }
  v31 = v167;
  if ( v167 )
  {
    v42 = *(unsigned __int16 *)v167;
    if ( (_WORD)v42 == 0xFFFE )
    {
      v46 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v46 > 4u && (unsigned __int8)tlgKeywordOn(v46, 512) )
      {
        LODWORD(v177) = v31[5];
        *(_QWORD *)&Buf1.Data1 = v31 + 6;
        LODWORD(v168) = *((_DWORD *)v167 + 2);
        LODWORD(v170) = *((_DWORD *)v167 + 1);
        LOWORD(v169) = *((_WORD *)v167 + 1);
        v171 = L"WAVEFORMATEXTENSIBLE";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v47,
          (unsigned int)byte_1801A294D,
          v47,
          v48,
          (__int64)&v171,
          (__int64)&v169,
          (__int64)&v170,
          (__int64)&v168,
          (__int64)&Buf1,
          (__int64)&v177);
      }
    }
    else
    {
      *(_QWORD *)&v210.Data2 = *(_QWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data2;
      *(_DWORD *)&v210.Data4[4] = *(_DWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data4[4];
      v210.Data1 = v42;
      v43 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v43 > 4u && (unsigned __int8)tlgKeywordOn(v43, 512) )
      {
        *(_QWORD *)&Buf1.Data1 = &v210;
        LODWORD(v177) = *((_DWORD *)v167 + 2);
        LODWORD(v168) = *((_DWORD *)v167 + 1);
        LOWORD(v169) = *((_WORD *)v167 + 1);
        v171 = L"WAVEFORMATEX";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          v44,
          (unsigned int)&dword_1801A29F4,
          v44,
          v45,
          (__int64)&v171,
          (__int64)&v169,
          (__int64)&v168,
          (__int64)&v177,
          (__int64)&Buf1);
      }
    }
  }
  else
  {
    v32 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
    if ( *v32 > 4u && (unsigned __int8)tlgKeywordOn(v32, 512) )
    {
      LODWORD(v177) = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v33,
        (unsigned int)&word_1801A2A8E,
        v33,
        v34,
        (__int64)&v177);
    }
  }
  v49 = Src;
  if ( Src )
  {
    wFormatTag = Src->wFormatTag;
    if ( (_WORD)wFormatTag == 0xFFFE )
    {
      v57 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v57 > 4u && (unsigned __int8)tlgKeywordOn(v57, 512) )
      {
        LODWORD(v177) = *(_DWORD *)&v49[1].nChannels;
        *(_QWORD *)&Buf1.Data1 = (char *)v49 + 24;
        LODWORD(v168) = Src->nAvgBytesPerSec;
        LODWORD(v170) = Src->nSamplesPerSec;
        LOWORD(v169) = Src->nChannels;
        v171 = L"WAVEFORMATEXTENSIBLE";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v58,
          (unsigned int)&word_1801A27AE,
          v58,
          v59,
          (__int64)&v171,
          (__int64)&v169,
          (__int64)&v170,
          (__int64)&v168,
          (__int64)&Buf1,
          (__int64)&v177);
      }
    }
    else
    {
      *(_QWORD *)&v210.Data2 = *(_QWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data2;
      *(_DWORD *)&v210.Data4[4] = *(_DWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data4[4];
      v210.Data1 = wFormatTag;
      v54 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v54 > 4u && (unsigned __int8)tlgKeywordOn(v54, 512) )
      {
        *(_QWORD *)&Buf1.Data1 = &v210;
        LODWORD(v177) = Src->nAvgBytesPerSec;
        LODWORD(v168) = Src->nSamplesPerSec;
        LOWORD(v169) = Src->nChannels;
        v171 = L"WAVEFORMATEX";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          v55,
          (unsigned int)&dword_1801A2854,
          v55,
          v56,
          (__int64)&v171,
          (__int64)&v169,
          (__int64)&v168,
          (__int64)&v177,
          (__int64)&Buf1);
      }
    }
  }
  else
  {
    v50 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
    if ( *v50 > 4u && (unsigned __int8)tlgKeywordOn(v50, 512) )
    {
      LODWORD(v177) = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v51,
        (unsigned int)byte_1801A28ED,
        v51,
        v52,
        (__int64)&v177);
    }
  }
  v60 = pv;
  if ( pv )
  {
    v64 = *(unsigned __int16 *)pv;
    if ( (_WORD)v64 == 0xFFFE )
    {
      v156 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v156 > 4u && (unsigned __int8)tlgKeywordOn(v156, 512) )
      {
        LODWORD(v177) = v60[5];
        *(_QWORD *)&Buf1.Data1 = v60 + 6;
        LODWORD(v168) = *((_DWORD *)pv + 2);
        LODWORD(v170) = *((_DWORD *)pv + 1);
        LOWORD(v169) = *((_WORD *)pv + 1);
        v171 = L"WAVEFORMATEXTENSIBLE";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v157,
          (unsigned int)word_1801A2612,
          v157,
          v158,
          (__int64)&v171,
          (__int64)&v169,
          (__int64)&v170,
          (__int64)&v168,
          (__int64)&Buf1,
          (__int64)&v177);
      }
    }
    else
    {
      *(_QWORD *)&v210.Data2 = *(_QWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data2;
      *(_DWORD *)&v210.Data4[4] = *(_DWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data4[4];
      v210.Data1 = v64;
      v65 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v65 > 4u && (unsigned __int8)tlgKeywordOn(v65, 512) )
      {
        *(_QWORD *)&Buf1.Data1 = &v210;
        LODWORD(v177) = *((_DWORD *)pv + 2);
        LODWORD(v168) = *((_DWORD *)pv + 1);
        LOWORD(v169) = *((_WORD *)pv + 1);
        v171 = L"WAVEFORMATEX";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          v66,
          (unsigned int)&byte_1801A26B7,
          v66,
          v67,
          (__int64)&v171,
          (__int64)&v169,
          (__int64)&v168,
          (__int64)&v177,
          (__int64)&Buf1);
      }
    }
  }
  else
  {
    v61 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
    if ( *v61 > 4u && (unsigned __int8)tlgKeywordOn(v61, 512) )
    {
      LODWORD(v177) = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v62,
        (unsigned int)&byte_1801A274F,
        v62,
        v63,
        (__int64)&v177);
    }
  }
  LODWORD(v169) = 0;
  v210 = v20;
  v68 = (int)lpCriticalSection;
  SharedModeEnginePeriodicity = EffectPack::GetSharedModeEnginePeriodicity(
                                  v182[1],
                                  (unsigned int)lpCriticalSection,
                                  pv,
                                  &v210);
  v22 = SharedModeEnginePeriodicity;
  if ( SharedModeEnginePeriodicity < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCDC,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)SharedModeEnginePeriodicity,
      0);
    v70 = pv;
    pv = 0;
    if ( v70 )
      CoTaskMemFree(v70);
    v71 = Src;
    Src = 0;
    if ( v71 )
      CoTaskMemFree(v71);
    v72 = v167;
    v167 = 0;
    if ( v72 )
      CoTaskMemFree(v72);
    v73 = v165;
    v165 = 0;
    if ( v73 )
      CoTaskMemFree(v73);
    goto LABEL_124;
  }
  v74 = (double)(int)v169 * 10000000.0 / (double)*((int *)pv + 1) + 0.5;
  v173 = 0;
  v210 = *(struct _GUID *)v188;
  v187 = v21;
  Buf1 = v20;
  v75 = InitializeStreamAndModeDescriptors(
          (AudioModeEffectsWatcherFactory *)v182,
          v68,
          &Buf1,
          (__int64)&v187,
          (__int64)&v210,
          0,
          0,
          (__int64)v165,
          0,
          (unsigned int)(int)v74,
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
          (__int64)&v173);
  v22 = v75;
  if ( v75 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCE5,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v75,
      v161);
    std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v173);
    v76 = pv;
    pv = 0;
    if ( v76 )
      CoTaskMemFree(v76);
    v77 = Src;
    Src = 0;
    if ( v77 )
      CoTaskMemFree(v77);
    v78 = v167;
    v167 = 0;
    if ( v78 )
      CoTaskMemFree(v78);
    v79 = v165;
    v165 = 0;
    if ( v79 )
      CoTaskMemFree(v79);
    goto LABEL_124;
  }
  memset_0(v199, 0, 0x50u);
  v202 = (unsigned int)(int)v74;
  v199[0] = v11;
  v201 = v21;
  v199[2] = v68;
  v80 = v194;
  v203 = v194;
  v199[1] = 1;
  v199[4] = GetCurrentProcessId();
  v200 = v189;
  if ( v173 )
  {
    *(_DWORD *)(*(_QWORD *)(v173 + 8) + 8LL) = *((unsigned __int16 *)v165 + 8) + 18;
    *(_QWORD *)(*(_QWORD *)(v173 + 8) + 16LL) = v165;
  }
  v199[3] = v68 == eConnectorCount;
  v176 = 0;
  v210 = *(struct _GUID *)v186;
  v81 = DeriveStreamGroupParametersForStream(v182, (unsigned int)v68, v11, v202);
  v22 = v81;
  if ( v81 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCFD,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v81,
      v161);
    std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v176);
    std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v173);
    v84 = pv;
    pv = 0;
    if ( v84 )
      CoTaskMemFree(v84);
    v85 = Src;
    Src = 0;
    if ( v85 )
      CoTaskMemFree(v85);
    v86 = v167;
    v167 = 0;
    if ( v86 )
      CoTaskMemFree(v86);
    v87 = v165;
    v165 = 0;
    if ( v87 )
      CoTaskMemFree(v87);
    goto LABEL_124;
  }
  if ( (Microsoft_Windows_AudioEnableBits & 0x20) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      (_DWORD)v82,
      (unsigned int)AudioResourceManager_StreamSettings_Derived,
      v83,
      1,
      (__int64)&v210);
  v186[0] = 0;
  EndpointStore = CEndpointStoreCache::GetEndpointStore(v82, v80, v186);
  v22 = EndpointStore;
  if ( EndpointStore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD02,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)EndpointStore,
      v161);
    wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(v186);
    std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v176);
    std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v173);
    v89 = pv;
    pv = 0;
    if ( v89 )
      CoTaskMemFree(v89);
    v90 = Src;
    Src = 0;
    if ( v90 )
      CoTaskMemFree(v90);
    v91 = v167;
    v167 = 0;
    if ( v91 )
      CoTaskMemFree(v91);
    v92 = v165;
    v165 = 0;
    if ( v92 )
      CoTaskMemFree(v92);
    goto LABEL_124;
  }
  v180[0] = 0;
  v170 = 0;
  CustomResourceManagerService = CEndpointCharacteristics::TryGetCustomResourceManagerService(
                                   v182[0],
                                   &GUID_475d74a7_6824_4b91_89be_33d893b255ed,
                                   &v170);
  v22 = CustomResourceManagerService;
  if ( CustomResourceManagerService < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD08,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)CustomResourceManagerService,
      v161);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v170);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v180);
    wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(v186);
    std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v176);
    std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v173);
    v94 = pv;
    pv = 0;
    if ( v94 )
      CoTaskMemFree(v94);
    v95 = Src;
    Src = 0;
    if ( v95 )
      CoTaskMemFree(v95);
    v96 = v167;
    v167 = 0;
    if ( v96 )
      CoTaskMemFree(v96);
    v97 = v165;
    v165 = 0;
    if ( v97 )
      CoTaskMemFree(v97);
    goto LABEL_124;
  }
  v98 = 0;
  v171 = 0;
  if ( v170 )
  {
    v99 = (*(__int64 (__fastcall **)(void *, LPCRITICAL_SECTION *))(*(_QWORD *)v170 + 104LL))(v170, &lpCriticalSection);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::operator=(
      &v171,
      v99);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    v98 = (struct _RTL_CRITICAL_SECTION *)v171;
  }
  v100 = v186[0];
  (*(void (__fastcall **)(_QWORD, LPCRITICAL_SECTION *))(**((_QWORD **)v186[0] + 13) + 128LL))(
    *((_QWORD *)v186[0] + 13),
    v188);
  v177 = 0;
  v101 = *(__int64 (__fastcall **)(struct IDeviceGraphManager *, CEndpointCharacteristics **, _QWORD, __int64))(*(_QWORD *)g_DeviceGraphManager + 48LL);
  wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v177);
  v162 = 0;
  v102 = v101(g_DeviceGraphManager, v182, *((_QWORD *)v100 + 13), v176);
  v103 = v102;
  if ( v102 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD17,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v102,
      0);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v177);
    if ( v188[0] )
      LeaveCriticalSection(v188[0]);
    if ( v98 )
      LeaveCriticalSection(v98);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v170);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v180);
    wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(v186);
    std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v176);
    std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v173);
    v104 = pv;
    pv = 0;
    if ( v104 )
      CoTaskMemFree(v104);
    v105 = Src;
    Src = 0;
    if ( v105 )
      CoTaskMemFree(v105);
    v106 = v167;
    v167 = 0;
    if ( v106 )
      CoTaskMemFree(v106);
    v107 = v165;
    v165 = 0;
    if ( v107 )
      CoTaskMemFree(v107);
LABEL_189:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v172);
    std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v184);
    EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)v182);
    return (unsigned int)v103;
  }
  p_Src = (struct tWAVEFORMATEX **)&v177;
  v205 = (struct tWAVEFORMATEX *)v199;
  *(_QWORD *)v206 = &v173;
  *(_QWORD *)&v206[8] = &v176;
  *(_QWORD *)&v206[16] = v180;
  v207 = &v193;
  v208 = &v184;
  v209 = &v189;
  v103 = lambda_cb723a5ef8b52b0dc033746828a6c36f_::operator()(&p_Src);
  v108 = (int *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
  v110 = *v108;
  if ( (unsigned int)*v108 > 4 )
  {
    v169 = v193;
    *(_QWORD *)&v187.Data1 = v189;
    *(_QWORD *)&v210.Data1 = v177;
    LODWORD(lpCriticalSection) = v103;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      (_DWORD)v108,
      (unsigned int)&dword_1801A25B4,
      (_DWORD)v108,
      v109,
      (__int64)&lpCriticalSection,
      (__int64)&v210,
      (__int64)&v187,
      (__int64)&v169);
  }
  if ( v103 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD37,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v103,
      v162);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v177);
    if ( v188[0] )
      LeaveCriticalSection(v188[0]);
    if ( v98 )
      LeaveCriticalSection(v98);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v170);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v180);
    wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(v186);
    std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v176);
    std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v173);
    v111 = pv;
    pv = 0;
    if ( v111 )
      CoTaskMemFree(v111);
    v112 = Src;
    Src = 0;
    if ( v112 )
      CoTaskMemFree(v112);
    v113 = v167;
    v167 = 0;
    if ( v113 )
      CoTaskMemFree(v113);
    v114 = v165;
    v165 = 0;
    if ( v114 )
      CoTaskMemFree(v114);
    goto LABEL_189;
  }
  if ( (Microsoft_Windows_AudioEnableBits & 0x20) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      v110,
      (unsigned int)AudioResourceManager_Stream_Created,
      (_DWORD)v108,
      1,
      (__int64)&v210);
  v168 = 0;
  v115 = v177;
  v116 = (__int64 (__fastcall *)(LPVOID *, __int64 **))*((_QWORD *)*v177 + 28);
  wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v168);
  v117 = v116(v115, &v168);
  v103 = v117;
  if ( v117 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD3D,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v117,
      v162);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v168);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v177);
    if ( v188[0] )
      LeaveCriticalSection(v188[0]);
    if ( v98 )
      LeaveCriticalSection(v98);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v170);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v180);
    wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(v186);
    std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v176);
    std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v173);
    v118 = pv;
    pv = 0;
    if ( v118 )
      CoTaskMemFree(v118);
    v119 = Src;
    Src = 0;
    if ( v119 )
      CoTaskMemFree(v119);
    v120 = v167;
    v167 = 0;
    if ( v120 )
      CoTaskMemFree(v120);
    v121 = v165;
    v165 = 0;
    if ( v121 )
      CoTaskMemFree(v121);
    goto LABEL_189;
  }
  v122 = v168;
  if ( !v168 )
  {
    lpCriticalSection = 0;
    p_pv = &lpCriticalSection;
    v191 = 0;
    v192 = 1;
    v210 = v21;
    v187 = v20;
    v103 = DeriveSaDeviceParametersForStream(
             (struct EndpointCharacteristicsDescriptor *)v182,
             AUDCLNT_SHAREMODE_SHARED,
             v68,
             &v187,
             &v210,
             (struct tWAVEFORMATEX *)pv,
             Src,
             *(_QWORD *)(v176 + 24),
             (struct SaDeviceParams **)&v191);
    wil::details::out_param_t<std::unique_ptr<SaDeviceParams>>::~out_param_t<std::unique_ptr<SaDeviceParams>>(&p_pv);
    if ( v103 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD45,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
        (const char *)(unsigned int)v103,
        v163);
      std::unique_ptr<SaDeviceParams>::~unique_ptr<SaDeviceParams>(&lpCriticalSection);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v168);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v177);
      if ( v188[0] )
        LeaveCriticalSection(v188[0]);
      if ( v98 )
        LeaveCriticalSection(v98);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v170);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v180);
      wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(v186);
      std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v176);
      std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v173);
      v123 = pv;
      pv = 0;
      if ( v123 )
        CoTaskMemFree(v123);
      v124 = Src;
      Src = 0;
      if ( v124 )
        CoTaskMemFree(v124);
      v125 = v167;
      v167 = 0;
      if ( v125 )
        CoTaskMemFree(v125);
      v126 = v165;
      v165 = 0;
      if ( v126 )
        CoTaskMemFree(v126);
      goto LABEL_189;
    }
    if ( CEndpointCharacteristics::DoesExclusiveModeOverrideShared(v182[0])
      && _InterlockedCompareExchange((volatile signed __int32 *)(*((_QWORD *)v100 + 12) + 276LL), 0, 0) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD4E,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
        (const char *)0x887C005CLL,
        v163);
      std::unique_ptr<SaDeviceParams>::~unique_ptr<SaDeviceParams>(&lpCriticalSection);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v168);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v177);
      if ( v188[0] )
        LeaveCriticalSection(v188[0]);
      if ( v98 )
        LeaveCriticalSection(v98);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v170);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v180);
      wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(v186);
      std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v176);
      std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v173);
      v127 = pv;
      pv = 0;
      if ( v127 )
        CoTaskMemFree(v127);
      v128 = Src;
      Src = 0;
      if ( v128 )
        CoTaskMemFree(v128);
      v129 = v167;
      v167 = 0;
      if ( v129 )
        CoTaskMemFree(v129);
      v130 = v165;
      v165 = 0;
      if ( v130 )
        CoTaskMemFree(v130);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v172);
      std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v184);
      EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)v182);
      return 2289827932LL;
    }
    *(_WORD *)((char *)&v205 + 5) = 0;
    HIBYTE(v205) = 0;
    *(_DWORD *)&v206[20] = 0;
    BYTE4(v205) = 1;
    LODWORD(v205) = 0;
    p_Src = 0;
    *(GUID *)&v206[4] = v20;
    *(_DWORD *)v206 = v68;
    wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v168);
    SaDeviceForSharedStream = CAudioResourceManager::GetSaDeviceForSharedStream(v211[0], v182, v170, lpCriticalSection);
    v134 = SaDeviceForSharedStream;
    if ( SaDeviceForSharedStream < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD5C,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
        (const char *)(unsigned int)SaDeviceForSharedStream,
        131074);
      std::unique_ptr<SaDeviceParams>::~unique_ptr<SaDeviceParams>(&lpCriticalSection);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v168);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v177);
      if ( v188[0] )
        LeaveCriticalSection(v188[0]);
      if ( v98 )
        LeaveCriticalSection(v98);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v170);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v180);
      wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(v186);
      std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v176);
      std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v173);
      v135 = pv;
      pv = 0;
      if ( v135 )
        CoTaskMemFree(v135);
      v136 = Src;
      Src = 0;
      if ( v136 )
        CoTaskMemFree(v136);
      v137 = v167;
      v167 = 0;
      if ( v137 )
        CoTaskMemFree(v137);
      v138 = v165;
      v165 = 0;
      if ( v138 )
        CoTaskMemFree(v138);
LABEL_218:
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v172);
      std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v184);
      EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)v182);
      return v134;
    }
    if ( (Microsoft_Windows_AudioEnableBits & 0x20) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(
        v132,
        (unsigned int)AudioResourceManager_SaDevice_Created,
        v133,
        1,
        (__int64)v211);
    v139 = (*(__int64 (__fastcall **)(struct IDeviceGraphManager *, LPVOID *, __int64 *, __int64))(*(_QWORD *)g_DeviceGraphManager
                                                                                                 + 32LL))(
             g_DeviceGraphManager,
             v177,
             v168,
             1);
    v134 = v139;
    if ( v139 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD68,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
        (const char *)(unsigned int)v139,
        0);
      std::unique_ptr<SaDeviceParams>::~unique_ptr<SaDeviceParams>(&lpCriticalSection);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v168);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v177);
      if ( v188[0] )
        LeaveCriticalSection(v188[0]);
      if ( v98 )
        LeaveCriticalSection(v98);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v170);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v180);
      wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(v186);
      std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v176);
      std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v173);
      v142 = pv;
      pv = 0;
      if ( v142 )
        CoTaskMemFree(v142);
      v143 = Src;
      Src = 0;
      if ( v143 )
        CoTaskMemFree(v143);
      v144 = v167;
      v167 = 0;
      if ( v144 )
        CoTaskMemFree(v144);
      v145 = v165;
      v165 = 0;
      if ( v145 )
        CoTaskMemFree(v145);
      goto LABEL_218;
    }
    if ( (Microsoft_Windows_AudioEnableBits & 0x20) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(
        v140,
        (unsigned int)AudioResourceManager_SaDevice_Connected,
        v141,
        1,
        (__int64)v211);
    std::unique_ptr<SaDeviceParams>::~unique_ptr<SaDeviceParams>(&lpCriticalSection);
    v122 = v168;
  }
  *(_QWORD *)&Buf1.Data1 = 0;
  v146 = *v122;
  p_pv = &Buf1;
  v191 = 0;
  v192 = 1;
  v147 = (*(__int64 (__fastcall **)(__int64 *, struct tWAVEFORMATEX **))(v146 + 120))(v122, &v191);
  wil::details::out_param_t<std::unique_ptr<SaDeviceParams>>::~out_param_t<std::unique_ptr<SaDeviceParams>>(&p_pv);
  if ( v147 >= 0 )
  {
    v148 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
    if ( *v148 > 4u )
    {
      v211[0] = (*(__int64 (__fastcall **)(struct IStreamGroupProxy *))(*(_QWORD *)v193 + 152LL))(v193);
      LOBYTE(v169) = v174;
      *(_QWORD *)&v210.Data1 = v194;
      *(_QWORD *)&v187.Data1 = v189;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v148,
        (unsigned int)&unk_1801A2540,
        v149,
        v150,
        (__int64)&v187,
        (__int64)&v210,
        (__int64)&v169,
        (__int64)v211);
    }
  }
  std::unique_ptr<SaDeviceParams>::~unique_ptr<SaDeviceParams>(&Buf1);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v168);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v177);
  if ( v188[0] )
    LeaveCriticalSection(v188[0]);
  if ( v98 )
    LeaveCriticalSection(v98);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v170);
  v151 = (struct IBridgeStreamInstanceProxy *)v180[0];
  v180[0] = 0;
  *v195 = v151;
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v180);
  wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(v186);
  std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v176);
  std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v173);
  v152 = pv;
  pv = 0;
  if ( v152 )
    CoTaskMemFree(v152);
  v153 = Src;
  Src = 0;
  if ( v153 )
    CoTaskMemFree(v153);
  v154 = v167;
  v167 = 0;
  if ( v154 )
    CoTaskMemFree(v154);
  v155 = v165;
  v165 = 0;
  if ( v155 )
    CoTaskMemFree(v155);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v172);
  std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v184);
  EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)v182);
  return 0;
}

```

## disassembly

```asm
0x1800c0154  mov     r11, rsp
0x1800c0157  push    rbx
0x1800c0158  push    rsi
0x1800c0159  push    rdi
0x1800c015a  push    r12
0x1800c015c  push    r13
0x1800c015e  push    r14
0x1800c0160  push    r15
0x1800c0162  sub     rsp, 320h
0x1800c0169  movaps  xmmword ptr [r11-48h], xmm6
0x1800c016e  movaps  xmmword ptr [r11-58h], xmm7
0x1800c0173  mov     rax, cs:__security_cookie
0x1800c017a  xor     rax, rsp
0x1800c017d  mov     [rsp+358h+var_68], rax
0x1800c0185  mov     sil, r9b
0x1800c0188  mov     r9, rdx
0x1800c018b  mov     [rsp+358h+var_140], rdx
0x1800c0193  mov     [rsp+358h+var_78], rcx
0x1800c019b  mov     [r11-168h], r8
0x1800c01a2  mov     rax, [rsp+358h+arg_20]
0x1800c01aa  mov     [r11-148h], rax
0x1800c01b1  mov     rax, [rsp+358h+arg_28]
0x1800c01b9  mov     [rsp+358h+var_138], rax
0x1800c01c1  xorps   xmm0, xmm0
0x1800c01c4  movdqu  xmmword ptr [rsp+358h+var_1C8], xmm0
0x1800c01cd  xor     r12d, r12d
0x1800c01d0  mov     [r11-1B8h], r12
0x1800c01d7  lea     r8, [r11-1C8h]; struct EndpointCharacteristicsDescriptor *
0x1800c01de  xor     edx, edx; int
0x1800c01e0  mov     rcx, r9; unsigned __int16 *
0x1800c01e3  call    ?GetEndpointCharacteristicsDescriptor@@YAJPEBGHPEAUEndpointCharacteristicsDescriptor@@@Z; GetEndpointCharacteristicsDescriptor(ushort const *,int,EndpointCharacteristicsDescriptor *)
0x1800c01e8  mov     ebx, eax
0x1800c01ea  test    eax, eax
0x1800c01ec  jns     short loc_1800C021F
0x1800c01ee  mov     rcx, [rsp+358h]; this
0x1800c01f6  mov     r9d, eax; char *
0x1800c01f9  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800c0200  mov     edx, 0C90h; void *
0x1800c0205  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c020a  nop
0x1800c020b  lea     rcx, [rsp+358h+var_1C8]; this
0x1800c0213  call    ??1EndpointCharacteristicsDescriptor@@QEAA@XZ; EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor(void)
0x1800c0218  mov     eax, ebx
0x1800c021a  jmp     loc_1800C26B4
0x1800c021f  mov     rax, [rsp+358h+var_1C8]
0x1800c0227  mov     r14b, [rax+108h]
0x1800c022e  mov     [rsp+358h+var_218], r14b
0x1800c0236  test    sil, sil
0x1800c0239  jz      short loc_1800C0246
0x1800c023b  test    r14b, r14b
0x1800c023e  mov     r13d, 3
0x1800c0244  jnz     short loc_1800C024C
0x1800c0246  mov     r13d, 2
0x1800c024c  xorps   xmm0, xmm0
0x1800c024f  movdqu  [rsp+358h+var_1B0], xmm0
0x1800c0258  mov     [rsp+358h+var_1A0], r12
0x1800c0260  mov     [rsp+358h+var_228], r12
0x1800c0268  lea     rcx, [rsp+358h+var_228]
0x1800c0270  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x1800c0275  lea     r8, [rsp+358h+var_228]; struct IUnknown **
0x1800c027d  lea     rdx, [rsp+358h+var_1C8]; struct EndpointCharacteristicsDescriptor *
0x1800c0285  mov     rcx, cs:?s_DspResourceTracker@@3V?$com_ptr_t@VCAudioPumpDspResourceTracker@@Uerr_returncode_policy@wil@@@wil@@A; this
0x1800c028c  call    ?AcquireAudioPumpDspTokenForEndpoint@CAudioPumpDspResourceTracker@@QEAAJPEAUEndpointCharacteristicsDescriptor@@PEAPEAUIUnknown@@@Z; CAudioPumpDspResourceTracker::AcquireAudioPumpDspTokenForEndpoint(EndpointCharacteristicsDescriptor *,IUnknown * *)
0x1800c0291  mov     ebx, eax
0x1800c0293  test    eax, eax
0x1800c0295  jns     short loc_1800C02E4
0x1800c0297  mov     rcx, [rsp+358h]; this
0x1800c029f  mov     r9d, eax; char *
0x1800c02a2  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800c02a9  mov     edx, 0C9Ch; void *
0x1800c02ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c02b3  nop
0x1800c02b4  lea     rcx, [rsp+358h+var_228]
0x1800c02bc  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800c02c1  nop
0x1800c02c2  lea     rcx, [rsp+358h+var_1B0]
0x1800c02ca  call    ??1?$vector@V?$com_ptr_t@VCAudioStream@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VCAudioStream@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(void)
0x1800c02cf  nop
0x1800c02d0  lea     rcx, [rsp+358h+var_1C8]; this
0x1800c02d8  call    ??1EndpointCharacteristicsDescriptor@@QEAA@XZ; EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor(void)
0x1800c02dd  mov     eax, ebx
0x1800c02df  jmp     loc_1800C26B4
0x1800c02e4  mov     rax, qword ptr [rsp+358h+var_1B0+8]
0x1800c02ec  cmp     rax, [rsp+358h+var_1A0]
0x1800c02f4  jz      short loc_1800C0311
0x1800c02f6  mov     rdx, [rsp+358h+var_228]
0x1800c02fe  mov     rcx, rax
0x1800c0301  call    ??0?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAVCEndpointCharacteristics@@@Z; wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>(CEndpointCharacteristics *)
0x1800c0306  add     qword ptr [rsp+358h+var_1B0+8], 8
0x1800c030f  jmp     short loc_1800C0329
0x1800c0311  lea     r8, [rsp+358h+var_228]
0x1800c0319  mov     rdx, rax
0x1800c031c  lea     rcx, [rsp+358h+var_1B0]
0x1800c0324  call    ??$_Emplace_reallocate@AEBV?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@@?$vector@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@AEAAPEAV?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAV23@AEBV23@@Z; std::vector<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>>::_Emplace_reallocate<wil::com_ptr_t<IUnknown,wil::err_returncode_policy> const &>(wil::com_ptr_t<IUnknown,wil::err_returncode_policy> * const,wil::com_ptr_t<IUnknown,wil::err_returncode_policy> const &)
0x1800c0329  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800c0330  movdqu  xmmword ptr [rsp+358h+var_88.Data1], xmm0
0x1800c0339  movdqu  xmmword ptr [rsp+358h+var_188.Data1], xmm0
0x1800c0342  movdqu  xmmword ptr [rsp+358h+Buf1.Data1], xmm0
0x1800c034b  movdqu  xmmword ptr [rsp+358h+var_198], xmm0
0x1800c0354  movdqu  xmmword ptr [rsp+358h+var_178], xmm0
0x1800c035d  lea     rdx, [rsp+358h+var_1B0]
0x1800c0365  lea     rcx, [rsp+358h+var_200]
0x1800c036d  call    ?TryGetAudioPumpDspResourceTokenFromTokenList@@YA?AUAudioPumpDspResourceTokenPair@@AEBV?$vector@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@@Z; TryGetAudioPumpDspResourceTokenFromTokenList(std::vector<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>> const &)
0x1800c0372  mov     rdi, [rax+8]
0x1800c0376  mov     [rax+8], r12
0x1800c037a  mov     [rsp+358h+var_230], rdi
0x1800c0382  lea     rcx, [rsp+358h+var_200]; this
0x1800c038a  call    ??1AudioPumpDspResourceTokenPair@@QEAA@XZ; AudioPumpDspResourceTokenPair::~AudioPumpDspResourceTokenPair(void)
0x1800c038f  test    sil, sil
0x1800c0392  jz      short loc_1800C03A4
0x1800c0394  test    r14b, r14b
0x1800c0397  jz      short loc_1800C03A4
0x1800c0399  mov     r15d, 1
0x1800c039f  mov     r9d, r15d
0x1800c03a2  jmp     short loc_1800C03AD
0x1800c03a4  mov     r9d, r12d; int
0x1800c03a7  mov     r15d, 1
0x1800c03ad  mov     [rsp+358h+Src], rdi; struct IUnknown *
0x1800c03b2  mov     [rsp+358h+var_330], r12; struct IProcessSubmixProxy *
0x1800c03b7  mov     qword ptr [rsp+358h+var_338], r12; struct tWAVEFORMATEX *
0x1800c03bc  xor     r8d, r8d; enum _AUDCLNT_SHAREMODE
0x1800c03bf  mov     edx, 20002h; unsigned int
0x1800c03c4  lea     rcx, [rsp+358h+var_1C8]; struct EndpointCharacteristicsDescriptor *
0x1800c03cc  call    ?GetConnectorTypeForStream@@YA?AW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUEndpointCharacteristicsDescriptor@@KW4_AUDCLNT_SHAREMODE@@HPEBUtWAVEFORMATEX@@PEAUIProcessSubmixProxy@@PEAUIUnknown@@@Z; GetConnectorTypeForStream(EndpointCharacteristicsDescriptor *,ulong,_AUDCLNT_SHAREMODE,int,tWAVEFORMATEX const *,IProcessSubmixProxy *,IUnknown *)
0x1800c03d1  mov     esi, eax
0x1800c03d3  mov     dword ptr [rsp+358h+lpCriticalSection], eax
0x1800c03da  lea     rax, [rsp+358h+var_178]
0x1800c03e2  mov     [rsp+358h+var_2E0], rax
0x1800c03e7  lea     rax, [rsp+358h+var_198]
0x1800c03ef  mov     [rsp+358h+var_2E8], rax
0x1800c03f4  lea     rax, [rsp+358h+Buf1]
0x1800c03fc  mov     [rsp+358h+var_2F0], rax
0x1800c0401  lea     rax, [rsp+358h+var_188]
0x1800c0409  mov     [rsp+358h+var_2F8], rax
0x1800c040e  lea     rax, [rsp+358h+var_88]
0x1800c0416  mov     [rsp+358h+var_300], rax
0x1800c041b  mov     [rsp+358h+var_308], r12
0x1800c0420  mov     dword ptr [rsp+358h+var_310], r12d
0x1800c0425  mov     dword ptr [rsp+358h+var_318], r12d
0x1800c042a  mov     [rsp+358h+var_320], r12
0x1800c042f  mov     dword ptr [rsp+358h+Src], esi
0x1800c0433  mov     dword ptr [rsp+358h+var_330], r12d
0x1800c0438  mov     [rsp+358h+var_338], r13d; int
0x1800c043d  lea     r9, [rsp+358h+var_1C8]
0x1800c0445  xor     r8d, r8d
0x1800c0448  xor     edx, edx
0x1800c044a  xor     ecx, ecx
0x1800c044c  call    ?DeriveAudioProcessingModeConfiguration@@YAJKHHPEAUEndpointCharacteristicsDescriptor@@W4SYSTEM_AUDIO_STREAM_TYPE@@W4_AUDCLNT_SHAREMODE@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUIProcessSubmixProxy@@HHPEBUtWAVEFORMATEX@@PEAU_GUID@@6666@Z; DeriveAudioProcessingModeConfiguration(ulong,int,int,EndpointCharacteristicsDescriptor *,SYSTEM_AUDIO_STREAM_TYPE,_AUDCLNT_SHAREMODE,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,IProcessSubmixProxy *,int,int,tWAVEFORMATEX const *,_GUID *,_GUID *,_GUID *,_GUID *,_GUID *)
0x1800c0451  mov     ebx, eax
0x1800c0453  test    eax, eax
0x1800c0455  jns     short loc_1800C04B2
0x1800c0457  mov     rcx, [rsp+358h]; this
0x1800c045f  mov     r9d, eax; char *
0x1800c0462  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800c0469  mov     edx, 0CBCh; void *
0x1800c046e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c0473  nop
0x1800c0474  lea     rcx, [rsp+358h+var_230]
0x1800c047c  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800c0481  nop
0x1800c0482  lea     rcx, [rsp+358h+var_228]
0x1800c048a  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800c048f  nop
0x1800c0490  lea     rcx, [rsp+358h+var_1B0]
0x1800c0498  call    ??1?$vector@V?$com_ptr_t@VCAudioStream@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VCAudioStream@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(void)
0x1800c049d  nop
0x1800c049e  lea     rcx, [rsp+358h+var_1C8]; this
0x1800c04a6  call    ??1EndpointCharacteristicsDescriptor@@QEAA@XZ; EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor(void)
0x1800c04ab  mov     eax, ebx
0x1800c04ad  jmp     loc_1800C26B4
0x1800c04b2  test    rdi, rdi
0x1800c04b5  jz      short loc_1800C04C0
0x1800c04b7  movaps  xmm6, xmmword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1
0x1800c04be  jmp     short loc_1800C04C8
0x1800c04c0  movaps  xmm6, xmmword ptr [rsp+358h+var_88.Data1]
0x1800c04c8  lea     rcx, [rsp+358h+var_230]
0x1800c04d0  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800c04d5  mov     [rsp+358h+var_260], r12
0x1800c04dd  mov     [rsp+358h+var_250], r12
0x1800c04e5  mov     [rsp+358h+var_258], r12
0x1800c04ed  mov     [rsp+358h+pv], r12
0x1800c04f5  lea     rax, [rsp+358h+pv]
0x1800c04fd  mov     [rsp+358h+var_160], rax
0x1800c0505  mov     [rsp+358h+var_158], r12
0x1800c050d  mov     [rsp+358h+var_150], r15b
0x1800c0515  lea     rax, [rsp+358h+var_258]
0x1800c051d  mov     [rsp+358h+var_C8], rax
0x1800c0525  mov     [rsp+358h+var_C0], r12
0x1800c052d  mov     byte ptr [rsp+358h+var_B8], r15b
0x1800c0535  lea     rax, [rsp+358h+var_250]
0x1800c053d  mov     [rsp+358h+var_130], rax
0x1800c0545  mov     [rsp+358h+var_128], r12
0x1800c054d  mov     [rsp+358h+var_120], r15b
0x1800c0555  lea     rax, [rsp+358h+var_260]
0x1800c055d  mov     [rsp+358h+var_200], rax
0x1800c0565  mov     [rsp+358h+var_1F8], r12
0x1800c056d  mov     [rsp+358h+var_1F0], r15b
0x1800c0575  movdqa  xmmword ptr [rsp+358h+var_88.Data1], xmm6
0x1800c057e  movaps  xmm7, xmmword ptr [rsp+358h+var_188.Data1]
0x1800c0586  movdqa  xmmword ptr [rsp+358h+var_188.Data1], xmm7
0x1800c058f  movaps  xmm0, xmmword ptr [rsp+358h+Buf1.Data1]
0x1800c0597  movdqa  xmmword ptr [rsp+358h+Buf1.Data1], xmm0
0x1800c05a0  lea     rax, [rsp+358h+var_158]
0x1800c05a8  mov     [rsp+358h+var_2F8], rax; struct tWAVEFORMATEX **
0x1800c05ad  lea     rax, [rsp+358h+var_C0]
0x1800c05b5  mov     [rsp+358h+var_300], rax; struct tWAVEFORMATEX **
0x1800c05ba  lea     rax, [rsp+358h+var_128]
0x1800c05c2  mov     [rsp+358h+var_308], rax; struct tWAVEFORMATEX **
0x1800c05c7  lea     rax, [rsp+358h+var_1F8]
0x1800c05cf  mov     [rsp+358h+var_310], rax; struct tWAVEFORMATEX **
0x1800c05d4  mov     [rsp+358h+var_318], r12; struct tWAVEFORMATEX *
0x1800c05d9  lea     rax, [rsp+358h+var_88]
0x1800c05e1  mov     [rsp+358h+var_320], rax; struct _GUID *
0x1800c05e6  lea     rax, [rsp+358h+var_188]
0x1800c05ee  mov     [rsp+358h+Src], rax; struct _GUID *
0x1800c05f3  lea     rax, [rsp+358h+Buf1]
0x1800c05fb  mov     [rsp+358h+var_330], rax; struct _GUID *
0x1800c0600  mov     [rsp+358h+var_338], r12d; int
0x1800c0605  xor     r9d, r9d; enum _AUDCLNT_SHAREMODE
0x1800c0608  mov     r8d, esi; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x1800c060b  xor     edx, edx; bool
0x1800c060d  lea     rcx, [rsp+358h+var_1C8]; struct EndpointCharacteristicsDescriptor *
0x1800c0615  call    ?DeriveDeviceGraphFormatsForStream@@YAJPEAUEndpointCharacteristicsDescriptor@@_NW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@W4_AUDCLNT_SHAREMODE@@KU_GUID@@44PEAUtWAVEFORMATEX@@PEAPEAU5@666@Z; DeriveDeviceGraphFormatsForStream(EndpointCharacteristicsDescriptor *,bool,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_AUDCLNT_SHAREMODE,ulong,_GUID,_GUID,_GUID,tWAVEFORMATEX *,tWAVEFORMATEX * *,tWAVEFORMATEX * *,tWAVEFORMATEX * *,tWAVEFORMATEX * *)
0x1800c061a  mov     ebx, eax
0x1800c061c  lea     rcx, [rsp+358h+var_200]
0x1800c0624  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800c0629  nop
0x1800c062a  lea     rcx, [rsp+358h+var_130]
0x1800c0632  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800c0637  nop
0x1800c0638  lea     rcx, [rsp+358h+var_C8]
0x1800c0640  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800c0645  nop
0x1800c0646  lea     rcx, [rsp+358h+var_160]
0x1800c064e  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800c0653  test    ebx, ebx
0x1800c0655  jns     loc_1800C0718
0x1800c065b  mov     rcx, [rsp+358h]; this
0x1800c0663  mov     r9d, ebx; char *
0x1800c0666  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800c066d  mov     edx, 0CD2h; void *
0x1800c0672  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c0677  nop
0x1800c0678  mov     rcx, [rsp+358h+pv]; pv
0x1800c0680  mov     [rsp+358h+pv], r12
0x1800c0688  test    rcx, rcx
0x1800c068b  jz      short loc_1800C0694
0x1800c068d  call    cs:__imp_CoTaskMemFree
0x1800c0693  nop
0x1800c0694  mov     rcx, [rsp+358h+var_258]; pv
0x1800c069c  mov     [rsp+358h+var_258], r12
0x1800c06a4  test    rcx, rcx
0x1800c06a7  jz      short loc_1800C06B0
0x1800c06a9  call    cs:__imp_CoTaskMemFree
0x1800c06af  nop
0x1800c06b0  mov     rcx, [rsp+358h+var_250]; pv
0x1800c06b8  mov     [rsp+358h+var_250], r12
0x1800c06c0  test    rcx, rcx
0x1800c06c3  jz      short loc_1800C06CC
0x1800c06c5  call    cs:__imp_CoTaskMemFree
0x1800c06cb  nop
0x1800c06cc  mov     rcx, [rsp+358h+var_260]; pv
0x1800c06d4  mov     [rsp+358h+var_260], r12
0x1800c06dc  test    rcx, rcx
0x1800c06df  jz      short loc_1800C06E8
0x1800c06e1  call    cs:__imp_CoTaskMemFree
0x1800c06e7  nop
0x1800c06e8  lea     rcx, [rsp+358h+var_228]
0x1800c06f0  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800c06f5  nop
0x1800c06f6  lea     rcx, [rsp+358h+var_1B0]
0x1800c06fe  call    ??1?$vector@V?$com_ptr_t@VCAudioStream@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VCAudioStream@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(void)
0x1800c0703  nop
0x1800c0704  lea     rcx, [rsp+358h+var_1C8]; this
0x1800c070c  call    ??1EndpointCharacteristicsDescriptor@@QEAA@XZ; EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor(void)
0x1800c0711  mov     eax, ebx
0x1800c0713  jmp     loc_1800C26B4
0x1800c0718  mov     rdi, [rsp+358h+var_260]
0x1800c0720  test    rdi, rdi
0x1800c0723  jnz     loc_1800C07E7
0x1800c0729  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800c072e  mov     r8, [rax+8]
0x1800c0732  mov     eax, [r8]
0x1800c0735  mov     ebx, 200h
0x1800c073a  cmp     eax, 4
0x1800c073d  jbe     short loc_1800C0771
0x1800c073f  mov     edx, ebx
0x1800c0741  mov     rcx, r8
0x1800c0744  call    _tlgKeywordOn
0x1800c0749  test    al, al
0x1800c074b  jz      short loc_1800C0771
0x1800c074d  mov     dword ptr [rsp+358h+var_240], r12d
0x1800c0755  lea     rax, [rsp+358h+var_240]
0x1800c075d  mov     qword ptr [rsp+358h+var_338], rax
0x1800c0762  lea     rdx, word_1801A2C2A
0x1800c0769  mov     rcx, r8
0x1800c076c  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800c0771  mov     r14d, 0FFFEh
0x1800c0777  lea     rdi, aWaveformatexte; "WAVEFORMATEXTENSIBLE"
0x1800c077e  lea     rsi, aWaveformatex; "WAVEFORMATEX"
  ... truncated ...
```
