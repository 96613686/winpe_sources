# ARI::GetPackagePath_Internal_HRESULT(bool,ushort const *,PackagePathType,uint *,ushort *)

- ea: `0x18009df60`
- end: `0x18009f33c`
- name: `?GetPackagePath_Internal_HRESULT@ARI@@YAJ_NPEBGW4PackagePathType@@PEAIPEAG@Z`
- size: `5084`
- prototype: `int __high(bool, const unsigned __int16 *, enum PackagePathType, unsigned int *, unsigned __int16 *)`
- caller_count: `7`
- callee_count: `18`
- tags: `loader_planting`

## callers

- `0x18009daa0`
- `0x18009db00`
- `0x18009db54`
- `0x18009de70`
- `0x18009ded0`
- `0x18009df2c`
- `0x18009f5d0`

## callees

- `0x18002da14`
- `0x18002ddc0`
- `0x18002ea40`
- `0x18002efa8`
- `0x18002f340`
- `0x18002f738`
- `0x18002fd98`
- `0x180035a90`
- `0x180056554`
- `0x180057f40`
- `0x180058768`
- `0x180065e00`
- `0x1800689c8`
- `0x18009df60`
- `0x1800cac68`
- `0x18012d119`
- `0x180150c84`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18009e442`
- `ntdll!RtlFreeHeap` at `0x18009f14c`
- `ntdll!RtlFreeHeap` at `0x18009f1d1`
- `ntdll!RtlFreeHeap` at `0x18009f200`
- `ntdll!RtlFreeHeap` at `0x18009f27e`
- `ntdll!RtlFreeHeap` at `0x18009e442`
- `ntdll!RtlFreeHeap` at `0x18009f14c`
- `ntdll!RtlFreeHeap` at `0x18009f1d1`
- `ntdll!RtlFreeHeap` at `0x18009f200`
- `ntdll!RtlFreeHeap` at `0x18009f27e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18009e7ad`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18009ec5a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18009ee35`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18009effe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18009e7ad`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18009ec5a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18009ee35`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18009effe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18009e61b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18009eacc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18009e61b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18009eacc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18009e4e1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18009e992`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18009e4e1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18009e992`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18009dfc6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18009dfc6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009e505`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009e63f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009e70b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009e735`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009e772`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009e844`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009e9b6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009eaf0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009ebbc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009ebe6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009ec23`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009ecee`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009eecf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009ef22`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009f09d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009f0f2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009e505`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009e63f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009e70b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009e735`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009e772`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009e844`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009e9b6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009eaf0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009ebbc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009ebe6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009ec23`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009ecee`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009eecf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009ef22`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009f09d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009f0f2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18009dfea`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18009e372`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18009f16a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18009f21e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18009f29c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18009f2d8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18009dfea`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18009e372`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18009f16a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18009f21e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18009f29c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18009f2d8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009e354`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009e3c3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009e429`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009e6f6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009e75d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009e7f4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009e8fe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009eba7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009ec0e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009ec9e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009ee7f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009f04b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009f135`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009f1b6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009f1e9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009f267`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009e354`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009e3c3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009e429`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009e6f6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009e75d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009e7f4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009e8fe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009eba7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009ec0e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009ec9e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009ee7f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009f04b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009f135`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009f1b6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009f1e9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009f267`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18009e698`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18009eb49`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18009e698`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18009eb49`

## string_xrefs

- `0x18009e464`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18009e492`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18009e531`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18009e560`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18009e5d8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18009e66b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18009e6ca`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18009e809`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18009e917`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18009e943`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18009e9e2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18009ea11`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18009ea89`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18009eb1c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18009eb7b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18009ecb3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18009ed84`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18009edb0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18009edf1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18009ee94`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18009ef48`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18009ef73`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18009efb6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18009f060`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18009e516`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18009e650`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18009e6af`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18009e7c0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18009e9c7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18009eb01`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18009eb60`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18009ec6d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18009ee48`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18009f011`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18009dffb`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-manager.hpp`
- `0x18009e140`: `onecore\base\AppModel\Runtime\Src\PackagePath.hpp`
- `0x18009e170`: `onecore\base\AppModel\Runtime\Src\PackagePath.hpp`
- `0x18009e1da`: `onecore\base\AppModel\Runtime\Src\PackagePath.hpp`
- `0x18009e21e`: `onecore\base\AppModel\Runtime\Src\PackagePath.hpp`
- `0x18009e259`: `onecore\base\AppModel\Runtime\Src\PackagePath.hpp`
- `0x18009e286`: `onecore\base\AppModel\Runtime\Src\PackagePath.hpp`
- `0x18009e330`: `onecore\base\AppModel\Runtime\Src\PackagePath.hpp`
- `0x18009e3a7`: `onecore\base\AppModel\Runtime\Src\PackagePath.hpp`
- `0x18009e408`: `onecore\base\AppModel\Runtime\Src\PackagePath.hpp`
- `0x18009e868`: `onecore\base\AppModel\Runtime\Src\PackagePath.hpp`
- `0x18009e8dc`: `onecore\base\AppModel\Runtime\Src\PackagePath.hpp`
- `0x18009ed12`: `onecore\base\AppModel\Runtime\Src\PackagePath.hpp`
- `0x18009eef3`: `onecore\base\AppModel\Runtime\Src\PackagePath.hpp`
- `0x18009f0c1`: `onecore\base\AppModel\Runtime\Src\PackagePath.hpp`
- `0x18009f193`: `onecore\base\AppModel\Runtime\Src\PackagePath.hpp`
- `0x18009f23e`: `onecore\base\AppModel\Runtime\Src\PackagePath.hpp`
- `0x18009f2ba`: `onecore\base\AppModel\Runtime\Src\PackagePath.hpp`

## pseudocode

```c
__int64 __fastcall ARI::GetPackagePath_Internal_HRESULT(
        char a1,
        const unsigned __int16 *a2,
        int a3,
        unsigned int *a4,
        unsigned __int16 *a5)
{
  PVOID v8; // r14
  int v10; // ebx
  unsigned __int16 *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r10
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  int v18; // eax
  int v19; // eax
  void *v20; // rdx
  int v21; // eax
  int v22; // eax
  const unsigned __int16 *v23; // rbx
  unsigned __int16 *v24; // rcx
  __int64 v25; // rcx
  __int64 v27; // rdx
  unsigned __int16 *v28; // rcx
  __int64 v29; // rcx
  int EffectiveLocationByUserAndPackage; // eax
  unsigned __int16 *v31; // rcx
  __int64 v32; // rdx
  unsigned __int64 v33; // rdi
  unsigned __int16 *v34; // rcx
  int v35; // eax
  unsigned __int16 *v36; // rcx
  bool v37; // si
  int v38; // eax
  __int64 v39; // rcx
  __int64 v40; // rcx
  void *v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  PVOID v44; // rcx
  int Field_String; // eax
  unsigned __int16 *v46; // rcx
  void *v47; // rcx
  unsigned __int16 *v48; // rcx
  __int64 v49; // rdx
  unsigned __int64 v50; // rdi
  unsigned __int16 *v51; // rcx
  int v52; // eax
  unsigned __int16 *v53; // rcx
  bool v54; // si
  int v55; // eax
  __int64 v56; // rcx
  __int64 v57; // rcx
  void *v58; // rcx
  __int64 v59; // rcx
  __int64 v60; // rcx
  int v61; // eax
  unsigned __int16 *v62; // rcx
  void *v63; // rcx
  __int64 v64; // rdx
  __int64 v65; // rdi
  int v66; // eax
  unsigned __int64 v67; // r9
  __int64 v68; // rdx
  __int64 v69; // rcx
  int v70; // eax
  unsigned __int16 *v71; // rcx
  __int64 v72; // rcx
  __int64 v73; // rdx
  __int64 v74; // rdi
  int v75; // eax
  unsigned __int64 v76; // r9
  __int64 v77; // rdx
  int v78; // eax
  unsigned __int16 *v79; // rcx
  PVOID v80; // rcx
  __int64 v81; // rax
  unsigned __int64 v82; // rcx
  unsigned int v83; // eax
  unsigned __int16 *v84; // rcx
  __int64 v85; // rcx
  int v86; // eax
  int v87; // eax
  unsigned __int16 *v88; // rcx
  unsigned __int16 *v89; // rcx
  __int64 v90; // rcx
  unsigned __int16 *v91; // rcx
  bool *v92; // [rsp+20h] [rbp-E0h]
  int v93; // [rsp+20h] [rbp-E0h]
  int v94; // [rsp+20h] [rbp-E0h]
  int v95; // [rsp+20h] [rbp-E0h]
  int v96; // [rsp+20h] [rbp-E0h]
  int v97; // [rsp+20h] [rbp-E0h]
  int v98; // [rsp+20h] [rbp-E0h]
  int v99; // [rsp+20h] [rbp-E0h]
  int v100; // [rsp+20h] [rbp-E0h]
  int v101; // [rsp+20h] [rbp-E0h]
  int v102; // [rsp+20h] [rbp-E0h]
  int v103; // [rsp+20h] [rbp-E0h]
  int v104; // [rsp+20h] [rbp-E0h]
  int v105; // [rsp+20h] [rbp-E0h]
  int v106; // [rsp+20h] [rbp-E0h]
  char *v107; // [rsp+28h] [rbp-D8h]
  bool v108; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v109; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v110; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v111; // [rsp+58h] [rbp-A8h] BYREF
  PVOID P; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 **v113; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v114; // [rsp+70h] [rbp-90h] BYREF
  char v115; // [rsp+78h] [rbp-88h]
  void *v116; // [rsp+80h] [rbp-80h] BYREF
  void *v117; // [rsp+88h] [rbp-78h] BYREF
  void *v118; // [rsp+90h] [rbp-70h] BYREF
  __int64 v119; // [rsp+98h] [rbp-68h] BYREF
  __int128 v120; // [rsp+A0h] [rbp-60h]
  unsigned __int16 *v121[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v122; // [rsp+C0h] [rbp-40h] BYREF
  char *v123[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v124; // [rsp+E0h] [rbp-20h]
  __int64 v125; // [rsp+E8h] [rbp-18h]
  int v126; // [rsp+F0h] [rbp-10h]
  int v127; // [rsp+F4h] [rbp-Ch]
  __int64 v128; // [rsp+F8h] [rbp-8h]
  __int64 v129; // [rsp+100h] [rbp+0h]
  const unsigned __int16 *v130; // [rsp+108h] [rbp+8h]
  __int128 v131; // [rsp+110h] [rbp+10h]
  int v132; // [rsp+120h] [rbp+20h]
  __int64 v133; // [rsp+128h] [rbp+28h]
  __int64 v134; // [rsp+130h] [rbp+30h]
  unsigned __int64 v135; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int64 v136; // [rsp+148h] [rbp+48h] BYREF
  __int64 v137; // [rsp+150h] [rbp+50h] BYREF
  __int64 v138; // [rsp+158h] [rbp+58h] BYREF
  unsigned __int16 **v139; // [rsp+160h] [rbp+60h]
  unsigned __int16 *v140; // [rsp+168h] [rbp+68h] BYREF
  char v141; // [rsp+170h] [rbp+70h]
  unsigned __int16 **v142; // [rsp+178h] [rbp+78h]
  unsigned __int16 *v143; // [rsp+180h] [rbp+80h] BYREF
  char v144; // [rsp+188h] [rbp+88h]
  unsigned __int16 **v145; // [rsp+190h] [rbp+90h]
  unsigned __int16 *v146; // [rsp+198h] [rbp+98h] BYREF
  char v147; // [rsp+1A0h] [rbp+A0h]
  __int64 v148; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v149[512]; // [rsp+1B8h] [rbp+B8h] BYREF
  __int64 v150; // [rsp+3B8h] [rbp+2B8h]
  __int64 v151; // [rsp+3C0h] [rbp+2C0h]
  _BYTE *v152; // [rsp+3C8h] [rbp+2C8h]
  __int64 v153; // [rsp+3D0h] [rbp+2D0h] BYREF
  _BYTE v154[512]; // [rsp+3D8h] [rbp+2D8h] BYREF
  __int64 v155; // [rsp+5D8h] [rbp+4D8h]
  __int64 v156; // [rsp+5E0h] [rbp+4E0h]
  _BYTE *v157; // [rsp+5E8h] [rbp+4E8h]
  wil::details::in1diag3 *retaddr; // [rsp+638h] [rbp+538h]

  v113 = (unsigned __int16 **)&v109;
  v8 = 0;
  v115 = 1;
  v109 = 0;
  v114 = 0;
  v10 = SRCacheManager_Open(0, &v114);
  if ( v115 )
  {
    v11 = *v113;
    *v113 = v114;
    if ( v11 )
      SRCacheManager_Close(v11);
  }
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-manager.hpp",
      (const char *)(unsigned int)v10,
      (int)v92);
    v12 = 73;
LABEL_248:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\AppModel\\Runtime\\Src\\PackagePath.hpp",
      (const char *)(unsigned int)v10,
      (int)v92);
    goto LABEL_249;
  }
  v122 = 0;
  v10 = StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
          (struct StateRepository::Cache::Manager_NoThrow *)&v109,
          a2,
          &v122);
  if ( v10 < 0 )
  {
    v12 = 75;
    goto LABEL_248;
  }
  v13 = v122;
  if ( !v122 )
  {
    if ( !a2
      || (memset_0(&v148, 0, 0xF0u),
          LODWORD(v110) = 240,
          (unsigned int)ARI::Identity::Convert<unsigned short,unsigned short *,unsigned short const *,PACKAGE_ID>::PackageIdBasicFromFullName(
                          a2,
                          v14,
                          &v110,
                          &v148) == 87) )
    {
      v12 = 79;
LABEL_247:
      v10 = -2147024809;
      goto LABEL_248;
    }
    v15 = v109;
    v109 = 0;
    goto LABEL_243;
  }
  v16 = 0;
  switch ( a3 )
  {
    case 0:
      v16 = 256;
      goto LABEL_16;
    case 1:
      v16 = 768;
      goto LABEL_16;
    case 2:
    case 3:
    case 4:
    case 5:
LABEL_16:
      v124 = 0;
      *(_OWORD *)v123 = 0;
      v17 = v16 | 0x20;
      v125 = 0;
      v126 = 0;
      v18 = 0;
      v128 = 0;
      if ( !a1 )
        v17 = v16;
      v127 = 0;
      v129 = 0;
      v130 = 0;
      v131 = 0;
      v132 = 0;
      v133 = 0;
      v134 = 0;
      if ( !v17 )
        goto LABEL_24;
      v108 = 0;
      v92 = &v108;
      v19 = StateRepository::Cache::Entity::Package_NoThrow::Get(&v109, v122, v17, v123);
      v10 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x71,
          (unsigned int)"onecore\\base\\AppModel\\Runtime\\Src\\PackagePath.hpp",
          (const char *)(unsigned int)v19,
          (int)&v108);
        StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v123);
LABEL_249:
        v29 = v109;
        v109 = 0;
        goto LABEL_250;
      }
      if ( !v108 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x72,
          (unsigned int)"onecore\\base\\AppModel\\Runtime\\Src\\PackagePath.hpp",
          (const char *)0x80070490LL,
          (int)&v108);
LABEL_242:
        StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v123);
        v15 = v109;
        v109 = 0;
LABEL_243:
        if ( v15 )
          SRCacheManager_Close(v15);
        return 2147943568LL;
      }
      v13 = v122;
      v18 = v127;
LABEL_24:
      v20 = 0;
      v118 = 0;
      if ( a1 && v18 != 2 )
      {
        v21 = StateRepository::Cache::Entity::User_NoThrow::GetByToken(
                (struct StateRepository::Cache::Manager_NoThrow *)&v109,
                0,
                (__int64 *)&v118);
        v10 = v21;
        if ( v21 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x7F,
            (unsigned int)"onecore\\base\\AppModel\\Runtime\\Src\\PackagePath.hpp",
            (const char *)(unsigned int)v21,
            (int)v92);
          StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v123);
          goto LABEL_249;
        }
        if ( !v118 )
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x80,
            (unsigned int)"onecore\\base\\AppModel\\Runtime\\Src\\PackagePath.hpp",
            (const char *)0x80070490LL,
            (int)"Unknown user",
            v107);
          goto LABEL_242;
        }
        v108 = 0;
        v22 = StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(
                (struct StateRepository::Cache::Manager_NoThrow *)&v109,
                (__int64)v118,
                (__int64)v123[0],
                &v108);
        v10 = v22;
        if ( v22 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x82,
            (unsigned int)"onecore\\base\\AppModel\\Runtime\\Src\\PackagePath.hpp",
            (const char *)(unsigned int)v22,
            (int)v92);
          StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v123);
          goto LABEL_249;
        }
        if ( !v108 )
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x83,
            (unsigned int)"onecore\\base\\AppModel\\Runtime\\Src\\PackagePath.hpp",
            (const char *)0x80070490LL,
            (int)"Package %I64X not registered to user %I64X",
            v123[0],
            v118);
          goto LABEL_242;
        }
        v13 = v122;
        v20 = v118;
      }
      break;
    default:
LABEL_246:
      v12 = 103;
      goto LABEL_247;
  }
  P = 0;
  v120 = 0;
  *(_OWORD *)v121 = 0;
  switch ( a3 )
  {
    case 0:
      v23 = v130;
      goto LABEL_215;
    case 1:
      v23 = (const unsigned __int16 *)v131;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_GetPackagePathNoMutableDirectoryNotAnError>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_GetPackagePathNoMutableDirectoryNotAnError>::GetImpl'::`2'::impl) )
      {
        if ( (_QWORD)v131 )
          goto LABEL_215;
      }
      else
      {
        if ( (_QWORD)v131 )
          goto LABEL_215;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x98,
          (unsigned int)"onecore\\base\\AppModel\\Runtime\\Src\\PackagePath.hpp",
          (const char *)0x80073D5BLL,
          (int)v92);
      }
      v24 = v121[1];
      v121[1] = 0;
      if ( v24 )
        SRCache_Free(v24);
      StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v123);
      v25 = v109;
      v109 = 0;
      if ( v25 )
        SRCacheManager_Close(v25);
      return 2147958107LL;
    case 2:
      if ( v20 )
        goto LABEL_54;
      v10 = StateRepository::Cache::Entity::User_NoThrow::GetByToken(
              (struct StateRepository::Cache::Manager_NoThrow *)&v109,
              0,
              (__int64 *)&v118);
      if ( v10 < 0 )
      {
        v27 = 159;
        goto LABEL_50;
      }
      v13 = v122;
      v20 = v118;
LABEL_54:
      EffectiveLocationByUserAndPackage = StateRepository::Cache::Entity::Package_NoThrow::GetEffectiveLocationByUserAndPackage(
                                            (struct StateRepository::Cache::Manager_NoThrow *)&v109,
                                            (__int64)v20,
                                            v13);
      v10 = EffectiveLocationByUserAndPackage;
      if ( EffectiveLocationByUserAndPackage >= 0 )
      {
        v8 = P;
        v23 = (const unsigned __int16 *)P;
        goto LABEL_215;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA1,
        (unsigned int)"onecore\\base\\AppModel\\Runtime\\Src\\PackagePath.hpp",
        (const char *)(unsigned int)EffectiveLocationByUserAndPackage,
        (int)v92);
      v31 = v121[1];
      v121[1] = 0;
      if ( v31 )
        SRCache_Free(v31);
      if ( P )
        RtlFreeHeap(ReservedForLocalUse::g_heap, 0, P);
      goto LABEL_52;
    case 3:
      if ( !v13 )
      {
        v10 = -2147024809;
        v32 = 225;
LABEL_105:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v32,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v10,
          (int)v92);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x32,
          (unsigned int)"onecore\\base\\AppModel\\Runtime\\Src\\PackagePath.hpp",
          (const char *)(unsigned int)v10,
          v98);
        v27 = 168;
        goto LABEL_50;
      }
      v135 = 0;
      v10 = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(
              (struct StateRepository::Cache::Manager_NoThrow *)&v109,
              0,
              v13,
              (__int64 *)&v135);
      if ( v10 < 0 )
      {
        v32 = 228;
        goto LABEL_105;
      }
      v33 = v135;
      if ( !v135 )
        goto LABEL_214;
      v113 = (unsigned __int16 **)&v110;
      v116 = 0;
      v110 = 0;
      v114 = 0;
      v115 = 1;
      v10 = SRCacheContext_Open(v109, L"PackageExternalLocation\\Data", 0, &v114);
      if ( v115 )
      {
        v34 = *v113;
        *v113 = v114;
        if ( v34 )
          SRCacheContext_Close(v34);
      }
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x18C,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
          (const char *)(unsigned int)v10,
          (int)v92);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFA,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v10,
          v93);
        goto LABEL_83;
      }
      if ( !v110 )
      {
        v10 = -2140733422;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFB,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)0x80670012LL,
          (int)v92);
        goto LABEL_83;
      }
      v148 = 0;
      memset_0(v149, 0, sizeof(v149));
      v150 = 0;
      v152 = v149;
      v151 = 256;
      v35 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v148, v33);
      v10 = v35;
      if ( v35 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFE,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v35,
          (int)v92);
        goto LABEL_81;
      }
      v113 = (unsigned __int16 **)&v116;
      v114 = 0;
      v115 = 1;
      v10 = SRCacheContext_OpenSubContext(v110, v152, 0, &v114);
      if ( v115 )
      {
        v36 = *v113;
        *v113 = v114;
        if ( v36 )
          SRCacheContext_Close(v36);
      }
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B0,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
          (const char *)(unsigned int)v10,
          (int)v92);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFF,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v10,
          v95);
        goto LABEL_81;
      }
      v37 = v116 != 0;
      v38 = SRCacheContext_AddToCache(v110, L"PackageExternalLocation\\Data");
      v10 = v38;
      if ( v38 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1A6,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
          (const char *)(unsigned int)v38,
          (int)v92);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x101,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v10,
          v96);
LABEL_81:
        v39 = v148;
        v148 = 0;
        if ( v39 )
          SRCache_Free(v39);
LABEL_83:
        v40 = v110;
        v110 = 0;
        if ( v40 )
          SRCacheContext_Close(v40);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA4,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v10,
          v94);
        v41 = v116;
        v116 = 0;
        if ( v41 )
          SRCacheContext_Close(v41);
        if ( v10 < 0 )
        {
LABEL_104:
          v32 = 231;
          goto LABEL_105;
        }
        goto LABEL_214;
      }
      v42 = v148;
      v148 = 0;
      if ( v42 )
        SRCache_Free(v42);
      v43 = v110;
      v110 = 0;
      if ( v43 )
        SRCacheContext_Close(v43);
      v44 = v116;
      if ( !v37 )
      {
        v116 = 0;
        goto LABEL_212;
      }
      v115 = 1;
      v113 = &v121[1];
      v114 = 0;
      Field_String = SRCacheContext_GetField_String(v116, L"Path", &v114);
      v10 = Field_String;
      if ( Field_String >= 0 )
        v10 = 0;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x246,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
          (const char *)(unsigned int)Field_String,
          (int)v92);
      if ( v115 )
      {
        v46 = *v113;
        *v113 = v114;
        if ( v46 )
          SRCache_Free(v46);
      }
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x269,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v10,
          (int)v92);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA9,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v10,
          v97);
        v47 = v116;
        v116 = 0;
        if ( v47 )
          SRCacheContext_Close(v47);
        goto LABEL_104;
      }
      v44 = v116;
      v116 = 0;
      *(_QWORD *)&v120 = v33;
      goto LABEL_212;
    case 4:
      if ( v20 )
        goto LABEL_114;
      v10 = StateRepository::Cache::Entity::User_NoThrow::GetByToken(
              (struct StateRepository::Cache::Manager_NoThrow *)&v109,
              0,
              (__int64 *)&v118);
      if ( v10 < 0 )
      {
        v27 = 176;
        goto LABEL_50;
      }
      v20 = v118;
      if ( !v118 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0xB1,
          (unsigned int)"onecore\\base\\AppModel\\Runtime\\Src\\PackagePath.hpp",
          (const char *)0x80070490LL,
          (int)"Unknown user",
          v107);
        v48 = v121[1];
        v121[1] = 0;
        if ( v48 )
          SRCache_Free(v48);
        goto LABEL_242;
      }
      v13 = v122;
LABEL_114:
      if ( !v13 )
      {
        v10 = -2147024809;
        v49 = 225;
LABEL_159:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v49,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v10,
          (int)v92);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x32,
          (unsigned int)"onecore\\base\\AppModel\\Runtime\\Src\\PackagePath.hpp",
          (const char *)(unsigned int)v10,
          v104);
        v27 = 179;
        goto LABEL_50;
      }
      v136 = 0;
      v10 = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(
              (struct StateRepository::Cache::Manager_NoThrow *)&v109,
              (__int64)v20,
              v13,
              (__int64 *)&v136);
      if ( v10 < 0 )
      {
        v49 = 228;
        goto LABEL_159;
      }
      v50 = v136;
      if ( !v136 )
        goto LABEL_214;
      v113 = (unsigned __int16 **)&v111;
      v117 = 0;
      v111 = 0;
      v114 = 0;
      v115 = 1;
      v10 = SRCacheContext_Open(v109, L"PackageExternalLocation\\Data", 0, &v114);
      if ( v115 )
      {
        v51 = *v113;
        *v113 = v114;
        if ( v51 )
          SRCacheContext_Close(v51);
      }
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x18C,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
          (const char *)(unsigned int)v10,
          (int)v92);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFA,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v10,
          v99);
        goto LABEL_137;
      }
      if ( !v111 )
      {
        v10 = -2140733422;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFB,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)0x80670012LL,
          (int)v92);
        goto LABEL_137;
      }
      v153 = 0;
      memset_0(v154, 0, sizeof(v154));
      v155 = 0;
      v157 = v154;
      v156 = 256;
      v52 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v153, v50);
      v10 = v52;
      if ( v52 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFE,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v52,
          (int)v92);
        goto LABEL_135;
      }
      v113 = (unsigned __int16 **)&v117;
      v114 = 0;
      v115 = 1;
      v10 = SRCacheContext_OpenSubContext(v111, v157, 0, &v114);
      if ( v115 )
      {
        v53 = *v113;
        *v113 = v114;
        if ( v53 )
          SRCacheContext_Close(v53);
      }
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B0,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
          (const char *)(unsigned int)v10,
          (int)v92);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFF,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v10,
          v101);
        goto LABEL_135;
      }
      v54 = v117 != 0;
      v55 = SRCacheContext_AddToCache(v111, L"PackageExternalLocation\\Data");
      v10 = v55;
      if ( v55 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1A6,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
          (const char *)(unsigned int)v55,
          (int)v92);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x101,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v10,
          v102);
LABEL_135:
        v56 = v153;
        v153 = 0;
        if ( v56 )
          SRCache_Free(v56);
LABEL_137:
        v57 = v111;
        v111 = 0;
        if ( v57 )
          SRCacheContext_Close(v57);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA4,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v10,
          v100);
        v58 = v117;
        v117 = 0;
        if ( v58 )
          SRCacheContext_Close(v58);
        if ( v10 < 0 )
        {
LABEL_158:
          v49 = 231;
          goto LABEL_159;
        }
        goto LABEL_214;
      }
      v59 = v153;
      v153 = 0;
      if ( v59 )
        SRCache_Free(v59);
      v60 = v111;
      v111 = 0;
      if ( v60 )
        SRCacheContext_Close(v60);
      v44 = v117;
      if ( !v54 )
      {
        v117 = 0;
        goto LABEL_212;
      }
      v141 = 1;
      v139 = &v121[1];
      v140 = 0;
      v61 = SRCacheContext_GetField_String(v117, L"Path", &v140);
      v10 = v61;
      if ( v61 >= 0 )
        v10 = 0;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x246,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
          (const char *)(unsigned int)v61,
          (int)v92);
      if ( v141 )
      {
        v62 = *v139;
        *v139 = v140;
        if ( v62 )
          SRCache_Free(v62);
      }
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x269,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v10,
          (int)v92);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA9,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v10,
          v103);
        v63 = v117;
        v117 = 0;
        if ( v63 )
          SRCacheContext_Close(v63);
        goto LABEL_158;
      }
      v44 = v117;
      v117 = 0;
      *(_QWORD *)&v120 = v50;
LABEL_212:
      if ( v44 )
        SRCacheContext_Close(v44);
LABEL_214:
      v23 = v121[1];
LABEL_215:
      if ( !v23 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0xD3,
          (unsigned int)"onecore\\base\\AppModel\\Runtime\\Src\\PackagePath.hpp",
          (const char *)0x80070490LL,
          (int)"Package %ls not found",
          (const char *)a2);
        v91 = v121[1];
        v121[1] = 0;
        if ( v91 )
          SRCache_Free(v91);
        if ( v8 )
          RtlFreeHeap(ReservedForLocalUse::g_heap, 0, v8);
        goto LABEL_242;
      }
LABEL_216:
      v81 = -1;
      do
        ++v81;
      while ( v23[v81] );
      v82 = *a4;
      v83 = v81 + 1;
      *a4 = v83;
      if ( (unsigned int)v82 < v83 )
      {
        v84 = v121[1];
        v121[1] = 0;
        if ( v84 )
          SRCache_Free(v84);
        if ( v8 )
          RtlFreeHeap(ReservedForLocalUse::g_heap, 0, v8);
        StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v123);
        v85 = v109;
        v109 = 0;
        if ( v85 )
          SRCacheManager_Close(v85);
        return 2147942522LL;
      }
      v86 = RtlStringCchCopyW(a5, v82, v23);
      if ( v86 < 0 )
      {
        v87 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0xE0,
                (unsigned int)"onecore\\base\\AppModel\\Runtime\\Src\\PackagePath.hpp",
                (const char *)(unsigned int)v86,
                (int)v92);
        v88 = v121[1];
        v10 = v87;
        v121[1] = 0;
        if ( v88 )
          SRCache_Free(v88);
        if ( v8 )
          RtlFreeHeap(ReservedForLocalUse::g_heap, 0, v8);
LABEL_52:
        StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v123);
        v29 = v109;
        v109 = 0;
LABEL_250:
        if ( v29 )
          SRCacheManager_Close(v29);
        return (unsigned int)v10;
      }
      v89 = v121[1];
      v121[1] = 0;
      if ( v89 )
        SRCache_Free(v89);
      if ( v8 )
        RtlFreeHeap(ReservedForLocalUse::g_heap, 0, v8);
      StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v123);
      v90 = v109;
      v109 = 0;
      if ( v90 )
        SRCacheManager_Close(v90);
      return 0;
    case 5:
      if ( v20 )
        goto LABEL_166;
      v10 = StateRepository::Cache::Entity::User_NoThrow::GetByToken(
              (struct StateRepository::Cache::Manager_NoThrow *)&v109,
              0,
              (__int64 *)&v118);
      if ( v10 < 0 )
      {
        v27 = 188;
        goto LABEL_50;
      }
      v20 = v118;
      if ( !v118 )
        goto LABEL_190;
      v13 = v122;
LABEL_166:
      v108 = 0;
      if ( !v13 )
      {
        v10 = -2147024809;
        v64 = 225;
LABEL_185:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v64,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v10,
          (int)v92);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x32,
          (unsigned int)"onecore\\base\\AppModel\\Runtime\\Src\\PackagePath.hpp",
          (const char *)(unsigned int)v10,
          v105);
        v27 = 194;
        goto LABEL_50;
      }
      v137 = 0;
      v10 = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(
              (struct StateRepository::Cache::Manager_NoThrow *)&v109,
              (__int64)v20,
              v13,
              &v137);
      if ( v10 < 0 )
      {
        v64 = 228;
        goto LABEL_185;
      }
      v65 = v137;
      if ( !v137 )
        goto LABEL_189;
      v119 = 0;
      v66 = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(
              (struct StateRepository::Cache::Manager_NoThrow *)&v109,
              v137,
              (struct StateRepository::Cache::Context_NoThrow *)&v119,
              &v108);
      v10 = v66;
      if ( v66 < 0 )
      {
        v67 = (unsigned int)v66;
        v68 = 164;
LABEL_182:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v68,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)v67,
          (int)v92);
        v72 = v119;
        v119 = 0;
        if ( v72 )
          ((void (*)(void))SRCacheContext_Close)();
        v64 = 231;
        goto LABEL_185;
      }
      v69 = v119;
      if ( v108 )
      {
        v143 = 0;
        v142 = &v121[1];
        v144 = 1;
        v70 = SRCacheContext_GetField_String(v119, L"Path", &v143);
        v10 = v70;
        if ( v70 >= 0 )
          v10 = 0;
        else
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x246,
            (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
            (const char *)(unsigned int)v70,
            (int)v92);
        if ( v144 )
        {
          v71 = *v142;
          *v142 = v143;
          if ( v71 )
            ((void (*)(void))SRCache_Free)();
        }
        if ( v10 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x269,
            (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
            (const char *)(unsigned int)v10,
            (int)v92);
          v67 = (unsigned int)v10;
          v68 = 169;
          goto LABEL_182;
        }
        v69 = v119;
        *(_QWORD *)&v120 = v65;
      }
      v119 = 0;
      if ( v69 )
        ((void (*)(void))SRCacheContext_Close)();
LABEL_189:
      v23 = v121[1];
      if ( v121[1] )
        goto LABEL_216;
LABEL_190:
      v108 = 0;
      if ( !v122 )
      {
        v10 = -2147024809;
        v73 = 225;
LABEL_209:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v73,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)(unsigned int)v10,
          (int)v92);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x32,
          (unsigned int)"onecore\\base\\AppModel\\Runtime\\Src\\PackagePath.hpp",
          (const char *)(unsigned int)v10,
          v106);
        v27 = 201;
LABEL_50:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v27,
          (unsigned int)"onecore\\base\\AppModel\\Runtime\\Src\\PackagePath.hpp",
          (const char *)(unsigned int)v10,
          (int)v92);
        v28 = v121[1];
        v121[1] = 0;
        if ( v28 )
          SRCache_Free(v28);
        goto LABEL_52;
      }
      v138 = 0;
      v10 = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(
              (struct StateRepository::Cache::Manager_NoThrow *)&v109,
              0,
              v122,
              &v138);
      if ( v10 < 0 )
      {
        v73 = 228;
        goto LABEL_209;
      }
      v74 = v138;
      if ( !v138 )
        goto LABEL_214;
      P = 0;
      v75 = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(
              (struct StateRepository::Cache::Manager_NoThrow *)&v109,
              v138,
              (struct StateRepository::Cache::Context_NoThrow *)&P,
              &v108);
      v10 = v75;
      if ( v75 < 0 )
      {
        v76 = (unsigned int)v75;
        v77 = 164;
LABEL_206:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v77,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
          (const char *)v76,
          (int)v92);
        v80 = P;
        P = 0;
        if ( v80 )
          ((void (*)(void))SRCacheContext_Close)();
        v73 = 231;
        goto LABEL_209;
      }
      v44 = P;
      if ( v108 )
      {
        v146 = 0;
        v145 = &v121[1];
        v147 = 1;
        v78 = SRCacheContext_GetField_String(P, L"Path", &v146);
        v10 = v78;
        if ( v78 >= 0 )
          v10 = 0;
        else
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x246,
            (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
            (const char *)(unsigned int)v78,
            (int)v92);
        if ( v147 )
        {
          v79 = *v145;
          *v145 = v146;
          if ( v79 )
            ((void (*)(void))SRCache_Free)();
        }
        if ( v10 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x269,
            (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
            (const char *)(unsigned int)v10,
            (int)v92);
          v76 = (unsigned int)v10;
          v77 = 169;
          goto LABEL_206;
        }
        v44 = P;
        *(_QWORD *)&v120 = v74;
      }
      P = 0;
      goto LABEL_212;
    default:
      goto LABEL_246;
  }
}

```

## disassembly

```asm
0x18009df60  mov     [rsp-8+arg_0], rbx
0x18009df65  push    rbp
0x18009df66  push    rsi
0x18009df67  push    rdi
0x18009df68  push    r12
0x18009df6a  push    r13
0x18009df6c  push    r14
0x18009df6e  push    r15
0x18009df70  lea     rbp, [rsp-500h]
0x18009df78  sub     rsp, 600h
0x18009df7f  mov     rax, cs:__security_cookie
0x18009df86  xor     rax, rsp
0x18009df89  mov     [rbp+530h+var_40], rax
0x18009df90  mov     r13, [rbp+530h+arg_20]
0x18009df97  lea     rax, [rsp+630h+var_5E8]
0x18009df9c  mov     r15, rdx
0x18009df9f  mov     [rsp+630h+var_5C8], rax
0x18009dfa4  movzx   esi, cl
0x18009dfa7  movsxd  rdi, r8d
0x18009dfaa  xor     r14d, r14d
0x18009dfad  mov     [rsp+630h+var_5B8], 1
0x18009dfb2  lea     rdx, [rsp+630h+var_5C0]
0x18009dfb7  mov     [rsp+630h+var_5E8], r14
0x18009dfbc  xor     ecx, ecx
0x18009dfbe  mov     [rsp+630h+var_5C0], r14
0x18009dfc3  mov     r12, r9
0x18009dfc6  call    cs:__imp_SRCacheManager_Open
0x18009dfcc  mov     ebx, eax
0x18009dfce  cmp     [rsp+630h+var_5B8], r14b
0x18009dfd3  jz      short loc_18009DFF0
0x18009dfd5  mov     r8, [rsp+630h+var_5C8]
0x18009dfda  mov     rdx, [rsp+630h+var_5C0]
0x18009dfdf  mov     rcx, [r8]
0x18009dfe2  mov     [r8], rdx
0x18009dfe5  test    rcx, rcx
0x18009dfe8  jz      short loc_18009DFF0
0x18009dfea  call    cs:__imp_SRCacheManager_Close
0x18009dff0  test    ebx, ebx
0x18009dff2  jns     short loc_18009E019
0x18009dff4  mov     rcx, [rbp+538h]; this
0x18009dffb  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18009e002  mov     r9d, ebx; char *
0x18009e005  mov     edx, 0A5h; void *
0x18009e00a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009e00f  mov     edx, 49h ; 'I'
0x18009e014  jmp     loc_18009F2B3
0x18009e019  lea     r8, [rbp+530h+var_570]; __int64 *
0x18009e01d  mov     [rbp+530h+var_570], r14
0x18009e021  mov     rdx, r15; unsigned __int16 *
0x18009e024  lea     rcx, [rsp+630h+var_5E8]; struct StateRepository::Cache::Manager_NoThrow *
0x18009e029  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x18009e02e  mov     ebx, eax
0x18009e030  test    eax, eax
0x18009e032  jns     short loc_18009E03E
0x18009e034  mov     edx, 4Bh ; 'K'
0x18009e039  jmp     loc_18009F2B3
0x18009e03e  mov     r10, [rbp+530h+var_570]
0x18009e042  test    r10, r10
0x18009e045  jnz     short loc_18009E09A
0x18009e047  test    r15, r15
0x18009e04a  jz      short loc_18009E090
0x18009e04c  xor     edx, edx; Val
0x18009e04e  lea     rcx, [rbp+530h+var_480]; void *
0x18009e055  mov     r8d, 0F0h; Size
0x18009e05b  call    memset_0
0x18009e060  lea     r9, [rbp+530h+var_480]
0x18009e067  mov     dword ptr [rsp+630h+var_5E0], 0F0h
0x18009e06f  lea     r8, [rsp+630h+var_5E0]
0x18009e074  mov     rcx, r15
0x18009e077  call    ?PackageIdBasicFromFullName@?$Convert@GPEAGPEBGUPACKAGE_ID@@@Identity@ARI@@SAJPEBGIPEAIPEAE@Z; ARI::Identity::Convert<ushort,ushort *,ushort const *,PACKAGE_ID>::PackageIdBasicFromFullName(ushort const *,uint,uint *,uchar *)
0x18009e07c  cmp     eax, 57h ; 'W'
0x18009e07f  jz      short loc_18009E090
0x18009e081  mov     rcx, [rsp+630h+var_5E8]
0x18009e086  mov     [rsp+630h+var_5E8], r14
0x18009e08b  jmp     loc_18009F297
0x18009e090  mov     edx, 4Fh ; 'O'
0x18009e095  jmp     loc_18009F2AE
0x18009e09a  cmp     edi, 5; switch 6 cases
0x18009e09d  ja      def_18009E0B8; jumptable 000000018009E0B8 default case
0x18009e0a3  lea     r8, __ImageBase
0x18009e0aa  mov     rdx, r14
0x18009e0ad  mov     ecx, ds:(jpt_18009E0B8 - 180000000h)[r8+rdi*4]
0x18009e0b5  add     rcx, r8
0x18009e0b8  jmp     rcx; switch jump
0x18009e0ba  mov     edx, 100h; jumptable 000000018009E0B8 case 0
0x18009e0bf  jmp     short loc_18009E0C6; jumptable 000000018009E0B8 cases 2-5
0x18009e0c1  mov     edx, 300h; jumptable 000000018009E0B8 case 1
0x18009e0c6  xorps   xmm0, xmm0; jumptable 000000018009E0B8 cases 2-5
0x18009e0c9  mov     [rbp+530h+var_550], r14
0x18009e0cd  mov     r8, rdx
0x18009e0d0  movdqa  xmmword ptr [rbp+530h+var_560], xmm0
0x18009e0d5  or      r8, 20h
0x18009e0d9  mov     [rbp+530h+var_548], r14
0x18009e0dd  test    sil, sil
0x18009e0e0  mov     [rbp+530h+var_540], r14d
0x18009e0e4  mov     eax, r14d
0x18009e0e7  mov     [rbp+530h+var_538], r14
0x18009e0eb  cmovz   r8, rdx
0x18009e0ef  mov     [rbp+530h+var_53C], eax
0x18009e0f2  mov     [rbp+530h+var_530], r14
0x18009e0f6  mov     [rbp+530h+var_528], r14
0x18009e0fa  movdqa  [rbp+530h+var_520], xmm0
0x18009e0ff  mov     [rbp+530h+var_510], r14d
0x18009e103  mov     [rbp+530h+var_508], r14
0x18009e107  mov     [rbp+530h+var_500], r14
0x18009e10b  test    r8, r8
0x18009e10e  jz      loc_18009E1A6
0x18009e114  mov     [rsp+630h+var_5F0], al
0x18009e118  lea     r9, [rbp+530h+var_560]
0x18009e11c  lea     rax, [rsp+630h+var_5F0]
0x18009e121  mov     rdx, r10
0x18009e124  lea     rcx, [rsp+630h+var_5E8]
0x18009e129  mov     qword ptr [rsp+630h+var_610], rax; int
0x18009e12e  call    ?Get@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x18009e133  mov     ebx, eax
0x18009e135  test    eax, eax
0x18009e137  jns     short loc_18009E162
0x18009e139  mov     rcx, [rbp+538h]; this
0x18009e140  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\AppModel\\Runtime\\Src\\"...
0x18009e147  mov     r9d, eax; char *
0x18009e14a  mov     edx, 71h ; 'q'; void *
0x18009e14f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009e154  lea     rcx, [rbp+530h+var_560]; this
0x18009e158  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18009e15d  jmp     loc_18009F2C9
0x18009e162  cmp     [rsp+630h+var_5F0], r14b
0x18009e167  jnz     short loc_18009E19F
0x18009e169  mov     rcx, [rbp+538h]; this
0x18009e170  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\AppModel\\Runtime\\Src\\"...
0x18009e177  mov     r9d, 80070490h; char *
0x18009e17d  mov     edx, 72h ; 'r'; void *
0x18009e182  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009e187  lea     rcx, [rbp+530h+var_560]; this
0x18009e18b  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18009e190  mov     rcx, [rsp+630h+var_5E8]
0x18009e195  mov     [rsp+630h+var_5E8], r14
0x18009e19a  jmp     loc_18009F297
0x18009e19f  mov     r10, [rbp+530h+var_570]
0x18009e1a3  mov     eax, [rbp+530h+var_53C]
0x18009e1a6  mov     rdx, r14; void *
0x18009e1a9  mov     [rbp+530h+var_5A0], rdx
0x18009e1ad  test    sil, sil
0x18009e1b0  jz      loc_18009E2CB
0x18009e1b6  cmp     eax, 2
0x18009e1b9  jz      loc_18009E2CB
0x18009e1bf  lea     r8, [rbp+530h+var_5A0]; __int64 *
0x18009e1c3  lea     rcx, [rsp+630h+var_5E8]; struct StateRepository::Cache::Manager_NoThrow *
0x18009e1c8  call    ?GetByToken@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByToken(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)
0x18009e1cd  mov     ebx, eax
0x18009e1cf  test    eax, eax
0x18009e1d1  jns     short loc_18009E1FC
0x18009e1d3  mov     rcx, [rbp+538h]; this
0x18009e1da  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\AppModel\\Runtime\\Src\\"...
0x18009e1e1  mov     r9d, eax; char *
0x18009e1e4  mov     edx, 7Fh; void *
0x18009e1e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009e1ee  lea     rcx, [rbp+530h+var_560]; this
0x18009e1f2  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18009e1f7  jmp     loc_18009F2C9
0x18009e1fc  mov     rdx, [rbp+530h+var_5A0]; __int64
0x18009e200  test    rdx, rdx
0x18009e203  jnz     short loc_18009E234
0x18009e205  mov     rcx, [rbp+538h]; this
0x18009e20c  lea     rax, aUnknownUser; "Unknown user"
0x18009e213  mov     r9d, 80070490h; char *
0x18009e219  mov     qword ptr [rsp+630h+var_610], rax; int
0x18009e21e  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\AppModel\\Runtime\\Src\\"...
0x18009e225  mov     edx, 80h; void *
0x18009e22a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18009e22f  jmp     loc_18009E187
0x18009e234  mov     r8, [rbp+530h+var_560]; __int64
0x18009e238  lea     r9, [rsp+630h+var_5F0]; bool *
0x18009e23d  lea     rcx, [rsp+630h+var_5E8]; struct StateRepository::Cache::Manager_NoThrow *
0x18009e242  mov     [rsp+630h+var_5F0], r14b
0x18009e247  call    ?ExistsByUserAndPackage@PackageUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_N@Z; StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,bool &)
0x18009e24c  mov     ebx, eax
0x18009e24e  test    eax, eax
0x18009e250  jns     short loc_18009E27B
0x18009e252  mov     rcx, [rbp+538h]; this
0x18009e259  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\AppModel\\Runtime\\Src\\"...
0x18009e260  mov     r9d, eax; char *
0x18009e263  mov     edx, 82h; void *
0x18009e268  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009e26d  lea     rcx, [rbp+530h+var_560]; this
0x18009e271  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18009e276  jmp     loc_18009F2C9
0x18009e27b  cmp     [rsp+630h+var_5F0], r14b
0x18009e280  jnz     short loc_18009E2C3
0x18009e282  mov     rax, [rbp+530h+var_5A0]
0x18009e286  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\AppModel\\Runtime\\Src\\"...
0x18009e28d  mov     rcx, [rbp+538h]; this
0x18009e294  mov     r9d, 80070490h; char *
0x18009e29a  mov     [rsp+630h+var_600], rax
0x18009e29f  mov     edx, 83h; void *
0x18009e2a4  mov     rax, [rbp+530h+var_560]
0x18009e2a8  mov     [rsp+630h+var_608], rax; char *
0x18009e2ad  lea     rax, aPackageI64xNot; "Package %I64X not registered to user %I"...
0x18009e2b4  mov     qword ptr [rsp+630h+var_610], rax; int
0x18009e2b9  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18009e2be  jmp     loc_18009E187
0x18009e2c3  mov     r10, [rbp+530h+var_570]
0x18009e2c7  mov     rdx, [rbp+530h+var_5A0]; void *
0x18009e2cb  lea     r8, __ImageBase
0x18009e2d2  xor     esi, esi
0x18009e2d4  mov     ecx, ds:(jpt_18009E2F4 - 180000000h)[r8+rdi*4]; switch 6 cases
0x18009e2dc  xorps   xmm0, xmm0
0x18009e2df  xorps   xmm1, xmm1
0x18009e2e2  mov     [rsp+630h+P], rsi
0x18009e2e7  add     rcx, r8
0x18009e2ea  movdqu  [rbp+530h+var_590], xmm0
0x18009e2ef  movdqu  xmmword ptr [rbp+530h+var_580], xmm1
0x18009e2f4  jmp     rcx; switch jump
0x18009e2f6  mov     rbx, [rbp+530h+var_528]; jumptable 000000018009E2F4 case 0
0x18009e2fa  jmp     loc_18009F0FC
0x18009e2ff  mov     rbx, qword ptr [rbp+530h+var_520]; jumptable 000000018009E2F4 case 1
0x18009e303  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GetPackagePathNoMutableDirectoryNotAnError@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GetPackagePathNoMutableDirectoryNotAnError@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GetPackagePathNoMutableDirectoryNotAnError> `wil::Feature<__WilFeatureTraits_Feature_GetPackagePathNoMutableDirectoryNotAnError>::GetImpl(void)'::`2'::impl
0x18009e30a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_GetPackagePathNoMutableDirectoryNotAnError@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GetPackagePathNoMutableDirectoryNotAnError>::__private_IsEnabled(void)
0x18009e30f  test    al, al
0x18009e311  jz      short loc_18009E31F
0x18009e313  cmp     qword ptr [rbp+530h+var_520], rsi
0x18009e317  jnz     loc_18009F0FC
0x18009e31d  jmp     short loc_18009E347
0x18009e31f  cmp     qword ptr [rbp+530h+var_520], rsi
0x18009e323  jnz     loc_18009F0FC
0x18009e329  mov     rcx, [rbp+538h]; this
0x18009e330  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\AppModel\\Runtime\\Src\\"...
0x18009e337  mov     r9d, 80073D5Bh; char *
0x18009e33d  mov     edx, 98h; void *
0x18009e342  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009e347  mov     rcx, [rbp+530h+var_580+8]
0x18009e34b  mov     [rbp+530h+var_580+8], rsi
0x18009e34f  test    rcx, rcx
0x18009e352  jz      short loc_18009E35A
0x18009e354  call    cs:__imp_SRCache_Free
0x18009e35a  lea     rcx, [rbp+530h+var_560]; this
0x18009e35e  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18009e363  mov     rcx, [rsp+630h+var_5E8]
0x18009e368  mov     [rsp+630h+var_5E8], rsi
0x18009e36d  test    rcx, rcx
0x18009e370  jz      short loc_18009E378
0x18009e372  call    cs:__imp_SRCacheManager_Close
0x18009e378  mov     eax, 80073D5Bh
0x18009e37d  jmp     loc_18009F2E0
0x18009e382  test    rdx, rdx; jumptable 000000018009E2F4 case 2
0x18009e385  jnz     short loc_18009E3E9
0x18009e387  lea     r8, [rbp+530h+var_5A0]; __int64 *
0x18009e38b  lea     rcx, [rsp+630h+var_5E8]; struct StateRepository::Cache::Manager_NoThrow *
0x18009e390  call    ?GetByToken@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByToken(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)
0x18009e395  mov     ebx, eax
0x18009e397  test    eax, eax
0x18009e399  jns     short loc_18009E3E1
0x18009e39b  mov     edx, 9Fh; void *
0x18009e3a0  mov     rcx, [rbp+538h]; this
0x18009e3a7  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\AppModel\\Runtime\\Src\\"...
0x18009e3ae  mov     r9d, ebx; char *
0x18009e3b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009e3b6  mov     rcx, [rbp+530h+var_580+8]
0x18009e3ba  mov     [rbp+530h+var_580+8], rsi
0x18009e3be  test    rcx, rcx
0x18009e3c1  jz      short loc_18009E3C9
0x18009e3c3  call    cs:__imp_SRCache_Free
0x18009e3c9  lea     rcx, [rbp+530h+var_560]; this
0x18009e3cd  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18009e3d2  mov     rcx, [rsp+630h+var_5E8]
0x18009e3d7  mov     [rsp+630h+var_5E8], rsi
0x18009e3dc  jmp     loc_18009F2D3
0x18009e3e1  mov     r10, [rbp+530h+var_570]
0x18009e3e5  mov     rdx, [rbp+530h+var_5A0]
0x18009e3e9  lea     r9, [rsp+630h+P]
0x18009e3ee  mov     r8, r10
0x18009e3f1  lea     rcx, [rsp+630h+var_5E8]
0x18009e3f6  call    ?GetEffectiveLocationByUserAndPackage@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@@Z; StateRepository::Cache::Entity::Package_NoThrow::GetEffectiveLocationByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &)
0x18009e3fb  mov     ebx, eax
0x18009e3fd  test    eax, eax
0x18009e3ff  jns     short loc_18009E44D
0x18009e401  mov     rcx, [rbp+538h]; this
0x18009e408  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\AppModel\\Runtime\\Src\\"...
0x18009e40f  mov     r9d, eax; char *
0x18009e412  mov     edx, 0A1h; void *
0x18009e417  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009e41c  mov     rcx, [rbp+530h+var_580+8]
0x18009e420  mov     [rbp+530h+var_580+8], rsi
0x18009e424  test    rcx, rcx
0x18009e427  jz      short loc_18009E42F
0x18009e429  call    cs:__imp_SRCache_Free
0x18009e42f  mov     r8, [rsp+630h+P]; P
0x18009e434  test    r8, r8
0x18009e437  jz      short loc_18009E3C9
0x18009e439  mov     rcx, cs:?g_heap@ReservedForLocalUse@@3PEAXEA; HeapHandle
0x18009e440  xor     edx, edx; Flags
0x18009e442  call    cs:__imp_RtlFreeHeap
0x18009e448  jmp     loc_18009E3C9
0x18009e44d  mov     r14, [rsp+630h+P]
0x18009e452  mov     rbx, r14
0x18009e455  jmp     loc_18009F0FC
0x18009e45a  test    r10, r10; jumptable 000000018009E2F4 case 3
0x18009e45d  jnz     short loc_18009E475
0x18009e45f  mov     ebx, 80070057h
0x18009e464  lea     rdi, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18009e46b  mov     edx, 0E1h
  ... truncated ...
```
