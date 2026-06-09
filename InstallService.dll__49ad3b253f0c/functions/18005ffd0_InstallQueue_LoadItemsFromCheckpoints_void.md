# InstallQueue::_LoadItemsFromCheckpoints(void)

- ea: `0x18005ffd0`
- end: `0x180060f70`
- name: `?_LoadItemsFromCheckpoints@InstallQueue@@QEAA?AV?$vector@V?$ComPtr@VInstallItem@Internal@WindowsUpdate@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VInstallItem@Internal@WindowsUpdate@@@WRL@Microsoft@@@std@@@std@@XZ`
- size: `4000`
- prototype: `unsigned __int16 ***__fastcall(HSTRING, unsigned __int16 ***)`
- caller_count: `1`
- callee_count: `42`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18005fa9c`

## callees

- `0x180009ea0`
- `0x18000ab24`
- `0x18000ad30`
- `0x1800101f4`
- `0x18001bf24`
- `0x18001ddb0`
- `0x18001f784`
- `0x180020960`
- `0x1800225e4`
- `0x180028cd4`
- `0x18002c310`
- `0x18002ec2c`
- `0x18002f214`
- `0x180031d3c`
- `0x180032184`
- `0x1800321d4`
- `0x1800325b4`
- `0x1800375c0`
- `0x18004615c`
- `0x18004e44c`
- `0x18004ec88`
- `0x18004f67c`
- `0x18004fa8c`
- `0x18004ffc4`
- `0x1800514d8`
- `0x180051750`
- `0x180052268`
- `0x180052494`
- `0x180056c60`
- `0x180058a54`
- `0x18005b8fc`
- `0x18005becc`
- `0x18005c000`
- `0x18005ffd0`
- `0x180062e20`
- `0x180069a84`
- `0x18006f0b0`
- `0x1800d7528`
- `0x1800d7808`
- `0x1800d7b64`
- `0x1800db5cc`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060440`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006087f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060440`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006087f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800601a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006097b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800601a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006097b`

## string_xrefs

- `0x18006021a`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x180060353`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x1800603a0`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x180060426`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x180060545`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x18006057c`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x180060651`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x18006068c`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x1800606c7`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x180060702`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x180060745`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x180060783`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x180060965`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x180060ebb`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x180060ed0`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x180060ee5`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=35 #try_helpers=1
unsigned __int16 ***__fastcall InstallQueue::_LoadItemsFromCheckpoints(HSTRING a1, unsigned __int16 ***a2)
{
  int v3; // esi
  HSTRING *v4; // r15
  HSTRING *v5; // rax
  const unsigned __int16 *StringRawBuffer; // rax
  int v7; // eax
  unsigned int v8; // esi
  unsigned int v9; // r13d
  unsigned int v10; // edx
  int v11; // eax
  int v12; // eax
  __int64 v13; // rbx
  __int64 v14; // rcx
  int v15; // eax
  char *v16; // rbx
  __int64 v17; // rcx
  int v18; // eax
  int v19; // eax
  struct Windows::Storage::Streams::IBuffer *v20; // r12
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  __int64 v28; // rax
  __int64 v29; // rdx
  const unsigned __int16 *v30; // rax
  __int64 *v31; // rbx
  __int64 v32; // rsi
  __int64 (__fastcall *v33)(__int64, HSTRING *); // rdi
  int v34; // eax
  int v35; // edx
  __int64 v36; // r9
  __int64 v37; // r9
  __int64 v38; // rax
  __int64 v39; // rdi
  __int64 v40; // rsi
  __int64 v41; // r14
  __int64 v42; // r15
  __int64 v43; // r12
  __int64 v44; // r13
  int v45; // eax
  int v46; // eax
  int i; // eax
  unsigned __int16 *v48; // rdi
  __int64 v49; // rcx
  __int64 v50; // rdi
  int v51; // esi
  int v52; // eax
  int v53; // eax
  unsigned __int16 ***v54; // rdi
  unsigned __int16 **v55; // rdx
  __int64 **v56; // rcx
  __int64 *j; // rax
  __int64 *k; // rcx
  int v60; // [rsp+20h] [rbp-3E8h]
  unsigned __int16 **v61; // [rsp+28h] [rbp-3E0h]
  unsigned __int16 **v62; // [rsp+30h] [rbp-3D8h]
  unsigned __int16 **v63; // [rsp+38h] [rbp-3D0h]
  struct Windows::Storage::Streams::IBuffer **v64; // [rsp+40h] [rbp-3C8h]
  int v65; // [rsp+50h] [rbp-3B8h]
  int v66; // [rsp+58h] [rbp-3B0h]
  HSTRING v67; // [rsp+70h] [rbp-398h] BYREF
  int v68; // [rsp+78h] [rbp-390h]
  struct Windows::Storage::Streams::IBuffer *v69; // [rsp+80h] [rbp-388h] BYREF
  HSTRING v70; // [rsp+88h] [rbp-380h] BYREF
  unsigned __int16 *v71; // [rsp+90h] [rbp-378h] BYREF
  HSTRING string; // [rsp+98h] [rbp-370h] BYREF
  struct WindowsUpdate::Internal::IFulfillmentDataInfo *v73; // [rsp+A0h] [rbp-368h] BYREF
  HSTRING v74; // [rsp+A8h] [rbp-360h] BYREF
  HSTRING v75; // [rsp+B0h] [rbp-358h] BYREF
  unsigned __int16 *v76; // [rsp+B8h] [rbp-350h] BYREF
  HSTRING v77; // [rsp+C0h] [rbp-348h] BYREF
  HSTRING v78; // [rsp+C8h] [rbp-340h] BYREF
  char *v79; // [rsp+D0h] [rbp-338h] BYREF
  int v80[2]; // [rsp+D8h] [rbp-330h] BYREF
  int v81; // [rsp+E0h] [rbp-328h]
  HSTRING *v82; // [rsp+E8h] [rbp-320h] BYREF
  unsigned __int16 ***v83; // [rsp+F0h] [rbp-318h]
  _QWORD v84[2]; // [rsp+F8h] [rbp-310h] BYREF
  unsigned __int16 **v85; // [rsp+108h] [rbp-300h] BYREF
  unsigned __int16 *v86; // [rsp+110h] [rbp-2F8h] BYREF
  __int64 v87; // [rsp+118h] [rbp-2F0h] BYREF
  HSTRING v88; // [rsp+120h] [rbp-2E8h]
  HSTRING v89; // [rsp+128h] [rbp-2E0h] BYREF
  int v90; // [rsp+130h] [rbp-2D8h]
  __int64 v91; // [rsp+138h] [rbp-2D0h] BYREF
  Microsoft::WRL::Wrappers::HString *v92; // [rsp+140h] [rbp-2C8h] BYREF
  HSTRING *v93; // [rsp+148h] [rbp-2C0h]
  __int64 v94; // [rsp+150h] [rbp-2B8h]
  unsigned __int16 ***v95; // [rsp+158h] [rbp-2B0h]
  unsigned __int16 **v96; // [rsp+160h] [rbp-2A8h] BYREF
  unsigned __int16 *v97; // [rsp+168h] [rbp-2A0h] BYREF
  char v98; // [rsp+170h] [rbp-298h]
  HSTRING *v99; // [rsp+178h] [rbp-290h] BYREF
  unsigned __int16 *v100; // [rsp+180h] [rbp-288h] BYREF
  char v101; // [rsp+188h] [rbp-280h]
  HSTRING *v102; // [rsp+190h] [rbp-278h] BYREF
  unsigned __int16 *v103; // [rsp+198h] [rbp-270h] BYREF
  char v104; // [rsp+1A0h] [rbp-268h]
  HSTRING *v105; // [rsp+1A8h] [rbp-260h] BYREF
  unsigned __int16 *v106; // [rsp+1B0h] [rbp-258h] BYREF
  char v107; // [rsp+1B8h] [rbp-250h]
  HSTRING *v108; // [rsp+1C0h] [rbp-248h] BYREF
  unsigned __int16 *v109; // [rsp+1C8h] [rbp-240h] BYREF
  char v110; // [rsp+1D0h] [rbp-238h]
  _OWORD v111[4]; // [rsp+1E0h] [rbp-228h] BYREF
  __int64 v112; // [rsp+220h] [rbp-1E8h]
  unsigned int v113; // [rsp+270h] [rbp-198h] BYREF
  unsigned int v114; // [rsp+274h] [rbp-194h]
  int v115; // [rsp+278h] [rbp-190h]
  int v116; // [rsp+27Ch] [rbp-18Ch]
  int v117; // [rsp+280h] [rbp-188h]
  unsigned int v118; // [rsp+284h] [rbp-184h]
  unsigned int v119; // [rsp+288h] [rbp-180h]
  unsigned int v120; // [rsp+28Ch] [rbp-17Ch]
  __int64 v121; // [rsp+290h] [rbp-178h]
  __int64 v122; // [rsp+298h] [rbp-170h]
  __int64 v123; // [rsp+2A0h] [rbp-168h]
  _BYTE v124[135]; // [rsp+2A9h] [rbp-15Fh] BYREF
  _BYTE v125[160]; // [rsp+330h] [rbp-D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+408h] [rbp+0h]

  v83 = a2;
  v88 = a1;
  *(_QWORD *)v80 = a1;
  v95 = a2;
  v3 = 1;
  v68 = 1;
  v81 = 1;
  GetCheckpoints(&v92);
  v84[0] = 0;
  v84[1] = 0;
  std::_Tree_std::_Tmap_traits_Microsoft::WRL::Wrappers::HString_std::unique_ptr__InstallQueue::_LoadItemsFromCheckpoints_::_2_::WorkData_std::default_delete__InstallQueue::_LoadItemsFromCheckpoints_::_2_::WorkData____std::less_Microsoft::WRL::Wrappers::HString__std::allocator_std::pair_Microsoft::WRL::Wrappers::HString_const__std::unique_ptr__InstallQueue::_LoadItemsFromCheckpoints_::_2_::WorkData_std::default_delete__InstallQueue::_LoadItemsFromCheckpoints_::_2_::WorkData________0___::_Alloc_sentinel_and_proxy(v84);
  v4 = (HSTRING *)v92;
  v5 = v93;
  v74 = (HSTRING)v93;
  while ( 1 )
  {
    v82 = v4;
    if ( v4 == v5 )
      break;
    v71 = 0;
    v76 = 0;
    v75 = 0;
    v70 = 0;
    v78 = 0;
    v77 = 0;
    v69 = 0;
    memset_0(&v113, 0, 0xC0u);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v69);
    v85 = &v76;
    v86 = 0;
    LOBYTE(v87) = 1;
    v108 = &v75;
    v109 = 0;
    v110 = 1;
    v105 = &v78;
    v106 = 0;
    v107 = 1;
    v102 = &v70;
    v103 = 0;
    v104 = 1;
    v99 = &v77;
    v100 = 0;
    v101 = 1;
    v96 = &v71;
    v97 = 0;
    v98 = 1;
    StringRawBuffer = WindowsGetStringRawBuffer(*v4, 0);
    v7 = LoadCheckpointData(
           StringRawBuffer,
           (struct CheckpointData *)&v113,
           &v97,
           &v100,
           &v103,
           &v106,
           &v109,
           &v86,
           &v69);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6D1,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
        (const char *)(unsigned int)v7,
        v60);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v96);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v99);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v102);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v105);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v108);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v85);
    v8 = v114;
    if ( v114 - 4 <= 1 )
    {
      v30 = WindowsGetStringRawBuffer(*v4, 0);
      DeleteCheckpoint(v30);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v69);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v77);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v78);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v70);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v75);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v76);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v71);
      v3 = v68;
      v5 = (HSTRING *)v74;
      goto LABEL_53;
    }
    v9 = v113;
    if ( v113 > 4 || v114 > 0xE )
    {
      v10 = v119;
LABEL_51:
      v65 = v118;
      LODWORD(v64) = v120;
      LODWORD(v63) = v10;
      LODWORD(v62) = v8;
      LODWORD(v61) = v9;
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x6EB,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
        (const char *)0xD,
        (unsigned int)"Invalid checkpoint data: type = %u, state = %u, pct = %u, dloadpct = %u, cv = %hs, hresult = 0x%08x",
        (const char *)v61,
        v62,
        v63,
        v64,
        v124,
        v65);
    }
    v10 = v119;
    if ( v119 > 0x64 || v120 > 0x64 || StringHelpers::IsStringNullOrEmpty(v76) )
      goto LABEL_51;
    if ( !v118 )
      goto LABEL_14;
    if ( v8 != 12 )
    {
      if ( v8 != 2 )
        goto LABEL_51;
LABEL_14:
      if ( v8 - 9 <= 2 )
        goto LABEL_51;
    }
    CorrelationVector::ValidateAndCreate(v125, v124);
    v73 = 0;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v73);
    v11 = WindowsUpdate::Internal::FulfillmentDataInfo::Deserialize(v71, &v73);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6F1,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
        (const char *)(unsigned int)v11,
        v60);
    string = 0;
    v79 = (char *)v75;
    v12 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&string, &v79);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6F4,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
        (const char *)(unsigned int)v12,
        v60);
    std::_Tree_std::_Tmap_traits_Microsoft::WRL::Wrappers::HString_std::unique_ptr__InstallQueue::_LoadItemsFromCheckpoints_::_2_::WorkData_std::default_delete__InstallQueue::_LoadItemsFromCheckpoints_::_2_::WorkData____std::less_Microsoft::WRL::Wrappers::HString__std::allocator_std::pair_Microsoft::WRL::Wrappers::HString_const__std::unique_ptr__InstallQueue::_LoadItemsFromCheckpoints_::_2_::WorkData_std::default_delete__InstallQueue::_LoadItemsFromCheckpoints_::_2_::WorkData________0___::_Find_lower_bound_Microsoft::WRL::Wrappers::HString_(
      v84,
      &v85,
      &string);
    v13 = v87;
    if ( !(unsigned __int8)std::_Tree_std::_Tmap_traits_Microsoft::WRL::Wrappers::HString_std::unique_ptr__InstallQueue::_LoadItemsFromCheckpoints_::_2_::WorkData_std::default_delete__InstallQueue::_LoadItemsFromCheckpoints_::_2_::WorkData____std::less_Microsoft::WRL::Wrappers::HString__std::allocator_std::pair_Microsoft::WRL::Wrappers::HString_const__std::unique_ptr__InstallQueue::_LoadItemsFromCheckpoints_::_2_::WorkData_std::default_delete__InstallQueue::_LoadItemsFromCheckpoints_::_2_::WorkData________0___::_Lower_bound_duplicate_Microsoft::WRL::Wrappers::HString_(
                             v14,
                             v87,
                             &string)
      || v13 == v84[0] )
    {
      v16 = (char *)operator new(0x90u);
      memset_0(v16 + 16, 0, 0x50u);
      *(_QWORD *)v16 = 0;
      *((_QWORD *)v16 + 1) = 0;
      *((_QWORD *)v16 + 12) = 0;
      *((_QWORD *)v16 + 13) = 0;
      *((_QWORD *)v16 + 14) = 0;
      *((_QWORD *)v16 + 15) = 0;
      *((_QWORD *)v16 + 16) = 0;
      *((_QWORD *)v16 + 17) = 0;
      v79 = v16;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(v16);
      v18 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<WindowsUpdate::Internal::IFulfillmentDataInfo,Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>(
              v17,
              v16);
      if ( v18 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6FE,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
          (const char *)(unsigned int)v18,
          v60);
      v19 = (*(__int64 (__fastcall **)(_QWORD, struct WindowsUpdate::Internal::IFulfillmentDataInfo *))(**(_QWORD **)v16 + 104LL))(
              *(_QWORD *)v16,
              v73);
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6FF,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
          (const char *)(unsigned int)v19,
          v60);
      v20 = v69;
      if ( *((struct Windows::Storage::Streams::IBuffer **)v16 + 1) != v69 )
      {
        if ( v69 )
          (*(void (__fastcall **)(struct Windows::Storage::Streams::IBuffer *))(*(_QWORD *)v69 + 8LL))(v69);
        v67 = (HSTRING)*((_QWORD *)v16 + 1);
        *((_QWORD *)v16 + 1) = v20;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v67);
      }
      memset_0(v111, 0, 0x48u);
      *((_OWORD *)v16 + 1) = v111[0];
      *((_OWORD *)v16 + 2) = v111[1];
      *((_OWORD *)v16 + 3) = v111[2];
      *((_OWORD *)v16 + 4) = v111[3];
      *((_QWORD *)v16 + 10) = v112;
      *((_DWORD *)v16 + 22) = v9;
      *((_DWORD *)v16 + 23) = v115;
      v67 = v70;
      v21 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(v16 + 96, &v67);
      if ( v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x704,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
          (const char *)(unsigned int)v21,
          v60);
      v67 = v78;
      v22 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(v16 + 104, &v67);
      if ( v22 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x705,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
          (const char *)(unsigned int)v22,
          v60);
      v67 = v77;
      v23 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(v16 + 112, &v67);
      if ( v23 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x706,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
          (const char *)(unsigned int)v23,
          v60);
      v67 = v75;
      v24 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(v16 + 120, &v67);
      if ( v24 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x707,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
          (const char *)(unsigned int)v24,
          v60);
      v67 = CorrelationVector::hstring((CorrelationVector *)v125);
      v25 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)v16 + 16, &v67);
      if ( v25 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x708,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
          (const char *)(unsigned int)v25,
          v60);
      v67 = (HSTRING)v76;
      v26 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(v16 + 136, &v67);
      if ( v26 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x709,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
          (const char *)(unsigned int)v26,
          v60);
      *((_DWORD *)v16 + 5) = v8;
      *((_QWORD *)v16 + 3) = v121;
      *((_QWORD *)v16 + 4) = v122;
      *((_QWORD *)v16 + 5) = v123;
      *((_DWORD *)v16 + 12) = v119;
      *((_DWORD *)v16 + 13) = v120;
      *((_QWORD *)v16 + 7) = v118;
      v16[72] = (v115 & 0x10000000) != 0;
      *((_DWORD *)v16 + 16) = v116;
      *((_DWORD *)v16 + 17) = v117;
      v16[84] = v115 < 0;
      if ( (v115 & 0x20000000) != 0 )
        v27 = ((v115 & 0x40000000) != 0) + 1;
      else
        v27 = 0;
      *((_DWORD *)v16 + 19) = v27;
      v28 = *(_QWORD *)std::map_Microsoft::WRL::Wrappers::HString_std::unique_ptr__InstallQueue::_LoadItemsFromCheckpoints_::_2_::WorkData_std::default_delete__InstallQueue::_LoadItemsFromCheckpoints_::_2_::WorkData____std::less_Microsoft::WRL::Wrappers::HString__std::allocator_std::pair_Microsoft::WRL::Wrappers::HString_const__std::unique_ptr__InstallQueue::_LoadItemsFromCheckpoints_::_2_::WorkData_std::default_delete__InstallQueue::_LoadItemsFromCheckpoints_::_2_::WorkData_________::_Try_emplace_Microsoft::WRL::Wrappers::HString_(
                         v84,
                         &v89,
                         &string);
      v79 = 0;
      v29 = *(_QWORD *)(v28 + 40);
      *(_QWORD *)(v28 + 40) = v16;
      if ( v29 )
        std::default_delete__InstallQueue::_LoadItemsFromCheckpoints_::_2_::WorkData_::operator()();
      std::unique_ptr__InstallQueue::_LoadItemsFromCheckpoints_::_2_::WorkData_std::default_delete__InstallQueue::_LoadItemsFromCheckpoints_::_2_::WorkData___::_unique_ptr__InstallQueue::_LoadItemsFromCheckpoints_::_2_::WorkData_std::default_delete__InstallQueue::_LoadItemsFromCheckpoints_::_2_::WorkData___(&v79);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v73);
      CorrelationVector::~CorrelationVector((CorrelationVector *)v125);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v69);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v77);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v78);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v70);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v75);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v76);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v71);
      v3 = v68;
      v5 = (HSTRING *)v74;
    }
    else
    {
      v15 = (*(__int64 (__fastcall **)(_QWORD, struct WindowsUpdate::Internal::IFulfillmentDataInfo *))(***(_QWORD ***)(v13 + 40) + 104LL))(
              **(_QWORD **)(v13 + 40),
              v73);
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6F9,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
          (const char *)(unsigned int)v15,
          v60);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v73);
      CorrelationVector::~CorrelationVector((CorrelationVector *)v125);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v69);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v77);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v78);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v70);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v75);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v76);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v71);
      v3 = v68;
      v5 = (HSTRING *)v74;
    }
LABEL_53:
    ++v4;
  }
  std::vector<ChainedInstallServiceWork::SubTaskCheckpointData>::vector<ChainedInstallServiceWork::SubTaskCheckpointData>(a2);
  v81 = v3 | 1;
  v31 = *(__int64 **)v84[0];
  while ( !*((_BYTE *)v31 + 25) )
  {
    v74 = 0;
    v70 = 0;
    v32 = *(_QWORD *)v31[5];
    v33 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v32 + 64LL);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v70);
    v34 = v33(v32, &v70);
    if ( v34 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x72D,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
        (const char *)(unsigned int)v34,
        v60);
    CallerContext::Deserialize(v111, *(_QWORD *)(v31[5] + 136));
    v36 = v31[5];
    if ( *(_DWORD *)(v36 + 20) == 12
      && Utils::IsUserCredentialError((Utils *)*(unsigned int *)(v36 + 56), v35)
      && CallerContext::IsUserLoggedIn((CallerContext *)v111) )
    {
      *(_DWORD *)(v37 + 20) = 0;
      *(_QWORD *)(v31[5] + 56) = 0;
    }
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v74);
    v38 = v31[5];
    v39 = *(_QWORD *)(v38 + 128);
    v40 = *(_QWORD *)(v38 + 8);
    v41 = *(_QWORD *)(v38 + 112);
    v42 = *(_QWORD *)(v38 + 104);
    v43 = *(_QWORD *)(v38 + 96);
    v44 = v38 + 16;
    *(_QWORD *)v80 = *(_QWORD *)(v38 + 120);
    LODWORD(v69) = *(_DWORD *)(v38 + 92);
    LODWORD(string) = *(_DWORD *)(v38 + 88);
    v67 = v70;
    v45 = CallerContext::copy(v111, v125);
    v46 = RestoreInstallWork(
            v45,
            (_DWORD)v67,
            (_DWORD)string,
            (_DWORD)v69,
            v80[0],
            v44,
            v43,
            v42,
            v41,
            v40,
            v39,
            (__int64)&v74);
    if ( v46 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x749,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
        (const char *)(unsigned int)v46,
        v60);
    CallerContext::~CallerContext((CallerContext *)v125);
    LODWORD(v69) = 0;
    *(_QWORD *)v80 = v70;
    v89 = v70;
    v90 = 0;
    v91 = 0;
    wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::UI::Notifications::ToastNotification *>,wil::err_exception_policy>::end(
      v80,
      &v85);
    for ( i = v90; i != (_DWORD)v86; i = ++v90 )
    {
      v48 = *(unsigned __int16 **)wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::Application *>,wil::err_exception_policy>::vector_iterator::operator*(&v89);
      v79 = (char *)v48;
      if ( v48 )
        (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v48 + 8LL))(v48);
      v49 = v31[5];
      *(_QWORD *)v80 = v49 + 16;
      v67 = *(HSTRING *)(v49 + 112);
      v82 = *(HSTRING **)(v49 + 104);
      v78 = *(HSTRING *)(v49 + 96);
      v77 = v74;
      v76 = v48;
      v50 = v49 + 92;
      v51 = v49 + 88;
      v52 = CallerContext::copy(v111, v125);
      v75 = v88;
      wil::MakeOrThrow<WindowsUpdate::Internal::InstallItem,InstallQueue *,CallerContext,enum WindowsUpdate::Internal::InstallType &,unsigned long &,WindowsUpdate::Internal::IFulfillmentDataInfo *,WindowsUpdate::Internal::IInstallWork *,unsigned int &,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,WindowsUpdate::Internal::InstallWorkStatus *,bool>(
        (unsigned int)&v71,
        (unsigned int)&v75,
        v52,
        v51,
        v50,
        (__int64)&v76,
        (__int64)&v77,
        (__int64)&v69,
        (__int64)&v78,
        (__int64)&v82,
        (__int64)&v67,
        v66,
        (__int64)v80);
      CallerContext::~CallerContext((CallerContext *)v125);
      LODWORD(v69) = (_DWORD)v69 + 1;
      LODWORD(v73) = 0;
      v53 = (*(__int64 (__fastcall **)(unsigned __int16 *, struct WindowsUpdate::Internal::IFulfillmentDataInfo **))(*(_QWORD *)v71 + 64LL))(
              v71,
              &v73);
      if ( v53 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x75E,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
          (const char *)(unsigned int)v53,
          v60);
      if ( (unsigned int)((_DWORD)v73 - 4) > 1 )
      {
        v54 = v83;
        v55 = v83[1];
        if ( v55 == v83[2] )
        {
          std::vector<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::InstallItem>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::InstallItem> const &>(
            v83,
            v55,
            &v71);
        }
        else
        {
          *v55 = v71;
          Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(v55);
          ++v54[1];
        }
      }
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v71);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v79);
    }
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v87);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v91);
    CallerContext::~CallerContext((CallerContext *)v111);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v70);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v74);
    v56 = (__int64 **)v31[2];
    if ( *((_BYTE *)v56 + 25) )
    {
      for ( j = (__int64 *)v31[1]; !*((_BYTE *)j + 25) && v31 == (__int64 *)j[2]; j = (__int64 *)j[1] )
        v31 = j;
      v31 = j;
    }
    else
    {
      v31 = (__int64 *)v31[2];
      for ( k = *v56; !*((_BYTE *)k + 25); k = (__int64 *)*k )
        v31 = k;
    }
  }
  std::_Tree_std::_Tmap_traits_Microsoft::WRL::Wrappers::HString_std::unique_ptr__InstallQueue::_LoadItemsFromCheckpoints_::_2_::WorkData_std::default_delete__InstallQueue::_LoadItemsFromCheckpoints_::_2_::WorkData____std::less_Microsoft::WRL::Wrappers::HString__std::allocator_std::pair_Microsoft::WRL::Wrappers::HString_const__std::unique_ptr__InstallQueue::_LoadItemsFromCheckpoints_::_2_::WorkData_std::default_delete__InstallQueue::_LoadItemsFromCheckpoints_::_2_::WorkData________0___::__Tree_std::_Tmap_traits_Microsoft::WRL::Wrappers::HString_std::unique_ptr__InstallQueue::_LoadItemsFromCheckpoints_::_2_::WorkData_std::default_delete__InstallQueue::_LoadItemsFromCheckpoints_::_2_::WorkData____std::less_Microsoft::WRL::Wrappers::HString__std::allocator_std::pair_Microsoft::WRL::Wrappers::HString_const__std::unique_ptr__InstallQueue::_LoadItemsFromCheckpoints_::_2_::WorkData_std::default_delete__InstallQueue::_LoadItemsFromCheckpoints_::_2_::WorkData________0___(v84);
  if ( v92 )
  {
    std::_Destroy_range<std::allocator<Microsoft::WRL::Wrappers::HString>>(v92);
    std::_Deallocate<16>(v92, (v94 - (_QWORD)v92) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  return v83;
}

```

## disassembly

```asm
0x18005ffd0  mov     r11, rsp
0x18005ffd3  mov     [r11+18h], rbx
0x18005ffd7  mov     [r11+20h], rsi
0x18005ffdb  push    rdi
0x18005ffdc  push    r12
0x18005ffde  push    r13
0x18005ffe0  push    r14
0x18005ffe2  push    r15
0x18005ffe4  sub     rsp, 3E0h
0x18005ffeb  mov     rax, cs:__security_cookie
0x18005fff2  xor     rax, rsp
0x18005fff5  mov     [rsp+408h+var_38], rax
0x18005fffd  mov     rdi, rdx
0x180060000  mov     [r11-318h], rdx
0x180060007  mov     [rsp+408h+var_2E8], rcx
0x18006000f  mov     qword ptr [rsp+408h+var_330], rcx
0x180060017  mov     [r11-2B0h], rdx
0x18006001e  mov     esi, 1
0x180060023  mov     [rsp+408h+var_390], esi
0x180060027  mov     [rsp+408h+var_328], esi
0x18006002e  lea     rcx, [r11-2C8h]; void *
0x180060035  call    ?GetCheckpoints@@YA?AV?$vector@VHString@Wrappers@WRL@Microsoft@@V?$allocator@VHString@Wrappers@WRL@Microsoft@@@std@@@std@@XZ; GetCheckpoints(void)
0x18006003a  nop
0x18006003b  xor     r14d, r14d
0x18006003e  mov     [rsp+408h+var_310], r14
0x180060046  mov     [rsp+408h+var_308], r14
0x18006004e  lea     rcx, [rsp+408h+var_310]
0x180060056  call    std___Tree_std___Tmap_traits_Microsoft__WRL__Wrappers__HString_std__unique_ptr__InstallQueue___LoadItemsFromCheckpoints____2___WorkData_std__default_delete__InstallQueue___LoadItemsFromCheckpoints____2___WorkData____std__less_Microsoft__WRL__Wrappers__HString__std__allocator_std__pair_Microsoft__WRL__Wrappers__HString_const__std__unique_ptr__InstallQueue___LoadItemsFromCheckpoints____2___WorkData_std__default_delete__InstallQueue___LoadItemsFromCheckpoints____2___WorkData________0______Alloc_sentinel_and_proxy
0x18006005b  nop
0x18006005c  mov     r15, [rsp+408h+var_2C8]
0x180060064  mov     rax, [rsp+408h+var_2C0]
0x18006006c  mov     [rsp+408h+var_360], rax
0x180060074  mov     [rsp+408h+var_320], r15
0x18006007c  cmp     r15, rax
0x18006007f  jz      loc_180060A41
0x180060085  mov     [rsp+408h+var_378], r14
0x18006008d  mov     [rsp+408h+var_350], r14
0x180060095  mov     [rsp+408h+var_358], r14
0x18006009d  mov     [rsp+408h+var_380], r14
0x1800600a5  mov     [rsp+408h+var_340], r14
0x1800600ad  mov     [rsp+408h+var_348], r14
0x1800600b5  mov     [rsp+408h+var_388], r14
0x1800600bd  xor     edx, edx; Val
0x1800600bf  mov     r8d, 0C0h; Size
0x1800600c5  lea     rcx, [rsp+408h+var_198]; void *
0x1800600cd  call    memset_0
0x1800600d2  lea     rcx, [rsp+408h+var_388]
0x1800600da  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800600df  lea     rax, [rsp+408h+var_350]
0x1800600e7  mov     [rsp+408h+var_300], rax
0x1800600ef  mov     [rsp+408h+var_2F8], r14
0x1800600f7  mov     byte ptr [rsp+408h+var_2F0], 1
0x1800600ff  lea     rax, [rsp+408h+var_358]
0x180060107  mov     [rsp+408h+var_248], rax
0x18006010f  mov     [rsp+408h+var_240], r14
0x180060117  mov     [rsp+408h+var_238], 1
0x18006011f  lea     rax, [rsp+408h+var_340]
0x180060127  mov     [rsp+408h+var_260], rax
0x18006012f  mov     [rsp+408h+var_258], r14
0x180060137  mov     [rsp+408h+var_250], 1
0x18006013f  lea     rax, [rsp+408h+var_380]
0x180060147  mov     [rsp+408h+var_278], rax
0x18006014f  mov     [rsp+408h+var_270], r14
0x180060157  mov     [rsp+408h+var_268], 1
0x18006015f  lea     rax, [rsp+408h+var_348]
0x180060167  mov     [rsp+408h+var_290], rax
0x18006016f  mov     [rsp+408h+var_288], r14
0x180060177  mov     [rsp+408h+var_280], 1
0x18006017f  lea     rax, [rsp+408h+var_378]
0x180060187  mov     [rsp+408h+var_2A8], rax
0x18006018f  mov     [rsp+408h+var_2A0], r14
0x180060197  mov     [rsp+408h+var_298], 1
0x18006019f  xor     edx, edx; length
0x1800601a1  mov     rcx, [r15]; string
0x1800601a4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800601aa  lea     rcx, [rsp+408h+var_388]
0x1800601b2  mov     [rsp+408h+var_3C8], rcx; struct Windows::Storage::Streams::IBuffer **
0x1800601b7  lea     rcx, [rsp+408h+var_2F8]
0x1800601bf  mov     [rsp+408h+var_3D0], rcx; unsigned __int16 **
0x1800601c4  lea     rcx, [rsp+408h+var_240]
0x1800601cc  mov     [rsp+408h+var_3D8], rcx; unsigned __int16 **
0x1800601d1  lea     rcx, [rsp+408h+var_258]
0x1800601d9  mov     [rsp+408h+var_3E0], rcx; unsigned __int16 **
0x1800601de  lea     rcx, [rsp+408h+var_270]
0x1800601e6  mov     [rsp+408h+var_3E8], rcx; int
0x1800601eb  lea     r9, [rsp+408h+var_288]; unsigned __int16 **
0x1800601f3  lea     r8, [rsp+408h+var_2A0]; unsigned __int16 **
0x1800601fb  lea     rdx, [rsp+408h+var_198]; struct CheckpointData *
0x180060203  mov     rcx, rax; unsigned __int16 *
0x180060206  call    ?LoadCheckpointData@@YAJPEBGPEAUCheckpointData@@PEAPEAG22222PEAPEAUIBuffer@Streams@Storage@Windows@@@Z; LoadCheckpointData(ushort const *,CheckpointData *,ushort * *,ushort * *,ushort * *,ushort * *,ushort * *,ushort * *,Windows::Storage::Streams::IBuffer * *)
0x18006020b  mov     rcx, [rsp+408h]; this
0x180060213  test    eax, eax
0x180060215  jns     short loc_18006022C
0x180060217  mov     r9d, eax; char *
0x18006021a  lea     r8, aOnecoreuapEndu_86; "onecoreuap\\enduser\\winstore\\installs"...
0x180060221  mov     edx, 6D1h; void *
0x180060226  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006022c  lea     rcx, [rsp+408h+var_2A8]
0x180060234  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180060239  nop
0x18006023a  lea     rcx, [rsp+408h+var_290]
0x180060242  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180060247  nop
0x180060248  lea     rcx, [rsp+408h+var_278]
0x180060250  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180060255  nop
0x180060256  lea     rcx, [rsp+408h+var_260]
0x18006025e  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180060263  nop
0x180060264  lea     rcx, [rsp+408h+var_248]
0x18006026c  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180060271  nop
0x180060272  lea     rcx, [rsp+408h+var_300]
0x18006027a  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18006027f  mov     esi, dword ptr [rsp+408h+var_198+4]
0x180060286  lea     eax, [rsi-4]
0x180060289  cmp     eax, 1
0x18006028c  jbe     loc_180060976
0x180060292  mov     r13d, dword ptr [rsp+408h+var_198]
0x18006029a  cmp     r13d, 4
0x18006029e  ja      loc_180060914
0x1800602a4  cmp     esi, 0Eh
0x1800602a7  ja      loc_180060914
0x1800602ad  mov     edx, [rsp+408h+var_180]
0x1800602b4  cmp     edx, 64h ; 'd'
0x1800602b7  ja      loc_18006091B
0x1800602bd  cmp     [rsp+408h+var_17C], 64h ; 'd'
0x1800602c5  ja      loc_18006091B
0x1800602cb  mov     rcx, [rsp+408h+var_350]; unsigned __int16 *
0x1800602d3  call    ?IsStringNullOrEmpty@StringHelpers@@SA_NPEBG@Z; StringHelpers::IsStringNullOrEmpty(ushort const *)
0x1800602d8  test    al, al
0x1800602da  jnz     loc_18006091B
0x1800602e0  cmp     [rsp+408h+var_184], r14d
0x1800602e8  jz      short loc_1800602F8
0x1800602ea  cmp     esi, 0Ch
0x1800602ed  jz      short loc_180060304
0x1800602ef  cmp     esi, 2
0x1800602f2  jnz     loc_18006091B
0x1800602f8  lea     eax, [rsi-9]
0x1800602fb  cmp     eax, 2
0x1800602fe  jbe     loc_18006091B
0x180060304  lea     rdx, [rsp+408h+var_15F]
0x18006030c  lea     rcx, [rsp+408h+var_D8]
0x180060314  call    ?ValidateAndCreate@CorrelationVector@@SA?AV1@PEBD@Z; CorrelationVector::ValidateAndCreate(char const *)
0x180060319  nop
0x18006031a  mov     [rsp+408h+var_368], r14
0x180060322  lea     rcx, [rsp+408h+var_368]
0x18006032a  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18006032f  lea     rdx, [rsp+408h+var_368]; struct WindowsUpdate::Internal::IFulfillmentDataInfo **
0x180060337  mov     rcx, [rsp+408h+var_378]; unsigned __int16 *
0x18006033f  call    ?Deserialize@FulfillmentDataInfo@Internal@WindowsUpdate@@SAJPEBGPEAPEAUIFulfillmentDataInfo@23@@Z; WindowsUpdate::Internal::FulfillmentDataInfo::Deserialize(ushort const *,WindowsUpdate::Internal::IFulfillmentDataInfo * *)
0x180060344  mov     rcx, [rsp+408h]; this
0x18006034c  test    eax, eax
0x18006034e  jns     short loc_180060364
0x180060350  mov     r9d, eax; char *
0x180060353  lea     r8, aOnecoreuapEndu_86; "onecoreuap\\enduser\\winstore\\installs"...
0x18006035a  mov     edx, 6F1h; void *
0x18006035f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180060364  mov     [rsp+408h+string], r14
0x18006036c  mov     rax, [rsp+408h+var_358]
0x180060374  mov     [rsp+408h+var_338], rax
0x18006037c  lea     rdx, [rsp+408h+var_338]
0x180060384  lea     rcx, [rsp+408h+string]
0x18006038c  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x180060391  mov     rcx, [rsp+408h]; this
0x180060399  test    eax, eax
0x18006039b  jns     short loc_1800603B1
0x18006039d  mov     r9d, eax; char *
0x1800603a0  lea     r8, aOnecoreuapEndu_86; "onecoreuap\\enduser\\winstore\\installs"...
0x1800603a7  mov     edx, 6F4h; void *
0x1800603ac  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800603b1  lea     r8, [rsp+408h+string]
0x1800603b9  lea     rdx, [rsp+408h+var_300]
0x1800603c1  lea     rcx, [rsp+408h+var_310]
0x1800603c9  call    std___Tree_std___Tmap_traits_Microsoft__WRL__Wrappers__HString_std__unique_ptr__InstallQueue___LoadItemsFromCheckpoints____2___WorkData_std__default_delete__InstallQueue___LoadItemsFromCheckpoints____2___WorkData____std__less_Microsoft__WRL__Wrappers__HString__std__allocator_std__pair_Microsoft__WRL__Wrappers__HString_const__std__unique_ptr__InstallQueue___LoadItemsFromCheckpoints____2___WorkData_std__default_delete__InstallQueue___LoadItemsFromCheckpoints____2___WorkData________0______Find_lower_bound_Microsoft__WRL__Wrappers__HString_
0x1800603ce  lea     r8, [rsp+408h+string]
0x1800603d6  mov     rbx, [rsp+408h+var_2F0]
0x1800603de  mov     rdx, rbx
0x1800603e1  call    std___Tree_std___Tmap_traits_Microsoft__WRL__Wrappers__HString_std__unique_ptr__InstallQueue___LoadItemsFromCheckpoints____2___WorkData_std__default_delete__InstallQueue___LoadItemsFromCheckpoints____2___WorkData____std__less_Microsoft__WRL__Wrappers__HString__std__allocator_std__pair_Microsoft__WRL__Wrappers__HString_const__std__unique_ptr__InstallQueue___LoadItemsFromCheckpoints____2___WorkData_std__default_delete__InstallQueue___LoadItemsFromCheckpoints____2___WorkData________0______Lower_bound_duplicate_Microsoft__WRL__Wrappers__HString_
0x1800603e6  test    al, al
0x1800603e8  jz      loc_1800604DD
0x1800603ee  cmp     rbx, [rsp+408h+var_310]
0x1800603f6  jz      loc_1800604DD
0x1800603fc  mov     rax, [rbx+28h]
0x180060400  mov     rcx, [rax]
0x180060403  mov     rax, [rcx]
0x180060406  mov     rdx, [rsp+408h+var_368]
0x18006040e  mov     rax, [rax+68h]
0x180060412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060417  mov     rcx, [rsp+408h]; this
0x18006041f  test    eax, eax
0x180060421  jns     short loc_180060438
0x180060423  mov     r9d, eax; char *
0x180060426  lea     r8, aOnecoreuapEndu_86; "onecoreuap\\enduser\\winstore\\installs"...
0x18006042d  mov     edx, 6F9h; void *
0x180060432  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180060438  mov     rcx, [rsp+408h+string]; string
0x180060440  call    cs:__imp_WindowsDeleteString
0x180060446  mov     [rsp+408h+string], r14
0x18006044e  lea     rcx, [rsp+408h+var_368]
0x180060456  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18006045b  nop
0x18006045c  lea     rcx, [rsp+408h+var_D8]; this
0x180060464  call    ??1CorrelationVector@@QEAA@XZ; CorrelationVector::~CorrelationVector(void)
0x180060469  nop
0x18006046a  lea     rcx, [rsp+408h+var_388]
0x180060472  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180060477  nop
0x180060478  lea     rcx, [rsp+408h+var_348]
0x180060480  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180060485  nop
0x180060486  lea     rcx, [rsp+408h+var_340]
0x18006048e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180060493  nop
0x180060494  lea     rcx, [rsp+408h+var_380]
0x18006049c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800604a1  nop
0x1800604a2  lea     rcx, [rsp+408h+var_358]
0x1800604aa  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800604af  nop
0x1800604b0  lea     rcx, [rsp+408h+var_350]
0x1800604b8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800604bd  nop
0x1800604be  lea     rcx, [rsp+408h+var_378]
0x1800604c6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800604cb  nop
0x1800604cc  mov     esi, [rsp+408h+var_390]
0x1800604d0  mov     rax, [rsp+408h+var_360]
0x1800604d8  jmp     loc_180060A38
0x1800604dd  mov     ecx, 90h; Size
0x1800604e2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800604e7  mov     rbx, rax
0x1800604ea  lea     rcx, [rax+10h]; void *
0x1800604ee  xor     edx, edx; Val
0x1800604f0  lea     r8d, [rdx+50h]; Size
0x1800604f4  call    memset_0
0x1800604f9  mov     [rbx], r14
0x1800604fc  mov     [rbx+8], r14
0x180060500  mov     [rbx+60h], r14
0x180060504  mov     [rbx+68h], r14
0x180060508  mov     [rbx+70h], r14
0x18006050c  mov     [rbx+78h], r14
0x180060510  mov     [rbx+80h], r14
0x180060517  mov     [rbx+88h], r14
0x18006051e  mov     [rsp+408h+var_338], rbx
0x180060526  mov     rcx, rbx
0x180060529  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18006052e  mov     rdx, rbx
0x180060531  call    ??$CreateExternalObjectVector@UIFulfillmentDataInfo@Internal@WindowsUpdate@@V?$AgileVector@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@U?$DefaultEqualityPredicate@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2567@$0A@@2Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@U?$DefaultEqualityPredicate@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2567@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<WindowsUpdate::Internal::IFulfillmentDataInfo,Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0> * *)
0x180060536  mov     rcx, [rsp+408h]; this
0x18006053e  test    eax, eax
0x180060540  jns     short loc_180060556
0x180060542  mov     r9d, eax; char *
0x180060545  lea     r8, aOnecoreuapEndu_86; "onecoreuap\\enduser\\winstore\\installs"...
0x18006054c  mov     edx, 6FEh; void *
0x180060551  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180060556  mov     rcx, [rbx]
0x180060559  mov     rax, [rcx]
0x18006055c  mov     rdx, [rsp+408h+var_368]
0x180060564  mov     rax, [rax+68h]
0x180060568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006056d  mov     rcx, [rsp+408h]; this
0x180060575  test    eax, eax
0x180060577  jns     short loc_18006058D
0x180060579  mov     r9d, eax; char *
0x18006057c  lea     r8, aOnecoreuapEndu_86; "onecoreuap\\enduser\\winstore\\installs"...
0x180060583  mov     edx, 6FFh; void *
0x180060588  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006058d  mov     r12, [rsp+408h+var_388]
0x180060595  cmp     [rbx+8], r12
0x180060599  jz      short loc_1800605C8
0x18006059b  test    r12, r12
0x18006059e  jz      short loc_1800605B1
0x1800605a0  mov     rax, [r12]
0x1800605a4  mov     rcx, r12
0x1800605a7  mov     rax, [rax+8]
0x1800605ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800605b0  nop
0x1800605b1  mov     rax, [rbx+8]
0x1800605b5  mov     [rsp+408h+var_398], rax
0x1800605ba  mov     [rbx+8], r12
0x1800605be  lea     rcx, [rsp+408h+var_398]
0x1800605c3  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800605c8  xor     edx, edx; Val
0x1800605ca  lea     r8d, [rdx+48h]; Size
0x1800605ce  lea     rcx, [rsp+408h+var_228]; void *
0x1800605d6  call    memset_0
0x1800605db  movaps  xmm0, [rsp+408h+var_228]
0x1800605e3  movups  xmmword ptr [rbx+10h], xmm0
0x1800605e7  movaps  xmm1, [rsp+408h+var_218]
0x1800605ef  movups  xmmword ptr [rbx+20h], xmm1
0x1800605f3  movaps  xmm0, [rsp+408h+var_208]
0x1800605fb  movups  xmmword ptr [rbx+30h], xmm0
0x1800605ff  movaps  xmm1, [rsp+408h+var_1F8]
0x180060607  movups  xmmword ptr [rbx+40h], xmm1
0x18006060b  movsd   xmm0, [rsp+408h+var_1E8]
0x180060614  movsd   qword ptr [rbx+50h], xmm0
0x180060619  mov     [rbx+58h], r13d
0x18006061d  mov     eax, [rsp+408h+var_190]
0x180060624  mov     [rbx+5Ch], eax
  ... truncated ...
```
