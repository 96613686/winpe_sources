# InstallQueue2::_EvaluateQueueImpl(void)

- ea: `0x1801732f4`
- end: `0x1801746c5`
- name: `?_EvaluateQueueImpl@InstallQueue2@@AEAAXXZ`
- size: `5073`
- prototype: `void __fastcall(InstallQueue2 *__hidden this)`
- caller_count: `2`
- callee_count: `85`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18016c438`
- `0x1801746d0`

## callees

- `0x180009ea0`
- `0x1800116f4`
- `0x1800127c8`
- `0x18001bf24`
- `0x18001c414`
- `0x18001c964`
- `0x180020868`
- `0x1800208e4`
- `0x180022298`
- `0x180022e50`
- `0x18002d98c`
- `0x18002ec10`
- `0x180033584`
- `0x180037200`
- `0x1800378d0`
- `0x18003f560`
- `0x180044b84`
- `0x1800453bc`
- `0x180045588`
- `0x180046110`
- `0x18006cc2c`
- `0x18007658c`
- `0x18007aa00`
- `0x180095b68`
- `0x180099350`
- `0x1800d32d0`
- `0x1800d630c`
- `0x1800ee7fc`
- `0x18012e7c4`
- `0x180138ec8`
- `0x1801391a8`
- `0x18013a1c8`
- `0x18014a37c`
- `0x18014bce0`
- `0x18014f3cc`
- `0x18014fd30`
- `0x18014fe70`
- `0x1801504c8`
- `0x180154898`
- `0x180154930`
- `0x180154d9c`
- `0x180155708`
- `0x18015579c`
- `0x180156050`
- `0x1801560f8`
- `0x180156de4`
- `0x180157264`
- `0x180157674`
- `0x180157760`
- `0x1801579ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs_s` at `0x18017385a`
- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs_s` at `0x18017385a`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180174358`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180174358`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180173f06`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180173f06`
- `msvcp_win!_Xtime_get_ticks` at `0x18017338a`
- `msvcp_win!_Xtime_get_ticks` at `0x1801742b1`
- `msvcp_win!_Xtime_get_ticks` at `0x18017338a`
- `msvcp_win!_Xtime_get_ticks` at `0x1801742b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801733d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801733d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18017424f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18017424f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180173a5d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180173a5d`

## string_xrefs

- `0x180173412`: `onecoreuap\enduser\winstore\installservice\libqueue2\installqueue2.cpp`
- `0x18017390a`: `onecoreuap\enduser\winstore\installservice\libqueue2\installqueue2.cpp`
- `0x180173aec`: `onecoreuap\enduser\winstore\installservice\libqueue2\installqueue2.cpp`
- `0x180173f9d`: `onecoreuap\enduser\winstore\installservice\libqueue2\installqueue2.cpp`
- `0x1801743c5`: `onecoreuap\enduser\winstore\installservice\libqueue2\installqueue2.cpp`
- `0x180174438`: `onecoreuap\enduser\winstore\installservice\libqueue2\installqueue2.cpp`
- `0x18017460d`: `onecoreuap\enduser\winstore\installservice\libqueue2\installqueue2.cpp`
- `0x1801746ac`: `onecoreuap\enduser\winstore\installservice\libqueue2\installqueue2.cpp`
- `0x1801733f1`: `InstallService UO safeguard unblocked low priority updates scheduled with UO`
- `0x180173abc`: `Messaged USO that work is complete`
- `0x180173405`: `InstallQueue2::_EvaluateQueueImpl`
- `0x1801738f5`: `InstallQueue2::_EvaluateQueueImpl`
- `0x180173ad7`: `InstallQueue2::_EvaluateQueueImpl`
- `0x180173f88`: `InstallQueue2::_EvaluateQueueImpl`
- `0x1801743b8`: `InstallQueue2::_EvaluateQueueImpl`
- `0x180174423`: `InstallQueue2::_EvaluateQueueImpl`
- `0x1801745f8`: `InstallQueue2::_EvaluateQueueImpl`
- `0x180174408`: `Failed to open delayed queue evaluation tip test `
- `0x180173f6d`: `Queue evaluation terminated for service stop.`

## pseudocode

```c
// Hidden C++ exception states: #wind=42
void __fastcall InstallQueue2::_EvaluateQueueImpl(InstallQueue2 *this)
{
  InstallQueue2 *v1; // r14
  InstallQueue2 *v2; // rbx
  int v4; // r12d
  __int64 ticks; // rbx
  HSTRING ClientIdIfMissing; // rax
  const unsigned __int16 *StringRawBuffer; // rax
  __int64 v8; // rax
  std::_Ref_count_base *v9; // rbx
  std::_Ref_count_base *v10; // rdi
  __int64 j; // rbx
  __int64 v12; // rdi
  __int64 v13; // rax
  __int64 *v14; // r13
  std::_Ref_count_base *v15; // rbx
  std::_Ref_count_base *v16; // rdi
  __int64 *v17; // r15
  __int64 *v18; // rbx
  __int64 v19; // rax
  __int64 v20; // rdi
  InstallQueue2 *v21; // rax
  _QWORD *v22; // r12
  _QWORD *i; // rbx
  winrt::hstring *v24; // r15
  __int64 v25; // rax
  bool v26; // di
  _QWORD *v27; // rdi
  unsigned int v28; // eax
  unsigned int v29; // eax
  __int64 v30; // rax
  __int64 v31; // rbx
  __int64 v32; // rdi
  __int64 v33; // rax
  const struct CheckpointData::Data *v34; // rdx
  std::_Ref_count_base *v35; // r15
  __int64 *v36; // rdi
  _QWORD *v37; // rbx
  __int64 v38; // rcx
  _QWORD *k; // r8
  __int64 v40; // r13
  std::_Ref_count_base *m; // rbx
  __int64 v42; // rax
  void *n; // rax
  const char *v44; // r9
  __int64 v45; // r8
  unsigned int v46; // r12d
  _QWORD *NextPendingItem; // rax
  __int64 v48; // rbx
  void (__fastcall ***v49)(_QWORD, __int64 *, InstallQueue2 **); // rcx
  InstallQueue2 *v50; // rbx
  int v51; // r12d
  unsigned int v52; // eax
  char v53; // al
  __int64 v54; // rax
  char IsEnabled; // al
  char *v56; // r15
  std::_Ref_count_base *v57; // r8
  _BYTE *v58; // rdx
  __int64 *v59; // rax
  __int64 v60; // rdi
  __int128 v61; // xmm1
  LPVOID v62; // rax
  wil::details::in1diag3 *v63; // rcx
  __int64 v64; // kr30_8
  int v65; // r12d
  const struct store_lock *v66; // rdx
  unsigned int AvailableOperationsCount; // r13d
  _QWORD *v68; // rax
  __int64 v69; // rbx
  _DWORD *v70; // rbx
  int v71; // r9d
  _BYTE v72[32]; // [rsp+0h] [rbp-428h] BYREF
  __int64 v73; // [rsp+48h] [rbp-3E0h]
  __int64 v74; // [rsp+50h] [rbp-3D8h]
  _BYTE v75[8]; // [rsp+60h] [rbp-3C8h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-3C0h] BYREF
  int v77; // [rsp+70h] [rbp-3B8h]
  std::_Ref_count_base *v78; // [rsp+78h] [rbp-3B0h] BYREF
  std::_Ref_count_base *v79[2]; // [rsp+80h] [rbp-3A8h] BYREF
  __int64 v80; // [rsp+90h] [rbp-398h] BYREF
  __int64 v81; // [rsp+98h] [rbp-390h] BYREF
  InstallQueue2 *v82; // [rsp+A0h] [rbp-388h] BYREF
  InstallQueue2 *v83; // [rsp+A8h] [rbp-380h]
  _QWORD *v84; // [rsp+B0h] [rbp-378h] BYREF
  std::_Ref_count_base *v85; // [rsp+B8h] [rbp-370h] BYREF
  std::_Ref_count_base *v86[2]; // [rsp+C0h] [rbp-368h] BYREF
  InstallQueue2 *v87; // [rsp+D0h] [rbp-358h] BYREF
  InstallQueue2 *v88; // [rsp+D8h] [rbp-350h]
  _BYTE v89[8]; // [rsp+E0h] [rbp-348h] BYREF
  _BYTE v90[8]; // [rsp+E8h] [rbp-340h] BYREF
  _BYTE v91[16]; // [rsp+F0h] [rbp-338h] BYREF
  int v92; // [rsp+100h] [rbp-328h] BYREF
  _BYTE v93[8]; // [rsp+108h] [rbp-320h] BYREF
  __int64 v94; // [rsp+110h] [rbp-318h]
  _QWORD v95[7]; // [rsp+140h] [rbp-2E8h] BYREF
  __int128 v96; // [rsp+178h] [rbp-2B0h] BYREF
  __int64 v97; // [rsp+188h] [rbp-2A0h]
  std::_Ref_count_base *v98[4]; // [rsp+198h] [rbp-290h] BYREF
  _QWORD v99[4]; // [rsp+1B8h] [rbp-270h] BYREF
  const wchar_t *v100; // [rsp+1D8h] [rbp-250h] BYREF
  __int64 v101; // [rsp+1E0h] [rbp-248h]
  _BYTE v102[16]; // [rsp+1F8h] [rbp-230h] BYREF
  __int64 v103; // [rsp+208h] [rbp-220h]
  _BYTE v104[24]; // [rsp+230h] [rbp-1F8h] BYREF
  _OWORD v105[8]; // [rsp+250h] [rbp-1D8h] BYREF
  char v106; // [rsp+2D0h] [rbp-158h]
  __int64 v107; // [rsp+2D8h] [rbp-150h] BYREF
  _BYTE v108[272]; // [rsp+2E0h] [rbp-148h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+428h] [rbp+0h]

  try
  {
    v1 = this;
    v82 = this;
    v2 = this;
    v83 = this;
    v88 = this;
    v87 = this;
    v4 = 0;
    v77 = 0;
    LODWORD(v80) = 0;
    std::_State_manager<int>::wait((char *)this + 680);
    InstallQueue2::FlushEventQueue(this);
    v81 = 0;
    if ( (unsigned __int8)RetrieveAutoUpdateWorkScheduledWithUOTime(&v81) )
    {
      ticks = _Xtime_get_ticks();
      if ( (ticks - v81) / 10000000 + ticks - v81 >= GetUOMaximumBlockedTimeFromOneSettings() )
      {
        ClientIdIfMissing = CreateClientIdIfMissing(0);
        StringRawBuffer = WindowsGetStringRawBuffer(ClientIdIfMissing, 0);
        InstallQueue2::UnblockLowPriorityWorkItems(this, StringRawBuffer, (InstallQueue2 *)((char *)this + 32));
        LogSimpleMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp",
          0x1046u,
          "InstallQueue2::_EvaluateQueueImpl",
          -1,
          L"InstallService UO safeguard unblocked low priority updates scheduled with UO",
          0,
          0);
      }
      v2 = v83;
    }
    std::unordered_map<winrt::hstring,std::shared_ptr<InstallQueue2::QueueItem>>::unordered_map<winrt::hstring,std::shared_ptr<InstallQueue2::QueueItem>>(&v92);
    InstallQueue2::_LockQueueForRead(v1, v99);
    v81 = (__int64)v1 + 200;
    if ( &v92 != (int *)((char *)v1 + 200) )
    {
      ppv = &v92;
      v92 = *((_DWORD *)v1 + 50);
      std::list<std::pair<winrt::hstring const,std::shared_ptr<InstallQueue2::QueueItem>>>::_Assign_cast<std::pair<winrt::hstring,std::shared_ptr<InstallQueue2::QueueItem>> &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,std::shared_ptr<InstallQueue2::QueueItem>>>>,std::_Iterator_base0>>(
        (__int64)v93,
        **((_QWORD ***)v1 + 26),
        *((_QWORD **)v1 + 26));
      v8 = std::_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::_Desired_grow_bucket_count(
             &v92,
             v94);
      std::_Hash<std::_Umap_traits<winrt::hstring,std::shared_ptr<InstallQueue2::QueueItem>,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,std::shared_ptr<InstallQueue2::QueueItem>>>,0>>::_Forced_rehash(
        &v92,
        v8);
      ppv = 0;
      std::_Hash<std::_Umap_traits<winrt::hstring,std::shared_ptr<InstallQueue2::QueueItem>,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,std::shared_ptr<InstallQueue2::QueueItem>>>,0>>::_Clear_guard::~_Clear_guard(&ppv);
    }
    shared_lock::~shared_lock((shared_lock *)v99);
    v97 = 0;
    v96 = 0;
    if ( *((_BYTE *)v1 + 696) )
    {
      InstallQueue2::_LockQueueForRead(v1, v99);
      v14 = (__int64 *)((char *)v2 + 360);
      std::vector<std::shared_ptr<InstallQueue2::QueueItem>>::vector<std::shared_ptr<InstallQueue2::QueueItem>>(
        v98,
        (char *)v2 + 360);
      v15 = v98[0];
      v16 = v98[1];
      while ( v15 != v16 )
      {
        if ( (unsigned int)winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkItem<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem>::Priority(*(_QWORD *)v15 + 96LL) == 1
          && *(_DWORD *)(*(_QWORD *)v15 + 28LL) == 2 )
        {
          if ( *((_QWORD *)&v96 + 1) == v97 )
          {
            std::vector<std::shared_ptr<InstallQueue2::QueueItem>>::_Emplace_reallocate<std::shared_ptr<InstallQueue2::QueueItem> const &>(
              &v96,
              *((__int64 *)&v96 + 1),
              (__int64)v15);
          }
          else
          {
            std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(*((_QWORD *)&v96 + 1), v15);
            *((_QWORD *)&v96 + 1) += 16LL;
          }
        }
        v15 = (std::_Ref_count_base *)((char *)v15 + 16);
      }
      std::vector<std::shared_ptr<NotificationQueue>>::~vector<std::shared_ptr<NotificationQueue>>(v98);
      shared_lock::~shared_lock((shared_lock *)v99);
      v17 = (__int64 *)*((_QWORD *)&v96 + 1);
      v18 = (__int64 *)v96;
      if ( (_QWORD)v96 == *((_QWORD *)&v96 + 1) )
      {
        v79[0] = (std::_Ref_count_base *)L"Evaluating whether low priority items have left queue";
        v79[1] = (std::_Ref_count_base *)53;
        std::string::string(v98, "InstallQueue2::_EvaluateQueueImpl");
        std::string::string(v102, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp");
        Logging::Log<>((unsigned int)v102, 4237, (unsigned int)v98, 3, (__int64)v79);
        std::string::~string(v102);
        std::string::~string(v98);
        InstallQueue2::_LockQueueForRead(v1, v99);
        v21 = v83;
        v22 = (_QWORD *)*((_QWORD *)v83 + 26);
        for ( i = (_QWORD *)*v22; i != v22; i = (_QWORD *)*i )
        {
          v26 = (v24 = std::pair<winrt::hstring,std::shared_ptr<InstallQueue2::QueueItem>>::pair<winrt::hstring,std::shared_ptr<InstallQueue2::QueueItem>>(
                         (winrt::hstring *)v98,
                         (const struct winrt::hstring *)(i + 2)),
                 v84 = v24,
                 (unsigned int)winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkItem<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem>::Priority(*((_QWORD *)v24 + 1) + 96LL) == 1)
             && ((v25 = *((_QWORD *)v24 + 1), !*(_DWORD *)(v25 + 24)) || *(_DWORD *)(v25 + 24) == 1)
             && !*(_DWORD *)(v25 + 28);
          std::pair<winrt::hstring const,std::shared_ptr<CatalogDataStore::CatalogItem>>::~pair<winrt::hstring const,std::shared_ptr<CatalogDataStore::CatalogItem>>(v24);
          v21 = v83;
          if ( v26 )
            break;
        }
        v27 = (_QWORD *)*((_QWORD *)v21 + 26);
        shared_lock::~shared_lock((shared_lock *)v99);
        if ( i == v27 )
        {
          InstallQueue2::BlockLowPriorityWorkItems(v1, L"IA", (InstallQueue2 *)((char *)v1 + 32));
          ppv = 0;
          LODWORD(v98[0]) = 0;
          *(_OWORD *)&v98[1] = 0;
          v28 = CoCreateInstance(
                  &GUID_9c695035_48d2_4229_8b73_4c70e756e519,
                  0,
                  4u,
                  &GUID_c53f3549_0dbf_429a_8297_c812ba00742d,
                  &ppv);
          winrt::check_hresult(&v78, v28, v98);
          LODWORD(v98[0]) = 0;
          *(_OWORD *)&v98[1] = 0;
          v29 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, __int64))(*(_QWORD *)ppv + 40LL))(
                  ppv,
                  L"IA",
                  1);
          winrt::check_hresult(&v78, v29, v98);
          v79[0] = (std::_Ref_count_base *)L"Messaged USO that work is complete";
          v79[1] = (std::_Ref_count_base *)34;
          std::string::string(v98, "InstallQueue2::_EvaluateQueueImpl");
          std::string::string(v102, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp");
          Logging::Log<>((unsigned int)v102, 4264, (unsigned int)v98, 3, (__int64)v79);
          std::string::~string(v102);
          std::string::~string(v98);
          if ( ppv )
            winrt::com_ptr<IInspectable>::unconditional_release_ref(&ppv);
        }
        v4 = v77;
      }
      else
      {
        while ( v18 != v17 )
        {
          InstallQueue2::exclusive_lock::exclusive_lock((InstallQueue2::exclusive_lock *)v102, v1);
          v4 |= 4u;
          v77 = v4;
          LODWORD(v80) = v4;
          ppv = 0;
          v19 = std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(&v100, v18);
          InstallQueue2::_SwitchState(
            (_DWORD)v1,
            (unsigned int)&v85,
            (unsigned int)v102,
            (_DWORD)v1 + 32,
            v19,
            (__int64)&ppv);
          _release___exclusive_lock_with_release_callback_VInstallQueue2__P81_EAAXX_E__UEAAXXZ(v102);
          v20 = *v18;
          v105[0] = *(_OWORD *)((char *)v83 + 40);
          v105[1] = *(_OWORD *)((char *)v83 + 56);
          v105[2] = *(_OWORD *)((char *)v83 + 72);
          v105[3] = *(_OWORD *)((char *)v83 + 88);
          v105[4] = *(_OWORD *)((char *)v83 + 104);
          v105[5] = *(_OWORD *)((char *)v83 + 120);
          v105[6] = *(_OWORD *)((char *)v83 + 136);
          v105[7] = *(_OWORD *)((char *)v83 + 152);
          v106 = *((_BYTE *)v83 + 168);
          winrt::hstring::hstring((winrt::hstring *)&v107, (InstallQueue2 *)((char *)v83 + 176));
          if ( !v107 )
          {
            _o_mbstowcs_s(0, v108, 129, v105, 129);
            winrt::hstring::operator=(&v107, v108);
          }
          v99[0] = *(_QWORD *)winrt::hstring::hstring((winrt::hstring *)&v78, (const struct winrt::hstring *)&v107);
          winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkItem<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem>::UserOverrideRequestedForBlockedState(
            v20 + 96,
            v99,
            1);
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v78);
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v107);
          __1__exclusive_lock_with_release_callback_VInstallQueue2__P81_EAAXX_E__UEAA_XZ(v102);
          v18 += 2;
        }
      }
      std::vector<std::shared_ptr<NotificationQueue>>::~vector<std::shared_ptr<NotificationQueue>>(&v96);
    }
    else
    {
      InstallQueue2::_LockQueueForRead(v1, v99);
      std::vector<std::shared_ptr<InstallQueue2::QueueItem>>::vector<std::shared_ptr<InstallQueue2::QueueItem>>(
        v98,
        (char *)v1 + 264);
      v9 = v98[0];
      v10 = v98[1];
      while ( v9 != v10 )
      {
        if ( (unsigned int)winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkItem<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem>::Priority(*(_QWORD *)v9 + 96LL) == 1 )
        {
          if ( *((_QWORD *)&v96 + 1) == v97 )
          {
            std::vector<std::shared_ptr<InstallQueue2::QueueItem>>::_Emplace_reallocate<std::shared_ptr<InstallQueue2::QueueItem> const &>(
              &v96,
              *((__int64 *)&v96 + 1),
              (__int64)v9);
          }
          else
          {
            std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(*((_QWORD *)&v96 + 1), v9);
            *((_QWORD *)&v96 + 1) += 16LL;
          }
        }
        v9 = (std::_Ref_count_base *)((char *)v9 + 16);
      }
      std::vector<std::shared_ptr<NotificationQueue>>::~vector<std::shared_ptr<NotificationQueue>>(v98);
      shared_lock::~shared_lock((shared_lock *)v99);
      if ( (_QWORD)v96 != *((_QWORD *)&v96 + 1) )
      {
        InstallQueue2::exclusive_lock::exclusive_lock((InstallQueue2::exclusive_lock *)v95, v1);
        v4 = 2;
        v77 = 2;
        LODWORD(v80) = 2;
        v12 = *((_QWORD *)&v96 + 1);
        for ( j = v96; j != v12; j += 16 )
        {
          ppv = (LPVOID)0x200000004LL;
          v13 = std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(&v100, j);
          InstallQueue2::_SwitchState(
            (_DWORD)v1,
            (unsigned int)&v85,
            (unsigned int)v95,
            (_DWORD)v1 + 32,
            v13,
            (__int64)&ppv);
        }
        __1__exclusive_lock_with_release_callback_VInstallQueue2__P81_EAAXX_E__UEAA_XZ(v95);
      }
      std::vector<std::shared_ptr<NotificationQueue>>::~vector<std::shared_ptr<NotificationQueue>>(&v96);
      v14 = (__int64 *)((char *)this + 360);
    }
    while ( 1 )
    {
      *(_OWORD *)v86 = 0;
      v78 = 0;
      InstallQueue2::_LockQueueForEditNoEval(v1, v79);
      v30 = *((_QWORD *)v1 + 50);
      if ( *((_QWORD *)v1 + 49) == v30 )
        break;
      v69 = v30 - 24;
      winrt::hstring::operator=(&v78, v30 - 24);
      std::shared_ptr<CheckpointData::Data>::operator=(v86, v69 + 8);
      std::pair<winrt::hstring const,std::shared_ptr<CatalogDataStore::CatalogItem>>::~pair<winrt::hstring const,std::shared_ptr<CatalogDataStore::CatalogItem>>(*((_QWORD *)v1 + 50) - 24LL);
      *((_QWORD *)v1 + 50) -= 24LL;
      v70 = (_DWORD *)((char *)v86[0] + 24);
      if ( (*((_DWORD *)v86[0] + 6) != 2 || *((_DWORD *)v86[0] + 7)) && (*v70 != 3 || *((_DWORD *)v86[0] + 7)) )
      {
        v100 = L"Item queued for abort no longer requires it";
        v101 = 43;
        std::string::string(v102, "InstallQueue2::_EvaluateQueueImpl");
        std::string::string(v99, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp");
        Logging::Log<std::shared_ptr<InstallQueue2::QueueItem> &,InstallQueue2::QueueItemState &>(
          (unsigned int)v99,
          4284,
          (unsigned int)v102,
          v71,
          (__int64)&v100,
          (__int64)v86,
          (__int64)v70);
        std::string::~string(v99);
        std::string::~string(v102);
        std::unique_lock<std::shared_mutex>::~unique_lock<std::shared_mutex>(v79);
      }
      else
      {
        std::unique_lock<std::shared_mutex>::~unique_lock<std::shared_mutex>(v79);
        if ( *((_DWORD *)v86[0] + 6) != 2 || *((_DWORD *)v86[0] + 7) )
        {
          v98[0] = v78;
          winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItemSubTask>,winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItemSubTask>::Append(
            (char *)v86[0] + 96,
            v98);
        }
        else
        {
          *(_QWORD *)&v96 = v78;
          winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkItem<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem>::Pause(
            (char *)v86[0] + 96,
            &v96);
        }
      }
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v78);
      if ( v86[1] )
        std::_Ref_count_base::_Decref(v86[1]);
    }
    std::unique_lock<std::shared_mutex>::~unique_lock<std::shared_mutex>(v79);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v78);
    if ( v86[1] )
      std::_Ref_count_base::_Decref(v86[1]);
    memset(v98, 0, 24);
    InstallQueue2::_LockQueueForEditNoEval(v1, &v100);
    v31 = *v14;
    v32 = v14[1];
    while ( v31 != v32 )
    {
      v33 = *(_QWORD *)v31;
      if ( *(_DWORD *)(*(_QWORD *)v31 + 24LL) == 4 && (*(_DWORD *)(v33 + 28) == 5 || *(_DWORD *)(v33 + 28) == 6) )
      {
        if ( v98[1] == v98[2] )
        {
          std::vector<std::shared_ptr<InstallQueue2::QueueItem>>::_Emplace_reallocate<std::shared_ptr<InstallQueue2::QueueItem> const &>(
            v98,
            (__int64)v98[1],
            v31);
        }
        else
        {
          std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(v98[1], v31);
          v98[1] = (std::_Ref_count_base *)((char *)v98[1] + 16);
        }
      }
      v31 += 16;
    }
    std::unique_lock<std::shared_mutex>::~unique_lock<std::shared_mutex>(&v100);
    v35 = v98[1];
    v36 = (__int64 *)v98[0];
    if ( v98[0] != v98[1] )
    {
      v37 = (_QWORD *)v81;
      v84 = (_QWORD *)v81;
      v96 = 0;
      v97 = 0;
      v85 = v98[1];
      while ( 1 )
      {
        v78 = (std::_Ref_count_base *)v36;
        if ( v36 == (__int64 *)v35 )
          break;
        try
        {
          CheckpointData::Delete(*(CheckpointData **)(*v36 + 48), v34);
          InstallQueue2::_LockQueueForEditNoEval(v1, &v100);
          std::_Hash<std::_Umap_traits<winrt::hstring,std::shared_ptr<InstallQueue2::QueueItem>,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,std::shared_ptr<InstallQueue2::QueueItem>>>,0>>::_Erase<winrt::hstring>(
            v37,
            *v36);
          v38 = *(int *)(*v36 + 24);
          for ( k = (_QWORD *)*((_QWORD *)v1 + 3 * v38 + 33); k != *((_QWORD **)v1 + 3 * v38 + 34); k += 2 )
          {
            if ( *k == *v36 )
            {
              std::vector<std::shared_ptr<InstallQueue2::QueueItem>>::erase((char *)v1 + 24 * v38 + 264, v90);
              break;
            }
          }
          v40 = *v36 + 96;
          std::_Hash<std::_Umap_traits<winrt::hstring,InstallQueue2::TrackerData,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,InstallQueue2::TrackerData>>,1>>::equal_range(
            (char *)v1 + 616,
            v86);
          for ( m = v86[0]; m != v86[1]; m = *(std::_Ref_count_base **)m )
          {
            v42 = winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkItem<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem>::Attributes(
                    v40,
                    v89);
            winrt::Windows::Foundation::IUnknown::operator=(*((_QWORD *)m + 3) + 112LL, v42);
            winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v89);
            std::make_shared<InstallItemData,InstallItemData &>(v79, *((_QWORD *)m + 3));
            if ( *((_QWORD *)&v96 + 1) == v97 )
            {
              std::vector<std::shared_ptr<InstallItemData>>::_Emplace_reallocate<std::shared_ptr<InstallItemData> const &>(
                (__int64 *)&v96,
                *((__int64 *)&v96 + 1),
                (__int64)v79);
            }
            else
            {
              std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(*((_QWORD *)&v96 + 1), v79);
              *((_QWORD *)&v96 + 1) += 16LL;
            }
            if ( v79[1] )
              std::_Ref_count_base::_Decref(v79[1]);
          }
          std::_Hash<std::_Umap_traits<winrt::hstring,InstallQueue2::TrackerData,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,InstallQueue2::TrackerData>>,1>>::find(
            (char *)v1 + 616,
            &ppv,
            *v36);
          for ( n = ppv; n != *((void **)v87 + 78); ppv = n )
          {
            std::_Hash<std::_Umap_traits<winrt::hstring,InstallQueue2::TrackerData,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,InstallQueue2::TrackerData>>,1>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,InstallQueue2::TrackerData>>>>,0>(
              (char *)v1 + 616,
              v91,
              n);
            n = *(void **)std::_Hash<std::_Umap_traits<winrt::hstring,InstallQueue2::TrackerData,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,InstallQueue2::TrackerData>>,1>>::find(
                            (char *)v1 + 616,
                            v104,
                            *v36);
          }
          std::unique_lock<std::shared_mutex>::~unique_lock<std::shared_mutex>(&v100);
          v4 = v77;
          v37 = (_QWORD *)v81;
        }
        catch ( ... )
        {
          v34 = (const struct CheckpointData::Data *)v72;
          v36 = (__int64 *)v78;
          v35 = v85;
          v4 = v80;
          v77 = v80;
          v37 = v84;
          v81 = (__int64)v84;
          v1 = v82;
        }
        v36 += 2;
      }
      try
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SendProgressAsync>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SendProgressAsync>::GetImpl'::`2'::impl) )
          InstallQueue2::_NotifyHandlers(v1);
        else
          InstallQueue2::_NotifyCompletion(v1, &v96);
      }
      catch ( ... )
      {
        v79[0] = (std::_Ref_count_base *)L"Completion notification to clients failed";
        v79[1] = (std::_Ref_count_base *)41;
        std::string::string(&v100, "InstallQueue2::_EvaluateQueueImpl");
        std::string::string(v102, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp");
        Logging::Log<>((unsigned int)v72 + 504, 4363, (unsigned int)v72 + 472, 3, (__int64)v79);
        std::string::~string(v102);
        std::string::~string(&v100);
        v4 = v80;
        v1 = v82;
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WorkReleaseDeadlock>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WorkReleaseDeadlock>::GetImpl'::`2'::impl)
        && !QueueUserWorkItem(InstallQueue2::_WorkItemFinalizer, v1, 0) )
      {
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x1111,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp",
          v44);
      }
      if ( (_QWORD)v96 )
      {
        std::_Destroy_range<std::allocator<std::shared_ptr<InstallQueue2::QueueItem>>>(v96, *((__int64 *)&v96 + 1));
        std::_Deallocate<16>((void *)v96, (struct std::nothrow_t *)((v97 - v96) & 0xFFFFFFFFFFFFFFF0uLL));
      }
    }
    std::vector<std::shared_ptr<NotificationQueue>>::~vector<std::shared_ptr<NotificationQueue>>(v98);
    if ( InstallQueue2::_serviceStop )
    {
      v79[0] = (std::_Ref_count_base *)L"Queue evaluation terminated for service stop.";
      v79[1] = (std::_Ref_count_base *)45;
      std::string::string(&v96, "InstallQueue2::_EvaluateQueueImpl");
      std::string::string(v102, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp");
      Logging::Log<>((unsigned int)v102, 4377, (unsigned int)&v96, 4, (__int64)v79);
      std::string::~string(v102);
      std::string::~string(&v96);
    }
    else
    {
      *(_OWORD *)v79 = 0;
      PEAVInstallQueue2::QEAA::exclusive_lock_with_release_callback<InstallQueue2,void (InstallQueue2::*)(void) throw(unsigned __int8)>::exclusive_lock_with_release_callback<InstallQueue2,void (InstallQueue2::*)(void) throw(unsigned __int8)>(
        v95,
        v1,
        InstallQueue2::_ScheduleQueueEvaluation,
        (char *)v1 + 192);
      v95[0] = &___7__exclusive_lock_with_release_callback_VInstallQueue2__P81_EAAXX_E__6B_;
      v46 = v4 | 8;
      while ( 1 )
      {
        NextPendingItem = InstallQueue2::_FindNextPendingItem(v1, v98, v45, (__int64)&v92);
        v48 = *(_QWORD *)std::shared_ptr<CatalogDataStore::CatalogItem>::operator=(v79, NextPendingItem);
        if ( v98[1] )
          std::_Ref_count_base::_Decref(v98[1]);
        if ( !v48 )
          break;
        v49 = (void (__fastcall ***)(_QWORD, __int64 *, InstallQueue2 **))*((_QWORD *)v79[0] + 12);
        if ( v49 )
        {
          v82 = 0;
          (**v49)(
            v49,
            &winrt::impl::guid_v<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem2>,
            &v82);
          v50 = v82;
          ppv = v82;
        }
        else
        {
          ppv = 0;
          v50 = 0;
        }
        v84 = 0;
        v51 = v46 | 1;
        LODWORD(v80) = v51;
        if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&ppv, &v84)
          || (v75[0] = 0,
              *(_DWORD *)v104 = 0,
              *(_OWORD *)&v104[8] = 0,
              v52 = (*(__int64 (__fastcall **)(InstallQueue2 *, _BYTE *))(*(_QWORD *)v50 + 48LL))(v50, v75),
              winrt::check_hresult(&v78, v52, v104),
              v53 = 1,
              v75[0]) )
        {
          v53 = 0;
        }
        v46 = v51 & 0xFFFFFFFE;
        v77 = v46;
        if ( !v53 )
        {
          v81 = 1;
          v54 = std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(&v96, v79);
          InstallQueue2::_SwitchState(
            (_DWORD)v1,
            (unsigned int)v91,
            (unsigned int)v95,
            (_DWORD)v1 + 32,
            v54,
            (__int64)&v81);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AcquisitionEnqueueToWorkingDelayTip>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AcquisitionEnqueueToWorkingDelayTip>::GetImpl'::`2'::impl) )
          {
            IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixAcquisitionToWorkingDedupTIP>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixAcquisitionToWorkingDedupTIP>::GetImpl'::`2'::impl);
            v56 = (char *)v88 + 712;
            if ( IsEnabled )
            {
              v57 = (std::_Ref_count_base *)(*((_QWORD *)v79[0] + 1) + 24LL);
              v58 = v90;
            }
            else
            {
              v57 = v79[0];
              v58 = v89;
            }
            v59 = (__int64 *)std::_Hash<std::_Umap_traits<winrt::hstring,winrt::hstring,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,winrt::hstring>>,0>>::find(
                               (char *)v88 + 712,
                               v58,
                               v57);
            v60 = *v59;
            if ( *v59 != *((_QWORD *)v83 + 90) )
            {
              v61 = *(_OWORD *)(v60 + 24);
              v103 = *(_QWORD *)(v60 + 40);
              v80 = 0;
              *(_OWORD *)v104 = v61;
              v62 = CoTaskMemAlloc(0x128u);
              if ( !v62 )
                wil::details::in1diag3::_FailFastImmediate_Unexpected(v63);
              v82 = (InstallQueue2 *)tip2::details::merged_data<TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest,TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest>::merged_data<TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest,TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest>(
                                       v62,
                                       v104);
              wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest,TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest>,wil::err_returncode_policy>::operator=(
                &v80,
                &v82);
              wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest,TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest,TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest>,wil::err_returncode_policy>(&v82);
              if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::has_ever_started(v80 + 8) )
              {
                v64 = _Xtime_get_ticks() - v103;
                *(_QWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest,TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest>>::operator->(
                                         &v80,
                                         &v85)
                          + 280LL) = v64 / 10000000;
                tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest,TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest,TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest>>(&v85);
                if ( v64 / 10000000 > 60 )
                {
                  InitOnceExecuteOnce(&InitOnce, InitializeInstallServiceConfiguration, 0, 0);
                  v65 = dword_1802CA684;
                  AvailableOperationsCount = InstallQueue2::GetAvailableOperationsCount(v1, v66);
                  v68 = (_QWORD *)std::to_wstring(v99, v64 / 10000000);
                  if ( v68[3] > 7u )
                    v68 = (_QWORD *)*v68;
                  LODWORD(v74) = v65;
                  LODWORD(v73) = AvailableOperationsCount;
                  LogMessage(
                    2u,
                    "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp",
                    0x1148u,
                    "InstallQueue2::_EvaluateQueueImpl",
                    -1,
                    L"Queue Evaluation time for the queue Item is %s seconds. Available operations count is %d. Max concur"
                     "rent queue items is %d.",
                    0,
                    0,
                    v68,
                    v73,
                    v74);
                  std::wstring::_Tidy_deallocate(v99);
                  v46 = v77;
                }
                else
                {
                  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest,TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest>>::operator->(
                                          &v80,
                                          &v87)
                           + 272LL) = 1;
                  tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest,TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest,TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest>>(&v87);
                }
                if ( v80 )
                  tip2::details::shared_data<1,0,0>::complete_without_lock(v80 + 8);
              }
              else
              {
                v100 = L"Failed to open delayed queue evaluation tip test ";
                v101 = 49;
                std::string::string(v99, "InstallQueue2::_EvaluateQueueImpl");
                std::string::string(v104, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp");
                Logging::Log<>((unsigned int)v104, 4430, (unsigned int)v99, 1, (__int64)&v100);
                std::string::~string(v104);
                std::string::~string(v99);
              }
              std::_Hash<std::_Umap_traits<winrt::hstring,InstallQueue2::EnqueueToWorkingDelayTipData,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,InstallQueue2::EnqueueToWorkingDelayTipData>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,InstallQueue2::EnqueueToWorkingDelayTipData>>>>,0>(
                v56,
                v86,
                v60);
              wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest,TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest,TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest>,wil::err_returncode_policy>(&v80);
            }
          }
        }
        winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&ppv);
      }
      __1__exclusive_lock_with_release_callback_VInstallQueue2__P81_EAAXX_E__UEAA_XZ(v95);
      if ( v79[1] )
        std::_Ref_count_base::_Decref(v79[1]);
    }
    InstallQueue2::FlushEventQueue(v1);
    std::_Hash<std::_Umap_traits<winrt::hstring,std::shared_ptr<InstallQueue2::QueueItem>,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,std::shared_ptr<InstallQueue2::QueueItem>>>,0>>::~_Hash<std::_Umap_traits<winrt::hstring,std::shared_ptr<InstallQueue2::QueueItem>,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,std::shared_ptr<InstallQueue2::QueueItem>>>,0>>(&v92);
  }
  catch ( ... )
  {
    winrt::hstring::hstring((winrt::hstring *)v79, L"Error");
    v79[1] = (std::_Ref_count_base *)*(unsigned int *)winrt::to_hresult(&v78);
    v100 = L"EvaluateQueueImpl hitting error ";
    v101 = 32;
    std::string::string(v102, "InstallQueue2::_EvaluateQueueImpl");
    std::string::string(v99, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp");
    Logging::Log<Logging::ErrorCode>(
      (unsigned int)v72 + 440,
      4443,
      (unsigned int)v72 + 504,
      1,
      (__int64)&v100,
      (__int64)v79);
    std::string::~string(v99);
    std::string::~string(v102);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v79);
  }
}

```

## disassembly

```asm
0x1801732f4  mov     [rsp+arg_8], rbx
0x1801732f9  mov     [rsp+arg_10], rsi
0x1801732fe  push    rdi
0x1801732ff  push    r12
0x180173301  push    r13
0x180173303  push    r14
0x180173305  push    r15
0x180173307  sub     rsp, 400h
0x18017330e  mov     rax, cs:__security_cookie
0x180173315  xor     rax, rsp
0x180173318  mov     [rsp+428h+var_38], rax
0x180173320  mov     r14, rcx
0x180173323  mov     [rsp+428h+var_388], rcx
0x18017332b  mov     rbx, rcx
0x18017332e  mov     [rsp+428h+var_380], rcx
0x180173336  mov     r15, rcx
0x180173339  mov     [rsp+428h+var_350], rcx
0x180173341  mov     [rsp+428h+var_358], rcx
0x180173349  xor     esi, esi
0x18017334b  mov     r12d, esi
0x18017334e  mov     [rsp+428h+var_3B8], esi
0x180173352  mov     dword ptr [rsp+428h+var_398], esi
0x180173359  add     rcx, 2A8h
0x180173360  call    ?wait@?$_State_manager@H@std@@QEBAXXZ; std::_State_manager<int>::wait(void)
0x180173365  mov     rcx, r15; this
0x180173368  call    ?FlushEventQueue@InstallQueue2@@QEAAXXZ; InstallQueue2::FlushEventQueue(void)
0x18017336d  mov     [rsp+428h+var_390], rsi
0x180173375  lea     rcx, [rsp+428h+var_390]
0x18017337d  call    ?RetrieveAutoUpdateWorkScheduledWithUOTime@@YA_NAEAV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; RetrieveAutoUpdateWorkScheduledWithUOTime(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> &)
0x180173382  test    al, al
0x180173384  jz      loc_180173429
0x18017338a  call    cs:__imp__Xtime_get_ticks
0x180173390  mov     rbx, rax
0x180173393  call    ?GetUOMaximumBlockedTimeFromOneSettings@@YA_JXZ; GetUOMaximumBlockedTimeFromOneSettings(void)
0x180173398  mov     r8, rax
0x18017339b  sub     rbx, [rsp+428h+var_390]
0x1801733a3  mov     rax, 0D6BF94D5E57A42BDh
0x1801733ad  imul    rbx
0x1801733b0  add     rdx, rbx
0x1801733b3  sar     rdx, 17h
0x1801733b7  mov     rcx, rdx
0x1801733ba  shr     rcx, 3Fh
0x1801733be  add     rdx, rcx
0x1801733c1  cmp     rdx, r8
0x1801733c4  jl      short loc_180173421
0x1801733c6  xor     ecx, ecx; HSTRING
0x1801733c8  call    ?CreateClientIdIfMissing@@YAPEAUHSTRING__@@PEAU1@@Z; CreateClientIdIfMissing(HSTRING__ *)
0x1801733cd  mov     rcx, rax; string
0x1801733d0  xor     edx, edx; length
0x1801733d2  call    cs:__imp_WindowsGetStringRawBuffer
0x1801733d8  mov     rdx, rax; unsigned __int16 *
0x1801733db  lea     r8, [r15+20h]; struct CorrelationVector *
0x1801733df  mov     rcx, r15; this
0x1801733e2  call    ?UnblockLowPriorityWorkItems@InstallQueue2@@QEAAXPEBGAEAVCorrelationVector@@@Z; InstallQueue2::UnblockLowPriorityWorkItems(ushort const *,CorrelationVector &)
0x1801733e7  mov     [rsp+428h+var_3F0], rsi; unsigned __int16 *
0x1801733ec  mov     [rsp+428h+var_3F8], rsi; char *
0x1801733f1  lea     rax, aInstallservice_11; "InstallService UO safeguard unblocked l"...
0x1801733f8  mov     [rsp+428h+var_400], rax; unsigned __int16 *
0x1801733fd  mov     dword ptr [rsp+428h+ppv], 0FFFFFFFFh; int
0x180173405  lea     r9, aInstallqueue2E_0; "InstallQueue2::_EvaluateQueueImpl"
0x18017340c  mov     r8d, 1046h; unsigned int
0x180173412  lea     rdx, aOnecoreuapEndu_22; "onecoreuap\\enduser\\winstore\\installs"...
0x180173419  lea     ecx, [rsi+3]; unsigned int
0x18017341c  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x180173421  mov     rbx, [rsp+428h+var_380]
0x180173429  lea     rcx, [rsp+428h+var_328]
0x180173431  call    ??0?$unordered_map@Uhstring@winrt@@V?$shared_ptr@UQueueItem@InstallQueue2@@@std@@U?$hash@Uhstring@winrt@@@4@U?$equal_to@Uhstring@winrt@@@4@V?$allocator@U?$pair@$$CBUhstring@winrt@@V?$shared_ptr@UQueueItem@InstallQueue2@@@std@@@std@@@4@@std@@QEAA@XZ; std::unordered_map<winrt::hstring,std::shared_ptr<InstallQueue2::QueueItem>>::unordered_map<winrt::hstring,std::shared_ptr<InstallQueue2::QueueItem>>(void)
0x180173436  nop
0x180173437  lea     rdx, [rsp+428h+var_270]
0x18017343f  mov     rcx, r14
0x180173442  call    ?_LockQueueForRead@InstallQueue2@@AEAA?AVshared_lock@@XZ; InstallQueue2::_LockQueueForRead(void)
0x180173447  nop
0x180173448  lea     rcx, [r14+0C8h]
0x18017344f  mov     [rsp+428h+var_390], rcx
0x180173457  lea     rax, [rsp+428h+var_328]
0x18017345f  cmp     rax, rcx
0x180173462  jz      short loc_1801734C6
0x180173464  lea     rax, [rsp+428h+var_328]
0x18017346c  mov     [rsp+428h+var_3C0], rax
0x180173471  mov     eax, [rcx]
0x180173473  mov     [rsp+428h+var_328], eax
0x18017347a  mov     rdx, [rcx+8]
0x18017347e  mov     r8, rdx
0x180173481  mov     rdx, [rdx]
0x180173484  lea     rcx, [rsp+428h+var_320]
0x18017348c  call    ??$_Assign_cast@AEAU?$pair@Uhstring@winrt@@V?$shared_ptr@UQueueItem@InstallQueue2@@@std@@@std@@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUhstring@winrt@@V?$shared_ptr@UQueueItem@InstallQueue2@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@?$list@U?$pair@$$CBUhstring@winrt@@V?$shared_ptr@UQueueItem@InstallQueue2@@@std@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@V?$shared_ptr@UQueueItem@InstallQueue2@@@std@@@std@@@2@@std@@AEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUhstring@winrt@@V?$shared_ptr@UQueueItem@InstallQueue2@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@1@V21@@Z; std::list<std::pair<winrt::hstring const,std::shared_ptr<InstallQueue2::QueueItem>>>::_Assign_cast<std::pair<winrt::hstring,std::shared_ptr<InstallQueue2::QueueItem>> &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,std::shared_ptr<InstallQueue2::QueueItem>>>>,std::_Iterator_base0>>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,std::shared_ptr<InstallQueue2::QueueItem>>>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,std::shared_ptr<InstallQueue2::QueueItem>>>>,std::_Iterator_base0>)
0x180173491  mov     rdx, [rsp+428h+var_318]
0x180173499  lea     rcx, [rsp+428h+var_328]
0x1801734a1  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x1801734a6  mov     rdx, rax
0x1801734a9  lea     rcx, [rsp+428h+var_328]
0x1801734b1  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@Uhstring@winrt@@V?$shared_ptr@UQueueItem@InstallQueue2@@@std@@V?$_Uhash_compare@Uhstring@winrt@@U?$hash@Uhstring@winrt@@@std@@U?$equal_to@Uhstring@winrt@@@4@@4@V?$allocator@U?$pair@$$CBUhstring@winrt@@V?$shared_ptr@UQueueItem@InstallQueue2@@@std@@@std@@@4@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<winrt::hstring,std::shared_ptr<InstallQueue2::QueueItem>,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,std::shared_ptr<InstallQueue2::QueueItem>>>,0>>::_Forced_rehash(unsigned __int64)
0x1801734b6  mov     [rsp+428h+var_3C0], rsi
0x1801734bb  lea     rcx, [rsp+428h+var_3C0]
0x1801734c0  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@Uhstring@winrt@@V?$shared_ptr@UQueueItem@InstallQueue2@@@std@@V?$_Uhash_compare@Uhstring@winrt@@U?$hash@Uhstring@winrt@@@std@@U?$equal_to@Uhstring@winrt@@@4@@4@V?$allocator@U?$pair@$$CBUhstring@winrt@@V?$shared_ptr@UQueueItem@InstallQueue2@@@std@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<winrt::hstring,std::shared_ptr<InstallQueue2::QueueItem>,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,std::shared_ptr<InstallQueue2::QueueItem>>>,0>>::_Clear_guard::~_Clear_guard(void)
0x1801734c5  nop
0x1801734c6  lea     rcx, [rsp+428h+var_270]; this
0x1801734ce  call    ??1shared_lock@@UEAA@XZ; shared_lock::~shared_lock(void)
0x1801734d3  xorps   xmm0, xmm0
0x1801734d6  mov     [rsp+428h+var_2A0], rsi
0x1801734de  movdqu  [rsp+428h+var_2B0], xmm0
0x1801734e7  cmp     [r14+2B8h], sil
0x1801734ee  jnz     loc_18017365D
0x1801734f4  lea     rdx, [rsp+428h+var_270]
0x1801734fc  mov     rcx, r14
0x1801734ff  call    ?_LockQueueForRead@InstallQueue2@@AEAA?AVshared_lock@@XZ; InstallQueue2::_LockQueueForRead(void)
0x180173504  nop
0x180173505  lea     rdx, [r14+108h]
0x18017350c  lea     rcx, [rsp+428h+var_290]
0x180173514  call    ??0?$vector@V?$shared_ptr@UQueueItem@InstallQueue2@@@std@@V?$allocator@V?$shared_ptr@UQueueItem@InstallQueue2@@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::shared_ptr<InstallQueue2::QueueItem>>::vector<std::shared_ptr<InstallQueue2::QueueItem>>(std::vector<std::shared_ptr<InstallQueue2::QueueItem>> const &)
0x180173519  nop
0x18017351a  mov     rbx, [rsp+428h+var_290]
0x180173522  mov     rdi, [rsp+428h+var_290+8]
0x18017352a  cmp     rbx, rdi
0x18017352d  jz      short loc_18017357E
0x18017352f  mov     rcx, [rbx]
0x180173532  add     rcx, 60h ; '`'
0x180173536  call    ?Priority@?$consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkItem@UIInstallServiceWorkItem@Plugin@InstallService@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkItem<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem>::Priority(void)
0x18017353b  cmp     eax, 1
0x18017353e  jnz     short loc_180173578
0x180173540  mov     rcx, qword ptr [rsp+428h+var_2B0+8]
0x180173548  cmp     rcx, [rsp+428h+var_2A0]
0x180173550  jz      short loc_180173565
0x180173552  mov     rdx, rbx
0x180173555  call    ??0?$shared_ptr@VNotificationQueue@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(std::shared_ptr<NotificationQueue> const &)
0x18017355a  add     qword ptr [rsp+428h+var_2B0+8], 10h
0x180173563  jmp     short loc_180173578
0x180173565  mov     r8, rbx
0x180173568  mov     rdx, rcx
0x18017356b  lea     rcx, [rsp+428h+var_2B0]
0x180173573  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@UQueueItem@InstallQueue2@@@std@@@?$vector@V?$shared_ptr@UQueueItem@InstallQueue2@@@std@@V?$allocator@V?$shared_ptr@UQueueItem@InstallQueue2@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@UQueueItem@InstallQueue2@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<InstallQueue2::QueueItem>>::_Emplace_reallocate<std::shared_ptr<InstallQueue2::QueueItem> const &>(std::shared_ptr<InstallQueue2::QueueItem> * const,std::shared_ptr<InstallQueue2::QueueItem> const &)
0x180173578  add     rbx, 10h
0x18017357c  jmp     short loc_18017352A
0x18017357e  lea     rcx, [rsp+428h+var_290]
0x180173586  call    ??1?$vector@V?$shared_ptr@VNotificationQueue@@@std@@V?$allocator@V?$shared_ptr@VNotificationQueue@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<NotificationQueue>>::~vector<std::shared_ptr<NotificationQueue>>(void)
0x18017358b  nop
0x18017358c  lea     rcx, [rsp+428h+var_270]; this
0x180173594  call    ??1shared_lock@@UEAA@XZ; shared_lock::~shared_lock(void)
0x180173599  mov     rax, qword ptr [rsp+428h+var_2B0+8]
0x1801735a1  cmp     qword ptr [rsp+428h+var_2B0], rax
0x1801735a9  jz      loc_180173644
0x1801735af  mov     rdx, r14; struct InstallQueue2 *
0x1801735b2  lea     rcx, [rsp+428h+var_2E8]; this
0x1801735ba  call    ??0exclusive_lock@InstallQueue2@@QEAA@PEAV1@@Z; InstallQueue2::exclusive_lock::exclusive_lock(InstallQueue2 *)
0x1801735bf  or      r12d, 2
0x1801735c3  mov     [rsp+428h+var_3B8], r12d
0x1801735c8  mov     dword ptr [rsp+428h+var_398], r12d
0x1801735d0  mov     rbx, qword ptr [rsp+428h+var_2B0]
0x1801735d8  mov     rdi, qword ptr [rsp+428h+var_2B0+8]
0x1801735e0  cmp     rbx, rdi
0x1801735e3  jz      short loc_180173636
0x1801735e5  mov     dword ptr [rsp+428h+var_3C0], 4
0x1801735ed  mov     dword ptr [rsp+428h+var_3C0+4], 2
0x1801735f5  mov     rdx, rbx
0x1801735f8  lea     rcx, [rsp+428h+var_250]
0x180173600  call    ??0?$shared_ptr@VNotificationQueue@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(std::shared_ptr<NotificationQueue> const &)
0x180173605  lea     r9, [r14+20h]
0x180173609  lea     rcx, [rsp+428h+var_3C0]
0x18017360e  mov     [rsp+428h+var_400], rcx
0x180173613  mov     [rsp+428h+ppv], rax
0x180173618  lea     r8, [rsp+428h+var_2E8]
0x180173620  lea     rdx, [rsp+428h+var_370]
0x180173628  mov     rcx, r14
0x18017362b  call    ?_SwitchState@InstallQueue2@@AEAA?AUQueueItemState@1@AEAUexclusive_lock@1@AEAVCorrelationVector@@V?$shared_ptr@UQueueItem@InstallQueue2@@@std@@U21@@Z; InstallQueue2::_SwitchState(InstallQueue2::exclusive_lock &,CorrelationVector &,std::shared_ptr<InstallQueue2::QueueItem>,InstallQueue2::QueueItemState)
0x180173630  add     rbx, 10h
0x180173634  jmp     short loc_1801735E0
0x180173636  lea     rcx, [rsp+428h+var_2E8]
0x18017363e  call    ??1?$exclusive_lock_with_release_callback@VInstallQueue2@@P81@EAAXX_E@@UEAA@XZ
0x180173643  nop
0x180173644  lea     rcx, [rsp+428h+var_2B0]
0x18017364c  call    ??1?$vector@V?$shared_ptr@VNotificationQueue@@@std@@V?$allocator@V?$shared_ptr@VNotificationQueue@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<NotificationQueue>>::~vector<std::shared_ptr<NotificationQueue>>(void)
0x180173651  lea     r13, [r15+168h]
0x180173658  jmp     loc_180173B6E
0x18017365d  lea     rdx, [rsp+428h+var_270]
0x180173665  mov     rcx, r14
0x180173668  call    ?_LockQueueForRead@InstallQueue2@@AEAA?AVshared_lock@@XZ; InstallQueue2::_LockQueueForRead(void)
0x18017366d  nop
0x18017366e  lea     r13, [rbx+168h]
0x180173675  mov     rdx, r13
0x180173678  lea     rcx, [rsp+428h+var_290]
0x180173680  call    ??0?$vector@V?$shared_ptr@UQueueItem@InstallQueue2@@@std@@V?$allocator@V?$shared_ptr@UQueueItem@InstallQueue2@@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::shared_ptr<InstallQueue2::QueueItem>>::vector<std::shared_ptr<InstallQueue2::QueueItem>>(std::vector<std::shared_ptr<InstallQueue2::QueueItem>> const &)
0x180173685  nop
0x180173686  mov     rbx, [rsp+428h+var_290]
0x18017368e  mov     rdi, [rsp+428h+var_290+8]
0x180173696  cmp     rbx, rdi
0x180173699  jz      short loc_1801736F3
0x18017369b  mov     rcx, [rbx]
0x18017369e  add     rcx, 60h ; '`'
0x1801736a2  call    ?Priority@?$consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkItem@UIInstallServiceWorkItem@Plugin@InstallService@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkItem<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem>::Priority(void)
0x1801736a7  cmp     eax, 1
0x1801736aa  jnz     short loc_1801736ED
0x1801736ac  mov     rax, [rbx]
0x1801736af  cmp     dword ptr [rax+1Ch], 2
0x1801736b3  jnz     short loc_1801736ED
0x1801736b5  mov     rcx, qword ptr [rsp+428h+var_2B0+8]
0x1801736bd  cmp     rcx, [rsp+428h+var_2A0]
0x1801736c5  jz      short loc_1801736DA
0x1801736c7  mov     rdx, rbx
0x1801736ca  call    ??0?$shared_ptr@VNotificationQueue@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(std::shared_ptr<NotificationQueue> const &)
0x1801736cf  add     qword ptr [rsp+428h+var_2B0+8], 10h
0x1801736d8  jmp     short loc_1801736ED
0x1801736da  mov     r8, rbx
0x1801736dd  mov     rdx, rcx
0x1801736e0  lea     rcx, [rsp+428h+var_2B0]
0x1801736e8  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@UQueueItem@InstallQueue2@@@std@@@?$vector@V?$shared_ptr@UQueueItem@InstallQueue2@@@std@@V?$allocator@V?$shared_ptr@UQueueItem@InstallQueue2@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@UQueueItem@InstallQueue2@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<InstallQueue2::QueueItem>>::_Emplace_reallocate<std::shared_ptr<InstallQueue2::QueueItem> const &>(std::shared_ptr<InstallQueue2::QueueItem> * const,std::shared_ptr<InstallQueue2::QueueItem> const &)
0x1801736ed  add     rbx, 10h
0x1801736f1  jmp     short loc_180173696
0x1801736f3  lea     rcx, [rsp+428h+var_290]
0x1801736fb  call    ??1?$vector@V?$shared_ptr@VNotificationQueue@@@std@@V?$allocator@V?$shared_ptr@VNotificationQueue@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<NotificationQueue>>::~vector<std::shared_ptr<NotificationQueue>>(void)
0x180173700  nop
0x180173701  lea     rcx, [rsp+428h+var_270]; this
0x180173709  call    ??1shared_lock@@UEAA@XZ; shared_lock::~shared_lock(void)
0x18017370e  mov     r15, qword ptr [rsp+428h+var_2B0+8]
0x180173716  mov     rbx, qword ptr [rsp+428h+var_2B0]
0x18017371e  cmp     rbx, r15
0x180173721  jz      loc_1801738DA
0x180173727  cmp     rbx, r15
0x18017372a  jz      loc_180173B61
0x180173730  mov     rdx, r14; struct InstallQueue2 *
0x180173733  lea     rcx, [rsp+428h+var_230]; this
0x18017373b  call    ??0exclusive_lock@InstallQueue2@@QEAA@PEAV1@@Z; InstallQueue2::exclusive_lock::exclusive_lock(InstallQueue2 *)
0x180173740  or      r12d, 4
0x180173744  mov     [rsp+428h+var_3B8], r12d
0x180173749  mov     dword ptr [rsp+428h+var_398], r12d
0x180173751  mov     [rsp+428h+var_3C0], rsi
0x180173756  mov     rdx, rbx
0x180173759  lea     rcx, [rsp+428h+var_250]
0x180173761  call    ??0?$shared_ptr@VNotificationQueue@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(std::shared_ptr<NotificationQueue> const &)
0x180173766  lea     r9, [r14+20h]
0x18017376a  lea     rcx, [rsp+428h+var_3C0]
0x18017376f  mov     [rsp+428h+var_400], rcx
0x180173774  mov     [rsp+428h+ppv], rax
0x180173779  lea     r8, [rsp+428h+var_230]
0x180173781  lea     rdx, [rsp+428h+var_370]
0x180173789  mov     rcx, r14
0x18017378c  call    ?_SwitchState@InstallQueue2@@AEAA?AUQueueItemState@1@AEAUexclusive_lock@1@AEAVCorrelationVector@@V?$shared_ptr@UQueueItem@InstallQueue2@@@std@@U21@@Z; InstallQueue2::_SwitchState(InstallQueue2::exclusive_lock &,CorrelationVector &,std::shared_ptr<InstallQueue2::QueueItem>,InstallQueue2::QueueItemState)
0x180173791  lea     rcx, [rsp+428h+var_230]
0x180173799  call    ?release@?$exclusive_lock_with_release_callback@VInstallQueue2@@P81@EAAXX_E@@UEAAXXZ
0x18017379e  mov     rdi, [rbx]
0x1801737a1  mov     rcx, [rsp+428h+var_380]
0x1801737a9  movups  xmm0, xmmword ptr [rcx+28h]
0x1801737ad  movups  [rsp+428h+var_1D8], xmm0
0x1801737b5  movups  xmm1, xmmword ptr [rcx+38h]
0x1801737b9  movups  [rsp+428h+var_1C8], xmm1
0x1801737c1  movups  xmm0, xmmword ptr [rcx+48h]
0x1801737c5  movups  [rsp+428h+var_1B8], xmm0
0x1801737cd  movups  xmm1, xmmword ptr [rcx+58h]
0x1801737d1  movups  [rsp+428h+var_1A8], xmm1
0x1801737d9  movups  xmm0, xmmword ptr [rcx+68h]
0x1801737dd  movups  [rsp+428h+var_198], xmm0
0x1801737e5  movups  xmm1, xmmword ptr [rcx+78h]
0x1801737e9  movups  [rsp+428h+var_188], xmm1
0x1801737f1  movups  xmm0, xmmword ptr [rcx+88h]
0x1801737f8  movups  [rsp+428h+var_178], xmm0
0x180173800  movups  xmm1, xmmword ptr [rcx+98h]
0x180173807  movups  [rsp+428h+var_168], xmm1
0x18017380f  mov     al, [rcx+0A8h]
0x180173815  mov     [rsp+428h+var_158], al
0x18017381c  lea     rdx, [rcx+0B0h]; struct winrt::hstring *
0x180173823  lea     rcx, [rsp+428h+var_150]; this
0x18017382b  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x180173830  nop
0x180173831  cmp     [rsp+428h+var_150], rsi
0x180173839  jnz     short loc_180173875
0x18017383b  mov     eax, 81h
0x180173840  mov     [rsp+428h+ppv], rax
0x180173845  lea     r9, [rsp+428h+var_1D8]
0x18017384d  mov     r8d, eax
0x180173850  lea     rdx, [rsp+428h+var_148]
0x180173858  xor     ecx, ecx
0x18017385a  call    cs:__imp__o_mbstowcs_s
0x180173860  lea     rdx, [rsp+428h+var_148]
0x180173868  lea     rcx, [rsp+428h+var_150]
0x180173870  call    ??4hstring@winrt@@QEAAAEAU01@QEBG@Z; winrt::hstring::operator=(ushort const * const)
0x180173875  lea     rdx, [rsp+428h+var_150]; struct winrt::hstring *
0x18017387d  lea     rcx, [rsp+428h+var_3B0]; this
0x180173882  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x180173887  nop
0x180173888  mov     rax, [rax]
0x18017388b  mov     [rsp+428h+var_270], rax
0x180173893  mov     r8d, 1
0x180173899  lea     rdx, [rsp+428h+var_270]
0x1801738a1  lea     rcx, [rdi+60h]
0x1801738a5  call    ?UserOverrideRequestedForBlockedState@?$consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkItem@UIInstallServiceWorkItem@Plugin@InstallService@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@H@Z; winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkItem<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem>::UserOverrideRequestedForBlockedState(winrt::param::hstring const &,int)
0x1801738aa  nop
0x1801738ab  lea     rcx, [rsp+428h+var_3B0]
0x1801738b0  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1801738b5  nop
0x1801738b6  lea     rcx, [rsp+428h+var_150]
0x1801738be  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1801738c3  nop
0x1801738c4  lea     rcx, [rsp+428h+var_230]
0x1801738cc  call    ??1?$exclusive_lock_with_release_callback@VInstallQueue2@@P81@EAAXX_E@@UEAA@XZ
0x1801738d1  add     rbx, 10h
0x1801738d5  jmp     loc_180173727
0x1801738da  lea     rax, aEvaluatingWhet; "Evaluating whether low priority items h"...
0x1801738e1  mov     [rsp+428h+var_3A8], rax
0x1801738e9  mov     [rsp+428h+var_3A8+8], 35h ; '5'
0x1801738f5  lea     rdx, aInstallqueue2E_0; "InstallQueue2::_EvaluateQueueImpl"
0x1801738fc  lea     rcx, [rsp+428h+var_290]
  ... truncated ...
```
