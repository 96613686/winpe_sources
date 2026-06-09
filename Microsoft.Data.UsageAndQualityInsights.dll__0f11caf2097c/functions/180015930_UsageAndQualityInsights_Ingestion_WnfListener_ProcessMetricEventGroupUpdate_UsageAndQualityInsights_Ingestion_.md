# UsageAndQualityInsights::Ingestion::WnfListener::ProcessMetricEventGroupUpdate(UsageAndQualityInsights::Ingestion::MetricApiWnf)

- ea: `0x180015930`
- end: `0x1800162a1`
- name: `?ProcessMetricEventGroupUpdate@WnfListener@Ingestion@UsageAndQualityInsights@@CAXUMetricApiWnf@23@@Z`
- size: `2417`
- prototype: ``
- caller_count: `0`
- callee_count: `51`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800033d0`
- `0x1800038b8`
- `0x1800051ed`
- `0x18000eee0`
- `0x1800107b0`
- `0x1800108c8`
- `0x180010908`
- `0x18001219c`
- `0x180012940`
- `0x180012998`
- `0x180012d28`
- `0x180012dd4`
- `0x180013120`
- `0x18001321c`
- `0x1800138dc`
- `0x18001394c`
- `0x180013bbc`
- `0x180013dbc`
- `0x18001411c`
- `0x180014248`
- `0x1800149fc`
- `0x180014dc8`
- `0x18001573c`
- `0x180015930`
- `0x180016648`
- `0x180016754`
- `0x180016814`
- `0x180016998`
- `0x180016a6c`
- `0x180016b2c`
- `0x180016cac`
- `0x180016d2c`
- `0x180016dcc`
- `0x180017b1c`
- `0x180019f6c`
- `0x18001a488`
- `0x18001ba58`
- `0x180023334`
- `0x18002515c`
- `0x1800e6dcc`
- `0x1800ea674`
- `0x1800eb40c`
- `0x1800f58d4`
- `0x1800f5a1c`
- `0x1800f6a68`
- `0x1800f79b0`
- `0x1800f7adc`
- `0x1800f7c40`
- `0x1800f7dcc`
- `0x1800f8ed0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800159ca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015a07`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001615c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800159ca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015a07`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001615c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015a65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001624c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015a65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001624c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001619b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800161c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001619b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800161c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
void __fastcall UsageAndQualityInsights::Ingestion::WnfListener::ProcessMetricEventGroupUpdate(_QWORD *a1)
{
  UsageAndQualityInsights::Ingestion *v2; // rcx
  __int64 v3; // rdx
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  void *v6; // rbx
  _BYTE *ServiceObj; // rax
  __int64 v8; // rdx
  __int64 v9; // rax
  volatile signed __int32 *v10; // r14
  __int128 *v11; // r13
  __int64 v12; // rbx
  __int64 v13; // rdi
  _QWORD *v14; // rax
  _BYTE *v15; // rax
  bool v16; // r8
  __int64 v17; // rbx
  __int64 v18; // rax
  volatile signed __int32 *v19; // rbx
  __int64 v20; // rdi
  __int64 v21; // r12
  unsigned __int64 v22; // rax
  __int64 v23; // rax
  unsigned __int64 v24; // rsi
  _DWORD *v25; // rbx
  void *v26; // rax
  _DWORD *v27; // rsi
  _DWORD *v28; // r15
  _QWORD *v29; // rax
  int *i; // rbx
  int *v31; // rsi
  struct _RTL_CRITICAL_SECTION *v32; // rcx
  _BYTE *v33; // rax
  __int64 v34; // rsi
  __int64 v35; // rax
  struct _RTL_CRITICAL_SECTION *v36; // r15
  volatile signed __int32 *v37; // rsi
  __int64 v38; // rbx
  _QWORD *v39; // rax
  struct _RTL_CRITICAL_SECTION *v40; // rbx
  void *v41; // rbx
  __int128 *v42; // [rsp+30h] [rbp-258h] BYREF
  _QWORD v43[2]; // [rsp+38h] [rbp-250h] BYREF
  _DWORD *v44; // [rsp+48h] [rbp-240h] BYREF
  _DWORD *v45; // [rsp+50h] [rbp-238h]
  __int128 *v46; // [rsp+58h] [rbp-230h]
  LPCRITICAL_SECTION v47; // [rsp+60h] [rbp-228h] BYREF
  volatile signed __int32 *v48; // [rsp+68h] [rbp-220h]
  HKEY hKey; // [rsp+70h] [rbp-218h] BYREF
  HKEY v50; // [rsp+78h] [rbp-210h] BYREF
  __int128 v51; // [rsp+80h] [rbp-208h] BYREF
  __int64 v52; // [rsp+90h] [rbp-1F8h]
  __int128 *v53; // [rsp+98h] [rbp-1F0h] BYREF
  unsigned __int64 v54; // [rsp+A0h] [rbp-1E8h] BYREF
  char v55; // [rsp+A8h] [rbp-1E0h]
  _QWORD v56[3]; // [rsp+B0h] [rbp-1D8h] BYREF
  _QWORD v57[3]; // [rsp+C8h] [rbp-1C0h] BYREF
  __int64 v58; // [rsp+E0h] [rbp-1A8h] BYREF
  _BYTE v59[16]; // [rsp+E8h] [rbp-1A0h] BYREF
  _BYTE v60[24]; // [rsp+F8h] [rbp-190h] BYREF
  __int64 v61; // [rsp+110h] [rbp-178h]
  volatile signed __int32 *v62; // [rsp+118h] [rbp-170h]
  _BYTE v63[16]; // [rsp+120h] [rbp-168h] BYREF
  char v64[8]; // [rsp+130h] [rbp-158h] BYREF
  char v65[48]; // [rsp+138h] [rbp-150h] BYREF
  LPVOID pv; // [rsp+168h] [rbp-120h]
  __int128 v67; // [rsp+170h] [rbp-118h] BYREF
  _DWORD *v68; // [rsp+180h] [rbp-108h]
  _BYTE v69[24]; // [rsp+188h] [rbp-100h] BYREF
  _BYTE v70[28]; // [rsp+1A0h] [rbp-E8h] BYREF
  int v71; // [rsp+1BCh] [rbp-CCh]
  int v72; // [rsp+1C0h] [rbp-C8h]
  _BYTE v73[32]; // [rsp+1C8h] [rbp-C0h] BYREF
  _QWORD v74[4]; // [rsp+1E8h] [rbp-A0h] BYREF
  int v75; // [rsp+208h] [rbp-80h]
  int v76; // [rsp+20Ch] [rbp-7Ch]
  __int64 v77; // [rsp+210h] [rbp-78h]
  int v78; // [rsp+220h] [rbp-68h]
  _BYTE v79[32]; // [rsp+228h] [rbp-60h] BYREF

  tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>>((__int64)v64);
  try
  {
    v2 = (UsageAndQualityInsights::Ingestion *)((-(__int64)((unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::GetImpl'::`2'::impl) != 0)
                                               & 0xFFFFFFFF91128B7FuLL)
                                              + 2560586346u);
    v3 = 0;
    if ( *a1 )
    {
      while ( (UsageAndQualityInsights::Ingestion *)a1[2 * v3 + 1] != v2 )
      {
        if ( (unsigned __int64)++v3 >= *a1 )
          goto LABEL_5;
      }
      UsageAndQualityInsights::Ingestion::HandleDeleteDeviceRequest(v2);
      ServiceObj = (_BYTE *)GetServiceObj(&v47);
      if ( !ServiceObj[8] )
        std::_Throw_bad_optional_access();
      v8 = *(_QWORD *)ServiceObj;
      v9 = *(_QWORD *)(*(_QWORD *)ServiceObj + 48LL);
      if ( v9 )
        _InterlockedIncrement((volatile signed __int32 *)(v9 + 8));
      v61 = *(_QWORD *)(v8 + 40);
      v10 = *(volatile signed __int32 **)(v8 + 48);
      v62 = v10;
      UsageAndQualityInsights::Configuration::ConfigStore::GetCurrentConfig(v61, v60);
      UsageAndQualityInsights::Configuration::CompiledUQIConfig::GetEnrichmentDefinitions(v60, v59);
      wil::reg::open_unique_key((int)&v50);
      wil::reg::try_get_value<unsigned __int64>(&v54, v50, L"LastProcessedFileTime");
      v11 = (__int128 *)v54;
      UsageAndQualityInsights::Ingestion::MetricEventsFetcher::FetchMetricEvents(v57, v54 & -(__int64)(v55 != 0));
      UsageAndQualityInsights::Ingestion::EnrichmentEngine::EnrichEvents(v57, v59);
      v51 = 0;
      v52 = 0;
      v12 = v57[0];
      v13 = v57[1];
      while ( v12 != v13 )
      {
        v14 = (_QWORD *)UsageAndQualityInsights::Facts::FactView::FromMetricEvent(v56, v12);
        std::vector<UsageAndQualityInsights::Facts::FactRecord>::_Insert_counted_range<UsageAndQualityInsights::Facts::FactRecord const *>(
          &v51,
          *((_QWORD *)&v51 + 1),
          *v14,
          0xD37A6F4DE9BD37A7uLL * ((__int64)(v14[1] - *v14) >> 3));
        UsageAndQualityInsights::Facts::FactView::ReaggregateFacts((UsageAndQualityInsights::Facts::FactView *)&v51);
        std::vector<UsageAndQualityInsights::Facts::FactRecord>::_Tidy(v56);
        v12 += 264;
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57896588>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_57896588>::GetImpl'::`2'::impl) )
        UsageAndQualityInsights::Ingestion::WnfListener::EnrichFactViewWithExpId((struct UsageAndQualityInsights::Facts::FactView *)&v51);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59192442>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_59192442>::GetImpl'::`2'::impl) )
      {
        v15 = (_BYTE *)GetServiceObj(v43);
        if ( !v15[8] )
          std::_Throw_bad_optional_access();
        v17 = *(_QWORD *)v15;
        v18 = *(_QWORD *)(*(_QWORD *)v15 + 80LL);
        if ( v18 )
          _InterlockedIncrement((volatile signed __int32 *)(v18 + 8));
        v47 = *(LPCRITICAL_SECTION *)(v17 + 72);
        v19 = *(volatile signed __int32 **)(v17 + 80);
        v48 = v19;
        UsageAndQualityInsights::Facts::FactStoreManager::PushFactView(
          v47,
          (const struct UsageAndQualityInsights::Facts::FactView *)&v51,
          v16);
        if ( v19 )
        {
          if ( !_InterlockedDecrement(v19 + 2) )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
            if ( !_InterlockedDecrement(v19 + 3) )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
          }
        }
        UsageAndQualityInsightsTraceLogging::TraceLoggingInfo("Pushed FactView to FactStore from WNF listener");
      }
      else
      {
        UsageAndQualityInsights::Configuration::CompiledUQIConfig::GetTelemetryEndpointConfigs(v60, v56);
        v20 = v56[0];
        v21 = v56[1];
        while ( v20 != v21 )
        {
          v42 = &v67;
          v67 = 0;
          v68 = 0;
          v22 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*(_QWORD *)(v20 + 8) - *(_QWORD *)v20) >> 3);
          if ( v22 )
          {
            if ( v22 > 0x666666666666666LL )
              std::vector<std::pair<std::string_view,std::string_view>>::_Xlength();
            v23 = (__int64)(*(_QWORD *)(v20 + 8) - *(_QWORD *)v20) >> 3;
            v24 = 8 * v23;
            if ( 8 * v23 )
            {
              if ( v24 < 0x1000 )
              {
                v25 = operator new(8 * v23);
              }
              else
              {
                if ( v24 + 39 < v24 )
                  __scrt_throw_std_bad_array_new_length();
                v26 = operator new(v24 + 39);
                if ( !v26 )
                  __fastfail(5u);
                v25 = (_DWORD *)(((unsigned __int64)v26 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
                *((_QWORD *)v25 - 1) = v26;
              }
            }
            else
            {
              v25 = 0;
            }
            *(_QWORD *)&v67 = v25;
            *((_QWORD *)&v67 + 1) = v25;
            v68 = &v25[v24 / 4];
            v53 = &v67;
            v27 = *(_DWORD **)v20;
            v28 = *(_DWORD **)(v20 + 8);
            v44 = v25;
            v45 = v25;
            v46 = &v67;
            while ( v27 != v28 )
            {
              *v25 = *v27;
              std::wstring::wstring(v25 + 2, v27 + 2);
              v25 += 10;
              v45 = v25;
              v27 += 10;
            }
            *((_QWORD *)&v67 + 1) = v25;
          }
          std::vector<std::wstring>::vector<std::wstring>(v69, v20 + 24);
          std::vector<std::wstring>::vector<std::wstring>(v70, v20 + 48);
          v70[24] = *(_BYTE *)(v20 + 72);
          v71 = *(_DWORD *)(v20 + 76);
          v72 = *(_DWORD *)(v20 + 80);
          std::wstring::wstring(v73, v20 + 88);
          std::wstring::wstring(v74, v20 + 120);
          v75 = *(_DWORD *)(v20 + 152);
          v76 = *(_DWORD *)(v20 + 156);
          v77 = *(_QWORD *)(v20 + 160);
          std::vector<UsageAndQualityInsights::Facts::FactRecord>::vector<UsageAndQualityInsights::Facts::FactRecord>(
            &v44,
            &v51);
          v43[0] = 0;
          v43[1] = 0;
          v29 = operator new(0x40u);
          *v29 = v29;
          v29[1] = v29;
          v29[2] = v29;
          *((_WORD *)v29 + 12) = 257;
          v43[0] = v29;
          v31 = (int *)*((_QWORD *)&v67 + 1);
          for ( i = (int *)v67; i != v31; i += 10 )
          {
            v78 = *i;
            std::wstring::wstring(v79, i + 2);
            std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
              v43,
              v63,
              v79);
            std::wstring::~wstring(v79);
          }
          UsageAndQualityInsights::Facts::FactView::FilterFactNames(&v44, v43);
          UsageAndQualityInsights::Facts::FactView::FilterDimensions((UsageAndQualityInsights::Facts::FactView *)&v44);
          UsageAndQualityInsights::Facts::FactView::FilterMetricNames(&v44, v70);
          if ( v44 != v45 )
          {
            v32 = (struct _RTL_CRITICAL_SECTION *)v74;
            if ( v74[3] > 7u )
              v32 = (struct _RTL_CRITICAL_SECTION *)v74[0];
            v47 = v32;
            v48 = (volatile signed __int32 *)v74[2];
            UsageAndQualityInsights::Utilities::TelemetryExporter::ExportFactViewAsTelemetry(
              (unsigned int)&v44,
              (unsigned int)v73,
              v76,
              v77,
              (__int64)&v47);
          }
          std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v43);
          std::vector<UsageAndQualityInsights::Facts::FactRecord>::_Tidy(&v44);
          std::wstring::~wstring(v74);
          std::wstring::~wstring(v73);
          std::vector<std::wstring>::_Tidy(v70);
          std::vector<std::wstring>::_Tidy(v69);
          std::vector<UsageAndQualityInsights::Configuration::Fact>::_Tidy(&v67);
          v20 += 168;
        }
        std::vector<UsageAndQualityInsights::Configuration::TelemetryEndpointConfig>::~vector<UsageAndQualityInsights::Configuration::TelemetryEndpointConfig>(v56);
      }
      wil::reg::open_unique_key((int)&hKey);
      wil::reg::set_value<unsigned __int64>(hKey, L"LastProcessedFileTime", &v58);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59192442>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_59192442>::GetImpl'::`2'::impl) )
      {
        v42 = 0;
        WINRT_IMPL_GetSystemTimePreciseAsFileTime(&v42);
        v33 = (_BYTE *)GetServiceObj(v63);
        if ( !v33[8] )
          std::_Throw_bad_optional_access();
        v34 = *(_QWORD *)v33;
        v35 = *(_QWORD *)(*(_QWORD *)v33 + 80LL);
        if ( v35 )
          _InterlockedIncrement((volatile signed __int32 *)(v35 + 8));
        v36 = *(struct _RTL_CRITICAL_SECTION **)(v34 + 72);
        v47 = v36;
        v37 = *(volatile signed __int32 **)(v34 + 80);
        v48 = v37;
        v38 = *(_QWORD *)UsageAndQualityInsights::Utilities::TimePointFromFileTime(&v53, v58);
        if ( !v55 )
          v11 = v42 - 54000000000LL;
        v39 = (_QWORD *)UsageAndQualityInsights::Utilities::TimePointFromFileTime(v43, v11);
        UsageAndQualityInsights::Facts::FactStoreManager::TriggerPendingTelemetryEvents(v36, *v39, v38);
        if ( v37 )
        {
          if ( _InterlockedExchangeAdd(v37 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v37)(v37);
            if ( _InterlockedExchangeAdd(v37 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v37 + 8LL))(v37);
          }
        }
      }
      v40 = (struct _RTL_CRITICAL_SECTION *)pv;
      v42 = (__int128 *)pv;
      if ( pv )
        _InterlockedIncrement((volatile signed __int32 *)pv + 70);
      EnterCriticalSection(v40 + 5);
      ++LODWORD(v40[6].DebugInfo);
      LODWORD(v40[1].SpinCount) |= 0xB00u;
      if ( *(_QWORD *)&v40[6].LockCount )
        tip2::details::shared_data<0,0,0>::complete_helper(&v40->LockCount, 10);
      tip2::test_data_control<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>(&v42);
      if ( hKey )
        RegCloseKey(hKey);
      std::vector<UsageAndQualityInsights::Facts::FactRecord>::_Tidy(&v51);
      std::vector<UsageAndQualityInsights::Utilities::MetricEvent>::~vector<UsageAndQualityInsights::Utilities::MetricEvent>(v57);
      if ( v50 )
        RegCloseKey(v50);
      std::_Tree<std::_Tmap_traits<std::wstring,std::vector<UsageAndQualityInsights::Configuration::EnrichedFields>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::vector<UsageAndQualityInsights::Configuration::EnrichedFields>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::vector<UsageAndQualityInsights::Configuration::EnrichedFields>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::vector<UsageAndQualityInsights::Configuration::EnrichedFields>>>,0>>(v59);
      std::vector<UsageAndQualityInsights::Configuration::UQIConfig>::_Tidy(v60);
      if ( v10 )
      {
        if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
          if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
        }
      }
      v41 = pv;
      if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 70, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>::~merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>(v41);
        CoTaskMemFree(v41);
      }
    }
    else
    {
LABEL_5:
      v4 = (struct _RTL_CRITICAL_SECTION *)pv;
      v42 = (__int128 *)pv;
      if ( pv )
        _InterlockedIncrement((volatile signed __int32 *)pv + 70);
      EnterCriticalSection(v4 + 5);
      ++LODWORD(v4[6].DebugInfo);
      LOBYTE(v4[6].SpinCount) = 0;
      tip2::test_data_control<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>(&v42);
      v5 = (struct _RTL_CRITICAL_SECTION *)pv;
      v42 = (__int128 *)pv;
      if ( pv )
        _InterlockedIncrement((volatile signed __int32 *)pv + 70);
      EnterCriticalSection(v5 + 5);
      ++LODWORD(v5[6].DebugInfo);
      LODWORD(v5[1].SpinCount) |= 0xB00u;
      if ( *(_QWORD *)&v5[6].LockCount )
        tip2::details::shared_data<0,0,0>::complete_helper(&v5->LockCount, 10);
      tip2::test_data_control<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>(&v42);
      v6 = pv;
      if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 70, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>::~merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>(v6);
        CoTaskMemFree(v6);
      }
    }
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v65);
  }
  catch ( ... )
  {
  }
}

```

## disassembly

```asm
0x180015930  push    rbx
0x180015932  push    rsi
0x180015933  push    rdi
0x180015934  push    r12
0x180015936  push    r13
0x180015938  push    r14
0x18001593a  push    r15
0x18001593c  sub     rsp, 250h
0x180015943  mov     rax, cs:__security_cookie
0x18001594a  xor     rax, rsp
0x18001594d  mov     [rsp+288h+var_40], rax
0x180015955  mov     rbx, rcx
0x180015958  lea     rcx, [rsp+288h+var_158]
0x180015960  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_UQIWnfCallbackExecutionTipTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x180015965  nop
0x180015966  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UtcExtendedMetricsSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UtcExtendedMetricsSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport> `wil::Feature<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::GetImpl(void)'::`2'::impl
0x18001596d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UtcExtendedMetricsSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::__private_IsEnabled(void)
0x180015972  neg     al
0x180015974  sbb     rcx, rcx
0x180015977  and     rcx, 0FFFFFFFF91128B7Fh
0x18001597e  mov     eax, 989F726Ah
0x180015983  add     rcx, rax; this
0x180015986  xor     r15d, r15d
0x180015989  mov     edx, r15d
0x18001598c  cmp     [rbx], r15
0x18001598f  jbe     short loc_1800159AA
0x180015991  mov     rax, rdx
0x180015994  add     rax, rax
0x180015997  cmp     [rbx+rax*8+8], rcx
0x18001599c  jz      loc_180015A7E
0x1800159a2  inc     rdx
0x1800159a5  cmp     rdx, [rbx]
0x1800159a8  jb      short loc_180015991
0x1800159aa  mov     rbx, [rsp+288h+pv]
0x1800159b2  mov     [rsp+288h+var_258], rbx
0x1800159b7  test    rbx, rbx
0x1800159ba  jz      short loc_1800159C3
0x1800159bc  lock inc dword ptr [rbx+118h]
0x1800159c3  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800159ca  call    cs:__imp_EnterCriticalSection
0x1800159d0  inc     dword ptr [rbx+0F0h]
0x1800159d6  mov     [rbx+110h], r15b
0x1800159dd  lea     rcx, [rsp+288h+var_258]
0x1800159e2  call    ??1?$test_data_control@V?$merged_data@U_tip_UQIWnfCallbackExecutionTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>(void)
0x1800159e7  mov     rbx, [rsp+288h+pv]
0x1800159ef  mov     [rsp+288h+var_258], rbx
0x1800159f4  test    rbx, rbx
0x1800159f7  jz      short loc_180015A00
0x1800159f9  lock inc dword ptr [rbx+118h]
0x180015a00  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180015a07  call    cs:__imp_EnterCriticalSection
0x180015a0d  inc     dword ptr [rbx+0F0h]
0x180015a13  or      dword ptr [rbx+48h], 0B00h
0x180015a1a  cmp     [rbx+0F8h], r15
0x180015a21  jz      short loc_180015A31
0x180015a23  mov     edx, 0Ah
0x180015a28  lea     rcx, [rbx+8]
0x180015a2c  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180015a31  lea     rcx, [rsp+288h+var_258]
0x180015a36  call    ??1?$test_data_control@V?$merged_data@U_tip_UQIWnfCallbackExecutionTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>(void)
0x180015a3b  nop
0x180015a3c  mov     rbx, [rsp+288h+pv]
0x180015a44  test    rbx, rbx
0x180015a47  jz      short loc_180015A6B
0x180015a49  or      edi, 0FFFFFFFFh
0x180015a4c  mov     eax, edi
0x180015a4e  lock xadd [rbx+118h], eax
0x180015a56  add     eax, edi
0x180015a58  jnz     short loc_180015A6B
0x180015a5a  mov     rcx, rbx
0x180015a5d  call    ??1?$merged_data@U_tip_UQIWnfCallbackExecutionTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>::~merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>(void)
0x180015a62  mov     rcx, rbx; pv
0x180015a65  call    cs:__imp_CoTaskMemFree
0x180015a6b  lea     rcx, [rsp+288h+var_150]; this
0x180015a73  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180015a78  nop
0x180015a79  jmp     loc_180016260
0x180015a7e  call    ?HandleDeleteDeviceRequest@Ingestion@UsageAndQualityInsights@@YAXXZ; UsageAndQualityInsights::Ingestion::HandleDeleteDeviceRequest(void)
0x180015a83  lea     rcx, [rsp+288h+var_228]
0x180015a88  call    ?GetServiceObj@@YA?AV?$optional@V?$reference_wrapper@VUQIService@@@std@@@std@@XZ; GetServiceObj(void)
0x180015a8d  cmp     [rax+8], r15b
0x180015a91  jz      loc_180016283
0x180015a97  mov     rdx, [rax]
0x180015a9a  mov     rax, [rdx+30h]
0x180015a9e  test    rax, rax
0x180015aa1  jz      short loc_180015AA7
0x180015aa3  lock inc dword ptr [rax+8]
0x180015aa7  mov     rcx, [rdx+28h]
0x180015aab  mov     [rsp+288h+var_178], rcx
0x180015ab3  mov     r14, [rdx+30h]
0x180015ab7  mov     [rsp+288h+var_170], r14
0x180015abf  lea     rdx, [rsp+288h+var_190]
0x180015ac7  call    ?GetCurrentConfig@ConfigStore@Configuration@UsageAndQualityInsights@@QEBA?AVCompiledUQIConfig@23@XZ; UsageAndQualityInsights::Configuration::ConfigStore::GetCurrentConfig(void)
0x180015acc  nop
0x180015acd  lea     rdx, [rsp+288h+var_1A0]
0x180015ad5  lea     rcx, [rsp+288h+var_190]
0x180015add  call    ?GetEnrichmentDefinitions@CompiledUQIConfig@Configuration@UsageAndQualityInsights@@QEBA?AV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@UEnrichedFields@Configuration@UsageAndQualityInsights@@V?$allocator@UEnrichedFields@Configuration@UsageAndQualityInsights@@@std@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@UEnrichedFields@Configuration@UsageAndQualityInsights@@V?$allocator@UEnrichedFields@Configuration@UsageAndQualityInsights@@@std@@@2@@std@@@2@@std@@XZ; UsageAndQualityInsights::Configuration::CompiledUQIConfig::GetEnrichmentDefinitions(void)
0x180015ae2  nop
0x180015ae3  xor     r9d, r9d
0x180015ae6  lea     r8, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180015aed  lea     rcx, [rsp+288h+var_210]; int
0x180015af2  call    ?open_unique_key@reg@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@PEAUHKEY__@@PEB_WW4key_access@12@@Z; wil::reg::open_unique_key(HKEY__ *,wchar_t const *,wil::reg::key_access)
0x180015af7  nop
0x180015af8  lea     r8, aLastprocessedf; "LastProcessedFileTime"
0x180015aff  mov     rdx, [rsp+288h+var_210]
0x180015b04  lea     rcx, [rsp+288h+var_1E8]
0x180015b0c  call    ??$try_get_value@_K@reg@wil@@YA?AV?$optional@_K@std@@PEAUHKEY__@@PEB_W@Z; wil::reg::try_get_value<unsigned __int64>(HKEY__ *,wchar_t const *)
0x180015b11  mov     al, [rsp+288h+var_1E0]
0x180015b18  neg     al
0x180015b1a  sbb     rdx, rdx
0x180015b1d  mov     r13, [rsp+288h+var_1E8]
0x180015b25  and     rdx, r13
0x180015b28  lea     rcx, [rsp+288h+var_1C0]
0x180015b30  call    ?FetchMetricEvents@MetricEventsFetcher@Ingestion@UsageAndQualityInsights@@SA?AU?$pair@V?$vector@UMetricEvent@Utilities@UsageAndQualityInsights@@V?$allocator@UMetricEvent@Utilities@UsageAndQualityInsights@@@std@@@std@@_K@std@@_K@Z; UsageAndQualityInsights::Ingestion::MetricEventsFetcher::FetchMetricEvents(unsigned __int64)
0x180015b35  nop
0x180015b36  lea     rdx, [rsp+288h+var_1A0]
0x180015b3e  lea     rcx, [rsp+288h+var_1C0]
0x180015b46  call    ?EnrichEvents@EnrichmentEngine@Ingestion@UsageAndQualityInsights@@SAXAEAV?$vector@UMetricEvent@Utilities@UsageAndQualityInsights@@V?$allocator@UMetricEvent@Utilities@UsageAndQualityInsights@@@std@@@std@@AEBV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@UEnrichedFields@Configuration@UsageAndQualityInsights@@V?$allocator@UEnrichedFields@Configuration@UsageAndQualityInsights@@@std@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@UEnrichedFields@Configuration@UsageAndQualityInsights@@V?$allocator@UEnrichedFields@Configuration@UsageAndQualityInsights@@@std@@@2@@std@@@2@@5@@Z; UsageAndQualityInsights::Ingestion::EnrichmentEngine::EnrichEvents(std::vector<UsageAndQualityInsights::Utilities::MetricEvent> &,std::map<std::wstring,std::vector<UsageAndQualityInsights::Configuration::EnrichedFields>> const &)
0x180015b4b  xorps   xmm0, xmm0
0x180015b4e  movdqu  [rsp+288h+var_208], xmm0
0x180015b57  mov     [rsp+288h+var_1F8], r15
0x180015b5f  mov     rbx, [rsp+288h+var_1C0]
0x180015b67  mov     rdi, [rsp+288h+var_1B8]
0x180015b6f  cmp     rbx, rdi
0x180015b72  jz      short loc_180015BDA
0x180015b74  mov     rdx, rbx
0x180015b77  lea     rcx, [rsp+288h+var_1D8]
0x180015b7f  call    ?FromMetricEvent@FactView@Facts@UsageAndQualityInsights@@SA?AU123@AEBUMetricEvent@Utilities@3@@Z; UsageAndQualityInsights::Facts::FactView::FromMetricEvent(UsageAndQualityInsights::Utilities::MetricEvent const &)
0x180015b84  nop
0x180015b85  mov     r9, [rax+8]
0x180015b89  sub     r9, [rax]
0x180015b8c  sar     r9, 3
0x180015b90  mov     rcx, 0D37A6F4DE9BD37A7h
0x180015b9a  imul    r9, rcx
0x180015b9e  mov     r8, [rax]
0x180015ba1  mov     rdx, qword ptr [rsp+288h+var_208+8]
0x180015ba9  lea     rcx, [rsp+288h+var_208]
0x180015bb1  call    ??$_Insert_counted_range@PEBUFactRecord@Facts@UsageAndQualityInsights@@@?$vector@UFactRecord@Facts@UsageAndQualityInsights@@V?$allocator@UFactRecord@Facts@UsageAndQualityInsights@@@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UFactRecord@Facts@UsageAndQualityInsights@@@std@@@std@@@1@PEBUFactRecord@Facts@UsageAndQualityInsights@@_K@Z; std::vector<UsageAndQualityInsights::Facts::FactRecord>::_Insert_counted_range<UsageAndQualityInsights::Facts::FactRecord const *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<UsageAndQualityInsights::Facts::FactRecord>>>,UsageAndQualityInsights::Facts::FactRecord const *,unsigned __int64)
0x180015bb6  lea     rcx, [rsp+288h+var_208]; this
0x180015bbe  call    ?ReaggregateFacts@FactView@Facts@UsageAndQualityInsights@@QEAAXXZ; UsageAndQualityInsights::Facts::FactView::ReaggregateFacts(void)
0x180015bc3  nop
0x180015bc4  lea     rcx, [rsp+288h+var_1D8]
0x180015bcc  call    ?_Tidy@?$vector@UFactRecord@Facts@UsageAndQualityInsights@@V?$allocator@UFactRecord@Facts@UsageAndQualityInsights@@@std@@@std@@AEAAXXZ; std::vector<UsageAndQualityInsights::Facts::FactRecord>::_Tidy(void)
0x180015bd1  add     rbx, 108h
0x180015bd8  jmp     short loc_180015B6F
0x180015bda  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57896588@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57896588@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57896588> `wil::Feature<__WilFeatureTraits_Feature_57896588>::GetImpl(void)'::`2'::impl
0x180015be1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57896588@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57896588>::__private_IsEnabled(void)
0x180015be6  test    al, al
0x180015be8  jz      short loc_180015BF7
0x180015bea  lea     rcx, [rsp+288h+var_208]; struct UsageAndQualityInsights::Facts::FactView *
0x180015bf2  call    ?EnrichFactViewWithExpId@WnfListener@Ingestion@UsageAndQualityInsights@@CAXAEAUFactView@Facts@3@@Z; UsageAndQualityInsights::Ingestion::WnfListener::EnrichFactViewWithExpId(UsageAndQualityInsights::Facts::FactView &)
0x180015bf7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59192442@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59192442@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59192442> `wil::Feature<__WilFeatureTraits_Feature_59192442>::GetImpl(void)'::`2'::impl
0x180015bfe  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59192442@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59192442>::__private_IsEnabled(void)
0x180015c03  test    al, al
0x180015c05  jz      loc_180015C9B
0x180015c0b  lea     rcx, [rsp+288h+var_250]
0x180015c10  call    ?GetServiceObj@@YA?AV?$optional@V?$reference_wrapper@VUQIService@@@std@@@std@@XZ; GetServiceObj(void)
0x180015c15  cmp     [rax+8], r15b
0x180015c19  jz      loc_180016289
0x180015c1f  mov     rbx, [rax]
0x180015c22  mov     rax, [rbx+50h]
0x180015c26  test    rax, rax
0x180015c29  jz      short loc_180015C2F
0x180015c2b  lock inc dword ptr [rax+8]
0x180015c2f  mov     rcx, [rbx+48h]; lpCriticalSection
0x180015c33  mov     [rsp+288h+var_228], rcx
0x180015c38  mov     rbx, [rbx+50h]
0x180015c3c  mov     [rsp+288h+var_220], rbx
0x180015c41  lea     rdx, [rsp+288h+var_208]; struct UsageAndQualityInsights::Facts::FactView *
0x180015c49  call    ?PushFactView@FactStoreManager@Facts@UsageAndQualityInsights@@QEAAXAEBUFactView@23@_N@Z; UsageAndQualityInsights::Facts::FactStoreManager::PushFactView(UsageAndQualityInsights::Facts::FactView const &,bool)
0x180015c4e  nop
0x180015c4f  or      edi, 0FFFFFFFFh
0x180015c52  test    rbx, rbx
0x180015c55  jz      short loc_180015C8A
0x180015c57  mov     eax, edi
0x180015c59  lock xadd [rbx+8], eax
0x180015c5e  add     eax, edi
0x180015c60  jnz     short loc_180015C8A
0x180015c62  mov     rax, [rbx]
0x180015c65  mov     rcx, rbx
0x180015c68  mov     rax, [rax]
0x180015c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c70  mov     eax, edi
0x180015c72  lock xadd [rbx+0Ch], eax
0x180015c77  add     eax, edi
0x180015c79  jnz     short loc_180015C8A
0x180015c7b  mov     rax, [rbx]
0x180015c7e  mov     rcx, rbx
0x180015c81  mov     rax, [rax+8]
0x180015c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c8a  lea     rcx, aPushedFactview; "Pushed FactView to FactStore from WNF l"...
0x180015c91  call    ?TraceLoggingInfo@UsageAndQualityInsightsTraceLogging@@SAXPEBDZZ; UsageAndQualityInsightsTraceLogging::TraceLoggingInfo(char const *,...)
0x180015c96  jmp     loc_180016021
0x180015c9b  lea     rdx, [rsp+288h+var_1D8]
0x180015ca3  lea     rcx, [rsp+288h+var_190]
0x180015cab  call    ?GetTelemetryEndpointConfigs@CompiledUQIConfig@Configuration@UsageAndQualityInsights@@QEBA?AV?$vector@UTelemetryEndpointConfig@Configuration@UsageAndQualityInsights@@V?$allocator@UTelemetryEndpointConfig@Configuration@UsageAndQualityInsights@@@std@@@std@@XZ; UsageAndQualityInsights::Configuration::CompiledUQIConfig::GetTelemetryEndpointConfigs(void)
0x180015cb0  nop
0x180015cb1  mov     rdi, [rsp+288h+var_1D8]
0x180015cb9  mov     r12, [rsp+288h+var_1D0]
0x180015cc1  cmp     rdi, r12
0x180015cc4  jz      loc_180016011
0x180015cca  lea     rax, [rsp+288h+var_118]
0x180015cd2  mov     [rsp+288h+var_258], rax
0x180015cd7  xorps   xmm0, xmm0
0x180015cda  movdqa  [rsp+288h+var_118], xmm0
0x180015ce3  mov     [rsp+288h+var_108], r15
0x180015ceb  mov     rax, [rdi+8]
0x180015cef  sub     rax, [rdi]
0x180015cf2  sar     rax, 3
0x180015cf6  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x180015d00  imul    rax, rcx
0x180015d04  test    rax, rax
0x180015d07  jz      loc_180015DEE
0x180015d0d  mov     rcx, 666666666666666h
0x180015d17  cmp     rax, rcx
0x180015d1a  ja      loc_18001628F
0x180015d20  lea     rax, [rax+rax*4]
0x180015d24  lea     rsi, ds:0[rax*8]
0x180015d2c  test    rsi, rsi
0x180015d2f  jnz     short loc_180015D36
0x180015d31  mov     rbx, r15
0x180015d34  jmp     short loc_180015D74
0x180015d36  cmp     rsi, 1000h
0x180015d3d  jb      short loc_180015D69
0x180015d3f  lea     rcx, [rsi+27h]; Size
0x180015d43  cmp     rcx, rsi
0x180015d46  jbe     loc_180016294
0x180015d4c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015d51  test    rax, rax
0x180015d54  jnz     short loc_180015D5B
0x180015d56  lea     ecx, [rax+5]
0x180015d59  int     29h; Win8: RtlFailFast(ecx)
0x180015d5b  lea     rbx, [rax+27h]
0x180015d5f  and     rbx, 0FFFFFFFFFFFFFFE0h
0x180015d63  mov     [rbx-8], rax
0x180015d67  jmp     short loc_180015D74
0x180015d69  mov     rcx, rsi; Size
0x180015d6c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015d71  mov     rbx, rax
0x180015d74  mov     qword ptr [rsp+288h+var_118], rbx
0x180015d7c  mov     qword ptr [rsp+288h+var_118+8], rbx
0x180015d84  lea     rcx, [rbx+rsi]
0x180015d88  mov     [rsp+288h+var_108], rcx
0x180015d90  lea     rax, [rsp+288h+var_118]
0x180015d98  mov     [rsp+288h+var_1F0], rax
0x180015da0  mov     rsi, [rdi]
0x180015da3  mov     r15, [rdi+8]
0x180015da7  mov     [rsp+288h+var_240], rbx
0x180015dac  mov     [rsp+288h+var_238], rbx
0x180015db1  lea     rax, [rsp+288h+var_118]
0x180015db9  mov     [rsp+288h+var_230], rax
0x180015dbe  cmp     rsi, r15
0x180015dc1  jz      short loc_180015DE3
0x180015dc3  mov     eax, [rsi]
0x180015dc5  mov     [rbx], eax
0x180015dc7  lea     rdx, [rsi+8]
0x180015dcb  lea     rcx, [rbx+8]
0x180015dcf  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180015dd4  add     rbx, 28h ; '('
0x180015dd8  mov     [rsp+288h+var_238], rbx
0x180015ddd  add     rsi, 28h ; '('
0x180015de1  jmp     short loc_180015DBE
0x180015de3  mov     qword ptr [rsp+288h+var_118+8], rbx
0x180015deb  xor     r15d, r15d
0x180015dee  lea     rdx, [rdi+18h]
0x180015df2  lea     rcx, [rsp+288h+var_100]
0x180015dfa  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x180015dff  nop
0x180015e00  lea     rdx, [rdi+30h]
0x180015e04  lea     rcx, [rsp+288h+var_E8]
0x180015e0c  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x180015e11  mov     al, [rdi+48h]
0x180015e14  mov     [rsp+288h+var_D0], al
0x180015e1b  mov     eax, [rdi+4Ch]
0x180015e1e  mov     [rsp+288h+var_CC], eax
0x180015e25  mov     eax, [rdi+50h]
0x180015e28  mov     [rsp+288h+var_C8], eax
0x180015e2f  lea     rdx, [rdi+58h]
0x180015e33  lea     rcx, [rsp+288h+var_C0]
0x180015e3b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180015e40  nop
0x180015e41  lea     rdx, [rdi+78h]
0x180015e45  lea     rcx, [rsp+288h+var_A0]
0x180015e4d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180015e52  mov     eax, [rdi+98h]
0x180015e58  mov     [rsp+288h+var_80], eax
0x180015e5f  mov     eax, [rdi+9Ch]
0x180015e65  mov     [rsp+288h+var_7C], eax
0x180015e6c  mov     rax, [rdi+0A0h]
0x180015e73  mov     [rsp+288h+var_78], rax
0x180015e7b  lea     rdx, [rsp+288h+var_208]
0x180015e83  lea     rcx, [rsp+288h+var_240]
0x180015e88  call    ??0?$vector@UFactRecord@Facts@UsageAndQualityInsights@@V?$allocator@UFactRecord@Facts@UsageAndQualityInsights@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<UsageAndQualityInsights::Facts::FactRecord>::vector<UsageAndQualityInsights::Facts::FactRecord>(std::vector<UsageAndQualityInsights::Facts::FactRecord> const &)
0x180015e8d  nop
0x180015e8e  mov     [rsp+288h+var_250], r15
0x180015e93  mov     [rsp+288h+var_248], r15
0x180015e98  mov     ecx, 40h ; '@'; Size
0x180015e9d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015ea2  mov     [rax], rax
0x180015ea5  mov     [rax+8], rax
  ... truncated ...
```
