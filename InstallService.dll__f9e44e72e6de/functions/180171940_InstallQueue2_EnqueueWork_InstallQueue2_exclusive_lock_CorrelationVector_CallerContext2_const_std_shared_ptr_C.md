# InstallQueue2::_EnqueueWork(InstallQueue2::exclusive_lock &&,CorrelationVector &,CallerContext2 const &,std::shared_ptr<CatalogDataStore::CatalogItem>,winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem,std::shared_ptr<CheckpointData::Data>,bool)

- ea: `0x180171940`
- end: `0x1801732eb`
- name: `?_EnqueueWork@InstallQueue2@@AEAA?AV?$tuple@V?$vector@UInstallItem@Internal@WindowsUpdate@winrt@@V?$allocator@UInstallItem@Internal@WindowsUpdate@winrt@@@std@@@std@@V?$shared_ptr@UQueueItem@InstallQueue2@@@2@@std@@$$QEAUexclusive_lock@1@AEAVCorrelationVector@@AEBUCallerContext2@@V?$shared_ptr@UCatalogItem@CatalogDataStore@@@3@UIInstallServiceWorkItem@Plugin@InstallService@Internal@Windows@winrt@@V?$shared_ptr@UData@CheckpointData@@@3@_N@Z`
- size: `6571`
- prototype: `__int64 __usercall@<rax>(InstallQueue2 *this@<rcx>, __int64, __int64, __int64, __int64, char)`
- caller_count: `5`
- callee_count: `98`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18015b974`
- `0x18015c8e4`
- `0x18015db2c`
- `0x18015ed00`
- `0x1801765a8`

## callees

- `0x180009ea0`
- `0x1800127c8`
- `0x180020868`
- `0x1800208e4`
- `0x180022298`
- `0x180022e50`
- `0x18002d98c`
- `0x18002ec2c`
- `0x180037200`
- `0x1800378d0`
- `0x180044b84`
- `0x180044cb8`
- `0x180045338`
- `0x1800453a0`
- `0x1800453bc`
- `0x180045588`
- `0x1800532fc`
- `0x180053e24`
- `0x18005a910`
- `0x180067ca8`
- `0x18006cc00`
- `0x18006cc2c`
- `0x18006cf2c`
- `0x18006d98c`
- `0x18007a814`
- `0x18007aa00`
- `0x18007c3c4`
- `0x180095b68`
- `0x180097bfc`
- `0x180097cbc`
- `0x18009930c`
- `0x180099350`
- `0x18009937c`
- `0x1800a5114`
- `0x1800b063c`
- `0x1800b1e24`
- `0x1800b356c`
- `0x1800b7b08`
- `0x1800d32d0`
- `0x1801020b4`
- `0x180138ec8`
- `0x180148e14`
- `0x180149004`
- `0x1801497cc`
- `0x18014b45c`
- `0x18014fd30`
- `0x18014fe70`
- `0x180152e98`
- `0x180152fd0`
- `0x180153498`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs_s` at `0x18017219a`
- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs_s` at `0x18017219a`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180171b66`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180171b66`
- `msvcp_win!_Xtime_get_ticks` at `0x180171b06`
- `msvcp_win!_Xtime_get_ticks` at `0x180171b06`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801728e7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801728e7`

## string_xrefs

- `0x180172972`: `StartStoreUpdates`
- `0x180172966`: `PauseStoreUpdates`
- `0x180172979`: `%systemroot%\System32\usoclient.exe`
- `0x180171e3d`: `onecoreuap\enduser\winstore\installservice\libqueue2\installqueue2.cpp`
- `0x18017203c`: `onecoreuap\enduser\winstore\installservice\libqueue2\installqueue2.cpp`
- `0x1801722a4`: `onecoreuap\enduser\winstore\installservice\libqueue2\installqueue2.cpp`
- `0x180172374`: `onecoreuap\enduser\winstore\installservice\libqueue2\installqueue2.cpp`
- `0x1801729d2`: `onecoreuap\enduser\winstore\installservice\libqueue2\installqueue2.cpp`
- `0x180172af7`: `onecoreuap\enduser\winstore\installservice\libqueue2\installqueue2.cpp`
- `0x180173171`: `onecoreuap\enduser\winstore\installservice\libqueue2\installqueue2.cpp`
- `0x1801732c7`: `onecoreuap\enduser\winstore\installservice\libqueue2\installqueue2.cpp`
- `0x1801732d9`: `onecoreuap\enduser\winstore\installservice\libqueue2\installqueue2.cpp`
- `0x180171e28`: `InstallQueue2::_EnqueueWork`
- `0x180172027`: `InstallQueue2::_EnqueueWork`
- `0x18017228f`: `InstallQueue2::_EnqueueWork`
- `0x18017235f`: `InstallQueue2::_EnqueueWork`
- `0x1801729c5`: `InstallQueue2::_EnqueueWork`
- `0x180172ae2`: `InstallQueue2::_EnqueueWork`
- `0x18017315c`: `InstallQueue2::_EnqueueWork`
- `0x180171e0d`: `Work already enqueued. Refusing to queue duplicate work`
- `0x1801729b1`: `Scheduled work with UO from for a LowPriority Install`
- `0x180172274`: `Attempting to move existing work item out of idle state: `
- `0x180172ac7`: `Item inserted into the queue. Attempting to create progresstrackers`

## pseudocode

```c
// Hidden C++ exception states: #wind=60
__int64 __fastcall InstallQueue2::_EnqueueWork(
        InstallQueue2 *this,
        __int64 a2,
        __int64 a3,
        char *a4,
        struct CallerContext2 *a5,
        _QWORD *a6,
        void *a7,
        __int64 a8,
        char a9)
{
  char *v9; // r13
  __int64 v10; // r12
  InstallQueue2 *v11; // r15
  void *v12; // rbx
  int v13; // esi
  const struct store_lock *v14; // rdx
  int AvailableOperationsCount; // eax
  _QWORD *v16; // rax
  const struct store_lock *v17; // rdx
  unsigned int v18; // ecx
  __int64 *v19; // rdi
  __int64 v20; // rbx
  __int64 v21; // rbx
  BOOL (__stdcall *v22)(PINIT_ONCE, PVOID, PVOID *); // rdx
  union _RTL_RUN_ONCE *v23; // rcx
  __int64 v24; // rdi
  _QWORD *v25; // rdi
  _QWORD *i; // rbx
  __int64 v27; // rax
  __int64 v28; // rax
  char v29; // al
  int v30; // r9d
  struct winrt::hstring *v31; // rbx
  __int64 v32; // rcx
  __int64 v33; // r9
  __int64 v34; // rbx
  int v35; // r9d
  __int64 v36; // rax
  std::_Ref_count_base *v37; // rbx
  __int64 v38; // rax
  int v39; // r9d
  int v40; // r8d
  int v41; // esi
  __int64 v42; // rax
  _QWORD *v43; // rbx
  std::_Ref_count_base *v44; // rax
  int v45; // esi
  int v46; // esi
  __int64 v47; // rax
  std::_Ref_count_base *v48; // rcx
  __int64 v49; // rdx
  __int64 v50; // rax
  std::_Ref_count_base *v51; // r8
  __int64 v52; // rax
  __int64 v53; // rdx
  std::_Ref_count_base *v54; // rcx
  unsigned int v55; // edi
  unsigned int v56; // r12d
  int v57; // edi
  int v58; // eax
  int v59; // edx
  int v60; // eax
  int v61; // edx
  int v62; // eax
  int v63; // edx
  std::_Ref_count_base *v64; // rax
  _QWORD *v65; // rax
  int v66; // eax
  LPVOID *v67; // rbx
  char *v68; // r8
  char *v69; // r13
  char *v70; // r15
  int v71; // eax
  std::_Ref_count_base *v72; // rcx
  char *v73; // r15
  ScheduledTask *v74; // rbx
  int v75; // eax
  std::_Ref_count_base *v76; // rcx
  const struct CheckpointData::Data *v77; // rdx
  LPVOID v78; // rcx
  __int64 v79; // rax
  int v80; // esi
  winrt::hstring *v81; // rax
  const wchar_t *v82; // rax
  char v83; // bl
  unsigned int v84; // eax
  unsigned int v85; // eax
  unsigned int v86; // eax
  const char *v87; // r8
  int v88; // r8d
  int v89; // esi
  __int64 v90; // rbx
  __int64 v91; // rax
  __int64 *NamedString; // rax
  __int16 v93; // si
  __int64 v94; // rcx
  _QWORD *v95; // rdi
  __int64 v96; // rax
  __int64 v97; // r8
  __int64 v98; // rdx
  __int64 v99; // rdx
  std::_Ref_count_base *v100; // rax
  void (__fastcall ***v101)(_QWORD, __int64 *, void **); // rcx
  unsigned int j; // ebx
  __int64 v103; // rsi
  __int64 Value; // rdi
  __int64 v105; // rax
  __int64 v106; // rax
  __int64 v107; // r8
  __int64 v108; // rdx
  __int64 v109; // rbx
  __int64 *v110; // rsi
  __int64 v111; // r13
  __int64 v112; // rax
  char IsEnabled; // al
  __int64 *v114; // rcx
  __int64 v115; // rax
  __int64 v116; // r9
  __int64 v117; // rdx
  __int64 v118; // rcx
  __int64 v119; // rcx
  std::_Ref_count_base *v120; // rcx
  std::_Ref_count_base *v121; // rcx
  __int64 v123; // rax
  int ppv; // [rsp+20h] [rbp-3E8h]
  int ppva; // [rsp+20h] [rbp-3E8h]
  char *v126; // [rsp+28h] [rbp-3E0h]
  int v127; // [rsp+30h] [rbp-3D8h]
  __int64 v128; // [rsp+50h] [rbp-3B8h] BYREF
  char v129; // [rsp+58h] [rbp-3B0h]
  LPVOID v130; // [rsp+60h] [rbp-3A8h] BYREF
  std::_Ref_count_base *v131[2]; // [rsp+68h] [rbp-3A0h] BYREF
  unsigned __int64 v132; // [rsp+78h] [rbp-390h] BYREF
  struct winrt::hstring *v133; // [rsp+80h] [rbp-388h] BYREF
  ScheduledTask *v134; // [rsp+88h] [rbp-380h] BYREF
  std::_Ref_count_base *v135; // [rsp+90h] [rbp-378h]
  char *v136; // [rsp+98h] [rbp-370h] BYREF
  int v137; // [rsp+A0h] [rbp-368h]
  _BYTE *v138; // [rsp+A8h] [rbp-360h] BYREF
  InstallQueue2 *v139; // [rsp+B0h] [rbp-358h] BYREF
  __int64 *v140; // [rsp+B8h] [rbp-350h] BYREF
  _QWORD *v141; // [rsp+C0h] [rbp-348h]
  std::_Ref_count_base *v142[2]; // [rsp+D0h] [rbp-338h] BYREF
  void *v143; // [rsp+F0h] [rbp-318h]
  __int64 v144; // [rsp+F8h] [rbp-310h] BYREF
  char v145[8]; // [rsp+100h] [rbp-308h] BYREF
  __int64 v146; // [rsp+108h] [rbp-300h] BYREF
  char *v147; // [rsp+110h] [rbp-2F8h]
  char v148[8]; // [rsp+120h] [rbp-2E8h] BYREF
  char v149[8]; // [rsp+128h] [rbp-2E0h] BYREF
  struct CallerContext2 *v150; // [rsp+130h] [rbp-2D8h]
  InstallQueue2 *v151; // [rsp+138h] [rbp-2D0h]
  __int64 v152; // [rsp+140h] [rbp-2C8h]
  _QWORD *v153; // [rsp+148h] [rbp-2C0h]
  char v154[8]; // [rsp+150h] [rbp-2B8h] BYREF
  _BYTE v155[16]; // [rsp+158h] [rbp-2B0h] BYREF
  __int64 v156; // [rsp+168h] [rbp-2A0h]
  __int64 v157; // [rsp+170h] [rbp-298h]
  __int64 v158; // [rsp+178h] [rbp-290h]
  __int64 *v159; // [rsp+180h] [rbp-288h]
  char v160[8]; // [rsp+188h] [rbp-280h] BYREF
  char v161[8]; // [rsp+190h] [rbp-278h] BYREF
  char v162[8]; // [rsp+198h] [rbp-270h] BYREF
  __int128 v163; // [rsp+1A0h] [rbp-268h] BYREF
  __int64 v164; // [rsp+1B0h] [rbp-258h]
  _BYTE v165[32]; // [rsp+1B8h] [rbp-250h] BYREF
  __int64 v166; // [rsp+1D8h] [rbp-230h] BYREF
  __int128 v167; // [rsp+1E0h] [rbp-228h]
  _BYTE v168[40]; // [rsp+1F8h] [rbp-210h] BYREF
  unsigned __int16 v169[8]; // [rsp+220h] [rbp-1E8h] BYREF
  __int128 v170; // [rsp+230h] [rbp-1D8h]
  __int128 v171; // [rsp+240h] [rbp-1C8h]
  __int128 v172; // [rsp+250h] [rbp-1B8h]
  __int128 v173; // [rsp+260h] [rbp-1A8h]
  __int128 v174; // [rsp+270h] [rbp-198h]
  __int128 v175; // [rsp+280h] [rbp-188h]
  __int128 v176; // [rsp+290h] [rbp-178h]
  char v177; // [rsp+2A0h] [rbp-168h]
  __int64 v178; // [rsp+2A8h] [rbp-160h] BYREF
  _BYTE v179[272]; // [rsp+2B0h] [rbp-158h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+408h] [rbp+0h]

  v9 = a4;
  v136 = a4;
  v10 = a3;
  v138 = (_BYTE *)a3;
  v146 = a2;
  v11 = this;
  v139 = this;
  v151 = this;
  v156 = a2;
  v152 = a3;
  v147 = a4;
  v150 = a5;
  v141 = a6;
  v157 = (__int64)a6;
  v12 = a7;
  v143 = a7;
  v159 = (__int64 *)a7;
  v144 = a8;
  v158 = a8;
  v13 = 0;
  v137 = 0;
  if ( InstallQueue2::_serviceStop )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x794,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp",
      InstallQueue2::_serviceStop ? (const char *)0x803FB016LL : 0,
      ppv);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhanceFulfillmentInitiateEvent>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnhanceFulfillmentInitiateEvent>::GetImpl'::`2'::impl)
    && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_QueueStateInfoEvent>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_QueueStateInfoEvent>::GetImpl'::`2'::impl) )
  {
    AvailableOperationsCount = InstallQueue2::GetAvailableOperationsCount(v11, v14);
    WindowsUpdate::CommonTelemetry::QueueStateInfo(
      (WindowsUpdate::CommonTelemetry *)*((unsigned int *)v11 + 54),
      (__int64)(*((_QWORD *)v11 + 37) - *((_QWORD *)v11 + 36)) >> 4,
      (__int64)(*((_QWORD *)v11 + 34) - *((_QWORD *)v11 + 33)) >> 4,
      (__int64)(*((_QWORD *)v11 + 46) - *((_QWORD *)v11 + 45)) >> 4,
      AvailableOperationsCount,
      0,
      v127);
  }
  v130 = 0;
  v16 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<TipTests::_tip_QueueStuckTipTest,TipTests::_tip_QueueStuckTipTest>>::ensure_data(&v130);
  tip2::details::shared_data<1,0,0>::start(*v16 + 8LL, &v166);
  v153 = (_QWORD *)((char *)v11 + 264);
  v18 = InstallQueue2::GetAvailableOperationsCount(v11, v17);
  LODWORD(v133) = v18;
  v140 = (__int64 *)*((_QWORD *)v11 + 34);
  v19 = (__int64 *)*((_QWORD *)v11 + 33);
  if ( v19 != v140 && v18 )
  {
    while ( 1 )
    {
      v20 = *v19;
      v21 = (_Xtime_get_ticks() - *(_QWORD *)(v20 + 104)) / 10000000;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CatalogCacheImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CatalogCacheImprovements>::GetImpl'::`2'::impl) )
      {
        v22 = InitializeOneSettingsConfiguration;
        v23 = &stru_1802E4F70;
      }
      else
      {
        v22 = InitializeInstallServiceConfiguration;
        v23 = &InitOnce;
      }
      InitOnceExecuteOnce(v23, v22, 0, 0);
      if ( v21 >= qword_1802CA678 )
        break;
      v19 += 2;
      if ( v19 == v140 )
        goto LABEL_16;
    }
    v24 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<TipTests::_tip_QueueStuckTipTest,TipTests::_tip_QueueStuckTipTest>>::ensure_data(&v130);
    v140 = (__int64 *)v24;
    if ( v24 )
      _InterlockedIncrement((volatile signed __int32 *)(v24 + 280));
    tip2::details::shared_data<1,0,0>::begin_update(v24 + 8);
    *(_BYTE *)(v24 + 272) = 1;
    tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_QueueStuckTipTest,TipTests::_tip_QueueStuckTipTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_QueueStuckTipTest,TipTests::_tip_QueueStuckTipTest>>(&v140);
    *(_OWORD *)v169 = *(_OWORD *)(v9 + 8);
    v170 = *(_OWORD *)(v9 + 24);
    v171 = *(_OWORD *)(v9 + 40);
    v172 = *(_OWORD *)(v9 + 56);
    v173 = *(_OWORD *)(v9 + 72);
    v174 = *(_OWORD *)(v9 + 88);
    v175 = *(_OWORD *)(v9 + 104);
    v176 = *(_OWORD *)(v9 + 120);
    v177 = v9[136];
    winrt::hstring::hstring((winrt::hstring *)&v178, (const struct winrt::hstring *)(v9 + 144));
    WindowsUpdate::CommonTelemetry::QueueStuckError(
      (WindowsUpdate::CommonTelemetry *)*((unsigned int *)v11 + 54),
      (__int64)(v153[1] - *v153) >> 4,
      (int)v133,
      v21,
      (__int64)v169,
      v126);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v178);
LABEL_16:
    v12 = v143;
  }
  if ( v130 )
    tip2::details::shared_data<1,0,0>::complete_without_lock((char *)v130 + 8);
  wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_QueueStuckTipTest,TipTests::_tip_QueueStuckTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_QueueStuckTipTest,TipTests::_tip_QueueStuckTipTest>,wil::err_returncode_policy>(&v130);
  v163 = 0;
  v164 = 0;
  *(_OWORD *)v131 = 0;
  winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_Internal_IOEMHardwareInfo<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IOEMHardwareInfo>::OemId(
    v12,
    &v140);
  winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkItemSubTask<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItemSubTask>::SearchId(
    v12,
    v145);
  winrt::hstring::hstring((winrt::hstring *)v148, (const struct winrt::hstring *)&v140);
  winrt::hstring::hstring((winrt::hstring *)v149, (const struct winrt::hstring *)v145);
  v25 = (_QWORD *)*((_QWORD *)v11 + 26);
  for ( i = (_QWORD *)*v25; i != v25; i = (_QWORD *)*i )
  {
    v133 = (struct winrt::hstring *)(i + 2);
    v128 = 0;
    v13 |= 1u;
    v137 = v13;
    if ( (unsigned __int8)winrt::Windows::Foundation::operator==(i[3] + 96LL, &v128)
      || (v27 = winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkItemSubTask<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItemSubTask>::SearchId(
                  i[3] + 96LL,
                  &v130),
          v13 |= 2u,
          v137 = v13,
          !(unsigned __int8)winrt::operator==(v27, v145))
      || (v28 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_Internal_IOEMHardwareInfo<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IOEMHardwareInfo>::OemId(
                  i[3] + 96LL,
                  &v132),
          v13 |= 4u,
          v29 = winrt::operator==(v28, &v140),
          v129 = 1,
          !v29) )
    {
      v129 = 0;
    }
    if ( (v13 & 4) != 0 )
    {
      v13 &= ~4u;
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v132);
    }
    if ( (v13 & 2) != 0 )
    {
      v13 &= ~2u;
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v130);
    }
    if ( (v13 & 1) != 0 )
      v13 &= ~1u;
    if ( v129 )
    {
      v134 = (ScheduledTask *)L"Work already enqueued. Refusing to queue duplicate work";
      v135 = (std::_Ref_count_base *)55;
      std::string::string(v168, "InstallQueue2::_EnqueueWork");
      std::string::string(&v166, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp");
      Logging::Log<Logging::CatalogSearchInfo &>(
        (unsigned int)&v166,
        2002,
        (unsigned int)v168,
        v30,
        (__int64)&v134,
        (__int64)v148);
      std::string::~string(&v166);
      std::string::~string(v168);
      v31 = v133;
      std::shared_ptr<CheckpointData::Data>::operator=(v131, (char *)v133 + 8);
      v32 = *((_QWORD *)v131[0] + 10);
      if ( v32 == *((_QWORD *)v131[0] + 11) )
      {
        std::vector<std::shared_ptr<InstallItemData>>::_Emplace_reallocate<std::shared_ptr<InstallItemData> const &>(
          (char *)v131[0] + 72,
          *((_QWORD *)v131[0] + 10),
          v141);
      }
      else
      {
        std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(v32, v141);
        *(_QWORD *)(v33 + 80) += 16LL;
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixAcquisitionToWorkingDedupTIP>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixAcquisitionToWorkingDedupTIP>::GetImpl'::`2'::impl)
        && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AcquisitionEnqueueToWorkingDelayTip>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AcquisitionEnqueueToWorkingDelayTip>::GetImpl'::`2'::impl) )
      {
        std::_Hash<std::_Umap_traits<winrt::hstring,winrt::hstring,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,winrt::hstring>>,0>>::find(
          (char *)v11 + 712,
          &v128,
          *v141 + 24LL);
        v34 = v128;
        if ( v128 != *((_QWORD *)v11 + 90) )
        {
          *(_OWORD *)v142 = *(_OWORD *)(v128 + 24);
          tip2::tip_test<tip2::details::merged_data<TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest,TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest>>::tip_test<tip2::details::merged_data<TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest,TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest>>(
            &v130,
            v142);
          *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest,TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest>>::operator->(
                                  &v130,
                                  &v128)
                   + 272LL) = 1;
          tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest,TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest,TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest>>(&v128);
          *(_QWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest,TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest>>::operator->(
                                   &v130,
                                   &v128)
                    + 280LL) = 0;
          tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest,TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest,TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest>>(&v128);
          if ( v130 )
            tip2::details::shared_data<1,0,0>::complete_without_lock((char *)v130 + 8);
          std::_Hash<std::_Umap_traits<winrt::hstring,InstallQueue2::EnqueueToWorkingDelayTipData,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,InstallQueue2::EnqueueToWorkingDelayTipData>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,InstallQueue2::EnqueueToWorkingDelayTipData>>>>,0>(
            (char *)v11 + 712,
            &v134,
            v34);
          wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest,TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest,TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest>,wil::err_returncode_policy>(&v130);
        }
        v31 = v133;
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixPausedItemDedup>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixPausedItemDedup>::GetImpl'::`2'::impl) )
      {
        if ( *((_DWORD *)v131[0] + 6) == 4 )
        {
          v134 = (ScheduledTask *)L"Resuming existing idle work item: ";
          v135 = (std::_Ref_count_base *)34;
          std::string::string(v168, "InstallQueue2::_EnqueueWork");
          std::string::string(&v166, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp");
          Logging::Log<Logging::CatalogSearchInfo &>(
            (unsigned int)&v166,
            2029,
            (unsigned int)v168,
            v35,
            (__int64)&v134,
            (__int64)v148);
          std::string::~string(&v166);
          std::string::~string(v168);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WorkReleaseDeadlock>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WorkReleaseDeadlock>::GetImpl'::`2'::impl) )
          {
            v36 = std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(v142, v131);
            InstallQueue2::_DelayRelease(v11, v10, v36);
          }
          else
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
          }
          v37 = v131[0];
          *(_OWORD *)v169 = *(_OWORD *)(v9 + 8);
          v170 = *(_OWORD *)(v9 + 24);
          v171 = *(_OWORD *)(v9 + 40);
          v172 = *(_OWORD *)(v9 + 56);
          v173 = *(_OWORD *)(v9 + 72);
          v174 = *(_OWORD *)(v9 + 88);
          v175 = *(_OWORD *)(v9 + 104);
          v176 = *(_OWORD *)(v9 + 120);
          v177 = v9[136];
          winrt::hstring::hstring((winrt::hstring *)&v178, (const struct winrt::hstring *)(v9 + 144));
          if ( !v178 )
          {
            _o_mbstowcs_s(0, v179, 129, v169, 129);
            winrt::hstring::operator=(&v178, v179);
          }
          v166 = *(_QWORD *)winrt::hstring::hstring((winrt::hstring *)&v128, (const struct winrt::hstring *)&v178);
          winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkItem<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem>::UserOverrideRequestedForBlockedState(
            (char *)v37 + 96,
            &v166,
            0);
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v128);
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v178);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
          if ( *((_DWORD *)v131[0] + 6) == 4 )
          {
            v128 = 0;
            v38 = std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(v142, v131);
            InstallQueue2::_SwitchState((_DWORD)v11, (unsigned int)&v134, v10, (_DWORD)v9, v38, (__int64)&v128);
          }
        }
      }
      else if ( *((_DWORD *)v131[0] + 6) == 4 && !*((_DWORD *)v131[0] + 7) )
      {
        v134 = (ScheduledTask *)L"Attempting to move existing work item out of idle state: ";
        v135 = (std::_Ref_count_base *)57;
        std::string::string(v168, "InstallQueue2::_EnqueueWork");
        std::string::string(&v166, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp");
        Logging::Log<Logging::CatalogSearchInfo &>(
          (unsigned int)&v166,
          2052,
          (unsigned int)v168,
          v39,
          (__int64)&v134,
          (__int64)v148);
        std::string::~string(&v166);
        std::string::~string(v168);
        v128 = 0;
        InstallQueue2::Resume(v11, (struct CorrelationVector *)v9, v150, v31, (const struct winrt::hstring *)&v128);
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v128);
      }
      break;
    }
  }
  if ( !v131[0] )
  {
    v134 = (ScheduledTask *)L"Creating Queue Item for the work";
    v135 = (std::_Ref_count_base *)32;
    std::string::string(v168, "InstallQueue2::_EnqueueWork");
    std::string::string(&v166, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp");
    Logging::ActivityScope<Logging::CatalogSearchInfo &>::ActivityScope<Logging::CatalogSearchInfo &>(
      (unsigned int)v179,
      (unsigned int)&v166,
      v40,
      (unsigned int)v168,
      ppv,
      (__int64)&v134,
      (__int64)v148);
    v41 = v13 | 0x1000;
    std::string::~string(&v166);
    std::string::~string(v168);
    v42 = std::make_shared<InstallQueue2::QueueItem,>(v142);
    std::shared_ptr<CatalogDataStore::CatalogItem>::operator=(v131, v42);
    if ( v142[1] )
      std::_Ref_count_base::_Decref(v142[1]);
    winrt::Windows::Foundation::IUnknown::operator=((std::_Ref_count_base *)((char *)v131[0] + 96));
    v43 = (_QWORD *)v144;
    if ( (unsigned __int8)winrt::operator==(*(_QWORD *)v144 + 56LL, &dword_18023C12C) )
    {
      v46 = v41 | 0x10;
      v137 = v46;
      v47 = Guid::CreateNew(&v166);
      v44 = (std::_Ref_count_base *)Guid::operator winrt::hstring(v47, &v128);
      v45 = v46 | 0x20;
    }
    else
    {
      v44 = (std::_Ref_count_base *)winrt::hstring::hstring(
                                      (winrt::hstring *)&v132,
                                      (const struct winrt::hstring *)(*v43 + 56LL));
      v45 = v41 | 8;
    }
    v48 = v131[0];
    if ( v131[0] != v44 )
    {
      v49 = *(_QWORD *)v44;
      *(_QWORD *)v44 = 0;
      winrt::handle_type<winrt::impl::hstring_traits>::attach(v48, v49);
    }
    if ( (v45 & 0x20) != 0 )
    {
      v45 &= ~0x20u;
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v128);
    }
    if ( (v45 & 0x10) != 0 )
      v45 &= ~0x10u;
    if ( (v45 & 8) != 0 )
    {
      v45 &= ~8u;
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v132);
    }
    v128 = (__int64)v11;
    v50 = winrt::impl::create_and_initialize<InstallServiceConnectionImpl,InstallQueue2 *,winrt::hstring &>(
            &v128,
            v131[0]);
    v128 = (v50 + 16) & -(__int64)(v50 != 0);
    v13 = v45 | 0x2000;
    winrt::Windows::Foundation::IUnknown::operator=((char *)v131[0] + 64, &v128);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v128);
    v51 = v131[0];
    v52 = *v43;
    v53 = v43[1];
    *v43 = 0;
    v43[1] = 0;
    *((_QWORD *)v51 + 6) = v52;
    v54 = (std::_Ref_count_base *)*((_QWORD *)v51 + 7);
    *((_QWORD *)v51 + 7) = v53;
    if ( v54 )
      std::_Ref_count_base::_Decref(v54);
    winrt::hstring::operator=(*((_QWORD *)v131[0] + 6) + 56LL, v131[0]);
    std::shared_ptr<CheckpointData::Data>::operator=((char *)v131[0] + 8, v141);
    v55 = *(_DWORD *)(*((_QWORD *)v131[0] + 6) + 64LL);
    v56 = (unsigned __int8)v55;
    v57 = HIWORD(v55);
    if ( (unsigned int)winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkItem<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem>::Priority(v143) == 1 )
    {
      v128 = 0x200000004LL;
      v132 = __PAIR64__(v57, v56);
      v58 = std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(v142, v131);
      InstallQueue2::_FireStateTransitionTelemetryEvent(
        (unsigned int)&v128,
        v59,
        v58,
        (unsigned int)&v132,
        (__int64)&v128);
      v57 = 2;
      v56 = 4;
    }
    if ( a9 )
    {
      v128 = 0x100000004LL;
      v132 = __PAIR64__(v57, v56);
      v60 = std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(v142, v131);
      InstallQueue2::_FireStateTransitionTelemetryEvent(
        (unsigned int)&v128,
        v61,
        v60,
        (unsigned int)&v132,
        (__int64)&v128);
      v57 = 1;
      v56 = 4;
    }
    else if ( !v56 && !v57 )
    {
      goto LABEL_79;
    }
    if ( v56 != 4 )
    {
      v128 = 0;
      v132 = __PAIR64__(v57, v56);
      v62 = std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(v142, v131);
      InstallQueue2::_FireStateTransitionTelemetryEvent(
        (unsigned int)&v128,
        v63,
        v62,
        (unsigned int)&v132,
        (__int64)&v128);
      v56 = 0;
      v57 = 0;
      *(_DWORD *)(*v43 + 64LL) = 0;
    }
LABEL_79:
    v64 = v131[0];
    *((_DWORD *)v131[0] + 6) = v56;
    *((_DWORD *)v64 + 7) = v57;
    v65 = (_QWORD *)std::_Hash<std::_Umap_traits<winrt::hstring,std::shared_ptr<InstallQueue2::QueueItem>,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,std::shared_ptr<InstallQueue2::QueueItem>>>,0>>::_Try_emplace<winrt::hstring const &,>(
                      (char *)v11 + 200,
                      &v166,
                      v131[0]);
    std::shared_ptr<CheckpointData::Data>::operator=(*v65 + 24LL, v131);
    v66 = winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkItem<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem>::Priority((char *)v131[0] + 96);
    v67 = (LPVOID *)((char *)v11 + 24 * v56 + 264);
    v132 = (unsigned __int64)v67;
    if ( v66 == 2 )
    {
      v68 = (char *)*v67;
      if ( *v67 != v67[1] )
      {
        v69 = (char *)*v67;
        v70 = (char *)v67[1];
        do
        {
          v128 = std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(v142, v69);
          if ( !(unsigned int)winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkItem<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem>::Priority(*(_QWORD *)v128 + 96LL)
            || (v71 = winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkItem<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem>::Priority(*(_QWORD *)v128 + 96LL),
                v129 = 0,
                v71 == 1) )
          {
            v129 = 1;
          }
          v72 = *(std::_Ref_count_base **)(v128 + 8);
          if ( v72 )
            std::_Ref_count_base::_Decref(v72);
          if ( v129 )
            break;
          v69 += 16;
        }
        while ( v69 != v70 );
LABEL_98:
        v130 = v69;
        v9 = v136;
        v11 = v139;
        v68 = (char *)v130;
      }
    }
    else
    {
      if ( v66 )
      {
        v78 = v67[1];
        if ( v78 == v67[2] )
        {
          std::vector<std::shared_ptr<InstallQueue2::QueueItem>>::_Emplace_reallocate<std::shared_ptr<InstallQueue2::QueueItem> const &>(
            (char *)v11 + 24 * v56 + 264,
            v67[1],
            v131);
        }
        else
        {
          std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(v78, v131);
          v67[1] = (char *)v67[1] + 16;
        }
        goto LABEL_103;
      }
      v68 = (char *)*v67;
      if ( *v67 != v67[1] )
      {
        v69 = (char *)*v67;
        v73 = (char *)v67[1];
        do
        {
          v74 = (ScheduledTask *)std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(v142, v69);
          v134 = v74;
          v75 = winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkItem<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem>::Priority(*(_QWORD *)v74 + 96LL);
          LODWORD(v133) = v75;
          v76 = (std::_Ref_count_base *)*((_QWORD *)v74 + 1);
          if ( v76 )
          {
            std::_Ref_count_base::_Decref(v76);
            v75 = (int)v133;
          }
          if ( v75 == 1 )
            break;
          v69 += 16;
        }
        while ( v69 != v73 );
        v67 = (LPVOID *)v132;
        goto LABEL_98;
      }
    }
    std::vector<std::shared_ptr<InstallQueue2::QueueItem>>::emplace<std::shared_ptr<InstallQueue2::QueueItem> const &>(
      v67,
      &v134,
      v68,
      v131);
LABEL_103:
    if ( v56 != 4
      || v57 != 2
      || (v79 = winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkItem<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem>::Attributes(
                  (char *)v131[0] + 96,
                  &v128),
          v80 = v13 | 0x40,
          v137 = v80,
          v81 = (winrt::hstring *)winrt::impl::consume_Windows_Internal_Shell_AppRestore_IRestorableApp<winrt::Windows::Internal::Shell::AppRestore::IRestorableApp>::Arch(
                                    v79,
                                    &v136),
          v13 = v80 | 0x80,
          v82 = winrt::hstring::c_str(v81),
          v83 = 1,
          wcscmp_0(v82, L"Restore")) )
    {
      v83 = 0;
    }
    if ( (v13 & 0x80u) != 0 )
    {
      v13 &= ~0x80u;
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v136);
    }
    if ( (v13 & 0x40) != 0 )
    {
      v13 &= ~0x40u;
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v128);
    }
    if ( v83 )
    {
      v130 = 0;
      LODWORD(v166) = 0;
      v167 = 0;
      v84 = CoCreateInstance(
              &GUID_9c695035_48d2_4229_8b73_4c70e756e519,
              0,
              4u,
              &GUID_c53f3549_0dbf_429a_8297_c812ba00742d,
              &v130);
      winrt::check_hresult(&v133, v84, &v166);
      LODWORD(v166) = 0;
      v167 = 0;
      v85 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, _QWORD))(*(_QWORD *)v130 + 40LL))(
              v130,
              L"IA",
              0);
      winrt::check_hresult(&v133, v85, &v166);
      LODWORD(v166) = 0;
      v167 = 0;
      v86 = (*(__int64 (**)(LPVOID, const unsigned __int16 *, const wchar_t *, ...))(*(_QWORD *)v130 + 32LL))(
              v130,
              L"IA",
              L"%systemroot%\\System32\\usoclient.exe",
              L"StartStoreUpdates",
              L"PauseStoreUpdates");
      winrt::check_hresult(&v133, v86, &v166);
      LogSimpleMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp",
        0x85Fu,
        "InstallQueue2::_EnqueueWork",
        -1,
        L"Scheduled work with UO from for a LowPriority Install",
        0,
        0);
      *(_OWORD *)v169 = *(_OWORD *)(v9 + 8);
      v170 = *(_OWORD *)(v9 + 24);
      v171 = *(_OWORD *)(v9 + 40);
      v172 = *(_OWORD *)(v9 + 56);
      v173 = *(_OWORD *)(v9 + 72);
      v174 = *(_OWORD *)(v9 + 88);
      v175 = *(_OWORD *)(v9 + 104);
      v176 = *(_OWORD *)(v9 + 120);
      v177 = v9[136];
      winrt::hstring::hstring((winrt::hstring *)&v178, (const struct winrt::hstring *)(v9 + 144));
      WindowsUpdate::CommonTelemetry::ScheduleWorkWithUO((WindowsUpdate::CommonTelemetry *)L"IA-Restore", v169, v87);
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v178);
      if ( v130 )
        winrt::com_ptr<IInspectable>::unconditional_release_ref(&v130);
    }
    CheckpointData::Save(*((CheckpointData **)v131[0] + 6), v77);
    Logging::ActivityScope<Logging::CatalogSearchInfo &>::~ActivityScope<Logging::CatalogSearchInfo &>((Logging::Context *)v179);
    v10 = (__int64)v138;
  }
  try
  {
    v134 = (ScheduledTask *)L"Item inserted into the queue. Attempting to create progresstrackers";
    v135 = (std::_Ref_count_base *)67;
    std::string::string(v168, "InstallQueue2::_EnqueueWork");
    std::string::string(&v166, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp");
    Logging::ActivityScope<std::shared_ptr<InstallQueue2::QueueItem> &>::ActivityScope<std::shared_ptr<InstallQueue2::QueueItem> &>(
      (unsigned int)v179,
      (unsigned int)&v166,
      v88,
      (unsigned int)v168,
      ppv,
      (__int64)&v134,
      (__int64)v131);
    v89 = v13 | 0x4000;
    std::string::~string(&v166);
    std::string::~string(v168);
    v142[0] = *(std::_Ref_count_base **)(*((_QWORD *)v131[0] + 6) + 24LL);
    winrt::Windows::Data::Json::JsonObject::Parse((const struct winrt::param::hstring *)&v133);
    winrt::param::hstring::hstring((winrt::param::hstring *)&v166, L"ParentBundleId");
    if ( !(unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                             &v133,
                             &v166)
      || (v90 = *((_QWORD *)v131[0] + 1),
          winrt::param::hstring::hstring((winrt::param::hstring *)v168, L"ParentBundleId"),
          v91 = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
                  &v133,
                  &v132,
                  v168),
          v89 |= 0x100u,
          v137 = v89,
          (unsigned __int8)winrt::operator==(v91, v90 + 24)) )
    {
      NamedString = (__int64 *)&v138;
      v93 = v89 | 0x400;
      v94 = 0;
    }
    else
    {
      winrt::param::hstring::hstring((winrt::param::hstring *)v165, L"ParentBundleId");
      NamedString = (__int64 *)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
                                 &v133,
                                 &v136,
                                 v165);
      v93 = v89 | 0x200;
      v94 = *NamedString;
    }
    *NamedString = 0;
    v128 = v94;
    if ( (v93 & 0x400) != 0 )
    {
      v93 &= ~0x400u;
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v138);
    }
    if ( (v93 & 0x200) != 0 )
    {
      v93 &= ~0x200u;
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v136);
    }
    if ( (v93 & 0x100) != 0 )
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v132);
    v134 = (ScheduledTask *)v142;
    std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(v142, v131);
    winrt::hstring::hstring((winrt::hstring *)&v138, (const struct winrt::hstring *)&v128);
    v95 = v141;
    v96 = std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(v155, v141);
    ppva = v97;
    v98 = InstallQueue2::_CreateProgressTracker(v11, &v139, v97, v96);
    std::vector<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem>::push_back(&v163, v98);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v139);
    v100 = v131[0];
    v101 = (void (__fastcall ***)(_QWORD, __int64 *, void **))*((_QWORD *)v131[0] + 12);
    if ( v101 )
    {
      v136 = 0;
      (**v101)(
        v101,
        &winrt::impl::guid_v<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItemWithSubTasks>,
        (void **)&v136);
      v130 = v136;
      v100 = v131[0];
    }
    else
    {
      v130 = 0;
    }
    if ( !*((_DWORD *)v100 + 6) && !*((_DWORD *)v100 + 7) )
    {
      ScheduledTask::Get(&v134, v99, L"SmartRetry");
      ScheduledTask::SetTriggerEnabled(v134, L"PostBoot", 1);
      ScheduledTask::CommitChanges(v134);
      if ( v135 )
        std::_Ref_count_base::_Decref(v135);
    }
    v138 = 0;
    if ( !(unsigned __int8)winrt::Windows::Foundation::operator==(&v130, &v138) )
    {
      winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_Internal_IOEMHardwareInfo<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IOEMHardwareInfo>::OemId(
        &v130,
        &v132);
      for ( j = 0;
            j < (unsigned int)winrt::impl::consume_Windows_Networking_Connectivity_IConnectionProfile<winrt::Windows::Networking::Connectivity::IConnectionProfile>::GetNetworkConnectivityLevel(&v132);
            ++j )
      {
        winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItemSubTask>,winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItemSubTask>::GetAt(
          &v132,
          &v139,
          j);
        v136 = *(char **)CatalogDataStore::GetSingleton();
        v138 = (_BYTE *)winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkItemSubTask<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItemSubTask>::SearchId(
                          &v139,
                          v155);
        v103 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_Internal_IOEMHardwareInfo<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IOEMHardwareInfo>::OemId(
                 &v139,
                 v162);
        Value = PluginHelpers::WorkProperty::CatalogId::GetValue(v161, &v133);
        v105 = PluginHelpers::WorkProperty::UserIdentityInfo::GetValue(v160, &v133);
        CatalogDataStore::LookupForUser(
          (_DWORD)v136,
          (unsigned int)v142,
          (_DWORD)v9,
          (_DWORD)v150,
          v105,
          Value,
          v103,
          (__int64)v138,
          0);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v160);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v161);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v162);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v155);
        v138 = v168;
        std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(v168, v131);
        winrt::hstring::hstring((winrt::hstring *)v154, (const struct winrt::hstring *)&v128);
        v106 = std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(&v166, v142);
        ppva = v107;
        v108 = InstallQueue2::_CreateProgressTracker(v11, &v134, v107, v106);
        std::vector<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem>::push_back(&v163, v108);
        winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v134);
        if ( v142[1] )
          std::_Ref_count_base::_Decref(v142[1]);
        winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v139);
      }
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v132);
      v95 = v141;
    }
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v130);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v128);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v133);
    Logging::ActivityScope<std::shared_ptr<InstallQueue2::QueueItem> &>::~ActivityScope<std::shared_ptr<InstallQueue2::QueueItem> &>((Logging::Context *)v179);
    v109 = v144;
    v110 = (__int64 *)v143;
    v111 = v146;
  }
  catch ( ... )
  {
    v144 = 0x400000004LL;
    v123 = std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(&v166, v131);
    InstallQueue2::_SwitchState((_DWORD)v151, (unsigned int)&v146, v152, (_DWORD)v147, v123, (__int64)&v144);
    v111 = v156;
    v11 = v151;
    v10 = v152;
    v95 = (_QWORD *)v157;
    v109 = v158;
    v110 = v159;
  }
  v128 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DedupAppInstallItem>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DedupAppInstallItem>::GetImpl'::`2'::impl) )
    winrt::Windows::Foundation::IUnknown::operator=((winrt::Windows::Foundation::IUnknown *)&v128);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WorkReleaseDeadlock>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WorkReleaseDeadlock>::GetImpl'::`2'::impl) )
  {
    v112 = std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(&v166, v131);
    InstallQueue2::_DelayRelease(v11, v10, v112);
  }
  else
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_DedupAppInstallItem>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DedupAppInstallItem>::GetImpl'::`2'::impl);
  v114 = &v128;
  if ( !IsEnabled )
    v114 = v110;
  winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkItem<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem>::SetInstallServiceConnection(
    v114,
    (char *)v131[0] + 64);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
  v115 = std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(&v166, v131);
  LOBYTE(v116) = a9;
  InstallQueue2::_QueueForStatusChangedEvent(v11, v117, v115, v116);
  if ( !*((_BYTE *)v11 + 697) && *((_QWORD *)v11 + 88) == *((_QWORD *)v11 + 27) )
  {
    v142[0] = (std::_Ref_count_base *)L"Sorting pending queue";
    v142[1] = (std::_Ref_count_base *)21;
    std::string::string(v168, "InstallQueue2::_EnqueueWork");
    std::string::string(&v166, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp");
    Logging::Log<>((unsigned int)&v166, 2221, (unsigned int)v168, 3, (__int64)v142);
    std::string::~string(&v166);
    std::string::~string(v168);
    InstallQueue2::_SortCheckpointQueue<std::shared_ptr<InstallQueue2::QueueItem>,std::allocator<std::shared_ptr<InstallQueue2::QueueItem>>>(
      v118,
      v153);
    InstallQueue2::_SortCheckpointQueue<InstallQueue2::EventDescriptor,std::allocator<InstallQueue2::EventDescriptor>>(
      v119,
      (char *)v11 + 416);
  }
  if ( InstallQueue2::_serviceStop )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8B3,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp",
      InstallQueue2::_serviceStop ? (const char *)0x803FB016LL : 0,
      ppva);
  std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(v111, v131);
  std::vector<winrt::WindowsUpdate::Internal::InstallItem>::vector<winrt::WindowsUpdate::Internal::InstallItem>(
    v111 + 16,
    &v163);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v128);
  Logging::CheckpointRecovery::~CheckpointRecovery((Logging::CheckpointRecovery *)v148);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v145);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v140);
  if ( v131[1] )
    std::_Ref_count_base::_Decref(v131[1]);
  winrt::impl::removed_values<winrt::impl::vector_impl<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData,std::vector<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData>,winrt::impl::single_threaded_collection_base>,void>::~removed_values<winrt::impl::vector_impl<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData,std::vector<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData>,winrt::impl::single_threaded_collection_base>,void>(&v163);
  v120 = (std::_Ref_count_base *)v95[1];
  if ( v120 )
    std::_Ref_count_base::_Decref(v120);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v110);
  v121 = *(std::_Ref_count_base **)(v109 + 8);
  if ( v121 )
    std::_Ref_count_base::_Decref(v121);
  return v111;
}

```

## disassembly

```asm
0x180171940  mov     r11, rsp
0x180171943  push    rbx
0x180171944  push    rsi
0x180171945  push    rdi
0x180171946  push    r12
0x180171948  push    r13
0x18017194a  push    r14
0x18017194c  push    r15
0x18017194e  sub     rsp, 3D0h
0x180171955  mov     rax, cs:__security_cookie
0x18017195c  xor     rax, rsp
0x18017195f  mov     [rsp+408h+var_48], rax
0x180171967  mov     r13, r9
0x18017196a  mov     [rsp+408h+var_370], r9
0x180171972  mov     r12, r8
0x180171975  mov     [rsp+408h+var_360], r8
0x18017197d  mov     [r11-300h], rdx
0x180171984  mov     r15, rcx
0x180171987  mov     [rsp+408h+var_358], rcx
0x18017198f  mov     [rsp+408h+var_2D0], rcx
0x180171997  mov     [r11-2A0h], rdx
0x18017199e  mov     [rsp+408h+var_2C8], r8
0x1801719a6  mov     [rsp+408h+var_2F8], r9
0x1801719ae  mov     rax, [rsp+408h+arg_20]
0x1801719b6  mov     [rsp+408h+var_2D8], rax
0x1801719be  mov     rax, [rsp+408h+arg_28]
0x1801719c6  mov     [r11-348h], rax
0x1801719cd  mov     [r11-298h], rax
0x1801719d4  mov     rbx, [rsp+408h+arg_30]
0x1801719dc  mov     [r11-318h], rbx
0x1801719e3  mov     [r11-288h], rbx
0x1801719ea  mov     rax, [rsp+408h+arg_38]
0x1801719f2  mov     [r11-310h], rax
0x1801719f9  mov     [r11-290h], rax
0x180171a00  xor     r14d, r14d
0x180171a03  mov     esi, r14d
0x180171a06  mov     [r11-368h], r14d
0x180171a0d  mov     al, cs:?_serviceStop@InstallQueue2@@0_NA; bool InstallQueue2::_serviceStop
0x180171a13  neg     al
0x180171a15  sbb     r9d, r9d
0x180171a18  and     r9d, 803FB016h; char *
0x180171a1f  mov     rcx, [rsp+408h]; this
0x180171a27  jl      loc_1801732C7
0x180171a2d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnhanceFulfillmentInitiateEvent@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnhanceFulfillmentInitiateEvent@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhanceFulfillmentInitiateEvent> `wil::Feature<__WilFeatureTraits_Feature_EnhanceFulfillmentInitiateEvent>::GetImpl(void)'::`2'::impl
0x180171a34  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnhanceFulfillmentInitiateEvent@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhanceFulfillmentInitiateEvent>::__private_IsEnabled(void)
0x180171a39  test    al, al
0x180171a3b  jnz     short loc_180171AA0
0x180171a3d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_QueueStateInfoEvent@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_QueueStateInfoEvent@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_QueueStateInfoEvent> `wil::Feature<__WilFeatureTraits_Feature_QueueStateInfoEvent>::GetImpl(void)'::`2'::impl
0x180171a44  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_QueueStateInfoEvent@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_QueueStateInfoEvent>::__private_IsEnabled(void)
0x180171a49  test    al, al
0x180171a4b  jz      short loc_180171AA0
0x180171a4d  mov     rcx, r15; this
0x180171a50  call    ?GetAvailableOperationsCount@InstallQueue2@@AEAAIAEBUstore_lock@@@Z; InstallQueue2::GetAvailableOperationsCount(store_lock const &)
0x180171a55  mov     r9, [r15+170h]
0x180171a5c  sub     r9, [r15+168h]
0x180171a63  sar     r9, 4; int
0x180171a67  mov     r8, [r15+110h]
0x180171a6e  sub     r8, [r15+108h]
0x180171a75  sar     r8, 4; int
0x180171a79  mov     rdx, [r15+128h]
0x180171a80  sub     rdx, [r15+120h]
0x180171a87  sar     rdx, 4; int
0x180171a8b  mov     dword ptr [rsp+408h+var_3E0], r14d; char *
0x180171a90  mov     dword ptr [rsp+408h+ppv], eax; int
0x180171a94  mov     ecx, [r15+0D8h]; this
0x180171a9b  call    ?QueueStateInfo@CommonTelemetry@WindowsUpdate@@YAXHHHHHH@Z; WindowsUpdate::CommonTelemetry::QueueStateInfo(int,int,int,int,int,int)
0x180171aa0  mov     [rsp+408h+var_3A8], r14
0x180171aa5  lea     rcx, [rsp+408h+var_3A8]
0x180171aaa  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_QueueStuckTipTest@TipTests@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_QueueStuckTipTest@TipTests@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<TipTests::_tip_QueueStuckTipTest,TipTests::_tip_QueueStuckTipTest>>::ensure_data(void)
0x180171aaf  mov     rcx, [rax]
0x180171ab2  add     rcx, 8
0x180171ab6  lea     rdx, [rsp+408h+var_230]
0x180171abe  call    ?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<1,0,0>::start(void)
0x180171ac3  lea     rdi, [r15+108h]
0x180171aca  mov     [rsp+408h+var_2C0], rdi
0x180171ad2  mov     rcx, r15; this
0x180171ad5  call    ?GetAvailableOperationsCount@InstallQueue2@@AEAAIAEBUstore_lock@@@Z; InstallQueue2::GetAvailableOperationsCount(store_lock const &)
0x180171ada  mov     ecx, eax
0x180171adc  mov     dword ptr [rsp+408h+var_388], eax
0x180171ae3  mov     rax, [rdi+8]
0x180171ae7  mov     [rsp+408h+var_350], rax
0x180171aef  mov     rdi, [rdi]
0x180171af2  cmp     rdi, rax
0x180171af5  jz      loc_180171C9F
0x180171afb  test    ecx, ecx
0x180171afd  jz      loc_180171C9F
0x180171b03  mov     rbx, [rdi]
0x180171b06  call    cs:__imp__Xtime_get_ticks
0x180171b0c  mov     rcx, rax
0x180171b0f  sub     rcx, [rbx+68h]
0x180171b13  mov     rax, 0D6BF94D5E57A42BDh
0x180171b1d  imul    rcx
0x180171b20  lea     rbx, [rcx+rdx]
0x180171b24  sar     rbx, 17h
0x180171b28  mov     rax, rbx
0x180171b2b  shr     rax, 3Fh
0x180171b2f  add     rbx, rax
0x180171b32  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CatalogCacheImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CatalogCacheImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CatalogCacheImprovements> `wil::Feature<__WilFeatureTraits_Feature_CatalogCacheImprovements>::GetImpl(void)'::`2'::impl
0x180171b39  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CatalogCacheImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CatalogCacheImprovements>::__private_IsEnabled(void)
0x180171b3e  xor     r9d, r9d; Context
0x180171b41  xor     r8d, r8d; Parameter
0x180171b44  test    al, al
0x180171b46  jz      short loc_180171B58
0x180171b48  lea     rdx, InitializeOneSettingsConfiguration
0x180171b4f  lea     rcx, stru_1802E4F70
0x180171b56  jmp     short loc_180171B66
0x180171b58  lea     rdx, InitializeInstallServiceConfiguration; InitFn
0x180171b5f  lea     rcx, InitOnce; InitOnce
0x180171b66  call    cs:__imp_InitOnceExecuteOnce
0x180171b6c  cmp     rbx, cs:qword_1802CA678
0x180171b73  jge     short loc_180171B88
0x180171b75  add     rdi, 10h
0x180171b79  cmp     rdi, [rsp+408h+var_350]
0x180171b81  jnz     short loc_180171B03
0x180171b83  jmp     loc_180171C97
0x180171b88  lea     rcx, [rsp+408h+var_3A8]
0x180171b8d  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_QueueStuckTipTest@TipTests@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_QueueStuckTipTest@TipTests@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<TipTests::_tip_QueueStuckTipTest,TipTests::_tip_QueueStuckTipTest>>::ensure_data(void)
0x180171b92  mov     rdi, [rax]
0x180171b95  mov     [rsp+408h+var_350], rdi
0x180171b9d  test    rdi, rdi
0x180171ba0  jz      short loc_180171BA9
0x180171ba2  lock inc dword ptr [rdi+118h]
0x180171ba9  lea     rcx, [rdi+8]
0x180171bad  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x180171bb2  mov     byte ptr [rdi+110h], 1
0x180171bb9  lea     rcx, [rsp+408h+var_350]
0x180171bc1  call    ??1?$test_data_control@V?$merged_data@U_tip_QueueStuckTipTest@TipTests@@U12@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_QueueStuckTipTest,TipTests::_tip_QueueStuckTipTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_QueueStuckTipTest,TipTests::_tip_QueueStuckTipTest>>(void)
0x180171bc6  nop
0x180171bc7  movups  xmm0, xmmword ptr [r13+8]
0x180171bcc  movups  xmmword ptr [rsp+408h+var_1E8], xmm0
0x180171bd4  movups  xmm1, xmmword ptr [r13+18h]
0x180171bd9  movups  [rsp+408h+var_1D8], xmm1
0x180171be1  movups  xmm0, xmmword ptr [r13+28h]
0x180171be6  movups  [rsp+408h+var_1C8], xmm0
0x180171bee  movups  xmm1, xmmword ptr [r13+38h]
0x180171bf3  movups  [rsp+408h+var_1B8], xmm1
0x180171bfb  movups  xmm0, xmmword ptr [r13+48h]
0x180171c00  movups  [rsp+408h+var_1A8], xmm0
0x180171c08  movups  xmm1, xmmword ptr [r13+58h]
0x180171c0d  movups  [rsp+408h+var_198], xmm1
0x180171c15  movups  xmm0, xmmword ptr [r13+68h]
0x180171c1a  movups  [rsp+408h+var_188], xmm0
0x180171c22  movups  xmm1, xmmword ptr [r13+78h]
0x180171c27  movups  [rsp+408h+var_178], xmm1
0x180171c2f  mov     al, [r13+88h]
0x180171c36  mov     [rsp+408h+var_168], al
0x180171c3d  lea     rdx, [r13+90h]; struct winrt::hstring *
0x180171c44  lea     rcx, [rsp+408h+var_160]; this
0x180171c4c  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x180171c51  nop
0x180171c52  mov     r9d, ebx; int
0x180171c55  mov     rax, [rsp+408h+var_2C0]
0x180171c5d  mov     rdx, [rax+8]
0x180171c61  sub     rdx, [rax]
0x180171c64  sar     rdx, 4; int
0x180171c68  lea     rax, [rsp+408h+var_1E8]
0x180171c70  mov     [rsp+408h+ppv], rax; __int64
0x180171c75  mov     r8d, dword ptr [rsp+408h+var_388]; int
0x180171c7d  mov     ecx, [r15+0D8h]; this
0x180171c84  call    ?QueueStuckError@CommonTelemetry@WindowsUpdate@@YAXHHHHPEBD@Z; WindowsUpdate::CommonTelemetry::QueueStuckError(int,int,int,int,char const *)
0x180171c89  nop
0x180171c8a  lea     rcx, [rsp+408h+var_160]
0x180171c92  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180171c97  mov     rbx, [rsp+408h+var_318]
0x180171c9f  mov     rcx, [rsp+408h+var_3A8]
0x180171ca4  test    rcx, rcx
0x180171ca7  jz      short loc_180171CB3
0x180171ca9  add     rcx, 8
0x180171cad  call    ?complete_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<1,0,0>::complete_without_lock(void)
0x180171cb2  nop
0x180171cb3  lea     rcx, [rsp+408h+var_3A8]
0x180171cb8  call    ??1?$com_ptr_t@V?$merged_data@U_tip_QueueStuckTipTest@TipTests@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_QueueStuckTipTest,TipTests::_tip_QueueStuckTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_QueueStuckTipTest,TipTests::_tip_QueueStuckTipTest>,wil::err_returncode_policy>(void)
0x180171cbd  xorps   xmm0, xmm0
0x180171cc0  movdqu  [rsp+408h+var_268], xmm0
0x180171cc9  mov     [rsp+408h+var_258], r14
0x180171cd1  movdqu  xmmword ptr [rsp+408h+var_3A0], xmm0
0x180171cd7  lea     rdx, [rsp+408h+var_350]
0x180171cdf  mov     rcx, rbx
0x180171ce2  call    ?OemId@?$consume_Windows_ApplicationModel_Store_Preview_InstallControl_Internal_IOEMHardwareInfo@UIOEMHardwareInfo@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_Internal_IOEMHardwareInfo<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IOEMHardwareInfo>::OemId(void)
0x180171ce7  nop
0x180171ce8  lea     rdx, [rsp+408h+var_308]
0x180171cf0  mov     rcx, rbx
0x180171cf3  call    ?SearchId@?$consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkItemSubTask@UIInstallServiceWorkItemSubTask@Plugin@InstallService@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkItemSubTask<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItemSubTask>::SearchId(void)
0x180171cf8  nop
0x180171cf9  lea     rdx, [rsp+408h+var_350]; struct winrt::hstring *
0x180171d01  lea     rcx, [rsp+408h+var_2E8]; this
0x180171d09  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x180171d0e  nop
0x180171d0f  lea     rdx, [rsp+408h+var_308]; struct winrt::hstring *
0x180171d17  lea     rcx, [rsp+408h+var_2E0]; this
0x180171d1f  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x180171d24  nop
0x180171d25  mov     rdi, [r15+0D0h]
0x180171d2c  mov     rbx, [rdi]
0x180171d2f  cmp     rbx, rdi
0x180171d32  jz      loc_180172339
0x180171d38  lea     rax, [rbx+10h]
0x180171d3c  mov     [rsp+408h+var_388], rax
0x180171d44  mov     [rsp+408h+var_3B8], r14
0x180171d49  or      esi, 1
0x180171d4c  mov     [rsp+408h+var_368], esi
0x180171d53  mov     rcx, [rax+8]
0x180171d57  add     rcx, 60h ; '`'
0x180171d5b  lea     rdx, [rsp+408h+var_3B8]
0x180171d60  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180171d65  test    al, al
0x180171d67  jnz     short loc_180171DC8
0x180171d69  mov     rcx, [rbx+18h]
0x180171d6d  add     rcx, 60h ; '`'
0x180171d71  lea     rdx, [rsp+408h+var_3A8]
0x180171d76  call    ?SearchId@?$consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkItemSubTask@UIInstallServiceWorkItemSubTask@Plugin@InstallService@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkItemSubTask<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItemSubTask>::SearchId(void)
0x180171d7b  nop
0x180171d7c  or      esi, 2
0x180171d7f  mov     [rsp+408h+var_368], esi
0x180171d86  lea     rdx, [rsp+408h+var_308]
0x180171d8e  mov     rcx, rax
0x180171d91  call    ??8winrt@@YA_NAEBUhstring@0@0@Z; winrt::operator==(winrt::hstring const &,winrt::hstring const &)
0x180171d96  test    al, al
0x180171d98  jz      short loc_180171DC8
0x180171d9a  mov     rcx, [rbx+18h]
0x180171d9e  add     rcx, 60h ; '`'
0x180171da2  lea     rdx, [rsp+408h+var_390]
0x180171da7  call    ?OemId@?$consume_Windows_ApplicationModel_Store_Preview_InstallControl_Internal_IOEMHardwareInfo@UIOEMHardwareInfo@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_Internal_IOEMHardwareInfo<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IOEMHardwareInfo>::OemId(void)
0x180171dac  or      esi, 4
0x180171daf  lea     rdx, [rsp+408h+var_350]
0x180171db7  mov     rcx, rax
0x180171dba  call    ??8winrt@@YA_NAEBUhstring@0@0@Z; winrt::operator==(winrt::hstring const &,winrt::hstring const &)
0x180171dbf  test    al, al
0x180171dc1  mov     [rsp+408h+var_3B0], 1
0x180171dc6  jnz     short loc_180171DCD
0x180171dc8  mov     [rsp+408h+var_3B0], r14b
0x180171dcd  test    sil, 4
0x180171dd1  jz      short loc_180171DE1
0x180171dd3  and     esi, 0FFFFFFFBh
0x180171dd6  lea     rcx, [rsp+408h+var_390]
0x180171ddb  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180171de0  nop
0x180171de1  test    sil, 2
0x180171de5  jz      short loc_180171DF5
0x180171de7  and     esi, 0FFFFFFFDh
0x180171dea  lea     rcx, [rsp+408h+var_3A8]
0x180171def  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180171df4  nop
0x180171df5  test    sil, 1
0x180171df9  jz      short loc_180171DFE
0x180171dfb  and     esi, 0FFFFFFFEh
0x180171dfe  cmp     [rsp+408h+var_3B0], r14b
0x180171e03  jnz     short loc_180171E0D
0x180171e05  mov     rbx, [rbx]
0x180171e08  jmp     loc_180171D2F
0x180171e0d  lea     rax, aWorkAlreadyEnq; "Work already enqueued. Refusing to queu"...
0x180171e14  mov     [rsp+408h+var_380], rax
0x180171e1c  mov     [rsp+408h+var_378], 37h ; '7'
0x180171e28  lea     rdx, aInstallqueue2E; "InstallQueue2::_EnqueueWork"
0x180171e2f  lea     rcx, [rsp+408h+var_210]
0x180171e37  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180171e3c  nop
0x180171e3d  lea     rdx, aOnecoreuapEndu_22; "onecoreuap\\enduser\\winstore\\installs"...
0x180171e44  lea     rcx, [rsp+408h+var_230]
0x180171e4c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180171e51  nop
0x180171e52  lea     rax, [rsp+408h+var_2E8]
0x180171e5a  mov     [rsp+408h+var_3E0], rax
0x180171e5f  lea     rax, [rsp+408h+var_380]
0x180171e67  mov     [rsp+408h+ppv], rax
0x180171e6c  lea     r8, [rsp+408h+var_210]
0x180171e74  mov     edx, 7D2h
0x180171e79  lea     rcx, [rsp+408h+var_230]
0x180171e81  call    ??$Log@AEAUCatalogSearchInfo@Logging@@@Logging@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I0W4Level@0@AEBV?$basic_string_view@GU?$char_traits@G@std@@@2@AEAUCatalogSearchInfo@0@@Z; Logging::Log<Logging::CatalogSearchInfo &>(std::string const &,uint,std::string const &,Logging::Level,std::basic_string_view<ushort> const &,Logging::CatalogSearchInfo &)
0x180171e86  nop
0x180171e87  lea     rcx, [rsp+408h+var_230]
0x180171e8f  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180171e94  nop
0x180171e95  lea     rcx, [rsp+408h+var_210]
0x180171e9d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180171ea2  mov     rbx, [rsp+408h+var_388]
0x180171eaa  lea     rdx, [rbx+8]
0x180171eae  lea     rcx, [rsp+408h+var_3A0]
0x180171eb3  call    ??4?$shared_ptr@UData@CheckpointData@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<CheckpointData::Data>::operator=(std::shared_ptr<CheckpointData::Data> const &)
0x180171eb8  mov     r9, [rsp+408h+var_3A0]
0x180171ebd  mov     rcx, [r9+50h]
0x180171ec1  cmp     rcx, [r9+58h]
0x180171ec5  jz      short loc_180171EDB
0x180171ec7  mov     rdx, [rsp+408h+var_348]
0x180171ecf  call    ??0?$shared_ptr@VNotificationQueue@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(std::shared_ptr<NotificationQueue> const &)
0x180171ed4  add     qword ptr [r9+50h], 10h
0x180171ed9  jmp     short loc_180171EEF
0x180171edb  mov     r8, [rsp+408h+var_348]
0x180171ee3  mov     rdx, rcx
0x180171ee6  lea     rcx, [r9+48h]
0x180171eea  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@UInstallItemData@@@std@@@?$vector@V?$shared_ptr@UInstallItemData@@@std@@V?$allocator@V?$shared_ptr@UInstallItemData@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@UInstallItemData@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<InstallItemData>>::_Emplace_reallocate<std::shared_ptr<InstallItemData> const &>(std::shared_ptr<InstallItemData> * const,std::shared_ptr<InstallItemData> const &)
0x180171eef  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixAcquisitionToWorkingDedupTIP@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixAcquisitionToWorkingDedupTIP@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixAcquisitionToWorkingDedupTIP> `wil::Feature<__WilFeatureTraits_Feature_FixAcquisitionToWorkingDedupTIP>::GetImpl(void)'::`2'::impl
0x180171ef6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixAcquisitionToWorkingDedupTIP@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixAcquisitionToWorkingDedupTIP>::__private_IsEnabled(void)
0x180171efb  test    al, al
0x180171efd  jz      loc_180171FE9
0x180171f03  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AcquisitionEnqueueToWorkingDelayTip@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AcquisitionEnqueueToWorkingDelayTip@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AcquisitionEnqueueToWorkingDelayTip> `wil::Feature<__WilFeatureTraits_Feature_AcquisitionEnqueueToWorkingDelayTip>::GetImpl(void)'::`2'::impl
0x180171f0a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AcquisitionEnqueueToWorkingDelayTip@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AcquisitionEnqueueToWorkingDelayTip>::__private_IsEnabled(void)
0x180171f0f  test    al, al
0x180171f11  jz      loc_180171FE9
0x180171f17  lea     rdi, [r15+2C8h]
  ... truncated ...
```
