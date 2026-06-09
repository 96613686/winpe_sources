# DataStoreCache::TileStoreTransformer::UpdateTile(Windows::Internal::Tiles::ITileNotification * const,Windows::Internal::StateRepository::ITileViewStatics * const,Windows::Internal::StateRepository::IPackageUserStatics * const,Windows::Internal::StateRepository::IHostRuntimeStatics * const,Windows::Internal::StateRepository::IApplicationExtensionStatics * const,Windows::Internal::StateRepository::IUser * const,DataStoreTransformerTelemetry::TileStoreTransformerReconcileTiles &)

- ea: `0x18001b3e4`
- end: `0x18001d51b`
- name: `?UpdateTile@TileStoreTransformer@DataStoreCache@@AEAAXQEAUITileNotification@Tiles@Internal@Windows@@QEAUITileViewStatics@StateRepository@56@QEAUIPackageUserStatics@856@QEAUIHostRuntimeStatics@856@QEAUIApplicationExtensionStatics@856@QEAUIUser@856@AEAVTileStoreTransformerReconcileTiles@DataStoreTransformerTelemetry@@@Z`
- size: `8503`
- prototype: `void __fastcall(DataStoreCache::TileStoreTransformer *__hidden this, struct Windows::Internal::Tiles::ITileNotification *const, struct Windows::Internal::StateRepository::ITileViewStatics *const, struct Windows::Internal::StateRepository::IPackageUserStatics *const, struct Windows::Internal::StateRepository::IHostRuntimeStatics *const, struct Windows::Internal::StateRepository::IApplicationExtensionStatics *const, struct Windows::Internal::StateRepository::IUser *const, struct DataStoreTransformerTelemetry::TileStoreTransformerReconcileTiles *)`
- caller_count: `1`
- callee_count: `63`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18036e93c`

## callees

- `0x18000b5f0`
- `0x18000ce94`
- `0x1800108e4`
- `0x180010ce0`
- `0x1800112f8`
- `0x1800116e0`
- `0x180011858`
- `0x180011c34`
- `0x180011cd4`
- `0x180011e40`
- `0x180011ec8`
- `0x180013340`
- `0x180013504`
- `0x1800139dc`
- `0x180013b80`
- `0x180014650`
- `0x18001ac50`
- `0x18001b3e4`
- `0x18001dac0`
- `0x18001df50`
- `0x180022020`
- `0x180022ba0`
- `0x180047c88`
- `0x18004898c`
- `0x18006fd68`
- `0x180096c38`
- `0x1800a2c4c`
- `0x1800c5b3c`
- `0x1800c6f9c`
- `0x1800c7e8c`
- `0x1800c7eb8`
- `0x1800d3a50`
- `0x1800daa64`
- `0x1800dda54`
- `0x1800e4fd8`
- `0x1800e5370`
- `0x1800eaeb0`
- `0x18011e8bc`
- `0x180144638`
- `0x180144794`
- `0x18014483c`
- `0x180144904`
- `0x180146524`
- `0x180147be8`
- `0x18015596c`
- `0x1801593b0`
- `0x180161204`
- `0x180188a54`
- `0x180201e50`
- `0x18020511c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b73b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ba35`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001bbc3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c19a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c2c0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c3f0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c4c5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c649`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c8b4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b73b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ba35`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001bbc3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c19a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c2c0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c3f0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c4c5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c649`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c8b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bc4f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c224`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c54d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c7aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c93c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001cbdf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001cc61`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ccc9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001cd17`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d0a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d1c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d27a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bc4f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c224`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c54d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c7aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c93c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001cbdf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001cc61`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ccc9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001cd17`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d0a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d1c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d27a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001b6b9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001be2d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001c6f1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001b6b9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001be2d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001c6f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001bf3c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001c94f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001c9fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001bf3c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001c94f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001c9fd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001c810`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001c810`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001b708`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001b8a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001be74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001b708`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001b8a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001be74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b630`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b63f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b6f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b721`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b893`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001bd57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001bde2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001be62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001be8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c091`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c6b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c787`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c97f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cd6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cdb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cfaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d463`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b630`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b63f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b6f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b721`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b893`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001bd57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001bde2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001be62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001be8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c091`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c6b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c787`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c97f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cd6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cdb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cfaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d463`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001bcd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c03d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c7c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c7e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ca6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d21c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d287`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d299`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001bcd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c03d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c7c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c7e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ca6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d21c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d287`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d299`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18001ca34`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18001ca34`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18001ba8b`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18001c0b5`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18001c316`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18001c446`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18001c69f`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18001cb71`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18001cc84`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18001cd37`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18001ba8b`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18001c0b5`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18001c316`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18001c446`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18001c69f`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18001cb71`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18001cc84`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18001cd37`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001d475`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001d475`
- `ext-ms-win-appmodel-activation-l1-1-1!GetPackageExecutionContextForPackageByFullName` at `0x18001ca7f`
- `ext-ms-win-appmodel-activation-l1-1-1!GetPackageExecutionContextForPackageByFullName` at `0x18001ca7f`

## string_xrefs

- `0x18001cb3e`: `shellcommon\shell\datastorecache\transformers\tilestore\lib\tilestoretransformertilecontext.cpp`
- `0x18001c795`: `shellcommon\shell\DataStoreCache\inc\DataStoreCacheItemIdentifier.h`
- `0x18001c9b8`: `shellcommon\shell\DataStoreCache\inc\DataStoreCacheItemIdentifier.h`
- `0x18001c9d6`: `shellcommon\shell\DataStoreCache\inc\DataStoreCacheItemIdentifier.h`
- `0x18001b68e`: `shellcommon\shell\datastorecache\transformers\tilestore\lib\tilestoretransformer.cpp`
- `0x18001bebc`: `shellcommon\shell\datastorecache\transformers\tilestore\lib\tilestoretransformer.cpp`
- `0x18001bed1`: `shellcommon\shell\datastorecache\transformers\tilestore\lib\tilestoretransformer.cpp`
- `0x18001bee6`: `shellcommon\shell\datastorecache\transformers\tilestore\lib\tilestoretransformer.cpp`
- `0x18001befb`: `shellcommon\shell\datastorecache\transformers\tilestore\lib\tilestoretransformer.cpp`
- `0x18001c0bf`: `shellcommon\shell\datastorecache\transformers\tilestore\lib\tilestoretransformer.cpp`
- `0x18001c0d4`: `shellcommon\shell\datastorecache\transformers\tilestore\lib\tilestoretransformer.cpp`
- `0x18001c56f`: `shellcommon\shell\datastorecache\transformers\tilestore\lib\tilestoretransformer.cpp`
- `0x18001d1e8`: `shellcommon\shell\datastorecache\transformers\tilestore\lib\tilestoretransformer.cpp`
- `0x18001cab5`: `shellcommon\shell\DataStoreCache\Transformers\inc\DataStorePropertyTransformerBase.h`
- `0x18001cdbb`: `shellcommon\shell\DataStoreCache\Transformers\inc\DataStorePropertyTransformerBase.h`
- `0x18001cdcd`: `shellcommon\shell\DataStoreCache\Transformers\inc\DataStorePropertyTransformerBase.h`
- `0x18001cddf`: `shellcommon\shell\DataStoreCache\Transformers\inc\DataStorePropertyTransformerBase.h`
- `0x18001cdf1`: `shellcommon\shell\DataStoreCache\Transformers\inc\DataStorePropertyTransformerBase.h`
- `0x18001ce03`: `shellcommon\shell\DataStoreCache\Transformers\inc\DataStorePropertyTransformerBase.h`
- `0x18001ce15`: `shellcommon\shell\DataStoreCache\Transformers\inc\DataStorePropertyTransformerBase.h`
- `0x18001ce27`: `shellcommon\shell\DataStoreCache\Transformers\inc\DataStorePropertyTransformerBase.h`
- `0x18001ce39`: `shellcommon\shell\DataStoreCache\Transformers\inc\DataStorePropertyTransformerBase.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=59
void __fastcall DataStoreCache::TileStoreTransformer::UpdateTile(
        RTL_SRWLOCK *this,
        struct Windows::Internal::Tiles::ITileNotification *const a2,
        struct Windows::Internal::StateRepository::ITileViewStatics *const a3,
        struct Windows::Internal::StateRepository::IPackageUserStatics *const a4,
        struct Windows::Internal::StateRepository::IHostRuntimeStatics *const a5,
        struct Windows::Internal::StateRepository::IApplicationExtensionStatics *const a6,
        struct Windows::Internal::StateRepository::IUser *const a7,
        struct DataStoreTransformerTelemetry::TileStoreTransformerReconcileTiles *a8)
{
  PSRWLOCK v11; // r15
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  wil::details::in1diag3 *v17; // rcx
  int v18; // eax
  int v19; // eax
  int v20; // eax
  struct DataStoreCache::PropertyBagLookaside *v21; // rdi
  HSTRING *v22; // rax
  HSTRING v23; // rbx
  struct DataStoreCache::PropertyBagLookaside *v24; // rcx
  RTL_SRWLOCK *v25; // r13
  PSRWLOCK v26; // rdi
  RTL_SRWLOCK *v27; // r12
  HRESULT v28; // eax
  char v29; // bl
  __int64 v30; // rsi
  __int64 v31; // rsi
  __int64 v32; // rax
  _QWORD *Ptr; // rdx
  _QWORD *v34; // rbx
  _QWORD *v35; // r15
  _QWORD *v36; // r15
  __int64 v37; // rdx
  float v38; // xmm0_4
  __int64 v39; // rcx
  float v40; // xmm1_4
  _QWORD *v41; // rcx
  _QWORD *v42; // rax
  __int64 v43; // rsi
  _QWORD *v44; // rdx
  HSTRING *v45; // rdi
  HSTRING v46; // rbx
  HRESULT v47; // eax
  const char **v48; // r12
  const char **v49; // r13
  std::_Ref_count_base *v50; // rcx
  const char *v51; // r9
  int v52; // ecx
  RTL_SRWLOCK *v53; // rsi
  int v54; // edx
  int v55; // ecx
  int v56; // ecx
  int v57; // ecx
  int v58; // ecx
  int v59; // ebx
  _DWORD *v60; // rax
  const char *v61; // r9
  __int64 v62; // rax
  _QWORD *v63; // r8
  __int64 v64; // rdx
  int v65; // ecx
  int v66; // ecx
  int v67; // ecx
  int v68; // ecx
  int v69; // ecx
  int v70; // eax
  char *v71; // rax
  const char *v72; // r9
  __int64 v73; // rax
  _QWORD *v74; // r8
  __int64 v75; // rdx
  std::_Ref_count_base *v76; // r8
  std::_Ref_count_base *v77; // rcx
  int v78; // eax
  struct DataStoreTransformerTelemetry::TileStoreTransformerReconcileTiles *v79; // rbx
  DataStoreCache::DataItemIdentifier *v80; // rbx
  HSTRING v81; // rcx
  struct DataStoreCache::PropertyBagLookaside *v82; // rcx
  void *v83; // rcx
  __int64 v84; // rcx
  HRESULT v85; // eax
  char v86; // bl
  __int64 (__fastcall *v87)(struct DataStoreCache::PropertyBagLookaside *, HSTRING, HSTRING *); // rbx
  int v88; // eax
  int v89; // eax
  int v90; // eax
  wil::details::in1diag3 *v91; // rcx
  __int64 v92; // rcx
  HSTRING v93; // rcx
  HSTRING *v94; // rbx
  int v95; // eax
  _DWORD *v96; // rax
  const char *v97; // r9
  RTL_SRWLOCK *v98; // rbx
  __int64 v99; // rax
  _QWORD *v100; // r8
  __int64 v101; // rdx
  volatile signed __int32 *v102; // r8
  std::_Ref_count_base *v103; // rcx
  std::_Ref_count_base **v104; // rax
  const char *v105; // r9
  __int64 v106; // rax
  _QWORD *v107; // r8
  __int64 v108; // rdx
  int v109; // ebx
  __int64 v110; // rcx
  int v111; // eax
  _DWORD *v112; // rax
  const char *v113; // r9
  __int64 v114; // rax
  _QWORD *v115; // r8
  __int64 v116; // rdx
  std::_Ref_count_base **v117; // rax
  const char *v118; // r9
  RTL_SRWLOCK *v119; // rbx
  __int64 v120; // rax
  _QWORD *v121; // r8
  __int64 v122; // rdx
  std::_Ref_count_base *v123; // r8
  std::_Ref_count_base *v124; // rcx
  int v125; // eax
  int v126; // ebx
  _DWORD *v127; // rax
  const char *v128; // r9
  __int64 v129; // rax
  _QWORD *v130; // r8
  __int64 v131; // rdx
  struct DataStoreCache::PropertyBagLookaside *v132; // rsi
  const char *v133; // r9
  PVOID v134; // rcx
  char v135; // bl
  const WCHAR *StringRawBuffer; // rbx
  const WCHAR *v137; // rax
  int v138; // ebx
  _DWORD *v139; // rax
  const char *v140; // r9
  __int64 v141; // rax
  _QWORD *v142; // r8
  __int64 v143; // rdx
  volatile signed __int32 *v144; // r8
  std::_Ref_count_base *v145; // rcx
  struct DataStoreTransformerTelemetry::TileStoreTransformerReconcileTiles *v146; // rbx
  int v147; // eax
  HSTRING *PackageFullName; // rax
  PCWSTR v149; // rax
  int PackageExecutionContextForPackageByFullName; // eax
  std::_Ref_count_base *v151; // r8
  std::_Ref_count_base *v152; // rcx
  __int64 v153; // rcx
  __int64 v154; // r8
  std::_Ref_count_base *v155; // rcx
  volatile signed __int32 *v156; // r8
  std::_Ref_count_base *v157; // rcx
  volatile signed __int32 *v158; // r8
  std::_Ref_count_base *v159; // rcx
  struct Windows::Internal::Tiles::ISecondaryTile *SecondaryTile; // rdi
  __int64 (__fastcall *v161)(struct Windows::Internal::Tiles::ISecondaryTile *, HSTRING *); // rbx
  int v162; // eax
  HSTRING v163; // rcx
  __int64 v164; // rdx
  __int64 v165; // rax
  _QWORD *v166; // rdx
  _QWORD *v167; // r12
  _QWORD *v168; // r15
  __int64 v169; // rax
  HSTRING v170; // rdi
  unsigned __int8 (__fastcall *v171)(HSTRING, const struct _GUID *, GUID *, __int64); // rbx
  __int64 v172; // rax
  int v173; // eax
  __int64 v174; // rax
  int v175; // eax
  HSTRING v176; // rcx
  struct _FILETIME system_time; // rax
  int v178; // eax
  __int64 v179; // rax
  __int64 v180; // rcx
  __int64 v181; // rax
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING v184; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING string; // [rsp+50h] [rbp-B0h] BYREF
  char v186[8]; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING newString; // [rsp+60h] [rbp-A0h] BYREF
  struct DataStoreCache::PropertyBagLookaside *v188; // [rsp+68h] [rbp-98h] BYREF
  int v189; // [rsp+70h] [rbp-90h] BYREF
  struct Windows::Internal::Tiles::ITile *v190; // [rsp+78h] [rbp-88h] BYREF
  UINT32 length[4]; // [rsp+80h] [rbp-80h] BYREF
  int v192[2]; // [rsp+90h] [rbp-70h] BYREF
  struct DataStoreCache::PropertyBagLookaside *v193; // [rsp+98h] [rbp-68h] BYREF
  struct DataStoreCache::PropertyBagLookaside *v194; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING v195; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v196; // [rsp+B0h] [rbp-50h] BYREF
  struct DataStoreTransformerTelemetry::TileStoreTransformerReconcileTiles *v197; // [rsp+B8h] [rbp-48h]
  std::_Ref_count_base *v198[2]; // [rsp+C0h] [rbp-40h] BYREF
  std::_Ref_count_base *v199[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v200; // [rsp+E0h] [rbp-20h] BYREF
  char *v201; // [rsp+E8h] [rbp-18h] BYREF
  volatile signed __int32 *v202; // [rsp+F0h] [rbp-10h]
  char *v203; // [rsp+F8h] [rbp-8h] BYREF
  volatile signed __int32 *v204; // [rsp+100h] [rbp+0h]
  char *v205; // [rsp+108h] [rbp+8h] BYREF
  volatile signed __int32 *v206; // [rsp+110h] [rbp+10h]
  char *v207; // [rsp+118h] [rbp+18h] BYREF
  volatile signed __int32 *v208; // [rsp+120h] [rbp+20h]
  char *v209; // [rsp+128h] [rbp+28h] BYREF
  std::_Ref_count_base *v210; // [rsp+130h] [rbp+30h]
  DataStoreCache::DataItemIdentifier *v211; // [rsp+138h] [rbp+38h] BYREF
  std::_Ref_count_base *v212; // [rsp+140h] [rbp+40h]
  __int64 v213; // [rsp+148h] [rbp+48h]
  _QWORD v214[2]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v215; // [rsp+160h] [rbp+60h]
  int v216; // [rsp+1A8h] [rbp+A8h]
  int v217; // [rsp+1ACh] [rbp+ACh] BYREF
  _BYTE v218[4]; // [rsp+1B0h] [rbp+B0h] BYREF
  int v219; // [rsp+1B4h] [rbp+B4h]
  struct DataStoreTransformerTelemetry::TileStoreTransformerReconcileTiles *v220; // [rsp+1F0h] [rbp+F0h]
  int *v221; // [rsp+1F8h] [rbp+F8h]
  __int128 *p_Buf1; // [rsp+200h] [rbp+100h]
  int *v223; // [rsp+208h] [rbp+108h]
  HSTRING *p_string; // [rsp+210h] [rbp+110h]
  char v225; // [rsp+218h] [rbp+118h]
  char v226[8]; // [rsp+220h] [rbp+120h] BYREF
  std::_Ref_count_base *v227; // [rsp+228h] [rbp+128h]
  HSTRING v228[2]; // [rsp+230h] [rbp+130h] BYREF
  __int128 Buf1; // [rsp+240h] [rbp+140h] BYREF
  __int128 Buf2; // [rsp+250h] [rbp+150h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v11 = this;
  SRWLock = this;
  v197 = a8;
  v189 = 0;
  Buf1 = 0;
  *(_QWORD *)v192 = -1;
  string = 0;
  v220 = a8;
  v221 = &v189;
  p_Buf1 = &Buf1;
  v223 = v192;
  p_string = &string;
  v225 = 1;
  v12 = (*(__int64 (__fastcall **)(struct Windows::Internal::Tiles::ITileNotification *const, int *))(*(_QWORD *)a2 + 64LL))(
          a2,
          &v189);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x781,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\tilestoretransformer.cpp",
      (const char *)(unsigned int)v12,
      bIgnoreCase);
  v13 = (*(__int64 (__fastcall **)(struct Windows::Internal::Tiles::ITileNotification *const, __int128 *))(*(_QWORD *)a2 + 56LL))(
          a2,
          &Buf1);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x782,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\tilestoretransformer.cpp",
      (const char *)(unsigned int)v13,
      bIgnoreCase);
  v14 = (*(__int64 (__fastcall **)(struct Windows::Internal::Tiles::ITileNotification *const, int *))(*(_QWORD *)a2 + 72LL))(
          a2,
          v192);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x783,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\tilestoretransformer.cpp",
      (const char *)(unsigned int)v14,
      bIgnoreCase);
  v196 = 0;
  v15 = (*(__int64 (__fastcall **)(struct Windows::Internal::Tiles::ITileNotification *const, __int64 *))(*(_QWORD *)a2 + 80LL))(
          a2,
          &v196);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x789,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\tilestoretransformer.cpp",
      (const char *)(unsigned int)v15,
      bIgnoreCase);
  if ( !v196 )
    goto LABEL_10;
  LODWORD(v228[0]) = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v196 + 64LL))(v196, v228);
  v17 = retaddr;
  if ( v16 < 0 )
    goto LABEL_140;
  length[0] = 0;
  v18 = (*(__int64 (__fastcall **)(__int64, UINT32 *))(*(_QWORD *)v196 + 56LL))(v196, length);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x792,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\tilestoretransformer.cpp",
      (const char *)(unsigned int)v18,
      bIgnoreCase);
  if ( length[0] || LODWORD(v11[52].Ptr) != 1 || ((__int64)v228[0] & 1) != 0 )
  {
LABEL_10:
    v19 = v189;
  }
  else
  {
    v19 = 1;
    v189 = 1;
  }
  if ( v19 != 1 )
  {
    v190 = 0;
    v20 = (*(__int64 (__fastcall **)(struct Windows::Internal::Tiles::ITileNotification *const, struct Windows::Internal::Tiles::ITile **))(*(_QWORD *)a2 + 80LL))(
            a2,
            &v190);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7D0,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\tilestoretransformer.cpp",
        (const char *)(unsigned int)v20,
        bIgnoreCase);
    DataStoreCache::TileStoreTransformer::TileContext::TileContext(
      (DataStoreCache::TileStoreTransformer::TileContext *)v214,
      v190,
      a7,
      a4,
      a3,
      a5,
      a6);
    v21 = 0;
    if ( !v216 )
    {
      DataStoreCache::TileStoreTransformer::TileContext::EnsureAppTypeAndCanElevate((DataStoreCache::TileStoreTransformer::TileContext *)v214);
      if ( !v216 )
      {
        DataStoreTransformerTelemetry::TileStoreTransformerReconcileTiles::UnsupportedTileIgnored<_GUID &>(a8, &Buf1);
        goto LABEL_106;
      }
    }
    v22 = (HSTRING *)DataStoreCache::TileStoreTransformer::ComputeTileIdentifier(v11, &v195, v214);
    v23 = *v22;
    *v22 = 0;
    WindowsDeleteString(string);
    string = v23;
    WindowsDeleteString(v195);
    (*(void (__fastcall **)(PVOID, struct DataStoreCache::PropertyBagLookaside **, HSTRING))(*(_QWORD *)v11[55].Ptr
                                                                                           + 40LL))(
      v11[55].Ptr,
      &v188,
      string);
    v194 = 0;
    v200 = -1;
    if ( (*(unsigned __int8 (__fastcall **)(struct DataStoreCache::PropertyBagLookaside *, const struct _GUID *, GUID *, struct DataStoreCache::PropertyBagLookaside **))(*(_QWORD *)v188 + 48LL))(
           v188,
           &c_tileStoreTransformerId,
           &GUID_9dbb8733_cc6a_4eba_92cc_25fc80f0c2cb,
           &v194)
      && !(*(unsigned __int8 (__fastcall **)(struct DataStoreCache::PropertyBagLookaside *, void **, __int64, __int64 *))(*(_QWORD *)v194 + 24LL))(
            v194,
            &DataStoreCache::TileStoreProperties::TileRevision,
            8,
            &v200) )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x7E3,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\tilestoretransformer.cpp",
        (const char *)0x80070490LL,
        bIgnoreCase);
    }
    v24 = v194;
    if ( v194 && *(_QWORD *)v192 == v200 )
      goto LABEL_102;
    newString = 0;
    v25 = v11 + 19;
    AcquireSRWLockShared(v11 + 19);
    v26 = v11 + 20;
    std::_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>::find(
      &v11[20],
      &v184,
      &Buf1);
    v27 = v11 + 21;
    if ( v184 == v11[21].Ptr )
    {
      WindowsDeleteString(newString);
      newString = 0;
      v28 = WindowsDuplicateString(0, &newString);
      if ( v28 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x56,
          (unsigned int)"shellcommon\\shell\\DataStoreCache\\inc\\DataStoreCacheItemIdentifier.h",
          (const char *)(unsigned int)v28,
          bIgnoreCase);
      v29 = 0;
      WindowsDeleteString(0);
    }
    else
    {
      v94 = (HSTRING *)DataStoreCache::DataItemIdentifier::DataItemIdentifier(
                         &v184,
                         (const struct DataStoreCache::DataItemIdentifier *)(v184 + 8));
      v228[0] = (HSTRING)v94;
      DataStoreCache::DataItemIdentifier::operator=(&newString);
      WindowsDeleteString(*v94);
      *v94 = 0;
      v29 = 1;
    }
    if ( v11 != (PSRWLOCK)-152LL )
      ReleaseSRWLockShared(v11 + 19);
    if ( v29 )
    {
      length[0] = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(string, length);
      LODWORD(v228[0]) = 0;
      v137 = WindowsGetStringRawBuffer(newString, (UINT32 *)v228);
      if ( LODWORD(v228[0]) == length[0]
        && (v137 == StringRawBuffer || CompareStringOrdinal(v137, (int)v228[0], StringRawBuffer, length[0], 1) == 2) )
      {
        v21 = 0;
      }
      else
      {
        Microsoft::WRL::Wrappers::SRWLock::LockExclusive(v228, &v11[19]);
        v179 = std::_Hash<std::_Umap_traits<_GUID,DataStoreCache::DataItemIdentifier,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,DataStoreCache::DataItemIdentifier>>,0>>::_Try_emplace<_GUID const &,>(
                 &v11[20],
                 &v211,
                 &Buf1);
        DataStoreCache::DataItemIdentifier::operator=((HSTRING *)(*(_QWORD *)v179 + 32LL));
        v21 = 0;
        if ( v219 )
        {
          DataStoreCache::TileStoreTransformer::RemoveSecondaryTileIdentifierFromIndex((DataStoreCache::TileStoreTransformer *)v11);
          DataStoreCache::DataItemIdentifier::DataItemIdentifier(
            (HSTRING *)&SRWLock,
            (const struct DataStoreCache::DataItemIdentifier *)&string);
          DataStoreCache::TileStoreTransformer::AddSecondaryTileIdentifierToIndex((DataStoreCache::TileStoreTransformer *)v11);
          WindowsDeleteString((HSTRING)SRWLock);
        }
        else
        {
          v181 = std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>::operator()<DataStoreCache::DataItemIdentifier>(
                   v180,
                   &newString);
          std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,DataStoreCache::DataItemIdentifier,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,DataStoreCache::DataItemIdentifier>>,1>>::_Equal_range<DataStoreCache::DataItemIdentifier>(
            &v11[28],
            &v211,
            &newString,
            v181);
          std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,DataStoreCache::DataItemIdentifier,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,DataStoreCache::DataItemIdentifier>>,1>>::_Unchecked_erase(
            &v11[28],
            v211,
            v212);
        }
        if ( v228[0] )
          ReleaseSRWLockExclusive((PSRWLOCK)v228[0]);
        SRWLock = (PSRWLOCK)WindowsGetStringRawBuffer(string, 0);
        v228[0] = (HSTRING)WindowsGetStringRawBuffer(newString, 0);
        DataStoreTransformerTelemetry::TileStoreTransformerReconcileTiles::TileIdentityChanged<_GUID &,unsigned short const *,unsigned short const *,__int64 &>(
          (_DWORD)v197,
          (unsigned int)&Buf1,
          (unsigned int)v228,
          (unsigned int)&SRWLock,
          (__int64)v192);
        v184 = 0;
        v174 = (*(__int64 (__fastcall **)(PVOID, HSTRING *, HSTRING))(*(_QWORD *)v11[55].Ptr + 40LL))(
                 v11[55].Ptr,
                 v228,
                 newString);
        v175 = Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>::As<DataStoreCache::IDataUpdate>(v174, &v184);
        if ( v175 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x809,
            (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\tilestoretransformer.cpp",
            (const char *)(unsigned int)v175,
            bIgnoreCase);
        v176 = v228[0];
        if ( v228[0] )
        {
          v228[0] = 0;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v176 + 16LL))(v176);
        }
        (*(void (__fastcall **)(HSTRING, const struct _GUID *, _QWORD))(*(_QWORD *)v184 + 40LL))(
          v184,
          &c_tileStoreTransformerId,
          0);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v184);
      }
      goto LABEL_45;
    }
    AcquireSRWLockExclusive(v11 + 19);
    v228[0] = (HSTRING)&v11[19];
    v30 = std::_Conditionally_enabled_hash<HSTRING__ *,1>::operator()((unsigned __int8 *)&Buf1 + 8);
    v31 = std::_Conditionally_enabled_hash<HSTRING__ *,1>::operator()((unsigned __int8 *)&Buf1) ^ v30;
    v32 = (__int64)v11[26].Ptr & v31;
    Ptr = v11[23].Ptr;
    v34 = (_QWORD *)Ptr[2 * v32 + 1];
    v35 = v27->Ptr;
    if ( v34 != v27->Ptr )
    {
      v36 = (_QWORD *)Ptr[2 * v32];
      while ( 1 )
      {
        if ( !memcmp_0(&Buf1, v34 + 2, 0x10u) )
          goto LABEL_37;
        if ( v34 == v36 )
          break;
        v34 = (_QWORD *)v34[1];
      }
      v35 = v34;
    }
    if ( v26[2].Ptr == (PVOID)0x666666666666666LL )
      std::_Xlength_error("unordered_map/set too long");
    Buf2 = (unsigned __int64)v27;
    v34 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(40);
    *((_QWORD *)&Buf2 + 1) = v34;
    v184 = (HSTRING)&Buf1;
    ____0V__tuple_AEBU_GUID___std__V__tuple___V_1__0A___Z_S___pair___CBU_GUID__V__com_ptr_t_UICuratedTileGroup_CuratedTileCollections_UnifiedTile_Shell_WindowsInternal__Uerr_exception_policy_wil___wil___std__AEAA_AEAV__tuple_AEBU_GUID___1_AEAV__tuple___V_1_U__integer_sequence__K_0A__1_U__integer_sequence__K_S_1__Z(
      (__int64)(v34 + 2),
      (_OWORD **)&v184);
    v37 = (__int64)v26[2].Ptr + 1;
    if ( v37 < 0 )
      v38 = (float)(v37 & 1 | (unsigned int)((unsigned __int64)v37 >> 1))
          + (float)(v37 & 1 | (unsigned int)((unsigned __int64)v37 >> 1));
    else
      v38 = (float)(int)v37;
    v39 = (__int64)v26[7].Ptr;
    if ( v39 < 0 )
    {
      v169 = (__int64)v26[7].Ptr & 1 | ((unsigned __int64)v39 >> 1);
      v40 = (float)(int)v169 + (float)(int)v169;
    }
    else
    {
      v40 = (float)(int)v39;
    }
    if ( (float)(v38 / v40) > *(float *)&v26->Ptr )
    {
      v165 = std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,enum WindowsInternal::Shell::UnifiedTile::AppCategory,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,enum WindowsInternal::Shell::UnifiedTile::AppCategory>>,0>>::_Desired_grow_bucket_count(v26);
      std::_Hash<std::_Umap_traits<_GUID,DataStoreCache::DataItemIdentifier,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,DataStoreCache::DataItemIdentifier>>,0>>::_Forced_rehash(
        v26,
        v165);
      v166 = v26[3].Ptr;
      v167 = (_QWORD *)v166[2 * ((__int64)v26[6].Ptr & v31) + 1];
      v35 = v26[1].Ptr;
      if ( v167 == v35 )
        goto LABEL_320;
      v168 = (_QWORD *)v166[2 * ((__int64)v26[6].Ptr & v31)];
      while ( memcmp_0(v34 + 2, v167 + 2, 0x10u) )
      {
        if ( v167 == v168 )
        {
          v35 = v167;
          goto LABEL_320;
        }
        v167 = (_QWORD *)v167[1];
      }
      v35 = (_QWORD *)*v167;
LABEL_320:
      v27 = v26 + 1;
    }
    v41 = (_QWORD *)v35[1];
    ++v26[2].Ptr;
    *v34 = v35;
    v34[1] = v41;
    *v41 = v34;
    v35[1] = v34;
    v42 = v26[3].Ptr;
    v43 = 2 * ((__int64)v26[6].Ptr & v31);
    v44 = (_QWORD *)v42[v43];
    if ( v44 == v27->Ptr )
    {
      v42[v43] = v34;
LABEL_36:
      v42[v43 + 1] = v34;
      goto LABEL_37;
    }
    if ( v44 == v35 )
    {
      v42[v43] = v34;
    }
    else if ( (_QWORD *)v42[v43 + 1] == v41 )
    {
      goto LABEL_36;
    }
LABEL_37:
    v45 = (HSTRING *)(v34 + 4);
    v46 = string;
    if ( !string || (v47 = 0, string != *v45) )
    {
      WindowsDeleteString(*v45);
      *v45 = 0;
      v47 = WindowsDuplicateString(v46, v45);
      v46 = string;
    }
    v21 = 0;
    if ( v47 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x56,
        (unsigned int)"shellcommon\\shell\\DataStoreCache\\inc\\DataStoreCacheItemIdentifier.h",
        (const char *)(unsigned int)v47,
        bIgnoreCase);
    if ( v219 == 1 )
    {
      v184 = 0;
      DataStoreCache::DataItemIdentifier::operator=(&v184, v46);
      v11 = SRWLock;
      DataStoreCache::TileStoreTransformer::AddSecondaryTileIdentifierToIndex((DataStoreCache::TileStoreTransformer *)SRWLock);
      WindowsDeleteString(v184);
    }
    else
    {
      v11 = SRWLock;
    }
    if ( v25 )
      ReleaseSRWLockExclusive(v25);
LABEL_45:
    wil::MakeOrThrow<DataStoreCache::PropertyBagLookaside,_GUID const &,std::vector<DataStoreCache::DataStorePropertyIdentifier const *> &>(
      &v193,
      &c_tileStoreTransformerId,
      &v11[16]);
    v48 = (const char **)v11[16].Ptr;
    v49 = (const char **)v11[17].Ptr;
    while ( 1 )
    {
      if ( v48 == v49 )
      {
        if ( !v11[57].Ptr )
          goto LABEL_90;
LABEL_191:
        v228[0] = 0;
        v132 = v193;
        WindowsDeleteString(0);
        v228[0] = 0;
        if ( memcmp_0(DataStoreCache::TileStoreProperties::PackageFullName, *((const void **)v132 + 6), 0x10u) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x2DF,
            (unsigned int)"shellcommon\\shell\\DataStoreCache\\Transformers\\inc\\DataStorePropertyTransformerBase.h",
            v133);
        AcquireSRWLockShared((PSRWLOCK)v132 + 7);
        v184 = (HSTRING)((char *)v132 + 56);
        v228[0] = 0;
        std::_Hash<std::_Umap_traits<unsigned int,std::shared_ptr<DataStoreCache::PropertyBagLookaside::ILookasideProperty>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::shared_ptr<DataStoreCache::PropertyBagLookaside::ILookasideProperty>>>,0>>::find(
          (char *)v132 + 64,
          &SRWLock,
          &dword_1804C8188);
        if ( SRWLock == *((PSRWLOCK *)v132 + 9) || (v134 = SRWLock[3].Ptr) == 0 )
        {
          v135 = 0;
          v153 = *((_QWORD *)v132 + 16);
          if ( v153 )
            v135 = (*(__int64 (__fastcall **)(__int64, void *, HSTRING *))(*(_QWORD *)v153 + 32LL))(
                     v153,
                     &DataStoreCache::TileStoreProperties::PackageFullName,
                     v228);
        }
        else
        {
          (*(void (__fastcall **)(PVOID, HSTRING *))(*(_QWORD *)v134 + 8LL))(v134, v228);
          v135 = 1;
        }
        if ( v132 != (struct DataStoreCache::PropertyBagLookaside *)-56LL )
          ReleaseSRWLockShared((PSRWLOCK)v132 + 7);
        v21 = 0;
        if ( v135 )
          (*(void (__fastcall **)(PVOID, struct DataStoreCache::PropertyBagLookaside *, __int64, HSTRING))(*(_QWORD *)v11[57].Ptr + 48LL))(
            v11[57].Ptr,
            v188,
            1,
            v228[0]);
        WindowsDeleteString(v228[0]);
LABEL_90:
        v195 = 0;
        v78 = (**(__int64 (__fastcall ***)(struct DataStoreCache::PropertyBagLookaside *, GUID *, HSTRING *))v188)(
                v188,
                &GUID_5c9d52d7_3951_439f_88a5_3f591b54b57e,
                &v195);
        if ( v78 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x82D,
            (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\tilestoretransformer.cpp",
            (const char *)(unsigned int)v78,
            bIgnoreCase);
        (*(void (__fastcall **)(HSTRING, const struct _GUID *, _QWORD, unsigned __int64))(*(_QWORD *)v195 + 24LL))(
          v195,
          &c_tileStoreTransformerId,
          0,
          ((unsigned __int64)v193 + 8) & -(__int64)(v193 != 0));
        if ( v194 )
        {
          SRWLock = (PSRWLOCK)WindowsGetStringRawBuffer(string, 0);
          v79 = v197;
          DataStoreTransformerTelemetry::TileStoreTransformerReconcileTiles::TileUpdated<_GUID &,unsigned short const *,__int64 &,__int64 &>(
            (_DWORD)v197,
            (unsigned int)&Buf1,
            (unsigned int)&SRWLock,
            (unsigned int)&v200,
            (__int64)v192);
          goto LABEL_93;
        }
        v21 = (struct DataStoreCache::PropertyBagLookaside *)v11[56].Ptr;
        if ( v21 )
        {
          v184 = 0;
          v87 = *(__int64 (__fastcall **)(struct DataStoreCache::PropertyBagLookaside *, HSTRING, HSTRING *))(*(_QWORD *)v21 + 88LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v184);
          v88 = v87(v21, string, &v184);
          v21 = 0;
          if ( v88 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x843,
              (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\tilestoretransformer.cpp",
              (const char *)(unsigned int)v88,
              bIgnoreCase);
          }
          else
          {
            *(_QWORD *)length = 0;
            v89 = (**(__int64 (__fastcall ***)(HSTRING, GUID *, UINT32 *))v184)(
                    v184,
                    &GUID_f2456d27_5e13_42b8_bc25_00b4cc364e44,
                    length);
            if ( v89 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x846,
                (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\tilestoretransformer.cpp",
                (const char *)(unsigned int)v89,
                bIgnoreCase);
            v228[0] = 0;
            v90 = (*(__int64 (__fastcall **)(_QWORD, HSTRING *))(**(_QWORD **)length + 48LL))(*(_QWORD *)length, v228);
            v91 = retaddr;
            if ( v90 < 0 )
            {
              v164 = 2121;
LABEL_305:
              wil::details::in1diag3::_Log_Hr(
                v91,
                (void *)v164,
                (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\tilestoretransformer.cpp",
                (const char *)(unsigned int)v90,
                bIgnoreCase);
            }
            else if ( !v228[0] )
            {
              if ( v219
                || !DataStoreCache::PropertyBagLookaside::TryGetPropertyByValue(
                      (struct DataStoreCache::PropertyBagLookaside *)((char *)v193 + 8),
                      (const struct DataStoreCache::DataStorePropertyIdentifier *)&DataStoreCache::TileStoreProperties::InstallTime,
                      8u,
                      v228)
                || !v228[0] )
              {
                system_time = wil::filetime::get_system_time(v91);
                v178 = RoFileTimeToDateTime(system_time, (struct Windows::Foundation::DateTime *)v228);
                if ( v178 < 0 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x853,
                    (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\tilestoretransformer.cpp",
                    (const char *)(unsigned int)v178,
                    bIgnoreCase);
              }
              v90 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)length + 56LL))(*(_QWORD *)length);
              v91 = retaddr;
              if ( v90 < 0 )
              {
                v164 = 2136;
                goto LABEL_305;
              }
            }
            v92 = *(_QWORD *)length;
            if ( *(_QWORD *)length )
            {
              *(_QWORD *)length = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
            }
          }
          v93 = v184;
          if ( v184 )
          {
            v184 = 0;
            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v93 + 16LL))(v93);
          }
        }
        SRWLock = (PSRWLOCK)WindowsGetStringRawBuffer(string, 0);
        v79 = v197;
        DataStoreTransformerTelemetry::TileStoreTransformerReconcileTiles::TileAdded<_GUID &,unsigned short const *,__int64 &>(
          v197,
          &Buf1,
          &SRWLock,
          v192);
LABEL_93:
        std::vector<std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>>>::vector<std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>>>(&v211);
        if ( v219 == (_DWORD)v21 )
          DataStoreCache::TileStoreTransformer::UpdateSecondaryTiles(
            (DataStoreCache::TileStoreTransformer *)v11,
            (const struct DataStoreCache::DataItemIdentifier *)&string,
            (struct DataStoreCache::IDataStorePropertyBag *)(((unsigned __int64)v193 + 8) & -(__int64)(v193 != 0)),
            v79);
        v80 = v211;
        if ( v211 )
        {
          std::_Destroy_range<std::allocator<DataStoreCache::DataItemIdentifier>>(v211);
          std::_Deallocate<16>(v80, (v213 - (_QWORD)v80) & 0xFFFFFFFFFFFFFFF8uLL);
        }
        v81 = v195;
        if ( v195 )
        {
          v195 = (HSTRING)v21;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v81 + 16LL))(v81);
        }
        if ( v193 )
        {
          v193 = v21;
          Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,DataStoreCache::IDataStorePropertyBag,DataStoreCache::IPropertyBagLookasidePrivate>::Release();
        }
        WindowsDeleteString(newString);
        v24 = v194;
LABEL_102:
        if ( v24 )
        {
          v194 = v21;
          (*(void (__fastcall **)(struct DataStoreCache::PropertyBagLookaside *))(*(_QWORD *)v24 + 16LL))(v24);
        }
        v82 = v188;
        if ( v188 )
        {
          v188 = v21;
          (*(void (__fastcall **)(struct DataStoreCache::PropertyBagLookaside *))(*(_QWORD *)v82 + 16LL))(v82);
        }
LABEL_106:
        DataStoreCache::TileStoreTransformer::TileContext::~TileContext((DataStoreCache::TileStoreTransformer::TileContext *)v214);
        v83 = v190;
        if ( v190 )
        {
          v190 = v21;
          goto LABEL_108;
        }
        goto LABEL_109;
      }
      v51 = *v48;
      v52 = *((_DWORD *)*v48 + 2);
      if ( (unsigned int)v52 >= 0x1F )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x997,
          (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\tilestoretransformer.cpp",
          v51);
      v53 = (RTL_SRWLOCK *)v193;
      v54 = *(_DWORD *)&byte_1803D0038[16 * v52];
      if ( v54 )
        goto LABEL_68;
      if ( v52 > 6 )
      {
        v65 = v52 - 7;
        if ( !v65 )
          goto LABEL_160;
        v66 = v65 - 1;
        if ( !v66 )
        {
          DataStoreCache::TileStoreTransformer::AddInstallTimeProperty(
            (struct DataStoreCache::TileStoreTransformer::TileContext *)v214,
            v193);
          goto LABEL_49;
        }
        v67 = v66 - 1;
        if ( !v67 )
          goto LABEL_170;
        v68 = v67 - 1;
        if ( !v68 )
        {
          SRWLock = *(PSRWLOCK *)DataStoreCache::TileStoreTransformer::TileContext::GetPackageFullName((DataStoreCache::TileStoreTransformer::TileContext *)v214);
          v104 = (std::_Ref_count_base **)std::make_shared<DataStoreCache::PropertyBagLookaside::LookasidePropertyHSTRING,HSTRING__ * &>(
                                            v226,
                                            &SRWLock);
          *(_OWORD *)v198 = 0;
          v198[0] = *v104;
          v198[1] = v104[1];
          *v104 = 0;
          v104[1] = 0;
          SRWLock = (PSRWLOCK)v198;
          if ( memcmp_0(DataStoreCache::TileStoreProperties::PackageFullName, v53[6].Ptr, 0x10u) )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x311,
              (unsigned int)"shellcommon\\shell\\DataStoreCache\\Transformers\\inc\\DataStorePropertyTransformerBase.h",
              v105);
          v98 = v53 + 7;
          AcquireSRWLockExclusive(v53 + 7);
          v184 = (HSTRING)&v53[7];
          v106 = (__int64)v53[14].Ptr
               & std::_Conditionally_enabled_hash<enum DataStoreCache::PlaceholderTileTransformer::InstallDelayType,1>::operator()(&dword_1804C8188);
          v107 = v53[11].Ptr;
          v108 = v107[2 * v106 + 1];
          if ( (PVOID)v108 != v53[9].Ptr )
          {
            while ( *(_DWORD *)&dword_1804C8188 != *(_DWORD *)(v108 + 16) )
            {
              if ( v108 == v107[2 * v106] )
                goto LABEL_159;
              v108 = *(_QWORD *)(v108 + 8);
            }
            goto LABEL_239;
          }
LABEL_159:
          std::_Xout_of_range("invalid unordered_map<K, T> key");
LABEL_160:
          v109 = v217;
          if ( !v217 )
          {
            v110 = v215;
            if ( !v215 )
            {
              DataStoreCache::TileStoreTransformer::TileContext::EnsureApplicationAndPackage((DataStoreCache::TileStoreTransformer::TileContext *)v214);
              v110 = v215;
            }
            v111 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v110 + 1008LL))(v110, &v217);
            if ( v111 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x9B,
                (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\tilestoretransformertilecontext.cpp",
                (const char *)(unsigned int)v111,
                bIgnoreCase);
            v109 = v217;
          }
          v112 = operator new(0x20u);
          *(_OWORD *)v112 = 0;
          v112[2] = 1;
          v112[3] = 1;
          *(_QWORD *)v112 = &std::_Ref_count_obj2<DataStoreCache::PropertyBagLookaside::LookasidePropertyValueType<unsigned long>>::`vftable';
          *((_QWORD *)v112 + 2) = &DataStoreCache::PropertyBagLookaside::LookasidePropertyValueType<unsigned int>::`vftable';
          v112[6] = v109;
          *(_QWORD *)&Buf2 = v112 + 4;
          *((_QWORD *)&Buf2 + 1) = v112;
          *(_OWORD *)v228 = 0;
          SRWLock = (PSRWLOCK)&Buf2;
          if ( memcmp_0(DataStoreCache::TileStoreProperties::PackageOrigin, v53[6].Ptr, 0x10u) )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x311,
              (unsigned int)"shellcommon\\shell\\DataStoreCache\\Transformers\\inc\\DataStorePropertyTransformerBase.h",
              v113);
          AcquireSRWLockExclusive(v53 + 7);
          v184 = (HSTRING)&v53[7];
          v114 = (__int64)v53[14].Ptr
               & std::_Conditionally_enabled_hash<enum DataStoreCache::PlaceholderTileTransformer::InstallDelayType,1>::operator()(&dword_1804C8128);
          v115 = v53[11].Ptr;
          v116 = v115[2 * v114 + 1];
          if ( (PVOID)v116 != v53[9].Ptr )
          {
            while ( *(_DWORD *)&dword_1804C8128 != *(_DWORD *)(v116 + 16) )
            {
              if ( v116 == v115[2 * v114] )
                goto LABEL_169;
              v116 = *(_QWORD *)(v116 + 8);
            }
            if ( v116 )
            {
              v154 = *((_QWORD *)&Buf2 + 1);
              if ( *((_QWORD *)&Buf2 + 1) )
              {
                _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&Buf2 + 1) + 8LL));
                v154 = *((_QWORD *)&Buf2 + 1);
              }
              *(_QWORD *)(v116 + 24) = Buf2;
              v155 = *(std::_Ref_count_base **)(v116 + 32);
              *(_QWORD *)(v116 + 32) = v154;
              if ( v155 )
                std::_Ref_count_base::_Decref(v155);
              if ( v53 != (RTL_SRWLOCK *)-56LL )
                ReleaseSRWLockExclusive(v53 + 7);
              v50 = (std::_Ref_count_base *)*((_QWORD *)&Buf2 + 1);
              goto LABEL_47;
            }
          }
LABEL_169:
          std::_Xout_of_range("invalid unordered_map<K, T> key");
LABEL_170:
          SRWLock = *(PSRWLOCK *)DataStoreCache::TileStoreTransformer::TileContext::GetPackageFamilyName((DataStoreCache::TileStoreTransformer::TileContext *)v214);
          v117 = (std::_Ref_count_base **)std::make_shared<DataStoreCache::PropertyBagLookaside::LookasidePropertyHSTRING,HSTRING__ * &>(
                                            &v211,
                                            &SRWLock);
          *(_OWORD *)v199 = 0;
          v199[0] = *v117;
          v199[1] = v117[1];
          *v117 = 0;
          v117[1] = 0;
          SRWLock = (PSRWLOCK)v199;
          if ( memcmp_0(DataStoreCache::TileStoreProperties::PackageFamilyName, v53[6].Ptr, 0x10u) )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x311,
              (unsigned int)"shellcommon\\shell\\DataStoreCache\\Transformers\\inc\\DataStorePropertyTransformerBase.h",
              v118);
          v119 = v53 + 7;
          AcquireSRWLockExclusive(v53 + 7);
          v184 = (HSTRING)&v53[7];
          v120 = (__int64)v53[14].Ptr
               & std::_Conditionally_enabled_hash<enum DataStoreCache::PlaceholderTileTransformer::InstallDelayType,1>::operator()(&dword_1804C8168);
          v121 = v53[11].Ptr;
          v122 = v121[2 * v120 + 1];
          if ( (PVOID)v122 == v53[9].Ptr )
            goto LABEL_262;
          while ( *(_DWORD *)&dword_1804C8168 != *(_DWORD *)(v122 + 16) )
          {
            if ( v122 == v121[2 * v120] )
              goto LABEL_262;
            v122 = *(_QWORD *)(v122 + 8);
          }
          if ( !v122 )
          {
LABEL_262:
            std::_Xout_of_range("invalid unordered_map<K, T> key");
            goto LABEL_263;
          }
          v123 = v199[1];
          if ( v199[1] )
          {
            _InterlockedIncrement((volatile signed __int32 *)v199[1] + 2);
            v123 = v199[1];
          }
          *(std::_Ref_count_base **)(v122 + 24) = v199[0];
          v124 = *(std::_Ref_count_base **)(v122 + 32);
          *(_QWORD *)(v122 + 32) = v123;
          if ( v124 )
            std::_Ref_count_base::_Decref(v124);
          if ( v53 != (RTL_SRWLOCK *)-56LL )
            ReleaseSRWLockExclusive(v53 + 7);
          if ( v199[1] )
            std::_Ref_count_base::_Decref(v199[1]);
          v50 = v212;
LABEL_249:
          if ( v50 )
            goto LABEL_48;
          goto LABEL_49;
        }
        v69 = v68 - 1;
        if ( !v69 )
          goto LABEL_281;
        if ( v69 != 6 )
LABEL_357:
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x9D3,
            (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\tilestoretransformer.cpp",
            (const char *)0x80070057LL,
            bIgnoreCase);
        DataStoreCache::TileStoreTransformer::AddVisualGroupProperty(
          (struct DataStoreCache::TileStoreTransformer::TileContext *)v214,
          v193);
      }
      else
      {
        if ( v52 == 6 )
        {
          if ( (unsigned __int8)IsGetPackageExecutionContextForPackageByFullNamePresent() )
          {
            if ( `Details::GetDeviceFamily'::`2'::s_hasChecked )
            {
              v147 = `Details::GetDeviceFamily'::`2'::s_platform;
            }
            else
            {
              LODWORD(v228[0]) = 0;
              RtlGetDeviceFamilyInfoEnum(0, v228, 0);
              v147 = (int)v228[0];
              `Details::GetDeviceFamily'::`2'::s_platform = (int)v228[0];
              `Details::GetDeviceFamily'::`2'::s_hasChecked = 1;
            }
            if ( ((v147 - 14) & 0xFFFFFFFD) == 0 )
            {
              LODWORD(v228[0]) = 0;
              PackageFullName = (HSTRING *)DataStoreCache::TileStoreTransformer::TileContext::GetPackageFullName((DataStoreCache::TileStoreTransformer::TileContext *)v214);
              v149 = WindowsGetStringRawBuffer(*PackageFullName, 0);
              PackageExecutionContextForPackageByFullName = GetPackageExecutionContextForPackageByFullName(v149, v228);
              if ( PackageExecutionContextForPackageByFullName < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0xA0B,
                  (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\tilestoretransformer.cpp",
                  (const char *)(unsigned int)PackageExecutionContextForPackageByFullName,
                  bIgnoreCase);
              length[0] = (UINT32)v228[0];
              DataStoreCache::PropertyBagLookaside::SetLookasideValueType<unsigned int>(
                v53,
                &DataStoreCache::TileStoreProperties::PackageExecutionContext,
                length);
            }
          }
          goto LABEL_49;
        }
        if ( !v52 )
        {
          *(_OWORD *)v228 = 0;
          v70 = (*(__int64 (__fastcall **)(_QWORD, HSTRING *))(*(_QWORD *)v214[0] + 48LL))(v214[0], v228);
          if ( v70 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x9E1,
              (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\tilestoretransformer.cpp",
              (const char *)(unsigned int)v70,
              bIgnoreCase);
          v71 = (char *)operator new(0x28u);
          *(_OWORD *)v71 = 0;
          *((_DWORD *)v71 + 2) = 1;
          *((_DWORD *)v71 + 3) = 1;
          *(_QWORD *)v71 = &std::_Ref_count_obj2<DataStoreCache::PropertyBagLookaside::LookasidePropertyValueType<_GUID>>::`vftable';
          *((_QWORD *)v71 + 2) = &DataStoreCache::PropertyBagLookaside::LookasidePropertyValueType<_GUID>::`vftable';
          *(_OWORD *)(v71 + 24) = *(_OWORD *)v228;
          v209 = v71 + 16;
          v210 = (std::_Ref_count_base *)v71;
          *(_OWORD *)length = 0;
          SRWLock = (PSRWLOCK)&v209;
          if ( memcmp_0(DataStoreCache::TileStoreProperties::TileUniqueId, v53[6].Ptr, 0x10u) )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x311,
              (unsigned int)"shellcommon\\shell\\DataStoreCache\\Transformers\\inc\\DataStorePropertyTransformerBase.h",
              v72);
          AcquireSRWLockExclusive(v53 + 7);
          v184 = (HSTRING)&v53[7];
          v73 = (__int64)v53[14].Ptr
              & std::_Conditionally_enabled_hash<enum DataStoreCache::PlaceholderTileTransformer::InstallDelayType,1>::operator()(&dword_1804C8048);
          v74 = v53[11].Ptr;
          v75 = v74[2 * v73 + 1];
          if ( (PVOID)v75 == v53[9].Ptr )
            goto LABEL_139;
          while ( *(_DWORD *)&dword_1804C8048 != *(_DWORD *)(v75 + 16) )
          {
            if ( v75 == v74[2 * v73] )
              goto LABEL_139;
            v75 = *(_QWORD *)(v75 + 8);
          }
          if ( !v75 )
          {
LABEL_139:
            std::_Xout_of_range("invalid unordered_map<K, T> key");
LABEL_140:
            wil::details::in1diag3::Throw_Hr(
              v17,
              (void *)0x790,
              (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\tilestoretransformer.cpp",
              (const char *)(unsigned int)v16,
              bIgnoreCase);
          }
          v76 = v210;
          if ( v210 )
          {
            _InterlockedIncrement((volatile signed __int32 *)v210 + 2);
            v76 = v210;
          }
          *(_QWORD *)(v75 + 24) = v209;
          v77 = *(std::_Ref_count_base **)(v75 + 32);
          *(_QWORD *)(v75 + 32) = v76;
          if ( v77 )
            std::_Ref_count_base::_Decref(v77);
          if ( v53 != (RTL_SRWLOCK *)-56LL )
            ReleaseSRWLockExclusive(v53 + 7);
          v50 = v210;
          goto LABEL_47;
        }
        v55 = v52 - 1;
        if ( !v55 )
        {
          SRWLock = 0;
          v95 = (*(__int64 (__fastcall **)(_QWORD, PSRWLOCK *))(*(_QWORD *)v214[0] + 72LL))(v214[0], &SRWLock);
          if ( v95 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x9E8,
              (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\tilestoretransformer.cpp",
              (const char *)(unsigned int)v95,
              bIgnoreCase);
          v96 = operator new(0x20u);
          *(_OWORD *)v96 = 0;
          v96[2] = 1;
          v96[3] = 1;
          *(_QWORD *)v96 = &std::_Ref_count_obj2<DataStoreCache::PropertyBagLookaside::LookasidePropertyValueType<unsigned long>>::`vftable';
          *((_QWORD *)v96 + 2) = &DataStoreCache::PropertyBagLookaside::LookasidePropertyValueType<_FILETIME>::`vftable';
          *((_QWORD *)v96 + 3) = SRWLock;
          v207 = (char *)(v96 + 4);
          v208 = v96;
          *(_OWORD *)length = 0;
          v184 = (HSTRING)&v207;
          if ( memcmp_0(DataStoreCache::TileStoreProperties::TileRevision, v53[6].Ptr, 0x10u) )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x311,
              (unsigned int)"shellcommon\\shell\\DataStoreCache\\Transformers\\inc\\DataStorePropertyTransformerBase.h",
              v97);
          v98 = v53 + 7;
          AcquireSRWLockExclusive(v53 + 7);
          v228[0] = (HSTRING)&v53[7];
          v99 = (__int64)v53[14].Ptr
              & std::_Conditionally_enabled_hash<enum DataStoreCache::PlaceholderTileTransformer::InstallDelayType,1>::operator()(&dword_1804C8068);
          v100 = v53[11].Ptr;
          v101 = v100[2 * v99 + 1];
          if ( (PVOID)v101 != v53[9].Ptr )
          {
            while ( *(_DWORD *)&dword_1804C8068 != *(_DWORD *)(v101 + 16) )
            {
              if ( v101 == v100[2 * v99] )
                goto LABEL_238;
              v101 = *(_QWORD *)(v101 + 8);
            }
            if ( v101 )
            {
              v102 = v208;
              if ( v208 )
              {
                _InterlockedIncrement(v208 + 2);
                v102 = v208;
              }
              *(_QWORD *)(v101 + 24) = v207;
              v103 = *(std::_Ref_count_base **)(v101 + 32);
              *(_QWORD *)(v101 + 32) = v102;
              if ( v103 )
                std::_Ref_count_base::_Decref(v103);
              if ( v53 != (RTL_SRWLOCK *)-56LL )
                ReleaseSRWLockExclusive(v53 + 7);
              v50 = (std::_Ref_count_base *)v208;
              goto LABEL_47;
            }
          }
LABEL_238:
          std::_Xout_of_range("invalid unordered_map<K, T> key");
LABEL_239:
          if ( !v108 )
            goto LABEL_159;
          v151 = v198[1];
          if ( v198[1] )
          {
            _InterlockedIncrement((volatile signed __int32 *)v198[1] + 2);
            v151 = v198[1];
          }
          *(std::_Ref_count_base **)(v108 + 24) = v198[0];
          v152 = *(std::_Ref_count_base **)(v108 + 32);
          *(_QWORD *)(v108 + 32) = v151;
          if ( v152 )
            std::_Ref_count_base::_Decref(v152);
          if ( v98 )
            ReleaseSRWLockExclusive(v98);
          if ( v198[1] )
            std::_Ref_count_base::_Decref(v198[1]);
          v50 = v227;
          goto LABEL_249;
        }
        v56 = v55 - 1;
        if ( !v56 )
        {
          v138 = v219;
          v139 = operator new(0x20u);
          *(_OWORD *)v139 = 0;
          v139[2] = 1;
          v139[3] = 1;
          *(_QWORD *)v139 = &std::_Ref_count_obj2<DataStoreCache::PropertyBagLookaside::LookasidePropertyValueType<unsigned long>>::`vftable';
          *((_QWORD *)v139 + 2) = &DataStoreCache::PropertyBagLookaside::LookasidePropertyValueType<unsigned int>::`vftable';
          v139[6] = v138;
          v205 = (char *)(v139 + 4);
          v206 = v139;
          *(_OWORD *)v228 = 0;
          SRWLock = (PSRWLOCK)&v205;
          if ( memcmp_0(DataStoreCache::TileStoreProperties::TileType, v53[6].Ptr, 0x10u) )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x311,
              (unsigned int)"shellcommon\\shell\\DataStoreCache\\Transformers\\inc\\DataStorePropertyTransformerBase.h",
              v140);
          AcquireSRWLockExclusive(v53 + 7);
          v184 = (HSTRING)&v53[7];
          v141 = (__int64)v53[14].Ptr
               & std::_Conditionally_enabled_hash<enum DataStoreCache::PlaceholderTileTransformer::InstallDelayType,1>::operator()(&dword_1804C8088);
          v142 = v53[11].Ptr;
          v143 = v142[2 * v141 + 1];
          if ( (PVOID)v143 != v53[9].Ptr )
          {
            while ( *(_DWORD *)&dword_1804C8088 != *(_DWORD *)(v143 + 16) )
            {
              if ( v143 == v142[2 * v141] )
                goto LABEL_280;
              v143 = *(_QWORD *)(v143 + 8);
            }
            if ( v143 )
            {
              v144 = v206;
              if ( v206 )
              {
                _InterlockedIncrement(v206 + 2);
                v144 = v206;
              }
              *(_QWORD *)(v143 + 24) = v205;
              v145 = *(std::_Ref_count_base **)(v143 + 32);
              *(_QWORD *)(v143 + 32) = v144;
              if ( v145 )
                std::_Ref_count_base::_Decref(v145);
              if ( v53 != (RTL_SRWLOCK *)-56LL )
                ReleaseSRWLockExclusive(v53 + 7);
              v50 = (std::_Ref_count_base *)v206;
              goto LABEL_47;
            }
          }
LABEL_280:
          std::_Xout_of_range("invalid unordered_map<K, T> key");
LABEL_281:
          if ( v219 == 1 )
          {
            v228[0] = 0;
            SecondaryTile = DataStoreCache::TileStoreTransformer::TileContext::GetSecondaryTile((DataStoreCache::TileStoreTransformer::TileContext *)v214);
            v161 = *(__int64 (__fastcall **)(struct Windows::Internal::Tiles::ISecondaryTile *, HSTRING *))(*(_QWORD *)SecondaryTile + 64LL);
            WindowsDeleteString(v228[0]);
            v228[0] = 0;
            v162 = v161(SecondaryTile, v228);
            v21 = 0;
            if ( v162 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0xA3A,
                (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\tilestoretransformer.cpp",
                (const char *)(unsigned int)v162,
                bIgnoreCase);
            v163 = v228[0];
            if ( v228[0] )
            {
              DataStoreCache::PropertyBagLookaside::SetLookasideHSTRING(
                v53,
                &DataStoreCache::TileStoreProperties::SecondaryTileArguments,
                v228);
              v163 = v228[0];
            }
            WindowsDeleteString(v163);
          }
          goto LABEL_49;
        }
        v57 = v56 - 1;
        if ( !v57 )
        {
          LODWORD(v228[0]) = 0;
          v125 = (*(__int64 (__fastcall **)(_QWORD, HSTRING *))(*(_QWORD *)v214[0] + 64LL))(v214[0], v228);
          if ( v125 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x9F4,
              (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\tilestoretransformer.cpp",
              (const char *)(unsigned int)v125,
              bIgnoreCase);
          v126 = (int)v228[0];
          v127 = operator new(0x20u);
          *(_OWORD *)v127 = 0;
          v127[2] = 1;
          v127[3] = 1;
          *(_QWORD *)v127 = &std::_Ref_count_obj2<DataStoreCache::PropertyBagLookaside::LookasidePropertyValueType<unsigned long>>::`vftable';
          *((_QWORD *)v127 + 2) = &DataStoreCache::PropertyBagLookaside::LookasidePropertyValueType<unsigned int>::`vftable';
          v127[6] = v126;
          v203 = (char *)(v127 + 4);
          v204 = v127;
          *(_OWORD *)length = 0;
          SRWLock = (PSRWLOCK)&v203;
          if ( memcmp_0(DataStoreCache::TileStoreProperties::TileCapabilities, v53[6].Ptr, 0x10u) )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x311,
              (unsigned int)"shellcommon\\shell\\DataStoreCache\\Transformers\\inc\\DataStorePropertyTransformerBase.h",
              v128);
          v119 = v53 + 7;
          AcquireSRWLockExclusive(v53 + 7);
          v184 = (HSTRING)&v53[7];
          v129 = (__int64)v53[14].Ptr
               & std::_Conditionally_enabled_hash<enum DataStoreCache::PlaceholderTileTransformer::InstallDelayType,1>::operator()(&dword_1804C80A8);
          v130 = v53[11].Ptr;
          v131 = v130[2 * v129 + 1];
          if ( (PVOID)v131 == v53[9].Ptr )
          {
LABEL_190:
            std::_Xout_of_range("invalid unordered_map<K, T> key");
            goto LABEL_191;
          }
          while ( *(_DWORD *)&dword_1804C80A8 != *(_DWORD *)(v131 + 16) )
          {
            if ( v131 == v130[2 * v129] )
              goto LABEL_190;
            v131 = *(_QWORD *)(v131 + 8);
          }
LABEL_263:
          if ( !v131 )
            goto LABEL_190;
          v156 = v204;
          if ( v204 )
          {
            _InterlockedIncrement(v204 + 2);
            v156 = v204;
          }
          *(_QWORD *)(v131 + 24) = v203;
          v157 = *(std::_Ref_count_base **)(v131 + 32);
          *(_QWORD *)(v131 + 32) = v156;
          if ( v157 )
            std::_Ref_count_base::_Decref(v157);
          if ( v119 )
            ReleaseSRWLockExclusive(v119);
          v50 = (std::_Ref_count_base *)v204;
LABEL_47:
          if ( !v50 )
            goto LABEL_49;
LABEL_48:
          std::_Ref_count_base::_Decref(v50);
          goto LABEL_49;
        }
        v58 = v57 - 1;
        if ( v58 )
        {
          if ( v58 != 1 )
            goto LABEL_357;
          v59 = v216;
          if ( !v216 )
          {
            DataStoreCache::TileStoreTransformer::TileContext::EnsureAppTypeAndCanElevate((DataStoreCache::TileStoreTransformer::TileContext *)v214);
            v59 = v216;
          }
          v60 = operator new(0x20u);
          *(_OWORD *)v60 = 0;
          v60[2] = 1;
          v60[3] = 1;
          *(_QWORD *)v60 = &std::_Ref_count_obj2<DataStoreCache::PropertyBagLookaside::LookasidePropertyValueType<unsigned long>>::`vftable';
          *((_QWORD *)v60 + 2) = &DataStoreCache::PropertyBagLookaside::LookasidePropertyValueType<unsigned int>::`vftable';
          v60[6] = v59;
          v201 = (char *)(v60 + 4);
          v202 = v60;
          *(_OWORD *)v228 = 0;
          SRWLock = (PSRWLOCK)&v201;
          if ( memcmp_0(DataStoreCache::TileStoreProperties::ApplicationType, v53[6].Ptr, 0x10u) )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x311,
              (unsigned int)"shellcommon\\shell\\DataStoreCache\\Transformers\\inc\\DataStorePropertyTransformerBase.h",
              v61);
          AcquireSRWLockExclusive(v53 + 7);
          v184 = (HSTRING)&v53[7];
          v62 = (__int64)v53[14].Ptr
              & std::_Conditionally_enabled_hash<enum DataStoreCache::PlaceholderTileTransformer::InstallDelayType,1>::operator()(&dword_1804C80E8);
          v63 = v53[11].Ptr;
          v64 = v63[2 * v62 + 1];
          if ( (PVOID)v64 != v53[9].Ptr )
          {
            while ( *(_DWORD *)&dword_1804C80E8 != *(_DWORD *)(v64 + 16) )
            {
              if ( v64 == v63[2 * v62] )
                goto LABEL_67;
              v64 = *(_QWORD *)(v64 + 8);
            }
            if ( v64 )
            {
              v158 = v202;
              if ( v202 )
              {
                _InterlockedIncrement(v202 + 2);
                v158 = v202;
              }
              *(_QWORD *)(v64 + 24) = v201;
              v159 = *(std::_Ref_count_base **)(v64 + 32);
              *(_QWORD *)(v64 + 32) = v158;
              if ( v159 )
                std::_Ref_count_base::_Decref(v159);
              if ( v53 != (RTL_SRWLOCK *)-56LL )
                ReleaseSRWLockExclusive(v53 + 7);
              v50 = (std::_Ref_count_base *)v202;
              goto LABEL_47;
            }
          }
LABEL_67:
          std::_Xout_of_range("invalid unordered_map<K, T> key");
LABEL_68:
          if ( v54 != 983281 && v54 != -1 )
            DataStoreCache::TileStoreTransformer::AddVisualProperty(
              (const struct DataStoreCache::DataStorePropertyIdentifier *)v51,
              (struct DataStoreCache::TileStoreTransformer::TileContext *)v214,
              (struct DataStoreCache::PropertyBagLookaside *)v53);
          goto LABEL_49;
        }
        if ( !v218[1] )
          DataStoreCache::TileStoreTransformer::TileContext::EnsureAppTypeAndCanElevate((DataStoreCache::TileStoreTransformer::TileContext *)v214);
        if ( *(_BYTE *)std::optional<bool>::value(v218) )
        {
          v186[0] = 1;
          DataStoreCache::PropertyBagLookaside::SetLookasideValueType<bool>(
            v53,
            &DataStoreCache::TileStoreProperties::CanElevate,
            v186);
        }
      }
LABEL_49:
      ++v48;
    }
  }
  AcquireSRWLockShared(v11 + 19);
  std::_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>::find(
    &v11[20],
    &SRWLock,
    &Buf1);
  if ( SRWLock == v11[21].Ptr )
  {
    WindowsDeleteString(string);
    string = 0;
    v85 = WindowsDuplicateString(0, &string);
    if ( v85 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x56,
        (unsigned int)"shellcommon\\shell\\DataStoreCache\\inc\\DataStoreCacheItemIdentifier.h",
        (const char *)(unsigned int)v85,
        bIgnoreCase);
    v86 = 0;
    WindowsDeleteString(0);
  }
  else
  {
    v146 = (struct DataStoreTransformerTelemetry::TileStoreTransformerReconcileTiles *)DataStoreCache::DataItemIdentifier::DataItemIdentifier(
                                                                                         (HSTRING *)&SRWLock,
                                                                                         (const struct DataStoreCache::DataItemIdentifier *)&SRWLock[4]);
    v197 = v146;
    DataStoreCache::DataItemIdentifier::operator=(&string);
    WindowsDeleteString(*(HSTRING *)v146);
    *(_QWORD *)v146 = 0;
    v86 = 1;
  }
  if ( v11 != (PSRWLOCK)-152LL )
    ReleaseSRWLockShared(v11 + 19);
  if ( v86 )
  {
    Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, &v11[19]);
    std::_Hash<std::_Umap_traits<_GUID,DataStoreCache::DataItemIdentifier,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,DataStoreCache::DataItemIdentifier>>,0>>::_Erase<_GUID>(
      &v11[20],
      &Buf1);
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    (*(void (__fastcall **)(PVOID, HSTRING *, HSTRING))(*(_QWORD *)v11[55].Ptr + 40LL))(v11[55].Ptr, &v184, string);
    v188 = 0;
    v170 = v184;
    v171 = *(unsigned __int8 (__fastcall **)(HSTRING, const struct _GUID *, GUID *, __int64))(*(_QWORD *)v184 + 48LL);
    v172 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTilePrivate>>(&v188);
    if ( v171(v170, &c_tileStoreTransformerId, &GUID_9dbb8733_cc6a_4eba_92cc_25fc80f0c2cb, v172) )
    {
      Buf2 = 0;
      if ( (*(unsigned __int8 (__fastcall **)(struct DataStoreCache::PropertyBagLookaside *, void **, __int64, __int128 *))(*(_QWORD *)v188 + 24LL))(
             v188,
             &DataStoreCache::TileStoreProperties::TileUniqueId,
             16,
             &Buf2) )
      {
        if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
        {
          LODWORD(v228[0]) = 0;
          if ( (*(unsigned __int8 (__fastcall **)(struct DataStoreCache::PropertyBagLookaside *, void **, __int64, HSTRING *))(*(_QWORD *)v188 + 24LL))(
                 v188,
                 &DataStoreCache::TileStoreProperties::TileType,
                 4,
                 v228) )
          {
            if ( LODWORD(v228[0]) == 1 )
            {
              Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, &v11[19]);
              DataStoreCache::TileStoreTransformer::RemoveSecondaryTileIdentifierFromIndex((DataStoreCache::TileStoreTransformer *)v11);
              if ( SRWLock )
                ReleaseSRWLockExclusive(SRWLock);
            }
          }
          v190 = 0;
          v173 = Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>::As<DataStoreCache::IDataUpdate>(&v184, &v190);
          if ( v173 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x7BF,
              (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\tilestoretransformer.cpp",
              (const char *)(unsigned int)v173,
              bIgnoreCase);
          (*(void (__fastcall **)(struct Windows::Internal::Tiles::ITile *, const struct _GUID *, _QWORD))(*(_QWORD *)v190 + 40LL))(
            v190,
            &c_tileStoreTransformerId,
            0);
          SRWLock = (PSRWLOCK)WindowsGetStringRawBuffer(string, 0);
          DataStoreTransformerTelemetry::TileStoreTransformerReconcileTiles::TileRemoved<_GUID &,unsigned short const *,__int64 &>(
            a8,
            &Buf1,
            &SRWLock,
            v192);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v190);
        }
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v188);
    v83 = v184;
    if ( v184 )
    {
      v184 = 0;
LABEL_108:
      (*(void (__fastcall **)(void *))(*(_QWORD *)v83 + 16LL))(v83);
    }
  }
  else
  {
    DataStoreTransformerTelemetry::TileStoreTransformerReconcileTiles::CouldNotRemoveTileByTileUniqueId<_GUID &>(
      a8,
      &Buf1);
  }
LABEL_109:
  v225 = 0;
  v84 = v196;
  if ( v196 )
  {
    v196 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
  }
  WindowsDeleteString(string);
}

```

## disassembly

```asm
0x18001b3e4  mov     [rsp-8+arg_10], rbx
0x18001b3e9  push    rbp
0x18001b3ea  push    rsi
0x18001b3eb  push    rdi
0x18001b3ec  push    r12
0x18001b3ee  push    r13
0x18001b3f0  push    r14
0x18001b3f2  push    r15
0x18001b3f4  lea     rbp, [rsp-170h]
0x18001b3fc  sub     rsp, 270h
0x18001b403  mov     rax, cs:__security_cookie
0x18001b40a  xor     rax, rsp
0x18001b40d  mov     [rbp+1A0h+var_40], rax
0x18001b414  mov     rdi, r9
0x18001b417  mov     rsi, r8
0x18001b41a  mov     rbx, rdx
0x18001b41d  mov     r15, rcx
0x18001b420  mov     [rsp+2A0h+SRWLock], rcx
0x18001b425  mov     r14, [rbp+1A0h+arg_38]
0x18001b42c  mov     [rbp+1A0h+var_1E8], r14
0x18001b430  xor     r12d, r12d
0x18001b433  mov     [rsp+2A0h+var_230], r12d
0x18001b438  xorps   xmm0, xmm0
0x18001b43b  movups  [rbp+1A0h+Buf1], xmm0
0x18001b442  or      r13, 0FFFFFFFFFFFFFFFFh
0x18001b446  mov     qword ptr [rbp+1A0h+var_210], r13
0x18001b44a  mov     [rsp+2A0h+string], r12
0x18001b44f  mov     [rbp+1A0h+var_B0], r14
0x18001b456  lea     rax, [rsp+2A0h+var_230]
0x18001b45b  mov     [rbp+1A0h+var_A8], rax
0x18001b462  lea     rax, [rbp+1A0h+Buf1]
0x18001b469  mov     [rbp+1A0h+var_A0], rax
0x18001b470  lea     rax, [rbp+1A0h+var_210]
0x18001b474  mov     [rbp+1A0h+var_98], rax
0x18001b47b  lea     rax, [rsp+2A0h+string]
0x18001b480  mov     [rbp+1A0h+var_90], rax
0x18001b487  mov     [rbp+1A0h+var_88], 1
0x18001b48e  mov     rax, [rdx]
0x18001b491  lea     rdx, [rsp+2A0h+var_230]
0x18001b496  mov     rcx, rbx
0x18001b499  mov     rax, [rax+40h]
0x18001b49d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4a2  mov     rcx, [rbp+1A8h]; this
0x18001b4a9  test    eax, eax
0x18001b4ab  js      loc_18001BEB9
0x18001b4b1  mov     rax, [rbx]
0x18001b4b4  lea     rdx, [rbp+1A0h+Buf1]
0x18001b4bb  mov     rcx, rbx
0x18001b4be  mov     rax, [rax+38h]
0x18001b4c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4c7  mov     rcx, [rbp+1A8h]; this
0x18001b4ce  test    eax, eax
0x18001b4d0  js      loc_18001BECE
0x18001b4d6  mov     rax, [rbx]
0x18001b4d9  lea     rdx, [rbp+1A0h+var_210]
0x18001b4dd  mov     rcx, rbx
0x18001b4e0  mov     rax, [rax+48h]
0x18001b4e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4e9  mov     rcx, [rbp+1A8h]; this
0x18001b4f0  test    eax, eax
0x18001b4f2  js      loc_18001BEE3
0x18001b4f8  mov     [rbp+1A0h+var_1F0], r12
0x18001b4fc  mov     rax, [rbx]
0x18001b4ff  lea     rdx, [rbp+1A0h+var_1F0]
0x18001b503  mov     rcx, rbx
0x18001b506  mov     rax, [rax+50h]
0x18001b50a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b50f  mov     rcx, [rbp+1A8h]; this
0x18001b516  test    eax, eax
0x18001b518  js      loc_18001BEF8
0x18001b51e  mov     rcx, [rbp+1A0h+var_1F0]
0x18001b522  test    rcx, rcx
0x18001b525  jz      short loc_18001B58B
0x18001b527  mov     dword ptr [rbp+1A0h+var_70], r12d
0x18001b52e  mov     rax, [rcx]
0x18001b531  lea     rdx, [rbp+1A0h+var_70]
0x18001b538  mov     rax, [rax+40h]
0x18001b53c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b541  mov     rcx, [rbp+1A8h]
0x18001b548  test    eax, eax
0x18001b54a  js      loc_18001C0BC
0x18001b550  mov     [rbp+1A0h+length], r12d
0x18001b554  mov     rcx, [rbp+1A0h+var_1F0]
0x18001b558  mov     rax, [rcx]
0x18001b55b  lea     rdx, [rbp+1A0h+length]
0x18001b55f  mov     rax, [rax+38h]
0x18001b563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b568  mov     rcx, [rbp+1A8h]; this
0x18001b56f  test    eax, eax
0x18001b571  js      loc_18001C0D1
0x18001b577  cmp     [rbp+1A0h+length], r12d
0x18001b57b  jnz     short loc_18001B58B
0x18001b57d  cmp     dword ptr [r15+1A0h], 1
0x18001b585  jz      loc_18001BF1E
0x18001b58b  mov     eax, [rsp+2A0h+var_230]
0x18001b58f  cmp     eax, 1
0x18001b592  jz      loc_18001BE23
0x18001b598  mov     [rsp+2A0h+var_228], r12
0x18001b59d  mov     rax, [rbx]
0x18001b5a0  lea     rdx, [rsp+2A0h+var_228]
0x18001b5a5  mov     rcx, rbx
0x18001b5a8  mov     rax, [rax+50h]
0x18001b5ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b5b1  mov     rcx, [rbp+1A8h]; this
0x18001b5b8  test    eax, eax
0x18001b5ba  js      loc_18001C56C
0x18001b5c0  mov     rax, [rbp+1A0h+arg_28]
0x18001b5c7  mov     [rsp+2A0h+var_270], rax; struct Windows::Internal::StateRepository::IApplicationExtensionStatics *
0x18001b5cc  mov     rax, [rbp+1A0h+arg_20]
0x18001b5d3  mov     [rsp+2A0h+var_278], rax; struct Windows::Internal::StateRepository::IHostRuntimeStatics *
0x18001b5d8  mov     qword ptr [rsp+2A0h+bIgnoreCase], rsi; int
0x18001b5dd  mov     r9, rdi; struct Windows::Internal::StateRepository::IPackageUserStatics *
0x18001b5e0  mov     r8, [rbp+1A0h+arg_30]; struct Windows::Internal::StateRepository::IUser *
0x18001b5e7  mov     rdx, [rsp+2A0h+var_228]; struct Windows::Internal::Tiles::ITile *
0x18001b5ec  lea     rcx, [rbp+1A0h+var_150]; this
0x18001b5f0  call    ??0TileContext@TileStoreTransformer@DataStoreCache@@QEAA@PEAUITile@Tiles@Internal@Windows@@PEAUIUser@StateRepository@56@PEAUIPackageUserStatics@856@PEAUITileViewStatics@856@PEAUIHostRuntimeStatics@856@PEAUIApplicationExtensionStatics@856@@Z; DataStoreCache::TileStoreTransformer::TileContext::TileContext(Windows::Internal::Tiles::ITile *,Windows::Internal::StateRepository::IUser *,Windows::Internal::StateRepository::IPackageUserStatics *,Windows::Internal::StateRepository::ITileViewStatics *,Windows::Internal::StateRepository::IHostRuntimeStatics *,Windows::Internal::StateRepository::IApplicationExtensionStatics *)
0x18001b5f5  nop
0x18001b5f6  xor     edi, edi
0x18001b5f8  cmp     [rbp+1A0h+var_F8], edi
0x18001b5fe  jnz     short loc_18001B615
0x18001b600  lea     rcx, [rbp+1A0h+var_150]; this
0x18001b604  call    ?EnsureAppTypeAndCanElevate@TileContext@TileStoreTransformer@DataStoreCache@@AEAAXXZ; DataStoreCache::TileStoreTransformer::TileContext::EnsureAppTypeAndCanElevate(void)
0x18001b609  cmp     [rbp+1A0h+var_F8], edi
0x18001b60f  jz      loc_18001D3A0
0x18001b615  lea     r8, [rbp+1A0h+var_150]
0x18001b619  lea     rdx, [rbp+1A0h+var_1F8]
0x18001b61d  mov     rcx, r15
0x18001b620  call    ?ComputeTileIdentifier@TileStoreTransformer@DataStoreCache@@AEBA?AVDataItemIdentifier@2@AEAVTileContext@12@@Z; DataStoreCache::TileStoreTransformer::ComputeTileIdentifier(DataStoreCache::TileStoreTransformer::TileContext &)
0x18001b625  mov     rbx, [rax]
0x18001b628  mov     [rax], rdi
0x18001b62b  mov     rcx, [rsp+2A0h+string]; string
0x18001b630  call    cs:__imp_WindowsDeleteString
0x18001b636  mov     [rsp+2A0h+string], rbx
0x18001b63b  mov     rcx, [rbp+1A0h+var_1F8]; string
0x18001b63f  call    cs:__imp_WindowsDeleteString
0x18001b645  mov     rcx, [r15+1B8h]
0x18001b64c  mov     rax, [rcx]
0x18001b64f  mov     r8, [rsp+2A0h+string]
0x18001b654  lea     rdx, [rsp+2A0h+var_238]
0x18001b659  mov     rax, [rax+28h]
0x18001b65d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b662  nop
0x18001b663  mov     [rbp+1A0h+var_200], rdi
0x18001b667  mov     [rbp+1A0h+var_1C0], r13
0x18001b66b  mov     rcx, [rsp+2A0h+var_238]
0x18001b670  mov     rax, [rcx]
0x18001b673  lea     r9, [rbp+1A0h+var_200]
0x18001b677  lea     r8, _GUID_9dbb8733_cc6a_4eba_92cc_25fc80f0c2cb
0x18001b67e  lea     rdx, c_tileStoreTransformerId
0x18001b685  mov     rax, [rax+30h]
0x18001b689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b68e  lea     r14, aShellcommonShe_151; "shellcommon\\shell\\datastorecache\\tra"...
0x18001b695  test    al, al
0x18001b697  jnz     loc_18001CE69
0x18001b69d  mov     rcx, [rbp+1A0h+var_200]
0x18001b6a1  test    rcx, rcx
0x18001b6a4  jnz     loc_18001CE56
0x18001b6aa  mov     [rsp+2A0h+newString], rdi
0x18001b6af  lea     r13, [r15+98h]
0x18001b6b6  mov     rcx, r13; SRWLock
0x18001b6b9  call    cs:__imp_AcquireSRWLockShared
0x18001b6bf  lea     rdi, [r15+0A0h]
0x18001b6c6  lea     r8, [rbp+1A0h+Buf1]
0x18001b6cd  lea     rdx, [rsp+2A0h+var_258]
0x18001b6d2  mov     rcx, rdi
0x18001b6d5  call    ?find@?$_Hash@V?$_Umap_traits@U_GUID@@V?$shared_ptr@VCuratedTile@CuratedTileCollectionTransformer@DataStoreCache@@@std@@V?$_Uhash_compare@U_GUID@@UhashGUID@Util@DataStoreCache@@U?$equal_to@U_GUID@@@std@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VCuratedTile@CuratedTileCollectionTransformer@DataStoreCache@@@std@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VCuratedTile@CuratedTileCollectionTransformer@DataStoreCache@@@std@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::_Umap_traits<_GUID,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>,std::_Uhash_compare<_GUID,DataStoreCache::Util::hashGUID,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<DataStoreCache::CuratedTileCollectionTransformer::CuratedTile>>>,0>>::find(_GUID const &)
0x18001b6da  lea     r12, [rdi+8]
0x18001b6de  mov     rdx, [rsp+2A0h+var_258]
0x18001b6e3  cmp     rdx, [r12]
0x18001b6e7  jnz     loc_18001C069
0x18001b6ed  mov     rcx, [rsp+2A0h+newString]; string
0x18001b6f2  call    cs:__imp_WindowsDeleteString
0x18001b6f8  mov     [rsp+2A0h+newString], 0
0x18001b701  lea     rdx, [rsp+2A0h+newString]; newString
0x18001b706  xor     ecx, ecx; string
0x18001b708  call    cs:__imp_WindowsDuplicateString
0x18001b70e  mov     rcx, [rbp+1A8h]; this
0x18001b715  test    eax, eax
0x18001b717  js      loc_18001C792
0x18001b71d  xor     bl, bl
0x18001b71f  xor     ecx, ecx; string
0x18001b721  call    cs:__imp_WindowsDeleteString
0x18001b727  test    r13, r13
0x18001b72a  jnz     loc_18001BF39
0x18001b730  test    bl, bl
0x18001b732  jnz     loc_18001C7B5
0x18001b738  mov     rcx, r13; SRWLock
0x18001b73b  call    cs:__imp_AcquireSRWLockExclusive
0x18001b741  mov     [rbp+1A0h+var_70], r13
0x18001b748  lea     rcx, [rbp+1A0h+Buf1+8]; unsigned __int8 *
0x18001b74f  call    ??R?$_Conditionally_enabled_hash@PEAUHSTRING__@@$00@std@@SA_KAEBQEAUHSTRING__@@@Z; std::_Conditionally_enabled_hash<HSTRING__ *,1>::operator()(HSTRING__ * const &)
0x18001b754  mov     rsi, rax
0x18001b757  lea     rcx, [rbp+1A0h+Buf1]; unsigned __int8 *
0x18001b75e  call    ??R?$_Conditionally_enabled_hash@PEAUHSTRING__@@$00@std@@SA_KAEBQEAUHSTRING__@@@Z; std::_Conditionally_enabled_hash<HSTRING__ *,1>::operator()(HSTRING__ * const &)
0x18001b763  xor     rsi, rax
0x18001b766  mov     rax, rsi
0x18001b769  and     rax, [rdi+30h]
0x18001b76d  mov     rdx, [rdi+18h]
0x18001b771  mov     rcx, rax
0x18001b774  add     rcx, rcx
0x18001b777  mov     rbx, [rdx+rcx*8+8]
0x18001b77c  mov     r15, [r12]
0x18001b780  cmp     rbx, r15
0x18001b783  jz      short loc_18001B7B6
0x18001b785  add     rax, rax
0x18001b788  mov     r15, [rdx+rax*8]
0x18001b78c  lea     rdx, [rbx+10h]; Buf2
0x18001b790  mov     r8d, 10h; Size
0x18001b796  lea     rcx, [rbp+1A0h+Buf1]; Buf1
0x18001b79d  call    memcmp_0
0x18001b7a2  test    eax, eax
0x18001b7a4  jz      loc_18001B87B
0x18001b7aa  cmp     rbx, r15
0x18001b7ad  jnz     loc_18001C9CA
0x18001b7b3  mov     r15, rbx
0x18001b7b6  mov     rax, 666666666666666h
0x18001b7c0  cmp     [rdi+10h], rax
0x18001b7c4  jz      loc_18001D46E
0x18001b7ca  mov     qword ptr [rbp+1A0h+Buf2], r12
0x18001b7d1  mov     qword ptr [rbp+1A0h+Buf2+8], 0
0x18001b7dc  mov     ecx, 28h ; '('
0x18001b7e1  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001b7e6  mov     rbx, rax
0x18001b7e9  mov     qword ptr [rbp+1A0h+Buf2+8], rax
0x18001b7f0  lea     rcx, [rbp+1A0h+Buf1]
0x18001b7f7  mov     [rsp+2A0h+var_258], rcx
0x18001b7fc  lea     rdx, [rsp+2A0h+var_258]
0x18001b801  lea     rcx, [rax+10h]
0x18001b805  call    ??$?0V?$tuple@AEBU_GUID@@@std@@V?$tuple@$$V@1@$0A@$$Z$S@?$pair@$$CBU_GUID@@V?$com_ptr_t@UICuratedTileGroup@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@Uerr_exception_policy@wil@@@wil@@@std@@AEAA@AEAV?$tuple@AEBU_GUID@@@1@AEAV?$tuple@$$V@1@U?$integer_sequence@_K$0A@@1@U?$integer_sequence@_K$S@1@@Z
0x18001b80a  nop
0x18001b80b  mov     rdx, [rdi+10h]
0x18001b80f  add     rdx, 1
0x18001b813  xorps   xmm0, xmm0
0x18001b816  js      loc_18001D046
0x18001b81c  cvtsi2ss xmm0, rdx
0x18001b821  mov     rcx, [rdi+38h]
0x18001b825  xorps   xmm1, xmm1
0x18001b828  test    rcx, rcx
0x18001b82b  js      loc_18001D063
0x18001b831  cvtsi2ss xmm1, rcx
0x18001b836  divss   xmm0, xmm1
0x18001b83a  comiss  xmm0, dword ptr [rdi]
0x18001b83d  ja      loc_18001CFB5
0x18001b843  mov     rcx, [r15+8]
0x18001b847  inc     qword ptr [rdi+10h]
0x18001b84b  mov     [rbx], r15
0x18001b84e  mov     [rbx+8], rcx
0x18001b852  mov     [rcx], rbx
0x18001b855  mov     [r15+8], rbx
0x18001b859  mov     rax, [rdi+18h]
0x18001b85d  and     rsi, [rdi+30h]
0x18001b861  add     rsi, rsi
0x18001b864  mov     rdx, [rax+rsi*8]
0x18001b868  cmp     rdx, [r12]
0x18001b86c  jnz     loc_18001CB18
0x18001b872  mov     [rax+rsi*8], rbx
0x18001b876  mov     [rax+rsi*8+8], rbx
0x18001b87b  lea     rdi, [rbx+20h]
0x18001b87f  mov     rbx, [rsp+2A0h+string]
0x18001b884  test    rbx, rbx
0x18001b887  jz      short loc_18001B890
0x18001b889  xor     eax, eax
0x18001b88b  cmp     rbx, [rdi]
0x18001b88e  jz      short loc_18001B8B1
0x18001b890  mov     rcx, [rdi]; string
0x18001b893  call    cs:__imp_WindowsDeleteString
0x18001b899  mov     qword ptr [rdi], 0
0x18001b8a0  mov     rdx, rdi; newString
0x18001b8a3  mov     rcx, rbx; string
0x18001b8a6  call    cs:__imp_WindowsDuplicateString
0x18001b8ac  mov     rbx, [rsp+2A0h+string]
0x18001b8b1  mov     rcx, [rbp+1A8h]; this
0x18001b8b8  xor     edi, edi
0x18001b8ba  test    eax, eax
0x18001b8bc  js      loc_18001C9B5
0x18001b8c2  cmp     [rbp+1A0h+var_EC], 1
0x18001b8c9  jz      loc_18001CF75
0x18001b8cf  mov     r15, [rsp+2A0h+SRWLock]
0x18001b8d4  test    r13, r13
0x18001b8d7  jnz     loc_18001C7A7
0x18001b8dd  lea     rbx, [r15+80h]
0x18001b8e4  mov     r8, rbx
0x18001b8e7  lea     rdx, c_tileStoreTransformerId
0x18001b8ee  lea     rcx, [rbp+1A0h+var_208]
0x18001b8f2  call    ??$MakeOrThrow@VPropertyBagLookaside@DataStoreCache@@AEBU_GUID@@AEAV?$vector@PEBUDataStorePropertyIdentifier@DataStoreCache@@V?$allocator@PEBUDataStorePropertyIdentifier@DataStoreCache@@@std@@@std@@@wil@@YA?AV?$ComPtr@VPropertyBagLookaside@DataStoreCache@@@WRL@Microsoft@@AEBU_GUID@@AEAV?$vector@PEBUDataStorePropertyIdentifier@DataStoreCache@@V?$allocator@PEBUDataStorePropertyIdentifier@DataStoreCache@@@std@@@std@@@Z; wil::MakeOrThrow<DataStoreCache::PropertyBagLookaside,_GUID const &,std::vector<DataStoreCache::DataStorePropertyIdentifier const *> &>(_GUID const &,std::vector<DataStoreCache::DataStorePropertyIdentifier const *> &)
0x18001b8f7  nop
0x18001b8f8  mov     r12, [rbx]
0x18001b8fb  mov     r13, [rbx+8]
0x18001b8ff  jmp     short loc_18001B914
0x18001b901  mov     rcx, [rbp+1A0h+var_170]; this
0x18001b905  test    rcx, rcx
0x18001b908  jz      short loc_18001B910
0x18001b90a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001b90f  nop
0x18001b910  add     r12, 8
0x18001b914  cmp     r12, r13
0x18001b917  jz      loc_18001BC5A
0x18001b91d  mov     r9, [r12]; char *
0x18001b921  mov     ecx, [r9+8]
0x18001b925  mov     rax, [rbp+1A8h]
  ... truncated ...
```
