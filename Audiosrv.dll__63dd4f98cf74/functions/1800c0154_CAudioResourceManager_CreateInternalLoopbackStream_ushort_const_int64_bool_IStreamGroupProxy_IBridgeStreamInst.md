# CAudioResourceManager::CreateInternalLoopbackStream(ushort const *,__int64,bool,IStreamGroupProxy *,IBridgeStreamInstanceProxy * *)

- ea: `0x1800c0154`
- end: `0x1800c27bc`
- name: `?CreateInternalLoopbackStream@CAudioResourceManager@@IEAAJPEBG_J_NPEAUIStreamGroupProxy@@PEAPEAUIBridgeStreamInstanceProxy@@@Z`
- size: `9832`
- prototype: `__int64 __fastcall(CAudioResourceManager *this, unsigned __int16 *, __int64, char, struct IStreamGroupProxy *, struct IBridgeStreamInstanceProxy **)`
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
__int64 __fastcall CAudioResourceManager::CreateInternalLoopbackStream(
        CAudioResourceManager *this,
        unsigned __int16 *a2,
        __int64 a3,
        char a4,
        struct IStreamGroupProxy *a5,
        struct IBridgeStreamInstanceProxy **a6)
{
  int EndpointCharacteristicsDescriptor; // eax
  __int64 v8; // rdx
  unsigned int v9; // ebx
  char v11; // r14
  int v12; // r13d
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
  __int64 v82; // rax
  int v83; // eax
  CEndpointStoreCache *v84; // rcx
  int v85; // r8d
  void *v86; // rcx
  struct tWAVEFORMATEX *v87; // rcx
  void *v88; // rcx
  void *v89; // rcx
  int EndpointStore; // eax
  void *v91; // rcx
  struct tWAVEFORMATEX *v92; // rcx
  void *v93; // rcx
  void *v94; // rcx
  int CustomResourceManagerService; // eax
  void *v96; // rcx
  struct tWAVEFORMATEX *v97; // rcx
  void *v98; // rcx
  void *v99; // rcx
  struct _RTL_CRITICAL_SECTION *v100; // rbx
  __int64 v101; // rax
  struct CEndpointStore *v102; // rdi
  __int64 (__fastcall *v103)(struct IDeviceGraphManager *, CEndpointCharacteristics **, _QWORD, StreamGroupParams *); // rsi
  __int64 v104; // rdx
  int v105; // eax
  int v106; // esi
  void *v107; // rcx
  struct tWAVEFORMATEX *v108; // rcx
  void *v109; // rcx
  void *v110; // rcx
  __int64 v111; // rdx
  int *v112; // r8
  int v113; // r9d
  int v114; // ecx
  void *v115; // rcx
  struct tWAVEFORMATEX *v116; // rcx
  void *v117; // rcx
  void *v118; // rcx
  LPVOID *v119; // r14
  __int64 (__fastcall *v120)(LPVOID *, __int64 **); // rsi
  int v121; // eax
  void *v122; // rcx
  struct tWAVEFORMATEX *v123; // rcx
  void *v124; // rcx
  void *v125; // rcx
  __int64 *v126; // rcx
  void *v127; // rcx
  struct tWAVEFORMATEX *v128; // rcx
  void *v129; // rcx
  void *v130; // rcx
  __int64 v131; // rdx
  void *v132; // rcx
  struct tWAVEFORMATEX *v133; // rcx
  void *v134; // rcx
  void *v135; // rcx
  int SaDeviceForSharedStream; // eax
  int v137; // ecx
  int v138; // r8d
  unsigned int v139; // edi
  void *v140; // rcx
  struct tWAVEFORMATEX *v141; // rcx
  void *v142; // rcx
  void *v143; // rcx
  int v144; // eax
  int v145; // ecx
  int v146; // r8d
  void *v147; // rcx
  struct tWAVEFORMATEX *v148; // rcx
  void *v149; // rcx
  void *v150; // rcx
  __int64 v151; // rax
  int v152; // edi
  _DWORD *v153; // rdi
  int v154; // r8d
  int v155; // r9d
  struct IBridgeStreamInstanceProxy *v156; // rax
  void *v157; // rcx
  struct tWAVEFORMATEX *v158; // rcx
  void *v159; // rcx
  void *v160; // rcx
  _DWORD *v161; // r8
  int v162; // r8d
  int v163; // r9d
  int v164; // [rsp+20h] [rbp-338h]
  int v165; // [rsp+20h] [rbp-338h]
  __int64 v166; // [rsp+20h] [rbp-338h]
  int v167; // [rsp+20h] [rbp-338h]
  int v168; // [rsp+20h] [rbp-338h]
  int v169; // [rsp+20h] [rbp-338h]
  LPVOID pv; // [rsp+F0h] [rbp-268h] BYREF
  LPVOID v171; // [rsp+F8h] [rbp-260h] BYREF
  struct tWAVEFORMATEX *Src; // [rsp+100h] [rbp-258h] BYREF
  LPVOID v173; // [rsp+108h] [rbp-250h] BYREF
  __int64 *v174; // [rsp+110h] [rbp-248h] BYREF
  struct IStreamGroupProxy *v175; // [rsp+118h] [rbp-240h] BYREF
  void *v176; // [rsp+120h] [rbp-238h] BYREF
  const wchar_t *v177; // [rsp+128h] [rbp-230h] BYREF
  struct IUnknown *v178; // [rsp+130h] [rbp-228h] BYREF
  __int64 v179; // [rsp+138h] [rbp-220h] BYREF
  char v180; // [rsp+140h] [rbp-218h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+148h] [rbp-210h] BYREF
  StreamGroupParams *v182; // [rsp+150h] [rbp-208h] BYREF
  LPVOID *v183; // [rsp+158h] [rbp-200h] BYREF
  struct tWAVEFORMATEX *v184; // [rsp+160h] [rbp-1F8h] BYREF
  char v185; // [rsp+168h] [rbp-1F0h]
  _QWORD v186[2]; // [rsp+170h] [rbp-1E8h] BYREF
  struct _GUID Buf1; // [rsp+180h] [rbp-1D8h] BYREF
  CEndpointCharacteristics *v188[2]; // [rsp+190h] [rbp-1C8h] BYREF
  __int64 v189; // [rsp+1A0h] [rbp-1B8h]
  __int128 v190; // [rsp+1A8h] [rbp-1B0h] BYREF
  __int64 v191; // [rsp+1B8h] [rbp-1A0h]
  struct CEndpointStore *v192[2]; // [rsp+1C0h] [rbp-198h] BYREF
  struct _GUID v193; // [rsp+1D0h] [rbp-188h] BYREF
  LPCRITICAL_SECTION v194[2]; // [rsp+1E0h] [rbp-178h] BYREF
  __int64 v195; // [rsp+1F0h] [rbp-168h] BYREF
  void *p_pv; // [rsp+1F8h] [rbp-160h] BYREF
  struct tWAVEFORMATEX *v197; // [rsp+200h] [rbp-158h] BYREF
  char v198; // [rsp+208h] [rbp-150h]
  struct IStreamGroupProxy *v199; // [rsp+210h] [rbp-148h] BYREF
  unsigned __int16 *v200; // [rsp+218h] [rbp-140h]
  struct IBridgeStreamInstanceProxy **v201; // [rsp+220h] [rbp-138h]
  LPVOID *v202; // [rsp+228h] [rbp-130h] BYREF
  struct tWAVEFORMATEX *v203; // [rsp+230h] [rbp-128h] BYREF
  char v204; // [rsp+238h] [rbp-120h]
  _DWORD v205[6]; // [rsp+240h] [rbp-118h] BYREF
  __int64 v206; // [rsp+258h] [rbp-100h]
  struct _GUID v207; // [rsp+260h] [rbp-F8h]
  __int64 v208; // [rsp+270h] [rbp-E8h]
  unsigned __int16 *v209; // [rsp+278h] [rbp-E0h]
  struct tWAVEFORMATEX **p_Src; // [rsp+290h] [rbp-C8h] BYREF
  struct tWAVEFORMATEX *v211; // [rsp+298h] [rbp-C0h] BYREF
  _BYTE v212[24]; // [rsp+2A0h] [rbp-B8h]
  struct IStreamGroupProxy **v213; // [rsp+2B8h] [rbp-A0h]
  __int128 *v214; // [rsp+2C0h] [rbp-98h]
  __int64 *v215; // [rsp+2C8h] [rbp-90h]
  struct _GUID v216; // [rsp+2D0h] [rbp-88h] BYREF
  _QWORD v217[2]; // [rsp+2E0h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+358h] [rbp+0h]

  v200 = a2;
  v217[0] = this;
  v195 = a3;
  v199 = a5;
  v201 = a6;
  *(_OWORD *)v188 = 0;
  v189 = 0;
  EndpointCharacteristicsDescriptor = GetEndpointCharacteristicsDescriptor(
                                        a2,
                                        0,
                                        (struct EndpointCharacteristicsDescriptor *)v188);
  v9 = EndpointCharacteristicsDescriptor;
  if ( EndpointCharacteristicsDescriptor < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC90,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)EndpointCharacteristicsDescriptor,
      v164);
    EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)v188);
    return v9;
  }
  v11 = *((_BYTE *)v188[0] + 264);
  v180 = v11;
  if ( !a4 || (v12 = 3, !v11) )
    v12 = 2;
  v190 = 0;
  v191 = 0;
  v178 = 0;
  wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v178, v8);
  v13 = CAudioPumpDspResourceTracker::AcquireAudioPumpDspTokenForEndpoint(
          s_DspResourceTracker,
          (struct EndpointCharacteristicsDescriptor *)v188,
          &v178);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC9C,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v13,
      v164);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v178);
    std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v190);
    EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)v188);
    return v14;
  }
  if ( *((_QWORD *)&v190 + 1) == v191 )
  {
    std::vector<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>>::_Emplace_reallocate<wil::com_ptr_t<IUnknown,wil::err_returncode_policy> const &>(
      &v190,
      *((_QWORD *)&v190 + 1),
      &v178);
  }
  else
  {
    wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>(
      *((_QWORD *)&v190 + 1),
      v178);
    *((_QWORD *)&v190 + 1) += 8LL;
  }
  v216 = GUID_00000000_0000_0000_0000_000000000000;
  v193 = GUID_00000000_0000_0000_0000_000000000000;
  Buf1 = GUID_00000000_0000_0000_0000_000000000000;
  *(GUID *)v192 = GUID_00000000_0000_0000_0000_000000000000;
  *(GUID *)v194 = GUID_00000000_0000_0000_0000_000000000000;
  AudioPumpDspResourceTokenFromTokenList = TryGetAudioPumpDspResourceTokenFromTokenList(&v183, &v190);
  v16 = *(struct IUnknown **)(AudioPumpDspResourceTokenFromTokenList + 8);
  *(_QWORD *)(AudioPumpDspResourceTokenFromTokenList + 8) = 0;
  v177 = (const wchar_t *)v16;
  AudioPumpDspResourceTokenPair::~AudioPumpDspResourceTokenPair((AudioPumpDspResourceTokenPair *)&v183);
  v17 = a4 && v11;
  ConnectorTypeForStream = GetConnectorTypeForStream(
                             (struct EndpointCharacteristicsDescriptor *)v188,
                             0x20002u,
                             AUDCLNT_SHAREMODE_SHARED,
                             v17,
                             0,
                             0,
                             v16);
  LODWORD(lpCriticalSection) = ConnectorTypeForStream;
  v19 = DeriveAudioProcessingModeConfiguration(0, 0, 0, v188);
  v20 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCBC,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v19,
      v12);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v177);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v178);
    std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v190);
    EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)v188);
    return v20;
  }
  if ( v16 )
    v21 = GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf;
  else
    v21 = v216;
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v177);
  v171 = 0;
  v173 = 0;
  Src = 0;
  pv = 0;
  p_pv = &pv;
  v197 = 0;
  v198 = 1;
  p_Src = &Src;
  v211 = 0;
  v212[0] = 1;
  v202 = &v173;
  v203 = 0;
  v204 = 1;
  v183 = &v171;
  v184 = 0;
  v185 = 1;
  v216 = v21;
  v22 = v193;
  v23 = DeriveDeviceGraphFormatsForStream(
          v188,
          0,
          ConnectorTypeForStream,
          AUDCLNT_SHAREMODE_SHARED,
          0,
          (IAudioMediaType *)&Buf1,
          &v193,
          &v216,
          0,
          &v184,
          &v203,
          &v211,
          &v197);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v183);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v202);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_Src);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCD2,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v23,
      v165);
    v24 = pv;
    pv = 0;
    if ( v24 )
      CoTaskMemFree(v24);
    v25 = Src;
    Src = 0;
    if ( v25 )
      CoTaskMemFree(v25);
    v26 = v173;
    v173 = 0;
    if ( v26 )
      CoTaskMemFree(v26);
    v27 = v171;
    v171 = 0;
    if ( v27 )
      CoTaskMemFree(v27);
LABEL_124:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v178);
    std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v190);
    EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)v188);
    return (unsigned int)v23;
  }
  v28 = v171;
  if ( v171 )
  {
    v36 = *(unsigned __int16 *)v171;
    if ( (_WORD)v36 == 0xFFFE )
    {
      v40 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v40 > 4u && (unsigned __int8)tlgKeywordOn(v40, 512) )
      {
        LODWORD(v174) = v28[5];
        *(_QWORD *)&Buf1.Data1 = v28 + 6;
        LODWORD(v176) = *((_DWORD *)v171 + 2);
        LODWORD(v183) = *((_DWORD *)v171 + 1);
        LOWORD(v175) = *((_WORD *)v171 + 1);
        v177 = L"WAVEFORMATEXTENSIBLE";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v41,
          (unsigned int)&byte_1801A2AEF,
          v41,
          v42,
          (__int64)&v177,
          (__int64)&v175,
          (__int64)&v183,
          (__int64)&v176,
          (__int64)&Buf1,
          (__int64)&v174);
      }
    }
    else
    {
      *(_QWORD *)&v216.Data2 = *(_QWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data2;
      *(_DWORD *)&v216.Data4[4] = *(_DWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data4[4];
      v216.Data1 = v36;
      v37 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v37 > 4u && (unsigned __int8)tlgKeywordOn(v37, 512) )
      {
        *(_QWORD *)&Buf1.Data1 = &v216;
        LODWORD(v176) = *((_DWORD *)v171 + 2);
        LODWORD(v174) = *((_DWORD *)v171 + 1);
        LOWORD(v175) = *((_WORD *)v171 + 1);
        v177 = L"WAVEFORMATEX";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          v38,
          (unsigned int)byte_1801A2B93,
          v38,
          v39,
          (__int64)&v177,
          (__int64)&v175,
          (__int64)&v174,
          (__int64)&v176,
          (__int64)&Buf1);
      }
    }
  }
  else
  {
    v29 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
    if ( *v29 > 4u && (unsigned __int8)tlgKeywordOn(v29, 512) )
    {
      LODWORD(v175) = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v30,
        (unsigned int)word_1801A2C2A,
        v30,
        v31,
        (__int64)&v175);
    }
  }
  v32 = v173;
  if ( v173 )
  {
    v43 = *(unsigned __int16 *)v173;
    if ( (_WORD)v43 == 0xFFFE )
    {
      v47 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v47 > 4u && (unsigned __int8)tlgKeywordOn(v47, 512) )
      {
        LODWORD(v183) = v32[5];
        *(_QWORD *)&Buf1.Data1 = v32 + 6;
        LODWORD(v174) = *((_DWORD *)v173 + 2);
        LODWORD(v176) = *((_DWORD *)v173 + 1);
        LOWORD(v175) = *((_WORD *)v173 + 1);
        v177 = L"WAVEFORMATEXTENSIBLE";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v48,
          (unsigned int)byte_1801A294D,
          v48,
          v49,
          (__int64)&v177,
          (__int64)&v175,
          (__int64)&v176,
          (__int64)&v174,
          (__int64)&Buf1,
          (__int64)&v183);
      }
    }
    else
    {
      *(_QWORD *)&v216.Data2 = *(_QWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data2;
      *(_DWORD *)&v216.Data4[4] = *(_DWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data4[4];
      v216.Data1 = v43;
      v44 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v44 > 4u && (unsigned __int8)tlgKeywordOn(v44, 512) )
      {
        *(_QWORD *)&Buf1.Data1 = &v216;
        LODWORD(v183) = *((_DWORD *)v173 + 2);
        LODWORD(v174) = *((_DWORD *)v173 + 1);
        LOWORD(v175) = *((_WORD *)v173 + 1);
        v177 = L"WAVEFORMATEX";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          v45,
          (unsigned int)&dword_1801A29F4,
          v45,
          v46,
          (__int64)&v177,
          (__int64)&v175,
          (__int64)&v174,
          (__int64)&v183,
          (__int64)&Buf1);
      }
    }
  }
  else
  {
    v33 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
    if ( *v33 > 4u && (unsigned __int8)tlgKeywordOn(v33, 512) )
    {
      LODWORD(v183) = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v34,
        (unsigned int)&word_1801A2A8E,
        v34,
        v35,
        (__int64)&v183);
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
        LODWORD(v183) = *(_DWORD *)&v50[1].nChannels;
        *(_QWORD *)&Buf1.Data1 = (char *)v50 + 24;
        LODWORD(v174) = Src->nAvgBytesPerSec;
        LODWORD(v176) = Src->nSamplesPerSec;
        LOWORD(v175) = Src->nChannels;
        v177 = L"WAVEFORMATEXTENSIBLE";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v59,
          (unsigned int)&word_1801A27AE,
          v59,
          v60,
          (__int64)&v177,
          (__int64)&v175,
          (__int64)&v176,
          (__int64)&v174,
          (__int64)&Buf1,
          (__int64)&v183);
      }
    }
    else
    {
      *(_QWORD *)&v216.Data2 = *(_QWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data2;
      *(_DWORD *)&v216.Data4[4] = *(_DWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data4[4];
      v216.Data1 = wFormatTag;
      v55 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v55 > 4u && (unsigned __int8)tlgKeywordOn(v55, 512) )
      {
        *(_QWORD *)&Buf1.Data1 = &v216;
        LODWORD(v183) = Src->nAvgBytesPerSec;
        LODWORD(v174) = Src->nSamplesPerSec;
        LOWORD(v175) = Src->nChannels;
        v177 = L"WAVEFORMATEX";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          v56,
          (unsigned int)&dword_1801A2854,
          v56,
          v57,
          (__int64)&v177,
          (__int64)&v175,
          (__int64)&v174,
          (__int64)&v183,
          (__int64)&Buf1);
      }
    }
  }
  else
  {
    v51 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
    if ( *v51 > 4u && (unsigned __int8)tlgKeywordOn(v51, 512) )
    {
      LODWORD(v183) = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v52,
        (unsigned int)byte_1801A28ED,
        v52,
        v53,
        (__int64)&v183);
    }
  }
  v61 = pv;
  if ( pv )
  {
    v65 = *(unsigned __int16 *)pv;
    if ( (_WORD)v65 == 0xFFFE )
    {
      v161 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v161 > 4u && (unsigned __int8)tlgKeywordOn(v161, 512) )
      {
        LODWORD(v183) = v61[5];
        *(_QWORD *)&Buf1.Data1 = v61 + 6;
        LODWORD(v174) = *((_DWORD *)pv + 2);
        LODWORD(v176) = *((_DWORD *)pv + 1);
        LOWORD(v175) = *((_WORD *)pv + 1);
        v177 = L"WAVEFORMATEXTENSIBLE";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v162,
          (unsigned int)word_1801A2612,
          v162,
          v163,
          (__int64)&v177,
          (__int64)&v175,
          (__int64)&v176,
          (__int64)&v174,
          (__int64)&Buf1,
          (__int64)&v183);
      }
    }
    else
    {
      *(_QWORD *)&v216.Data2 = *(_QWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data2;
      *(_DWORD *)&v216.Data4[4] = *(_DWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data4[4];
      v216.Data1 = v65;
      v66 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v66 > 4u && (unsigned __int8)tlgKeywordOn(v66, 512) )
      {
        *(_QWORD *)&Buf1.Data1 = &v216;
        LODWORD(v183) = *((_DWORD *)pv + 2);
        LODWORD(v174) = *((_DWORD *)pv + 1);
        LOWORD(v175) = *((_WORD *)pv + 1);
        v177 = L"WAVEFORMATEX";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          v67,
          (unsigned int)&byte_1801A26B7,
          v67,
          v68,
          (__int64)&v177,
          (__int64)&v175,
          (__int64)&v174,
          (__int64)&v183,
          (__int64)&Buf1);
      }
    }
  }
  else
  {
    v62 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
    if ( *v62 > 4u && (unsigned __int8)tlgKeywordOn(v62, 512) )
    {
      LODWORD(v183) = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v63,
        (unsigned int)&byte_1801A274F,
        v63,
        v64,
        (__int64)&v183);
    }
  }
  LODWORD(v175) = 0;
  v216 = v21;
  v69 = (int)lpCriticalSection;
  SharedModeEnginePeriodicity = EffectPack::GetSharedModeEnginePeriodicity(
                                  v188[1],
                                  (unsigned int)lpCriticalSection,
                                  pv,
                                  &v216);
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
    v73 = v173;
    v173 = 0;
    if ( v73 )
      CoTaskMemFree(v73);
    v74 = v171;
    v171 = 0;
    if ( v74 )
      CoTaskMemFree(v74);
    goto LABEL_124;
  }
  v75 = (double)(int)v175 * 10000000.0 / (double)*((int *)pv + 1) + 0.5;
  v179 = 0;
  v216 = *(struct _GUID *)v194;
  v193 = v22;
  Buf1 = v21;
  v76 = InitializeStreamAndModeDescriptors(
          v188,
          0,
          0x20002u,
          v12,
          v69,
          &Buf1,
          &v193,
          &v216,
          0,
          0,
          (__int64)v171,
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
          (__int64)&v179);
  v23 = v76;
  if ( v76 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCE5,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v76,
      v166);
    std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v179);
    v77 = pv;
    pv = 0;
    if ( v77 )
      CoTaskMemFree(v77);
    v78 = Src;
    Src = 0;
    if ( v78 )
      CoTaskMemFree(v78);
    v79 = v173;
    v173 = 0;
    if ( v79 )
      CoTaskMemFree(v79);
    v80 = v171;
    v171 = 0;
    if ( v80 )
      CoTaskMemFree(v80);
    goto LABEL_124;
  }
  memset_0(v205, 0, 0x50u);
  v208 = (unsigned int)(int)v75;
  v205[0] = v12;
  v207 = v22;
  v205[2] = v69;
  v81 = v200;
  v209 = v200;
  v205[1] = 1;
  v205[4] = GetCurrentProcessId();
  v206 = v195;
  v82 = v179;
  if ( v179 )
  {
    *(_DWORD *)(*(_QWORD *)(v179 + 8) + 8LL) = *((unsigned __int16 *)v171 + 8) + 18;
    *(_QWORD *)(*(_QWORD *)(v179 + 8) + 16LL) = v171;
    v82 = v179;
  }
  v205[3] = v69 == eConnectorCount;
  v182 = 0;
  v216 = *(struct _GUID *)v192;
  v83 = DeriveStreamGroupParametersForStream(
          v188,
          v69,
          v12,
          v208,
          v166,
          &v216,
          0,
          0,
          (struct tWAVEFORMATEX *)v173,
          v82,
          0,
          &v182);
  v23 = v83;
  if ( v83 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCFD,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v83,
      v167);
    std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v182);
    std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v179);
    v86 = pv;
    pv = 0;
    if ( v86 )
      CoTaskMemFree(v86);
    v87 = Src;
    Src = 0;
    if ( v87 )
      CoTaskMemFree(v87);
    v88 = v173;
    v173 = 0;
    if ( v88 )
      CoTaskMemFree(v88);
    v89 = v171;
    v171 = 0;
    if ( v89 )
      CoTaskMemFree(v89);
    goto LABEL_124;
  }
  if ( (Microsoft_Windows_AudioEnableBits & 0x20) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      (_DWORD)v84,
      (unsigned int)AudioResourceManager_StreamSettings_Derived,
      v85,
      1,
      (__int64)&v216);
  v192[0] = 0;
  EndpointStore = CEndpointStoreCache::GetEndpointStore(v84, v81, v192);
  v23 = EndpointStore;
  if ( EndpointStore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD02,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)EndpointStore,
      v167);
    wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(v192);
    std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v182);
    std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v179);
    v91 = pv;
    pv = 0;
    if ( v91 )
      CoTaskMemFree(v91);
    v92 = Src;
    Src = 0;
    if ( v92 )
      CoTaskMemFree(v92);
    v93 = v173;
    v173 = 0;
    if ( v93 )
      CoTaskMemFree(v93);
    v94 = v171;
    v171 = 0;
    if ( v94 )
      CoTaskMemFree(v94);
    goto LABEL_124;
  }
  v186[0] = 0;
  v176 = 0;
  CustomResourceManagerService = CEndpointCharacteristics::TryGetCustomResourceManagerService(
                                   v188[0],
                                   &GUID_475d74a7_6824_4b91_89be_33d893b255ed,
                                   &v176);
  v23 = CustomResourceManagerService;
  if ( CustomResourceManagerService < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD08,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)CustomResourceManagerService,
      v167);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v176);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v186);
    wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(v192);
    std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v182);
    std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v179);
    v96 = pv;
    pv = 0;
    if ( v96 )
      CoTaskMemFree(v96);
    v97 = Src;
    Src = 0;
    if ( v97 )
      CoTaskMemFree(v97);
    v98 = v173;
    v173 = 0;
    if ( v98 )
      CoTaskMemFree(v98);
    v99 = v171;
    v171 = 0;
    if ( v99 )
      CoTaskMemFree(v99);
    goto LABEL_124;
  }
  v100 = 0;
  v177 = 0;
  if ( v176 )
  {
    v101 = (*(__int64 (__fastcall **)(void *, LPCRITICAL_SECTION *))(*(_QWORD *)v176 + 104LL))(v176, &lpCriticalSection);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::operator=(
      &v177,
      v101);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    v100 = (struct _RTL_CRITICAL_SECTION *)v177;
  }
  v102 = v192[0];
  (*(void (__fastcall **)(_QWORD, LPCRITICAL_SECTION *))(**((_QWORD **)v192[0] + 13) + 128LL))(
    *((_QWORD *)v192[0] + 13),
    v194);
  v183 = 0;
  v103 = *(__int64 (__fastcall **)(struct IDeviceGraphManager *, CEndpointCharacteristics **, _QWORD, StreamGroupParams *))(*(_QWORD *)g_DeviceGraphManager + 48LL);
  wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v183, v104);
  v168 = 0;
  v105 = v103(g_DeviceGraphManager, v188, *((_QWORD *)v102 + 13), v182);
  v106 = v105;
  if ( v105 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD17,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v105,
      0);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v183);
    if ( v194[0] )
      LeaveCriticalSection(v194[0]);
    if ( v100 )
      LeaveCriticalSection(v100);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v176);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v186);
    wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(v192);
    std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v182);
    std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v179);
    v107 = pv;
    pv = 0;
    if ( v107 )
      CoTaskMemFree(v107);
    v108 = Src;
    Src = 0;
    if ( v108 )
      CoTaskMemFree(v108);
    v109 = v173;
    v173 = 0;
    if ( v109 )
      CoTaskMemFree(v109);
    v110 = v171;
    v171 = 0;
    if ( v110 )
      CoTaskMemFree(v110);
LABEL_189:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v178);
    std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v190);
    EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)v188);
    return (unsigned int)v106;
  }
  p_Src = (struct tWAVEFORMATEX **)&v183;
  v211 = (struct tWAVEFORMATEX *)v205;
  *(_QWORD *)v212 = &v179;
  *(_QWORD *)&v212[8] = &v182;
  *(_QWORD *)&v212[16] = v186;
  v213 = &v199;
  v214 = &v190;
  v215 = &v195;
  v106 = lambda_cb723a5ef8b52b0dc033746828a6c36f_::operator()(&p_Src);
  v112 = (int *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
  v114 = *v112;
  if ( (unsigned int)*v112 > 4 )
  {
    v175 = v199;
    *(_QWORD *)&v193.Data1 = v195;
    *(_QWORD *)&v216.Data1 = v183;
    LODWORD(lpCriticalSection) = v106;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      (_DWORD)v112,
      (unsigned int)&dword_1801A25B4,
      (_DWORD)v112,
      v113,
      (__int64)&lpCriticalSection,
      (__int64)&v216,
      (__int64)&v193,
      (__int64)&v175);
  }
  if ( v106 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD37,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v106,
      v168);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v183);
    if ( v194[0] )
      LeaveCriticalSection(v194[0]);
    if ( v100 )
      LeaveCriticalSection(v100);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v176);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v186);
    wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(v192);
    std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v182);
    std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v179);
    v115 = pv;
    pv = 0;
    if ( v115 )
      CoTaskMemFree(v115);
    v116 = Src;
    Src = 0;
    if ( v116 )
      CoTaskMemFree(v116);
    v117 = v173;
    v173 = 0;
    if ( v117 )
      CoTaskMemFree(v117);
    v118 = v171;
    v171 = 0;
    if ( v118 )
      CoTaskMemFree(v118);
    goto LABEL_189;
  }
  if ( (Microsoft_Windows_AudioEnableBits & 0x20) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      v114,
      (unsigned int)AudioResourceManager_Stream_Created,
      (_DWORD)v112,
      1,
      (__int64)&v216);
  v174 = 0;
  v119 = v183;
  v120 = (__int64 (__fastcall *)(LPVOID *, __int64 **))*((_QWORD *)*v183 + 28);
  wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v174, v111);
  v121 = v120(v119, &v174);
  v106 = v121;
  if ( v121 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD3D,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v121,
      v168);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v174);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v183);
    if ( v194[0] )
      LeaveCriticalSection(v194[0]);
    if ( v100 )
      LeaveCriticalSection(v100);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v176);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v186);
    wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(v192);
    std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v182);
    std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v179);
    v122 = pv;
    pv = 0;
    if ( v122 )
      CoTaskMemFree(v122);
    v123 = Src;
    Src = 0;
    if ( v123 )
      CoTaskMemFree(v123);
    v124 = v173;
    v173 = 0;
    if ( v124 )
      CoTaskMemFree(v124);
    v125 = v171;
    v171 = 0;
    if ( v125 )
      CoTaskMemFree(v125);
    goto LABEL_189;
  }
  v126 = v174;
  if ( !v174 )
  {
    lpCriticalSection = 0;
    p_pv = &lpCriticalSection;
    v197 = 0;
    v198 = 1;
    v216 = v22;
    v193 = v21;
    v106 = DeriveSaDeviceParametersForStream(
             (struct EndpointCharacteristicsDescriptor *)v188,
             AUDCLNT_SHAREMODE_SHARED,
             v69,
             &v193,
             &v216,
             (struct tWAVEFORMATEX *)pv,
             Src,
             *((_QWORD *)v182 + 3),
             (struct SaDeviceParams **)&v197);
    wil::details::out_param_t<std::unique_ptr<SaDeviceParams>>::~out_param_t<std::unique_ptr<SaDeviceParams>>(&p_pv);
    if ( v106 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD45,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
        (const char *)(unsigned int)v106,
        v169);
      std::unique_ptr<SaDeviceParams>::~unique_ptr<SaDeviceParams>(&lpCriticalSection);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v174);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v183);
      if ( v194[0] )
        LeaveCriticalSection(v194[0]);
      if ( v100 )
        LeaveCriticalSection(v100);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v176);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v186);
      wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(v192);
      std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v182);
      std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v179);
      v127 = pv;
      pv = 0;
      if ( v127 )
        CoTaskMemFree(v127);
      v128 = Src;
      Src = 0;
      if ( v128 )
        CoTaskMemFree(v128);
      v129 = v173;
      v173 = 0;
      if ( v129 )
        CoTaskMemFree(v129);
      v130 = v171;
      v171 = 0;
      if ( v130 )
        CoTaskMemFree(v130);
      goto LABEL_189;
    }
    if ( CEndpointCharacteristics::DoesExclusiveModeOverrideShared(v188[0]) )
    {
      v131 = *((_QWORD *)v102 + 12);
      if ( _InterlockedCompareExchange((volatile signed __int32 *)(v131 + 276), 0, 0) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD4E,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
          (const char *)0x887C005CLL,
          v169);
        std::unique_ptr<SaDeviceParams>::~unique_ptr<SaDeviceParams>(&lpCriticalSection);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v174);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v183);
        if ( v194[0] )
          LeaveCriticalSection(v194[0]);
        if ( v100 )
          LeaveCriticalSection(v100);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v176);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v186);
        wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(v192);
        std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v182);
        std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v179);
        v132 = pv;
        pv = 0;
        if ( v132 )
          CoTaskMemFree(v132);
        v133 = Src;
        Src = 0;
        if ( v133 )
          CoTaskMemFree(v133);
        v134 = v173;
        v173 = 0;
        if ( v134 )
          CoTaskMemFree(v134);
        v135 = v171;
        v171 = 0;
        if ( v135 )
          CoTaskMemFree(v135);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v178);
        std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v190);
        EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)v188);
        return 2289827932LL;
      }
    }
    *(_WORD *)((char *)&v211 + 5) = 0;
    HIBYTE(v211) = 0;
    *(_DWORD *)&v212[20] = 0;
    BYTE4(v211) = 1;
    LODWORD(v211) = 0;
    p_Src = 0;
    *(GUID *)&v212[4] = v21;
    *(_DWORD *)v212 = v69;
    wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v174, v131);
    SaDeviceForSharedStream = CAudioResourceManager::GetSaDeviceForSharedStream(v217[0], v188, v176, lpCriticalSection);
    v139 = SaDeviceForSharedStream;
    if ( SaDeviceForSharedStream < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD5C,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
        (const char *)(unsigned int)SaDeviceForSharedStream,
        131074);
      std::unique_ptr<SaDeviceParams>::~unique_ptr<SaDeviceParams>(&lpCriticalSection);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v174);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v183);
      if ( v194[0] )
        LeaveCriticalSection(v194[0]);
      if ( v100 )
        LeaveCriticalSection(v100);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v176);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v186);
      wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(v192);
      std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v182);
      std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v179);
      v140 = pv;
      pv = 0;
      if ( v140 )
        CoTaskMemFree(v140);
      v141 = Src;
      Src = 0;
      if ( v141 )
        CoTaskMemFree(v141);
      v142 = v173;
      v173 = 0;
      if ( v142 )
        CoTaskMemFree(v142);
      v143 = v171;
      v171 = 0;
      if ( v143 )
        CoTaskMemFree(v143);
LABEL_218:
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v178);
      std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v190);
      EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)v188);
      return v139;
    }
    if ( (Microsoft_Windows_AudioEnableBits & 0x20) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(
        v137,
        (unsigned int)AudioResourceManager_SaDevice_Created,
        v138,
        1,
        (__int64)v217);
    v144 = (*(__int64 (__fastcall **)(struct IDeviceGraphManager *, LPVOID *, __int64 *, __int64))(*(_QWORD *)g_DeviceGraphManager
                                                                                                 + 32LL))(
             g_DeviceGraphManager,
             v183,
             v174,
             1);
    v139 = v144;
    if ( v144 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD68,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
        (const char *)(unsigned int)v144,
        0);
      std::unique_ptr<SaDeviceParams>::~unique_ptr<SaDeviceParams>(&lpCriticalSection);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v174);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v183);
      if ( v194[0] )
        LeaveCriticalSection(v194[0]);
      if ( v100 )
        LeaveCriticalSection(v100);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v176);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v186);
      wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(v192);
      std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v182);
      std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v179);
      v147 = pv;
      pv = 0;
      if ( v147 )
        CoTaskMemFree(v147);
      v148 = Src;
      Src = 0;
      if ( v148 )
        CoTaskMemFree(v148);
      v149 = v173;
      v173 = 0;
      if ( v149 )
        CoTaskMemFree(v149);
      v150 = v171;
      v171 = 0;
      if ( v150 )
        CoTaskMemFree(v150);
      goto LABEL_218;
    }
    if ( (Microsoft_Windows_AudioEnableBits & 0x20) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(
        v145,
        (unsigned int)AudioResourceManager_SaDevice_Connected,
        v146,
        1,
        (__int64)v217);
    std::unique_ptr<SaDeviceParams>::~unique_ptr<SaDeviceParams>(&lpCriticalSection);
    v126 = v174;
  }
  *(_QWORD *)&Buf1.Data1 = 0;
  v151 = *v126;
  p_pv = &Buf1;
  v197 = 0;
  v198 = 1;
  v152 = (*(__int64 (__fastcall **)(__int64 *, struct tWAVEFORMATEX **))(v151 + 120))(v126, &v197);
  wil::details::out_param_t<std::unique_ptr<SaDeviceParams>>::~out_param_t<std::unique_ptr<SaDeviceParams>>(&p_pv);
  if ( v152 >= 0 )
  {
    v153 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
    if ( *v153 > 4u )
    {
      v217[0] = (*(__int64 (__fastcall **)(struct IStreamGroupProxy *))(*(_QWORD *)v199 + 152LL))(v199);
      LOBYTE(v175) = v180;
      *(_QWORD *)&v216.Data1 = v200;
      *(_QWORD *)&v193.Data1 = v195;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v153,
        (unsigned int)&unk_1801A2540,
        v154,
        v155,
        (__int64)&v193,
        (__int64)&v216,
        (__int64)&v175,
        (__int64)v217);
    }
  }
  std::unique_ptr<SaDeviceParams>::~unique_ptr<SaDeviceParams>(&Buf1);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v174);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v183);
  if ( v194[0] )
    LeaveCriticalSection(v194[0]);
  if ( v100 )
    LeaveCriticalSection(v100);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v176);
  v156 = (struct IBridgeStreamInstanceProxy *)v186[0];
  v186[0] = 0;
  *v201 = v156;
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v186);
  wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(v192);
  std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v182);
  std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v179);
  v157 = pv;
  pv = 0;
  if ( v157 )
    CoTaskMemFree(v157);
  v158 = Src;
  Src = 0;
  if ( v158 )
    CoTaskMemFree(v158);
  v159 = v173;
  v173 = 0;
  if ( v159 )
    CoTaskMemFree(v159);
  v160 = v171;
  v171 = 0;
  if ( v160 )
    CoTaskMemFree(v160);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v178);
  std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v190);
  EndpointCharacteristicsDescriptor::~EndpointCharacteristicsDescriptor((EndpointCharacteristicsDescriptor *)v188);
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
