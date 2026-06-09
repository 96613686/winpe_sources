# Container::Manager::Core::Details::ConfigurationBuilder::CreateKryptonContainerConfiguration(_GUID const &,_CMS_VIRTUAL_MACHINE_CONTAINER_PROPERTIES const &,Container::Manager::Hcs::ComputeSystemCreateType,Container::Manager::Core::Details::ContainerConfiguration &)

- ea: `0x1800939a4`
- end: `0x18009475d`
- name: `?CreateKryptonContainerConfiguration@ConfigurationBuilder@Details@Core@Manager@Container@@AEBAJAEBU_GUID@@AEBU_CMS_VIRTUAL_MACHINE_CONTAINER_PROPERTIES@@W4ComputeSystemCreateType@Hcs@45@AEAUContainerConfiguration@2345@@Z`
- size: `3513`
- prototype: `int __fastcall(__int64, _OWORD *, __int64, int, struct Container::Manager::Core::Details::ContainerConfiguration *)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180093474`

## callees

- `0x180004bd0`
- `0x180004fc4`
- `0x1800054a0`
- `0x180005704`
- `0x180006cac`
- `0x180008bf0`
- `0x180008d04`
- `0x18000a10c`
- `0x18000da68`
- `0x18000da88`
- `0x18000dad8`
- `0x180016774`
- `0x18002b800`
- `0x18002db24`
- `0x18002dc8c`
- `0x18002e2b4`
- `0x18008a164`
- `0x18008bf34`
- `0x18008bfc0`
- `0x180092660`
- `0x1800939a4`
- `0x180096b70`
- `0x180096cbc`
- `0x180097598`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x180093b6a`
- `ntdll!NtQuerySystemInformation` at `0x180093b6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180093bfd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180093c11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18009412a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18009413e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180093bfd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180093c11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18009412a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18009413e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180093c3b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180094168`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180093c3b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180094168`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180093c7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800941a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800941ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009437d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009459e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800945d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180094658`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800946dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180094719`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180093c7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800941a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800941ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009437d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009459e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800945d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180094658`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800946dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180094719`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800942cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180094351`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180094576`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180094630`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800942cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180094351`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180094576`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180094630`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180094299`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180094299`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180093a97`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180093a97`

## string_xrefs

- `0x1800939f7`: `onecore\base\gendrv\silos\clem\core\lib\configurationbuilder.cpp`
- `0x180093af2`: `onecore\base\gendrv\silos\clem\core\lib\configurationbuilder.cpp`
- `0x180093baf`: `onecore\base\gendrv\silos\clem\core\lib\configurationbuilder.cpp`
- `0x180093c54`: `onecore\base\gendrv\silos\clem\core\lib\configurationbuilder.cpp`
- `0x180093d24`: `onecore\base\gendrv\silos\clem\core\lib\configurationbuilder.cpp`
- `0x180093de7`: `onecore\base\gendrv\silos\clem\core\lib\configurationbuilder.cpp`
- `0x180093ed8`: `onecore\base\gendrv\silos\clem\core\lib\configurationbuilder.cpp`
- `0x180093fbb`: `onecore\base\gendrv\silos\clem\core\lib\configurationbuilder.cpp`
- `0x18009400e`: `onecore\base\gendrv\silos\clem\core\lib\configurationbuilder.cpp`
- `0x1800940cd`: `onecore\base\gendrv\silos\clem\core\lib\configurationbuilder.cpp`
- `0x180094181`: `onecore\base\gendrv\silos\clem\core\lib\configurationbuilder.cpp`
- `0x180094257`: `onecore\base\gendrv\silos\clem\core\lib\configurationbuilder.cpp`
- `0x1800942b0`: `onecore\base\gendrv\silos\clem\core\lib\configurationbuilder.cpp`
- `0x18009431e`: `onecore\base\gendrv\silos\clem\core\lib\configurationbuilder.cpp`
- `0x180094468`: `onecore\base\gendrv\silos\clem\core\lib\configurationbuilder.cpp`
- `0x18009451b`: `onecore\base\gendrv\silos\clem\core\lib\configurationbuilder.cpp`
- `0x18009469f`: `onecore\base\gendrv\silos\clem\core\lib\configurationbuilder.cpp`
- `0x180094748`: `onecore\base\gendrv\silos\clem\core\lib\configurationbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
int __fastcall Container::Manager::Core::Details::ConfigurationBuilder::CreateKryptonContainerConfiguration(
        __int64 a1,
        _OWORD *a2,
        __int64 a3,
        int a4,
        struct Container::Manager::Core::Details::ContainerConfiguration *a5)
{
  __int64 v9; // rdx
  int v11; // ecx
  int *v12; // rcx
  int v13; // ecx
  Container::Manager::Core::Details *v14; // rcx
  int MaxVirtualProcessorCount; // eax
  int LastError; // ebx
  char v17; // al
  __int64 v18; // rdx
  HANDLE *v19; // rsi
  HANDLE CurrentProcess; // rdi
  void *v21; // rbx
  HANDLE v22; // rax
  const char *v23; // r9
  HANDLE v24; // rcx
  bool v25; // cc
  HANDLE *v26; // rcx
  _WORD *v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rdx
  void *v30; // rcx
  _WORD *v31; // r8
  __int64 v32; // rcx
  _WORD *v33; // rdx
  _DWORD *v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // rdx
  void *v37; // rcx
  unsigned __int64 v38; // rax
  unsigned __int64 v39; // r8
  unsigned __int64 v40; // rax
  unsigned __int64 v41; // rdx
  HANDLE v42; // rcx
  bool v43; // cc
  unsigned __int64 v44; // rbx
  __int64 v45; // rdx
  __int64 v46; // r8
  const char *v47; // r9
  _WORD *v48; // rax
  _WORD *v49; // rcx
  __int64 v50; // rdx
  void **v51; // rbx
  __int64 v52; // rdx
  __int64 v53; // r8
  HANDLE *v54; // rsi
  HANDLE v55; // rbx
  void *v56; // rdi
  HANDLE v57; // rax
  const char *v58; // r9
  HANDLE v59; // rcx
  bool v60; // cc
  HANDLE *v61; // rbx
  int token_information; // eax
  void *v63; // rcx
  void *v64; // rdi
  const char *v65; // r9
  __int64 v66; // rdx
  __int64 v67; // r8
  char *v68; // rcx
  DWORD dwDesiredAccess; // [rsp+20h] [rbp-E0h]
  DWORD dwDesiredAccessa; // [rsp+20h] [rbp-E0h]
  HANDLE hObject; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE v72; // [rsp+48h] [rbp-B8h] BYREF
  void *v73; // [rsp+50h] [rbp-B0h] BYREF
  char *v74; // [rsp+58h] [rbp-A8h]
  _WORD v75[8]; // [rsp+60h] [rbp-A0h] BYREF
  LPWSTR StringSid; // [rsp+70h] [rbp-90h] BYREF
  void *v77[2]; // [rsp+78h] [rbp-88h] BYREF
  _WORD v78[8]; // [rsp+88h] [rbp-78h] BYREF
  void *v79[2]; // [rsp+98h] [rbp-68h] BYREF
  _WORD v80[8]; // [rsp+A8h] [rbp-58h] BYREF
  void *v81[2]; // [rsp+B8h] [rbp-48h] BYREF
  _WORD v82[12]; // [rsp+C8h] [rbp-38h] BYREF
  struct _SYSTEM_INFO SystemInfo; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD v84[4]; // [rsp+110h] [rbp+10h] BYREF
  void *v85[2]; // [rsp+120h] [rbp+20h] BYREF
  _WORD v86[8]; // [rsp+130h] [rbp+30h] BYREF
  void *v87[2]; // [rsp+140h] [rbp+40h] BYREF
  _WORD v88[16]; // [rsp+150h] [rbp+50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  *((_DWORD *)a5 + 22) = 1;
  if ( *(_DWORD *)a3 < 0x100u )
  {
    v9 = 500;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\configurationbuilder.cpp",
      (const char *)0x80070057LL,
      dwDesiredAccess);
    return -2147024809;
  }
  v11 = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 124LL);
  *((_DWORD *)a5 + 68) = v11;
  if ( v11 || (v11 = *(_DWORD *)a3) != 0 )
  {
    if ( (v11 & 1) != 0 )
      v11 = v11 - (v11 & 1) + 2;
  }
  else
  {
    v11 = 2;
  }
  *((_DWORD *)a5 + 68) = v11;
  v12 = *(int **)(a3 + 8);
  if ( v12 )
  {
    v13 = *v12;
    *((_DWORD *)a5 + 76) = v13;
    *((_BYTE *)a5 + 308) = 1;
    *(_WORD *)((char *)a5 + 309) = *(_WORD *)((char *)&SystemInfo.dwPageSize + 1);
    *((_BYTE *)a5 + 311) = HIBYTE(SystemInfo.dwPageSize);
    if ( !v13
      || (memset(&SystemInfo, 0, sizeof(SystemInfo)), GetSystemInfo(&SystemInfo), *((_BYTE *)a5 + 308))
      && *((_DWORD *)a5 + 76) > SystemInfo.dwNumberOfProcessors )
    {
      v9 = 535;
      goto LABEL_3;
    }
  }
  else
  {
    LODWORD(v72) = 0;
    v14 = (Container::Manager::Core::Details *)(*(_DWORD *)(*(_QWORD *)(a1 + 8) + 96LL) >> 18);
    LOBYTE(v14) = (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 96LL) & 0x40000) != 0;
    MaxVirtualProcessorCount = Container::Manager::Core::Details::GetMaxVirtualProcessorCount(
                                 v14,
                                 (bool)&v72,
                                 (unsigned int *)a3);
    LastError = MaxVirtualProcessorCount;
    if ( MaxVirtualProcessorCount < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x221,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\configurationbuilder.cpp",
        (const char *)(unsigned int)MaxVirtualProcessorCount,
        dwDesiredAccess);
      return LastError;
    }
    *((_DWORD *)a5 + 76) = (_DWORD)v72;
    *((_BYTE *)a5 + 308) = 1;
    *(_WORD *)((char *)a5 + 309) = *(_WORD *)((char *)&SystemInfo.dwPageSize + 1);
    *((_BYTE *)a5 + 311) = HIBYTE(SystemInfo.dwPageSize);
  }
  *((_DWORD *)a5 + 23) |= 0x78u;
  if ( a4 == 1 )
  {
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_KryptonSoftLargePages>::__private_GetVariant(`wil::Feature<__WilFeatureTraits_Feature_KryptonSoftLargePages>::GetImpl'::`2'::impl)
      || (memset(&SystemInfo, 0, 24),
          NtQuerySystemInformation(SystemPrefetcherInformation|0x80, &SystemInfo, 0x18u, 0) < 0)
      || (v17 = 1,
          *(_QWORD *)&SystemInfo.dwOemId >> 20 < (unsigned __int64)*(unsigned int *)(*(_QWORD *)(a1 + 8) + 104LL)) )
    {
      v17 = 0;
    }
    if ( v17 )
      *((_DWORD *)a5 + 23) |= 2u;
  }
  if ( (*(_BYTE *)(a3 + 16) & 1) != 0 )
  {
    if ( a4 != 1 )
    {
      v18 = 580;
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v18,
               (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\configurationbuilder.cpp",
               (const char *)0x32,
               dwDesiredAccess);
    }
    *((_DWORD *)a5 + 23) |= 1u;
  }
  if ( (*(_BYTE *)(a3 + 16) & 2) != 0 )
  {
    if ( a4 != 1 )
    {
      v18 = 594;
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v18,
               (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\configurationbuilder.cpp",
               (const char *)0x32,
               dwDesiredAccess);
    }
    *((_DWORD *)a5 + 23) |= 4u;
  }
  hObject = 0;
  v19 = (HANDLE *)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(&hObject);
  CurrentProcess = GetCurrentProcess();
  v21 = *(void **)(a3 + 24);
  v22 = GetCurrentProcess();
  if ( !DuplicateHandle(v22, v21, CurrentProcess, v19, 2u, 0, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x261,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\configurationbuilder.cpp",
                  v23);
    v24 = hObject;
    v25 = (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
    goto LABEL_37;
  }
  v26 = (HANDLE *)((char *)a5 + 160);
  if ( *((_BYTE *)a5 + 168) )
  {
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      v26,
      &hObject);
  }
  else
  {
    *v26 = hObject;
    hObject = 0;
    *((_BYTE *)a5 + 168) = 1;
  }
  v73 = v75;
  v74 = (char *)v75;
  v75[0] = 0;
  v27 = *(_WORD **)(a3 + 32);
  if ( v27 )
  {
    if ( !*v27 || (*(_BYTE *)(a3 + 16) & 8) != 0 )
    {
      v36 = 621;
LABEL_62:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v36,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\configurationbuilder.cpp",
        (const char *)0x80070057LL,
        dwDesiredAccessa);
      v37 = v73;
      if ( v73 == v75 )
        goto LABEL_201;
LABEL_200:
      operator delete(v37, (const struct std::nothrow_t *)&std::nothrow);
LABEL_201:
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      return -2147024809;
    }
    v28 = -1;
    do
      ++v28;
    while ( v27[v28] );
    *(_QWORD *)&SystemInfo.dwOemId = *(_QWORD *)(a3 + 32);
    SystemInfo.lpMinimumApplicationAddress = (LPVOID)v28;
    LastError = Container::Manager::Core::Details::ConfigurationBuilder::SanitizeName(&SystemInfo, 0, &v73);
    if ( LastError < 0 )
    {
      v29 = 627;
      goto LABEL_49;
    }
    v31 = *(_WORD **)(a3 + 32);
    v32 = -1;
    do
      ++v32;
    while ( v31[v32] );
    v33 = v73;
    if ( v32 != (v74 - (_BYTE *)v73) >> 1 )
    {
LABEL_61:
      v36 = 631;
      goto LABEL_62;
    }
    if ( v32 )
    {
      while ( *v33 == *v31 )
      {
        ++v33;
        ++v31;
        if ( !--v32 )
          goto LABEL_58;
      }
      goto LABEL_61;
    }
  }
  else if ( (*(_BYTE *)(a3 + 16) & 8) == 0 )
  {
    *(_QWORD *)&SystemInfo.dwOemId = *((_QWORD *)a5 + 5);
    SystemInfo.lpMinimumApplicationAddress = (LPVOID)((__int64)(*((_QWORD *)a5 + 6) - *(_QWORD *)&SystemInfo.dwOemId) >> 1);
    LastError = Container::Manager::Core::Details::ConfigurationBuilder::SanitizeName(&SystemInfo, 0, &v73);
    if ( LastError < 0 )
    {
      v29 = 646;
LABEL_49:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v29,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\configurationbuilder.cpp",
        (const char *)(unsigned int)LastError,
        dwDesiredAccessa);
      v30 = v73;
      if ( v73 == v75 )
      {
LABEL_51:
        v24 = hObject;
        v25 = (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
LABEL_37:
        if ( v25 )
          CloseHandle(v24);
        return LastError;
      }
LABEL_50:
      operator delete(v30, (const struct std::nothrow_t *)&std::nothrow);
      goto LABEL_51;
    }
  }
LABEL_58:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
    (char *)a5 + 408,
    &v73);
  v34 = *(_DWORD **)(a3 + 40);
  if ( v34 )
  {
    if ( !*v34 )
    {
      v35 = 657;
      goto LABEL_199;
    }
    v38 = (__int64)(*((_QWORD *)a5 + 37) - *((_QWORD *)a5 + 35)) >> 5;
    v39 = (unsigned int)*v34;
    if ( v39 > v38 )
    {
      v40 = 7 * (v38 >> 2) + 8;
      v41 = (unsigned int)v39;
      if ( v40 >= v39 )
        v41 = v40;
      if ( v41 > 0x3FFFFFFFFFFFFFFLL )
        v41 = 0x3FFFFFFFFFFFFFFLL;
      if ( v39 > v41
        || !(unsigned __int8)utl::vector<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::_SetCapacity((char *)a5 + 280) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x295,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\configurationbuilder.cpp",
          (const char *)0x8007000ELL,
          dwDesiredAccessa);
LABEL_77:
        if ( v73 != v75 )
          operator delete(v73, (const struct std::nothrow_t *)&std::nothrow);
        v42 = hObject;
        v43 = (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
LABEL_179:
        if ( v43 )
          CloseHandle(v42);
        return -2147024882;
      }
      v34 = *(_DWORD **)(a3 + 40);
    }
    if ( *v34 )
    {
      v44 = 0;
      while ( *(_QWORD *)&v34[2 * v44 + 2] )
      {
        v79[0] = v80;
        v79[1] = v80;
        v80[0] = 0;
        v45 = *(_QWORD *)&v34[2 * v44 + 2];
        if ( v45 )
        {
          v46 = -1;
          do
            ++v46;
          while ( *(_WORD *)(v45 + 2 * v46) );
        }
        else
        {
          v46 = 0;
        }
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                 v79,
                                 v45,
                                 v46) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2A1,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\configurationbuilder.cpp",
            (const char *)0x8007000ELL,
            dwDesiredAccessa);
          v48 = v80;
          v49 = v79[0];
          goto LABEL_95;
        }
        if ( !(unsigned __int8)utl::vector<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::emplace_back<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,0>(
                                 (char *)a5 + 280,
                                 v79) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x2A5,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\configurationbuilder.cpp",
            v47);
        if ( v79[0] != v80 )
          operator delete(v79[0], (const struct std::nothrow_t *)&std::nothrow);
        ++v44;
        v34 = *(_DWORD **)(a3 + 40);
        if ( v44 >= (unsigned int)*v34 )
          goto LABEL_98;
      }
      v35 = 668;
LABEL_199:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v35,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\configurationbuilder.cpp",
        (const char *)0x80070057LL,
        dwDesiredAccessa);
      v37 = v73;
      if ( v73 == v75 )
        goto LABEL_201;
      goto LABEL_200;
    }
  }
LABEL_98:
  LastError = Container::Manager::Core::Details::ConfigurationBuilder::SetupHvSocketConfigurationIfNecessary(
                *(struct _HV_SOCKET_SYSTEM_CONFIG **)(a3 + 48),
                a5);
  if ( LastError < 0 )
  {
    v50 = 683;
LABEL_100:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v50,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\configurationbuilder.cpp",
      (const char *)(unsigned int)LastError,
      dwDesiredAccessa);
    goto LABEL_101;
  }
  if ( (*(_BYTE *)(a3 + 56) & 1) != 0 )
  {
    v51 = (void **)((char *)a5 + 112);
    if ( *((_BYTE *)a5 + 152)
      && *((_BYTE *)a5 + 144)
      && *((struct Container::Manager::Core::Details::ContainerConfiguration **)a5 + 14) != (struct Container::Manager::Core::Details::ContainerConfiguration *)((char *)a5 + 128) )
    {
      operator delete(*v51, (const struct std::nothrow_t *)&std::nothrow);
    }
    *(_OWORD *)v51 = 0;
    *((_OWORD *)a5 + 8) = 0;
    *((_QWORD *)a5 + 18) = 0;
    *((_BYTE *)a5 + 144) = 0;
    *((_BYTE *)a5 + 152) = 1;
    v52 = *(_QWORD *)(a3 + 64);
    if ( v52 )
    {
      v81[0] = v82;
      v81[1] = v82;
      v82[0] = 0;
      v53 = -1;
      do
        ++v53;
      while ( *(_WORD *)(v52 + 2 * v53) );
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               v81,
                               v52,
                               v53) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2B6,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\configurationbuilder.cpp",
          (const char *)0x8007000ELL,
          dwDesiredAccessa);
        v48 = v82;
        v49 = v81[0];
LABEL_95:
        if ( v49 != v48 )
          operator delete(v49, (const struct std::nothrow_t *)&std::nothrow);
        goto LABEL_77;
      }
      utl::optional<Csl::Path>::operator=<Csl::Path,0>((char *)a5 + 112, v81);
      if ( v81[0] != v82 )
        operator delete(v81[0], (const struct std::nothrow_t *)&std::nothrow);
    }
  }
  else if ( *(_QWORD *)(a3 + 64) )
  {
    v35 = 702;
    goto LABEL_199;
  }
  if ( (*(_BYTE *)(a3 + 56) & 2) != 0 )
  {
    v72 = 0;
    v54 = (HANDLE *)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(&v72);
    v55 = GetCurrentProcess();
    v56 = *(void **)(a3 + 24);
    v57 = GetCurrentProcess();
    if ( !DuplicateHandle(v57, v56, v55, v54, 0, 0, 2u) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x2CC,
                    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\configurationbuilder.cpp",
                    v58);
      v59 = v72;
      v60 = (char *)v72 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
      goto LABEL_118;
    }
    v61 = (HANDLE *)((char *)a5 + 240);
    if ( *((_BYTE *)a5 + 248) )
    {
      if ( (char *)*v61 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(*v61);
      *((_BYTE *)a5 + 248) = 0;
    }
    *((GUID *)a5 + 14) = GUID_NULL;
    *v61 = 0;
    *((_BYTE *)a5 + 248) = 1;
    *((_OWORD *)a5 + 14) = *a2;
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      (char *)a5 + 240,
      &v72);
    *(_QWORD *)&SystemInfo.dwOemId = 0;
    token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&SystemInfo, *((_QWORD *)a5 + 30));
    LastError = token_information;
    if ( token_information < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D8,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\configurationbuilder.cpp",
        (const char *)(unsigned int)token_information,
        dwDesiredAccessa);
      v63 = *(void **)&SystemInfo.dwOemId;
      if ( !*(_QWORD *)&SystemInfo.dwOemId )
      {
LABEL_129:
        v59 = v72;
        v60 = (char *)v72 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
LABEL_118:
        if ( v60 )
          CloseHandle(v59);
LABEL_101:
        v30 = v73;
        if ( v73 == v75 )
          goto LABEL_51;
        goto LABEL_50;
      }
LABEL_128:
      operator delete(v63);
      goto LABEL_129;
    }
    StringSid = 0;
    v64 = *(void **)&SystemInfo.dwOemId;
    if ( !ConvertSidToStringSidW(**(PSID **)&SystemInfo.dwOemId, &StringSid) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x2DB,
                    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\configurationbuilder.cpp",
                    v65);
      if ( StringSid )
        LocalFree(StringSid);
      if ( !v64 )
        goto LABEL_129;
      v63 = v64;
      goto LABEL_128;
    }
    v77[0] = v78;
    v77[1] = v78;
    v78[0] = 0;
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             v77,
                             L"D:P(A;;FA;;;SY)(A;;FA;;;BA)(A;;FA;;;S-1-15-3-3)(A;;FA;;;",
                             56) )
    {
      v66 = 737;
LABEL_137:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v66,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\configurationbuilder.cpp",
        (const char *)0x8007000ELL,
        dwDesiredAccessa);
LABEL_138:
      if ( v77[0] != v78 )
        operator delete(v77[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( StringSid )
        LocalFree(StringSid);
      if ( v64 )
        operator delete(v64);
      if ( (char *)v72 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(v72);
      goto LABEL_77;
    }
    if ( StringSid )
    {
      v67 = -1;
      do
        ++v67;
      while ( StringSid[v67] );
    }
    else
    {
      v67 = 0;
    }
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v77,
                             StringSid,
                             v67) )
    {
      v66 = 738;
      goto LABEL_137;
    }
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v77,
                             L")",
                             1) )
    {
      v66 = 739;
      goto LABEL_137;
    }
    v85[0] = v86;
    v85[1] = v86;
    v86[0] = 0;
    v87[0] = v88;
    v87[1] = v88;
    v88[0] = 0;
    v84[0] = -1411906840;
    v84[1] = 1087569868;
    v84[2] = 1274081701;
    v84[3] = -926215651;
    v88[8] = 0;
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
      v85,
      v77);
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             v87,
                             L"D:P(D;;FA;;;WD)",
                             15) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2EE,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\configurationbuilder.cpp",
        (const char *)0x8007000ELL,
        dwDesiredAccessa);
      if ( v87[0] != v88 )
        operator delete(v87[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v85[0] != v86 )
        operator delete(v85[0], (const struct std::nothrow_t *)&std::nothrow);
      goto LABEL_138;
    }
    if ( *((_BYTE *)a5 + 400) )
    {
      v68 = (char *)a5 + 376;
    }
    else
    {
      memset_0((char *)a5 + 312, 0, 0x58u);
      *((_QWORD *)a5 + 39) = (char *)a5 + 328;
      *((_QWORD *)a5 + 40) = (char *)a5 + 328;
      *((_QWORD *)a5 + 43) = (char *)a5 + 360;
      *((_QWORD *)a5 + 44) = (char *)a5 + 360;
      v68 = (char *)a5 + 376;
      *((_QWORD *)a5 + 47) = -1;
      *((_QWORD *)a5 + 48) = -1;
      *((_QWORD *)a5 + 49) = -1;
      *((_BYTE *)a5 + 400) = 1;
    }
    if ( !(unsigned __int8)utl::vector<Container::Manager::Hcs::HvSocketServiceConfig,utl::allocator<Container::Manager::Hcs::HvSocketServiceConfig>>::emplace_back<Container::Manager::Hcs::HvSocketServiceConfig,0>(
                             v68,
                             v84) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2F7,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\configurationbuilder.cpp",
        (const char *)0x8007000ELL,
        dwDesiredAccessa);
      if ( v87[0] != v88 )
        operator delete(v87[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v85[0] != v86 )
        operator delete(v85[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v77[0] != v78 )
        operator delete(v77[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( StringSid )
        LocalFree(StringSid);
      if ( v64 )
        operator delete(v64);
      if ( (char *)v72 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(v72);
      if ( v73 != v75 )
        operator delete(v73, (const struct std::nothrow_t *)&std::nothrow);
      v42 = hObject;
      v43 = (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
      goto LABEL_179;
    }
    if ( v87[0] != v88 )
      operator delete(v87[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v85[0] != v86 )
      operator delete(v85[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v77[0] != v78 )
      operator delete(v77[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( StringSid )
      LocalFree(StringSid);
    if ( v64 )
      operator delete(v64);
    if ( (char *)v72 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(v72);
  }
  LastError = Container::Manager::Core::Details::ConfigurationBuilder::ConvertGpuConfiguration(
                (const struct _CMS_GPU_CONFIGURATION *)(a3 + 72),
                (struct Container::Manager::Core::Details::ContainerConfiguration *)((char *)a5 + 216));
  if ( LastError < 0 )
  {
    v50 = 764;
    goto LABEL_100;
  }
  if ( (*(_BYTE *)(a3 + 16) & 4) != 0 )
  {
    if ( !*((_DWORD *)a5 + 54) )
    {
      v35 = 772;
      goto LABEL_199;
    }
    *((_DWORD *)a5 + 23) |= 0x80u;
  }
  if ( v73 != v75 )
    operator delete(v73, (const struct std::nothrow_t *)&std::nothrow);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return 0;
}

```

## disassembly

```asm
0x1800939a4  push    rbp
0x1800939a6  push    rbx
0x1800939a7  push    rsi
0x1800939a8  push    rdi
0x1800939a9  push    r12
0x1800939ab  push    r13
0x1800939ad  push    r14
0x1800939af  push    r15
0x1800939b1  lea     rbp, [rsp-88h]
0x1800939b9  sub     rsp, 188h
0x1800939c0  mov     rax, cs:__security_cookie
0x1800939c7  xor     rax, rsp
0x1800939ca  mov     [rbp+0C0h+var_50], rax
0x1800939ce  mov     edi, r9d
0x1800939d1  mov     r12, r8
0x1800939d4  mov     r13, rdx
0x1800939d7  mov     rsi, rcx
0x1800939da  mov     r15, [rbp+0C0h+arg_20]
0x1800939e1  mov     dword ptr [r15+58h], 1
0x1800939e9  cmp     dword ptr [r8], 100h
0x1800939f0  jnb     short loc_180093A1A
0x1800939f2  mov     edx, 1F4h; void *
0x1800939f7  lea     r8, aOnecoreBaseGen_55; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800939fe  mov     r9d, 80070057h; char *
0x180093a04  mov     rcx, [rbp+0C8h]; this
0x180093a0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180093a10  mov     eax, 80070057h
0x180093a15  jmp     loc_180094727
0x180093a1a  mov     rax, [rcx+8]
0x180093a1e  mov     ecx, [rax+7Ch]
0x180093a21  mov     [r15+110h], ecx
0x180093a28  xor     r14d, r14d
0x180093a2b  test    ecx, ecx
0x180093a2d  jnz     short loc_180093A3C
0x180093a2f  mov     ecx, [r8]
0x180093a32  test    ecx, ecx
0x180093a34  jnz     short loc_180093A3C
0x180093a36  lea     ecx, [r14+2]
0x180093a3a  jmp     short loc_180093A48
0x180093a3c  mov     eax, ecx
0x180093a3e  and     eax, 1
0x180093a41  jz      short loc_180093A48
0x180093a43  sub     ecx, eax
0x180093a45  add     ecx, 2
0x180093a48  mov     [r15+110h], ecx
0x180093a4f  mov     rcx, [r8+8]
0x180093a53  test    rcx, rcx
0x180093a56  jz      short loc_180093AC6
0x180093a58  mov     ecx, [rcx]
0x180093a5a  mov     [r15+130h], ecx
0x180093a61  mov     byte ptr [r15+134h], 1
0x180093a69  movzx   eax, word ptr [rbp+0C0h+SystemInfo.dwPageSize+1]
0x180093a6d  mov     [r15+135h], ax
0x180093a75  mov     al, byte ptr [rbp+0C0h+SystemInfo.dwPageSize+3]
0x180093a78  mov     [r15+137h], al
0x180093a7f  cmp     ecx, 1
0x180093a82  jb      short loc_180093ABC
0x180093a84  xorps   xmm0, xmm0
0x180093a87  movups  xmmword ptr [rbp-20h], xmm0
0x180093a8b  movups  xmmword ptr [rbp+0C0h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180093a8f  movups  xmmword ptr [rbp+0C0h+SystemInfo.dwNumberOfProcessors], xmm0
0x180093a93  lea     rcx, [rbp+0C0h+SystemInfo]; lpSystemInfo
0x180093a97  call    cs:__imp_GetSystemInfo
0x180093a9e  nop     dword ptr [rax+rax+00h]
0x180093aa3  cmp     [r15+134h], r14b
0x180093aaa  jz      loc_180093B33
0x180093ab0  mov     eax, [rbp+0C0h+SystemInfo.dwNumberOfProcessors]
0x180093ab3  cmp     [r15+130h], eax
0x180093aba  jbe     short loc_180093B33
0x180093abc  mov     edx, 217h
0x180093ac1  jmp     loc_1800939F7
0x180093ac6  mov     dword ptr [rsp+1C0h+var_178], r14d
0x180093acb  mov     rcx, [rsi+8]
0x180093acf  mov     ecx, [rcx+60h]
0x180093ad2  shr     ecx, 12h
0x180093ad5  and     cl, 1; this
0x180093ad8  lea     rdx, [rsp+1C0h+var_178]; bool
0x180093add  call    ?GetMaxVirtualProcessorCount@Details@Core@Manager@Container@@YAJ_NAEAK@Z; Container::Manager::Core::Details::GetMaxVirtualProcessorCount(bool,ulong &)
0x180093ae2  mov     ebx, eax
0x180093ae4  test    eax, eax
0x180093ae6  jns     short loc_180093B0A
0x180093ae8  mov     rcx, [rbp+0C8h]; this
0x180093aef  mov     r9d, eax; char *
0x180093af2  lea     r8, aOnecoreBaseGen_55; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180093af9  mov     edx, 221h; void *
0x180093afe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180093b03  mov     eax, ebx
0x180093b05  jmp     loc_180094727
0x180093b0a  mov     eax, dword ptr [rsp+1C0h+var_178]
0x180093b0e  mov     [r15+130h], eax
0x180093b15  mov     byte ptr [r15+134h], 1
0x180093b1d  movzx   eax, word ptr [rbp+0C0h+SystemInfo.dwPageSize+1]
0x180093b21  mov     [r15+135h], ax
0x180093b29  mov     al, byte ptr [rbp+0C0h+SystemInfo.dwPageSize+3]
0x180093b2c  mov     [r15+137h], al
0x180093b33  or      dword ptr [r15+5Ch], 78h
0x180093b38  cmp     edi, 1
0x180093b3b  jnz     short loc_180093B9D
0x180093b3d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_KryptonSoftLargePages@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_KryptonSoftLargePages@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_KryptonSoftLargePages> `wil::Feature<__WilFeatureTraits_Feature_KryptonSoftLargePages>::GetImpl(void)'::`2'::impl
0x180093b44  call    ?__private_GetVariant@?$FeatureImpl@U__WilFeatureTraits_Feature_KryptonSoftLargePages@@@details@wil@@QEAA?AW4Variant_KryptonSoftLargePages@@W4VariantReportingKind@3@_N@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_KryptonSoftLargePages>::__private_GetVariant(wil::VariantReportingKind,bool)
0x180093b49  test    al, al
0x180093b4b  jz      short loc_180093B91
0x180093b4d  xorps   xmm0, xmm0
0x180093b50  xor     eax, eax
0x180093b52  movups  xmmword ptr [rbp+0C0h+SystemInfo], xmm0
0x180093b56  mov     [rbp+0C0h+SystemInfo.lpMaximumApplicationAddress], rax
0x180093b5a  xor     r9d, r9d; ReturnLength
0x180093b5d  lea     r8d, [rdi+17h]; SystemInformationLength
0x180093b61  lea     rdx, [rbp+0C0h+SystemInfo]; SystemInformation
0x180093b65  mov     ecx, 0B8h; SystemInformationClass
0x180093b6a  call    cs:__imp_NtQuerySystemInformation
0x180093b71  nop     dword ptr [rax+rax+00h]
0x180093b76  test    eax, eax
0x180093b78  js      short loc_180093B91
0x180093b7a  mov     rdx, qword ptr [rbp+0C0h+SystemInfo]
0x180093b7e  shr     rdx, 14h
0x180093b82  mov     rax, [rsi+8]
0x180093b86  mov     ecx, [rax+68h]
0x180093b89  cmp     rdx, rcx
0x180093b8c  mov     al, dil
0x180093b8f  jnb     short loc_180093B94
0x180093b91  mov     al, r14b
0x180093b94  test    al, al
0x180093b96  jz      short loc_180093B9D
0x180093b98  or      dword ptr [r15+5Ch], 2
0x180093b9d  test    byte ptr [r12+10h], 1
0x180093ba3  jz      short loc_180093BD2
0x180093ba5  cmp     edi, 1
0x180093ba8  jz      short loc_180093BCD
0x180093baa  mov     edx, 244h; void *
0x180093baf  lea     r8, aOnecoreBaseGen_55; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180093bb6  mov     r9d, 32h ; '2'; char *
0x180093bbc  mov     rcx, [rbp+0C8h]; this
0x180093bc3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180093bc8  jmp     loc_180094727
0x180093bcd  or      dword ptr [r15+5Ch], 1
0x180093bd2  test    byte ptr [r12+10h], 2
0x180093bd8  jz      short loc_180093BEB
0x180093bda  cmp     edi, 1
0x180093bdd  jz      short loc_180093BE6
0x180093bdf  mov     edx, 252h
0x180093be4  jmp     short loc_180093BAF
0x180093be6  or      dword ptr [r15+5Ch], 4
0x180093beb  mov     [rsp+1C0h+hObject], r14
0x180093bf0  lea     rcx, [rsp+1C0h+hObject]
0x180093bf5  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x180093bfa  mov     rsi, rax
0x180093bfd  call    cs:__imp_GetCurrentProcess
0x180093c04  nop     dword ptr [rax+rax+00h]
0x180093c09  mov     rdi, rax
0x180093c0c  mov     rbx, [r12+18h]
0x180093c11  call    cs:__imp_GetCurrentProcess
0x180093c18  nop     dword ptr [rax+rax+00h]
0x180093c1d  mov     [rsp+1C0h+dwOptions], r14d; dwOptions
0x180093c22  mov     [rsp+1C0h+bInheritHandle], r14d; bInheritHandle
0x180093c27  mov     [rsp+1C0h+dwDesiredAccess], 2; int
0x180093c2f  mov     r9, rsi; lpTargetHandle
0x180093c32  mov     r8, rdi; hTargetProcessHandle
0x180093c35  mov     rdx, rbx; hSourceHandle
0x180093c38  mov     rcx, rax; hSourceProcessHandle
0x180093c3b  call    cs:__imp_DuplicateHandle
0x180093c42  nop     dword ptr [rax+rax+00h]
0x180093c47  xor     esi, esi
0x180093c49  test    eax, eax
0x180093c4b  jnz     short loc_180093C8B
0x180093c4d  mov     rcx, [rbp+0C8h]; this
0x180093c54  lea     r8, aOnecoreBaseGen_55; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180093c5b  mov     edx, 261h; void *
0x180093c60  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180093c65  mov     ebx, eax
0x180093c67  mov     rcx, [rsp+1C0h+hObject]; hObject
0x180093c6c  lea     rdx, [rcx-1]
0x180093c70  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180093c74  ja      loc_180093B03
0x180093c7a  call    cs:__imp_CloseHandle
0x180093c81  nop     dword ptr [rax+rax+00h]
0x180093c86  jmp     loc_180093B03
0x180093c8b  lea     rcx, [r15+0A0h]
0x180093c92  cmp     [rcx+8], sil
0x180093c96  jz      short loc_180093CA4
0x180093c98  lea     rdx, [rsp+1C0h+hObject]
0x180093c9d  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180093ca2  jmp     short loc_180093CB5
0x180093ca4  mov     rax, [rsp+1C0h+hObject]
0x180093ca9  mov     [rcx], rax
0x180093cac  mov     [rsp+1C0h+hObject], rsi
0x180093cb1  mov     byte ptr [rcx+8], 1
0x180093cb5  lea     rax, [rsp+1C0h+var_160]
0x180093cba  mov     [rsp+1C0h+var_170], rax
0x180093cbf  lea     rax, [rsp+1C0h+var_160]
0x180093cc4  mov     [rsp+1C0h+var_168], rax
0x180093cc9  mov     [rsp+1C0h+var_160], si
0x180093cce  mov     rcx, [r12+20h]
0x180093cd3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180093cd7  test    rcx, rcx
0x180093cda  jz      loc_180093E26
0x180093ce0  cmp     [rcx], si
0x180093ce3  jz      loc_180093E1F
0x180093ce9  test    byte ptr [r12+10h], 8
0x180093cef  jnz     loc_180093E1F
0x180093cf5  mov     rax, rdi
0x180093cf8  inc     rax
0x180093cfb  cmp     [rcx+rax*2], si
0x180093cff  jnz     short loc_180093CF8
0x180093d01  mov     qword ptr [rbp+0C0h+SystemInfo], rcx
0x180093d05  mov     [rbp+0C0h+SystemInfo.lpMinimumApplicationAddress], rax
0x180093d09  lea     r8, [rsp+1C0h+var_170]
0x180093d0e  xor     edx, edx
0x180093d10  lea     rcx, [rbp+0C0h+SystemInfo]
0x180093d14  call    ?SanitizeName@ConfigurationBuilder@Details@Core@Manager@Container@@CAJV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@_NAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@7@@Z; Container::Manager::Core::Details::ConfigurationBuilder::SanitizeName(utl::basic_string_view<ushort,utl::char_traits<ushort>>,bool,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x180093d19  mov     ebx, eax
0x180093d1b  test    eax, eax
0x180093d1d  jns     short loc_180093D67
0x180093d1f  mov     edx, 273h; void *
0x180093d24  lea     r8, aOnecoreBaseGen_55; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180093d2b  mov     r9d, ebx; char *
0x180093d2e  mov     rcx, [rbp+0C8h]; this
0x180093d35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180093d3a  lea     rax, [rsp+1C0h+var_160]
0x180093d3f  mov     rcx, [rsp+1C0h+var_170]; void *
0x180093d44  cmp     rcx, rax
0x180093d47  jz      short loc_180093D55
0x180093d49  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180093d50  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180093d55  mov     rcx, [rsp+1C0h+hObject]
0x180093d5a  lea     rax, [rcx-1]
0x180093d5e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180093d62  jmp     loc_180093C74
0x180093d67  mov     r8, [r12+20h]
0x180093d6c  mov     rcx, rdi
0x180093d6f  inc     rcx
0x180093d72  cmp     [r8+rcx*2], si
0x180093d77  jnz     short loc_180093D6F
0x180093d79  mov     rax, [rsp+1C0h+var_168]
0x180093d7e  mov     rdx, [rsp+1C0h+var_170]
0x180093d83  sub     rax, rdx
0x180093d86  sar     rax, 1
0x180093d89  cmp     rcx, rax
0x180093d8c  jnz     short loc_180093DE2
0x180093d8e  test    rcx, rcx
0x180093d91  jz      short loc_180093DAA
0x180093d93  movzx   eax, word ptr [r8]
0x180093d97  cmp     [rdx], ax
0x180093d9a  jnz     short loc_180093DE2
0x180093d9c  add     rdx, 2
0x180093da0  add     r8, 2
0x180093da4  sub     rcx, 1
0x180093da8  jnz     short loc_180093D93
0x180093daa  lea     rcx, [r15+198h]
0x180093db1  lea     rdx, [rsp+1C0h+var_170]
0x180093db6  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x180093dbb  mov     rcx, [r12+28h]
0x180093dc0  lea     r14, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180093dc7  test    rcx, rcx
0x180093dca  jz      loc_180093FF6
0x180093dd0  cmp     [rcx], esi
0x180093dd2  jnz     loc_180093E6C
0x180093dd8  mov     edx, 291h
0x180093ddd  jmp     loc_180094699
0x180093de2  mov     edx, 277h; void *
0x180093de7  lea     r8, aOnecoreBaseGen_55; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180093dee  mov     r9d, 80070057h; char *
0x180093df4  mov     rcx, [rbp+0C8h]; this
0x180093dfb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180093e00  lea     rax, [rsp+1C0h+var_160]
0x180093e05  mov     rcx, [rsp+1C0h+var_170]
0x180093e0a  cmp     rcx, rax
0x180093e0d  jz      loc_1800946C9
0x180093e13  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180093e1a  jmp     loc_1800946C4
0x180093e1f  mov     edx, 26Dh
0x180093e24  jmp     short loc_180093DE7
0x180093e26  test    byte ptr [r12+10h], 8
0x180093e2c  jnz     loc_180093DAA
0x180093e32  mov     rax, [r15+28h]
0x180093e36  mov     qword ptr [rbp+0C0h+SystemInfo], rax
0x180093e3a  mov     rcx, [r15+30h]
0x180093e3e  sub     rcx, rax
0x180093e41  sar     rcx, 1
0x180093e44  mov     [rbp+0C0h+SystemInfo.lpMinimumApplicationAddress], rcx
0x180093e48  lea     r8, [rsp+1C0h+var_170]
0x180093e4d  xor     edx, edx
0x180093e4f  lea     rcx, [rbp+0C0h+SystemInfo]
0x180093e53  call    ?SanitizeName@ConfigurationBuilder@Details@Core@Manager@Container@@CAJV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@_NAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@7@@Z; Container::Manager::Core::Details::ConfigurationBuilder::SanitizeName(utl::basic_string_view<ushort,utl::char_traits<ushort>>,bool,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x180093e58  mov     ebx, eax
0x180093e5a  test    eax, eax
0x180093e5c  jns     loc_180093DAA
0x180093e62  mov     edx, 286h
0x180093e67  jmp     loc_180093D24
0x180093e6c  lea     rsi, [r15+118h]
0x180093e73  mov     rax, [rsi+10h]
0x180093e77  sub     rax, [rsi]
0x180093e7a  sar     rax, 5
0x180093e7e  mov     r8d, [rcx]
0x180093e81  cmp     r8, rax
0x180093e84  jbe     loc_180093F12
0x180093e8a  shr     rax, 2
0x180093e8e  imul    rax, 7
0x180093e92  add     rax, 8
0x180093e96  mov     edx, r8d
  ... truncated ...
```
