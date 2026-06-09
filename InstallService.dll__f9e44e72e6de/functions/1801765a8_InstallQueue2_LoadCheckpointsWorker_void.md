# InstallQueue2::_LoadCheckpointsWorker(void)

- ea: `0x1801765a8`
- end: `0x180177644`
- name: `?_LoadCheckpointsWorker@InstallQueue2@@AEAAXXZ`
- size: `4252`
- prototype: `void __fastcall(InstallQueue2 *__hidden this)`
- caller_count: `1`
- callee_count: `75`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801590ec`

## callees

- `0x180009ea0`
- `0x18000ad3c`
- `0x18001bf24`
- `0x18001c964`
- `0x180020868`
- `0x1800208e4`
- `0x180022298`
- `0x180022e50`
- `0x18002d98c`
- `0x180036618`
- `0x180036bd8`
- `0x180036e6c`
- `0x180036ea8`
- `0x180037200`
- `0x1800375c0`
- `0x1800378d0`
- `0x18003b7b0`
- `0x18003b8c0`
- `0x180044a28`
- `0x180044b48`
- `0x1800453a0`
- `0x180045588`
- `0x18004567c`
- `0x18004579c`
- `0x180047818`
- `0x18006c688`
- `0x18006cc00`
- `0x18006cc2c`
- `0x18006cf2c`
- `0x18006d98c`
- `0x180095b2c`
- `0x1800a5114`
- `0x1800b1e24`
- `0x1800b7b08`
- `0x1800c18bc`
- `0x1800c5470`
- `0x1800ced70`
- `0x1800fd090`
- `0x1800fd1f8`
- `0x180138ec8`
- `0x1801391a8`
- `0x18014ed14`
- `0x180157690`
- `0x1801576c8`
- `0x180157760`
- `0x180157a74`
- `0x180157ae4`
- `0x180157b6c`
- `0x180158d54`
- `0x180158d90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180176f43`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180176f43`
- `msvcp_win!_Xtime_get_ticks` at `0x180176e1a`
- `msvcp_win!_Xtime_get_ticks` at `0x180176f66`
- `msvcp_win!_Xtime_get_ticks` at `0x180176e1a`
- `msvcp_win!_Xtime_get_ticks` at `0x180176f66`

## string_xrefs

- `0x180176710`: `ScanForUpdates`
- `0x180176748`: `ScanForUpdatesForUser`
- `0x1801768fd`: `onecoreuap\enduser\winstore\installservice\libqueue2\installqueue2.cpp`
- `0x1801769ea`: `onecoreuap\enduser\winstore\installservice\libqueue2\installqueue2.cpp`
- `0x180176a88`: `onecoreuap\enduser\winstore\installservice\libqueue2\installqueue2.cpp`
- `0x180176ca2`: `onecoreuap\enduser\winstore\installservice\libqueue2\installqueue2.cpp`
- `0x1801770fa`: `onecoreuap\enduser\winstore\installservice\libqueue2\installqueue2.cpp`
- `0x180177559`: `onecoreuap\enduser\winstore\installservice\libqueue2\installqueue2.cpp`
- `0x1801769ba`: `checkpointDataJsonObj is null or empty. Cannot increment attempt count.`
- `0x1801768e8`: `InstallQueue2::_LoadCheckpointsWorker`
- `0x1801769d5`: `InstallQueue2::_LoadCheckpointsWorker`
- `0x180176a73`: `InstallQueue2::_LoadCheckpointsWorker`
- `0x180176c8d`: `InstallQueue2::_LoadCheckpointsWorker`
- `0x1801770e5`: `InstallQueue2::_LoadCheckpointsWorker`
- `0x180177544`: `InstallQueue2::_LoadCheckpointsWorker`
- `0x180176a58`: `CheckpointDataBlob is null or empty. Cannot increment attempt count.`
- `0x180177530`: `Fulfillment Data is not present so install cannot proceed.  Abandoning file since it cannot recover`
- `0x180176888`: `systemAttemptCount`
- `0x180176c2d`: `systemAttemptCount`

## pseudocode

```c
// Hidden C++ exception states: #wind=97 #try_helpers=1
void __fastcall InstallQueue2::_LoadCheckpointsWorker(InstallQueue2 *this)
{
  double v1; // xmm0_8
  InstallQueue2 *v2; // r13
  int v3; // r15d
  CheckpointData **v4; // rcx
  CheckpointData **v5; // rdx
  CheckpointData **v6; // r14
  const unsigned __int16 *v7; // rdx
  bool Value; // bl
  _QWORD *v9; // rcx
  const struct CheckpointData::Data *v10; // rdx
  _QWORD *v11; // rcx
  std::_Ref_count_base *v12; // rbx
  const unsigned __int16 *v13; // rbx
  unsigned int NetworkConnectivityLevel; // eax
  __int64 NumberValue; // rbx
  __int64 v16; // rbx
  int v17; // r9d
  __int64 v18; // rdx
  __int64 IBufferFromString; // rax
  __int64 *v20; // rax
  __int64 v21; // rcx
  const unsigned __int16 *v22; // rbx
  unsigned int v23; // eax
  __int64 v24; // rbx
  __int64 v25; // rbx
  int v26; // r9d
  __int64 v27; // rdx
  __int64 v28; // rax
  _QWORD *v29; // rax
  int v30; // ebx
  __int64 ticks; // rbx
  _QWORD *v32; // rax
  double v33; // xmm6_8
  __int64 v34; // rbx
  __int64 v35; // rdi
  const wchar_t *v36; // rax
  const wchar_t *v37; // rdx
  unsigned int v38; // ecx
  __int64 v39; // rax
  CheckpointData *v40; // rbx
  __int64 WorkProperties; // rax
  CheckpointData *v42; // rdx
  __int64 CatalogItemFromLocalData; // rax
  __int64 v44; // r12
  __int64 v45; // r13
  __int64 v46; // rdi
  __int64 v47; // rbx
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rdi
  _QWORD *v51; // rbx
  __int64 v52; // rax
  unsigned int *v53; // rax
  __int64 v54; // r8
  unsigned int *v55; // rax
  __int64 v56; // r8
  unsigned int *v57; // rax
  __int64 v58; // r8
  __int64 v59; // [rsp+58h] [rbp-780h] BYREF
  std::_Ref_count_base *v60[2]; // [rsp+60h] [rbp-778h] BYREF
  __int64 v61; // [rsp+78h] [rbp-760h] BYREF
  char v62[8]; // [rsp+80h] [rbp-758h] BYREF
  __int64 v63; // [rsp+88h] [rbp-750h] BYREF
  char v64[8]; // [rsp+90h] [rbp-748h] BYREF
  char v65[8]; // [rsp+98h] [rbp-740h] BYREF
  InstallQueue2 *v66; // [rsp+A0h] [rbp-738h]
  __int64 v67[2]; // [rsp+A8h] [rbp-730h] BYREF
  _QWORD v68[7]; // [rsp+B8h] [rbp-720h] BYREF
  __int64 v69; // [rsp+F0h] [rbp-6E8h] BYREF
  __int64 v70[2]; // [rsp+F8h] [rbp-6E0h] BYREF
  __int64 v71[4]; // [rsp+108h] [rbp-6D0h] BYREF
  CheckpointData **v72; // [rsp+128h] [rbp-6B0h] BYREF
  CheckpointData **v73; // [rsp+130h] [rbp-6A8h]
  __int64 v74; // [rsp+138h] [rbp-6A0h]
  CheckpointData **v75; // [rsp+148h] [rbp-690h]
  char v76[8]; // [rsp+150h] [rbp-688h] BYREF
  char v77[8]; // [rsp+158h] [rbp-680h] BYREF
  char v78[8]; // [rsp+160h] [rbp-678h] BYREF
  char v79[8]; // [rsp+168h] [rbp-670h] BYREF
  char v80[8]; // [rsp+170h] [rbp-668h] BYREF
  char v81[8]; // [rsp+178h] [rbp-660h] BYREF
  char v82[8]; // [rsp+180h] [rbp-658h] BYREF
  char v83[8]; // [rsp+188h] [rbp-650h] BYREF
  char v84[8]; // [rsp+190h] [rbp-648h] BYREF
  char v85[8]; // [rsp+198h] [rbp-640h] BYREF
  char v86[8]; // [rsp+1A0h] [rbp-638h] BYREF
  char v87[8]; // [rsp+1A8h] [rbp-630h] BYREF
  char v88[8]; // [rsp+1B0h] [rbp-628h] BYREF
  char v89[8]; // [rsp+1B8h] [rbp-620h] BYREF
  char v90[8]; // [rsp+1C0h] [rbp-618h] BYREF
  char v91[8]; // [rsp+1C8h] [rbp-610h] BYREF
  char v92[8]; // [rsp+1D0h] [rbp-608h] BYREF
  char v93[8]; // [rsp+1D8h] [rbp-600h] BYREF
  char v94[8]; // [rsp+1E0h] [rbp-5F8h] BYREF
  char v95[8]; // [rsp+1E8h] [rbp-5F0h] BYREF
  _BYTE v96[24]; // [rsp+1F0h] [rbp-5E8h] BYREF
  char v97[4]; // [rsp+208h] [rbp-5D0h] BYREF
  char v98[4]; // [rsp+20Ch] [rbp-5CCh] BYREF
  char v99[8]; // [rsp+210h] [rbp-5C8h] BYREF
  _QWORD v100[7]; // [rsp+218h] [rbp-5C0h] BYREF
  _QWORD v101[2]; // [rsp+250h] [rbp-588h] BYREF
  _QWORD v102[2]; // [rsp+260h] [rbp-578h] BYREF
  _QWORD v103[2]; // [rsp+270h] [rbp-568h] BYREF
  _QWORD v104[8]; // [rsp+280h] [rbp-558h] BYREF
  _QWORD v105[2]; // [rsp+2C0h] [rbp-518h] BYREF
  _QWORD v106[3]; // [rsp+2D0h] [rbp-508h] BYREF
  char v107[8]; // [rsp+2E8h] [rbp-4F0h] BYREF
  std::_Ref_count_base *v108; // [rsp+2F0h] [rbp-4E8h]
  _BYTE v109[16]; // [rsp+2F8h] [rbp-4E0h] BYREF
  char v110; // [rsp+308h] [rbp-4D0h] BYREF
  std::_Ref_count_base *v111; // [rsp+310h] [rbp-4C8h]
  char v112[16]; // [rsp+318h] [rbp-4C0h] BYREF
  char v113[24]; // [rsp+328h] [rbp-4B0h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+340h] [rbp-498h] BYREF
  _BYTE v115[24]; // [rsp+358h] [rbp-480h] BYREF
  _BYTE v116[24]; // [rsp+370h] [rbp-468h] BYREF
  char v117[16]; // [rsp+388h] [rbp-450h] BYREF
  char v118[16]; // [rsp+398h] [rbp-440h] BYREF
  _BYTE v119[40]; // [rsp+3A8h] [rbp-430h] BYREF
  char v120[24]; // [rsp+3D0h] [rbp-408h] BYREF
  char v121[24]; // [rsp+3E8h] [rbp-3F0h] BYREF
  _QWORD v122[4]; // [rsp+400h] [rbp-3D8h] BYREF
  _QWORD v123[2]; // [rsp+420h] [rbp-3B8h] BYREF
  __int64 v124; // [rsp+430h] [rbp-3A8h]
  unsigned __int64 v125; // [rsp+438h] [rbp-3A0h]
  _QWORD v126[4]; // [rsp+440h] [rbp-398h] BYREF
  char v127[304]; // [rsp+460h] [rbp-378h] BYREF
  _BYTE v128[32]; // [rsp+590h] [rbp-248h] BYREF
  _BYTE v129[448]; // [rsp+5B0h] [rbp-228h] BYREF

  v2 = this;
  v66 = this;
  v68[6] = this;
  v3 = 0;
  if ( InstallQueue2::_serviceStop )
    return;
  CheckpointData::Load(&v72);
  v4 = v72;
  v5 = v73;
  *((_QWORD *)v2 + 88) = ((char *)v73 - (char *)v72) >> 4;
  v6 = v4;
  v75 = v5;
  while ( 1 )
  {
    v68[3] = v6;
    if ( v6 == v75 )
      break;
    v67[1] = (__int64)v6;
    if ( InstallQueue2::_serviceStop )
      break;
    v122[0] = *((_QWORD *)*v6 + 3);
    winrt::Windows::Data::Json::JsonObject::Parse((const struct winrt::param::hstring *)v65);
    PluginHelpers::WorkProperty::CallerApplicationId::GetValue(v64, v65);
    v7 = winrt::hstring::c_str((winrt::hstring *)v64);
    GetClientIdFromFullAppId(v123, v7);
    Value = PluginHelpers::WorkProperty::IsInteractive::GetValue((const struct winrt::Windows::Data::Json::JsonObject *)v65);
    v9 = v123;
    if ( v125 > 7 )
      v9 = (_QWORD *)v123[0];
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v9, v124, L"ScanForUpdates", 14) )
      goto LABEL_11;
    v11 = v123;
    if ( v125 > 7 )
      v11 = (_QWORD *)v123[0];
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v11, v124, L"ScanForUpdatesForUser", 21) )
    {
LABEL_11:
      if ( !Value )
      {
        CheckpointData::Delete(*v6, v10);
        std::wstring::_Tidy_deallocate(v123);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v64);
        winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v65);
        goto LABEL_69;
      }
    }
    if ( !*((_QWORD *)*v6 + 1) )
    {
      winrt::impl::slim_source_location::current(v121);
      v57 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)v99, -2143309818);
      winrt::hresult_error::hresult_error(v116, *v57, v58);
      throw (winrt::hresult_error *)v116;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AttemptCountIncrementForRetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AttemptCountIncrementForRetry>::GetImpl'::`2'::impl) )
    {
      v60[0] = *((std::_Ref_count_base **)*v6 + 6);
      v12 = v60[0];
      winrt::Windows::Foundation::IUnknown::add_ref((winrt::Windows::Foundation::IUnknown *)v60);
      if ( v12
        && (unsigned int)winrt::impl::consume_Windows_Networking_Connectivity_IConnectionProfile<winrt::Windows::Networking::Connectivity::IConnectionProfile>::GetNetworkConnectivityLevel(v60) )
      {
        v13 = (const unsigned __int16 *)winrt::impl::consume_Windows_Storage_Streams_IBuffer<winrt::Windows::Storage::Streams::IBuffer>::data(v60);
        NetworkConnectivityLevel = winrt::impl::consume_Windows_Networking_Connectivity_IConnectionProfile<winrt::Windows::Networking::Connectivity::IConnectionProfile>::GetNetworkConnectivityLevel(v60);
        v100[0] = *(_QWORD *)winrt::hstring::hstring((winrt::hstring *)v76, v13, NetworkConnectivityLevel >> 1);
        winrt::Windows::Data::Json::JsonObject::Parse((const struct winrt::param::hstring *)&v61);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v76);
        if ( v61
          && (unsigned int)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Size(&v61) )
        {
          ++*((_DWORD *)*v6 + 17);
          NumberValue = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(v1);
          winrt::param::hstring::hstring((winrt::param::hstring *)v122, L"systemAttemptCount");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
            &v61,
            v122,
            NumberValue);
          winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v77);
          v16 = winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonArray>::Stringify(
                  &v61,
                  v78);
          v105[0] = L"LoadCheckpointWorker CheckpointDataBlob is  ";
          v105[1] = 44;
          std::string::string(v122, "InstallQueue2::_LoadCheckpointsWorker");
          std::string::string(v126, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp");
          Logging::Log<winrt::hstring>((unsigned int)v126, 4908, (unsigned int)v122, v17, (__int64)v105, v16);
          std::string::~string(v126);
          std::string::~string(v122);
          winrt::handle_type<winrt::impl::hstring_traits>::close(v78);
          v18 = winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonArray>::Stringify(
                  &v61,
                  v80);
          IBufferFromString = CreateIBufferFromString(v79, v18);
          winrt::Windows::Foundation::IUnknown::operator=((char *)*v6 + 48, IBufferFromString);
          winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v79);
          winrt::handle_type<winrt::impl::hstring_traits>::close(v80);
        }
        else
        {
          v101[0] = L"checkpointDataJsonObj is null or empty. Cannot increment attempt count.";
          v101[1] = 71;
          std::string::string(v126, "InstallQueue2::_LoadCheckpointsWorker");
          std::string::string(v122, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp");
          Logging::Log<>((unsigned int)v122, 4902, (unsigned int)v126, 2, (__int64)v101);
          std::string::~string(v122);
          std::string::~string(v126);
        }
        winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v61);
      }
      else
      {
        v102[0] = L"CheckpointDataBlob is null or empty. Cannot increment attempt count.";
        v102[1] = 68;
        std::string::string(v126, "InstallQueue2::_LoadCheckpointsWorker");
        std::string::string(v122, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp");
        Logging::Log<>((unsigned int)v122, 4895, (unsigned int)v126, 2, (__int64)v102);
        std::string::~string(v122);
        std::string::~string(v126);
      }
LABEL_34:
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v60);
      goto LABEL_35;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IncrementAttemptCountForRetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IncrementAttemptCountForRetry>::GetImpl'::`2'::impl) )
    {
      v60[0] = *((std::_Ref_count_base **)*v6 + 6);
      winrt::Windows::Foundation::IUnknown::add_ref((winrt::Windows::Foundation::IUnknown *)v60);
      v59 = 0;
      if ( (unsigned __int8)winrt::Windows::Foundation::operator==(v60, &v59) )
      {
        v69 = 0;
        v20 = &v69;
        v3 |= 1u;
        v21 = 0;
      }
      else
      {
        v22 = (const unsigned __int16 *)winrt::impl::consume_Windows_Storage_Streams_IBuffer<winrt::Windows::Storage::Streams::IBuffer>::data(v60);
        v23 = winrt::impl::consume_Windows_Networking_Connectivity_IConnectionProfile<winrt::Windows::Networking::Connectivity::IConnectionProfile>::GetNetworkConnectivityLevel(v60);
        v100[0] = *(_QWORD *)winrt::hstring::hstring((winrt::hstring *)v82, v22, v23 >> 1);
        v20 = (__int64 *)winrt::Windows::Data::Json::JsonObject::Parse((const struct winrt::param::hstring *)v81);
        v3 |= 6u;
        v21 = *v20;
      }
      *v20 = 0;
      v59 = v21;
      if ( (v3 & 4) != 0 )
      {
        v3 &= ~4u;
        winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v81);
      }
      if ( (v3 & 2) != 0 )
      {
        v3 &= ~2u;
        winrt::handle_type<winrt::impl::hstring_traits>::close(v82);
      }
      if ( (v3 & 1) != 0 )
      {
        v3 &= ~1u;
        winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v69);
      }
      ++*((_DWORD *)*v6 + 17);
      v24 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(v1);
      winrt::param::hstring::hstring((winrt::param::hstring *)v122, L"systemAttemptCount");
      winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
        &v59,
        v122,
        v24);
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v83);
      v25 = winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonArray>::Stringify(
              &v59,
              v84);
      v103[0] = L"LoadCheckpointWorker CheckpointDataBlob is  ";
      v103[1] = 44;
      std::string::string(v126, "InstallQueue2::_LoadCheckpointsWorker");
      std::string::string(v122, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp");
      Logging::Log<winrt::hstring>((unsigned int)v122, 4921, (unsigned int)v126, v26, (__int64)v103, v25);
      std::string::~string(v122);
      std::string::~string(v126);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v84);
      v27 = winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonArray>::Stringify(
              &v59,
              v86);
      v28 = CreateIBufferFromString(v85, v27);
      winrt::Windows::Foundation::IUnknown::operator=((char *)*v6 + 48, v28);
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v85);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v86);
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v59);
      goto LABEL_34;
    }
LABEL_35:
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TIPForCheckpoint>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TIPForCheckpoint>::GetImpl'::`2'::impl) )
    {
      v59 = 0;
      v29 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<TipTests::_tip_SystemAttemptCountTipTest,TipTests::_tip_SystemAttemptCountTipTest>>::ensure_data(&v59);
      tip2::details::shared_data<0,0,0>::start(*v29 + 8LL, v117);
      if ( *((_DWORD *)*v6 + 17) > 0x32u )
      {
        *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<TipTests::_tip_SystemAttemptCountTipTest,TipTests::_tip_SystemAttemptCountTipTest>>::operator->(
                                &v59,
                                v87)
                 + 272LL) = 1;
        tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_SystemAttemptCountTipTest,TipTests::_tip_SystemAttemptCountTipTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_SystemAttemptCountTipTest,TipTests::_tip_SystemAttemptCountTipTest>>(v87);
        v30 = *((_DWORD *)*v6 + 17);
        *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<TipTests::_tip_SystemAttemptCountTipTest,TipTests::_tip_SystemAttemptCountTipTest>>::operator->(
                                 &v59,
                                 v88)
                  + 276LL) = v30;
        tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_SystemAttemptCountTipTest,TipTests::_tip_SystemAttemptCountTipTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_SystemAttemptCountTipTest,TipTests::_tip_SystemAttemptCountTipTest>>(v88);
      }
      if ( v59 )
        tip2::details::shared_data<0,0,0>::complete_without_lock(v59 + 8);
      ticks = _Xtime_get_ticks();
      if ( ticks >= *((_QWORD *)*v6 + 12) )
      {
        v60[0] = 0;
        v32 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<TipTests::_tip_AppInstallCreationDateTipTest,TipTests::_tip_AppInstallCreationDateTipTest>>::ensure_data(v60);
        tip2::details::shared_data<0,0,0>::start(*v32 + 8LL, v118);
        v33 = (double)((int)ticks - *((_DWORD *)*v6 + 24)) / 8.64e11;
        if ( v33 > 90.0 )
        {
          *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<TipTests::_tip_AppInstallCreationDateTipTest,TipTests::_tip_AppInstallCreationDateTipTest>>::operator->(
                                  v60,
                                  v89)
                   + 272LL) = 1;
          tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_AppInstallCreationDateTipTest,TipTests::_tip_AppInstallCreationDateTipTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_AppInstallCreationDateTipTest,TipTests::_tip_AppInstallCreationDateTipTest>>(v89);
          *(_QWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<TipTests::_tip_AppInstallCreationDateTipTest,TipTests::_tip_AppInstallCreationDateTipTest>>::operator->(
                                   v60,
                                   v90)
                    + 280LL) = (int)v33;
          tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_AppInstallCreationDateTipTest,TipTests::_tip_AppInstallCreationDateTipTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_AppInstallCreationDateTipTest,TipTests::_tip_AppInstallCreationDateTipTest>>(v90);
        }
        if ( v60[0] )
          tip2::details::shared_data<0,0,0>::complete_without_lock((char *)v60[0] + 8);
        wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_AppInstallCreationDateTipTest,TipTests::_tip_AppInstallCreationDateTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_AppInstallCreationDateTipTest,TipTests::_tip_AppInstallCreationDateTipTest>,wil::err_returncode_policy>(v60);
      }
      wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_SystemAttemptCountTipTest,TipTests::_tip_SystemAttemptCountTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_SystemAttemptCountTipTest,TipTests::_tip_SystemAttemptCountTipTest>,wil::err_returncode_policy>(&v59);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AbandonStaleWindowsStoreCheckpoints>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AbandonStaleWindowsStoreCheckpoints>::GetImpl'::`2'::impl) )
    {
      GetCheckpointAbandonmentRulesFromOneSettings(v106);
      v34 = v106[0];
      v35 = v106[1];
      while ( v34 != v35 )
      {
        v36 = winrt::hstring::c_str((winrt::hstring *)v64);
        if ( wcsstr(v36, v37) )
        {
          if ( (v38 = *(_DWORD *)(v34 + 32)) != 0 && *((_DWORD *)*v6 + 17) > v38
            || *(_DWORD *)(v34 + 36)
            && (v39 = _Xtime_get_ticks(), v39 >= *((_QWORD *)*v6 + 12))
            && (double)((int)v39 - *((_DWORD *)*v6 + 24)) / 8.64e11 > (double)*(int *)(v34 + 36) )
          {
            winrt::impl::slim_source_location::current(v120);
            v53 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)v97, -2143309818);
            winrt::hresult_error::hresult_error(pExceptionObject, *v53, v54);
            throw (winrt::hresult_error *)pExceptionObject;
          }
        }
        v34 += 40;
      }
      std::vector<UpdateToDownload>::_Tidy(v106);
      v2 = v66;
    }
    PluginHelpers::ActivatePlugin(v70, (__int64 *)*v6, (CheckpointData *)((char *)*v6 + 8));
    v40 = *v6;
    WorkProperties = PluginHelpers::ParseCreateWorkProperties(
                       (PluginHelpers *)v91,
                       (CheckpointData *)((char *)*v6 + 24));
    v42 = *v6;
    v100[0] = *((_QWORD *)*v6 + 2);
    v122[0] = *(_QWORD *)v42;
    v126[0] = *((_QWORD *)v42 + 5);
    winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServicePlugin<winrt::Windows::Internal::InstallService::Plugin::IInstallServicePlugin>::CreateInstallServiceWork(
      (unsigned int)v70,
      (unsigned int)&v63,
      (unsigned int)v126,
      (unsigned int)v122,
      (__int64)v100,
      WorkProperties,
      (__int64)v40 + 48);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v91);
    CorrelationVector::ValidateAndCreate(v127, (char *)*v6 + 40);
    CallerContext2::CallerContext2((CallerContext2 *)v71, *v6, 1);
    v3 |= 8u;
    v100[0] = *((_QWORD *)*v6 + 3);
    winrt::Windows::Data::Json::JsonObject::Parse((const struct winrt::param::hstring *)v62);
    v1 = 0.0;
    *(_OWORD *)v60 = 0;
    if ( PluginHelpers::WorkProperty::SkipCatalogLookup::GetValue((const struct winrt::Windows::Data::Json::JsonObject *)v62) )
    {
      v104[0] = L"Skipcatalog lookup specified so creating catalogitem locally";
      v104[1] = 60;
      std::string::string(v126, "InstallQueue2::_LoadCheckpointsWorker");
      std::string::string(v122, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp");
      Logging::Log<>((unsigned int)v122, 4997, (unsigned int)v126, 3, (__int64)v104);
      std::string::~string(v122);
      std::string::~string(v126);
      PluginHelpers::WorkProperty::SerializedFulfillmentData::GetValue(v68, v62);
      if ( !v68[0] )
      {
        std::basic_string_view<unsigned short>::basic_string_view<unsigned short,std::char_traits<unsigned short>>(
          v109,
          L"Fulfillment Data is not present so install cannot proceed.  Abandoning file since it cannot recover");
        std::string::string(v129, "InstallQueue2::_LoadCheckpointsWorker");
        std::string::string(v128, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp");
        Logging::Log<>((unsigned int)v128, 5002, (unsigned int)v129, 1, (__int64)v109);
        std::string::~string(v128);
        std::string::~string(v129);
        winrt::impl::slim_source_location::current(v126);
        v55 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)v98, -2143309818);
        winrt::hresult_error::hresult_error(v115, *v55, v56);
        throw (winrt::hresult_error *)v115;
      }
      winrt::hstring::hstring((winrt::hstring *)v92, (const unsigned __int16 *)&dword_18023C12C);
      CatalogItemFromLocalData = CreateCatalogItemFromLocalData(v107, v71, (char *)*v6 + 24);
      std::shared_ptr<CatalogDataStore::CatalogItem>::operator=(v60, CatalogItemFromLocalData);
      if ( v108 )
        std::_Ref_count_base::_Decref(v108);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v92);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v68);
    }
    else
    {
      v44 = *(_QWORD *)CatalogDataStore::GetSingleton();
      v45 = winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkItemSubTask<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItemSubTask>::SearchId(
              &v63,
              v96);
      v46 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_Internal_IOEMHardwareInfo<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IOEMHardwareInfo>::OemId(
              &v63,
              v95);
      v47 = PluginHelpers::WorkProperty::CatalogId::GetValue(v94, v62);
      v48 = PluginHelpers::WorkProperty::UserIdentityInfo::GetValue(v93, v62);
      v49 = CatalogDataStore::LookupForUser(
              v44,
              (unsigned int)&v110,
              (unsigned int)v127,
              (unsigned int)v71,
              v48,
              v47,
              v46,
              v45,
              1);
      std::shared_ptr<CatalogDataStore::CatalogItem>::operator=(v60, v49);
      if ( v111 )
        std::_Ref_count_base::_Decref(v111);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v93);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v94);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v95);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v96);
      v2 = v66;
    }
    v50 = std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(v112, v6);
    v67[0] = v63;
    winrt::Windows::Foundation::IUnknown::add_ref((winrt::Windows::Foundation::IUnknown *)v67);
    v51 = (_QWORD *)std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(v113, v60);
    v52 = InstallQueue2::_LockQueueForEdit(v2, v100);
    InstallQueue2::_EnqueueWork(v2, (__int64)v119, v52, v127, (struct CallerContext2 *)v71, v51, v67, v50, 0);
    __1__exclusive_lock_with_release_callback_VInstallQueue2__P81_EAAXX_E__UEAA_XZ(v100);
    std::tuple<std::vector<winrt::WindowsUpdate::Internal::InstallItem>,std::shared_ptr<InstallQueue2::QueueItem>>::~tuple<std::vector<winrt::WindowsUpdate::Internal::InstallItem>,std::shared_ptr<InstallQueue2::QueueItem>>(v119);
    if ( v60[1] )
      std::_Ref_count_base::_Decref(v60[1]);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v62);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v71);
    CorrelationVector::~CorrelationVector((CorrelationVector *)v127);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v63);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v70);
    std::wstring::_Tidy_deallocate(v123);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v64);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v65);
LABEL_69:
    v6 += 2;
    v5 = v73;
    v4 = v72;
  }
  *((_BYTE *)v2 + 697) = 1;
  if ( v4 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<InstallQueue2::QueueItem>>>(v4, v5);
    std::_Deallocate<16>(v72, (v74 - (_QWORD)v72) & 0xFFFFFFFFFFFFFFF0uLL);
  }
}

```

## disassembly

```asm
0x1801765a8  mov     rax, rsp
0x1801765ab  mov     [rax+10h], rbx
0x1801765af  mov     [rax+18h], rsi
0x1801765b3  push    rdi
0x1801765b4  push    r12
0x1801765b6  push    r13
0x1801765b8  push    r14
0x1801765ba  push    r15
0x1801765bc  sub     rsp, 7B0h
0x1801765c3  movaps  xmmword ptr [rax-38h], xmm6
0x1801765c7  movaps  xmmword ptr [rax-48h], xmm7
0x1801765cb  movaps  xmmword ptr [rax-58h], xmm8
0x1801765d0  mov     rax, cs:__security_cookie
0x1801765d7  xor     rax, rsp
0x1801765da  mov     [rsp+7D8h+var_68], rax
0x1801765e2  mov     r13, rcx
0x1801765e5  mov     [rsp+7D8h+var_738], rcx
0x1801765ed  mov     [rsp+7D8h+var_6F0], rcx
0x1801765f5  xor     esi, esi
0x1801765f7  mov     r15d, esi
0x1801765fa  mov     [rsp+7D8h+var_788], esi
0x1801765fe  cmp     cs:?_serviceStop@InstallQueue2@@0_NA, sil; bool InstallQueue2::_serviceStop
0x180176605  jnz     loc_1801774AE
0x18017660b  lea     rcx, [rsp+7D8h+var_6B0]
0x180176613  call    ?Load@CheckpointData@@YA?AV?$vector@V?$shared_ptr@UData@CheckpointData@@@std@@V?$allocator@V?$shared_ptr@UData@CheckpointData@@@std@@@2@@std@@XZ; CheckpointData::Load(void)
0x180176618  nop
0x180176619  mov     rcx, [rsp+7D8h+var_6B0]
0x180176621  mov     rdx, [rsp+7D8h+var_6A8]
0x180176629  mov     rax, rdx
0x18017662c  sub     rax, rcx
0x18017662f  sar     rax, 4
0x180176633  mov     [r13+2C0h], rax
0x18017663a  mov     r14, rcx
0x18017663d  mov     [rsp+7D8h+var_690], rdx
0x180176645  lea     rdi, aLoadcheckpoint; "LoadCheckpointWorker CheckpointDataBlob"...
0x18017664c  movsd   xmm7, cs:__real@4269254d38000000
0x180176654  movsd   xmm8, cs:__real@4056800000000000
0x18017665d  mov     [rsp+7D8h+var_708], r14
0x180176665  cmp     r14, [rsp+7D8h+var_690]
0x18017666d  jz      loc_180177480
0x180176673  mov     [rsp+7D8h+var_728], r14
0x18017667b  cmp     cs:?_serviceStop@InstallQueue2@@0_NA, sil; bool InstallQueue2::_serviceStop
0x180176682  jnz     loc_180177480
0x180176688  mov     rax, [r14]
0x18017668b  mov     rcx, [rax+18h]
0x18017668f  mov     [rsp+7D8h+var_3D8], rcx
0x180176697  lea     rdx, [rsp+7D8h+var_3D8]
0x18017669f  lea     rcx, [rsp+7D8h+var_740]; struct winrt::param::hstring *
0x1801766a7  call    ?Parse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonObject::Parse(winrt::param::hstring const &)
0x1801766ac  nop
0x1801766ad  lea     rdx, [rsp+7D8h+var_740]
0x1801766b5  lea     rcx, [rsp+7D8h+var_748]
0x1801766bd  call    ?GetValue@CallerApplicationId@WorkProperty@PluginHelpers@@SA?AUhstring@winrt@@AEBUJsonObject@Json@Data@Windows@5@@Z; PluginHelpers::WorkProperty::CallerApplicationId::GetValue(winrt::Windows::Data::Json::JsonObject const &)
0x1801766c2  nop
0x1801766c3  lea     rcx, [rsp+7D8h+var_748]; this
0x1801766cb  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x1801766d0  mov     rdx, rax
0x1801766d3  lea     rcx, [rsp+7D8h+var_3B8]
0x1801766db  call    ?GetClientIdFromFullAppId@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; GetClientIdFromFullAppId(ushort const *)
0x1801766e0  nop
0x1801766e1  lea     rcx, [rsp+7D8h+var_740]; struct winrt::Windows::Data::Json::JsonObject *
0x1801766e9  call    ?GetValue@IsInteractive@WorkProperty@PluginHelpers@@SA_NAEBUJsonObject@Json@Data@Windows@winrt@@@Z; PluginHelpers::WorkProperty::IsInteractive::GetValue(winrt::Windows::Data::Json::JsonObject const &)
0x1801766ee  mov     bl, al
0x1801766f0  lea     rcx, [rsp+7D8h+var_3B8]
0x1801766f8  cmp     [rsp+7D8h+var_3A0], 7
0x180176701  cmova   rcx, [rsp+7D8h+var_3B8]
0x18017670a  mov     r9d, 0Eh
0x180176710  lea     r8, aScanforupdates_1; "ScanForUpdates"
0x180176717  mov     rdx, [rsp+7D8h+var_3A8]
0x18017671f  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180176724  test    al, al
0x180176726  jnz     short loc_180176760
0x180176728  lea     rcx, [rsp+7D8h+var_3B8]
0x180176730  cmp     [rsp+7D8h+var_3A0], 7
0x180176739  cmova   rcx, [rsp+7D8h+var_3B8]
0x180176742  mov     r9d, 15h
0x180176748  lea     r8, aScanforupdates; "ScanForUpdatesForUser"
0x18017674f  mov     rdx, [rsp+7D8h+var_3A8]
0x180176757  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18017675c  test    al, al
0x18017675e  jz      short loc_18017679C
0x180176760  test    bl, bl
0x180176762  jnz     short loc_18017679C
0x180176764  mov     rcx, [r14]; this
0x180176767  call    ?Delete@CheckpointData@@YAXAEBUData@1@@Z; CheckpointData::Delete(CheckpointData::Data const &)
0x18017676c  nop
0x18017676d  lea     rcx, [rsp+7D8h+var_3B8]
0x180176775  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18017677a  nop
0x18017677b  lea     rcx, [rsp+7D8h+var_748]
0x180176783  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180176788  nop
0x180176789  lea     rcx, [rsp+7D8h+var_740]; void *
0x180176791  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180176796  nop
0x180176797  jmp     loc_180177467
0x18017679c  mov     rax, [r14]
0x18017679f  cmp     [rax+8], rsi
0x1801767a3  jz      loc_1801775FD
0x1801767a9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AttemptCountIncrementForRetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AttemptCountIncrementForRetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AttemptCountIncrementForRetry> `wil::Feature<__WilFeatureTraits_Feature_AttemptCountIncrementForRetry>::GetImpl(void)'::`2'::impl
0x1801767b0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AttemptCountIncrementForRetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AttemptCountIncrementForRetry>::__private_IsEnabled(void)
0x1801767b5  test    al, al
0x1801767b7  jz      loc_180176AEC
0x1801767bd  mov     rax, [r14]
0x1801767c0  mov     rbx, [rax+30h]
0x1801767c4  mov     [rsp+7D8h+var_778], rbx
0x1801767c9  lea     rcx, [rsp+7D8h+var_778]; this
0x1801767ce  call    ?add_ref@IUnknown@Foundation@Windows@winrt@@AEBAXXZ; winrt::Windows::Foundation::IUnknown::add_ref(void)
0x1801767d3  nop
0x1801767d4  test    rbx, rbx
0x1801767d7  jz      loc_180176A58
0x1801767dd  lea     rcx, [rsp+7D8h+var_778]
0x1801767e2  call    ?GetNetworkConnectivityLevel@?$consume_Windows_Networking_Connectivity_IConnectionProfile@UIConnectionProfile@Connectivity@Networking@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Networking_Connectivity_IConnectionProfile<winrt::Windows::Networking::Connectivity::IConnectionProfile>::GetNetworkConnectivityLevel(void)
0x1801767e7  test    eax, eax
0x1801767e9  jz      loc_180176A58
0x1801767ef  lea     rcx, [rsp+7D8h+var_778]
0x1801767f4  call    ?data@?$consume_Windows_Storage_Streams_IBuffer@UIBuffer@Streams@Storage@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Storage_Streams_IBuffer<winrt::Windows::Storage::Streams::IBuffer>::data(void)
0x1801767f9  mov     rbx, rax
0x1801767fc  lea     rcx, [rsp+7D8h+var_778]
0x180176801  call    ?GetNetworkConnectivityLevel@?$consume_Windows_Networking_Connectivity_IConnectionProfile@UIConnectionProfile@Connectivity@Networking@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Networking_Connectivity_IConnectionProfile<winrt::Windows::Networking::Connectivity::IConnectionProfile>::GetNetworkConnectivityLevel(void)
0x180176806  shr     eax, 1
0x180176808  mov     r8d, eax; unsigned int
0x18017680b  mov     rdx, rbx; unsigned __int16 *
0x18017680e  lea     rcx, [rsp+7D8h+var_688]; this
0x180176816  call    ??0hstring@winrt@@QEAA@PEBGI@Z; winrt::hstring::hstring(ushort const *,uint)
0x18017681b  nop
0x18017681c  mov     rax, [rax]
0x18017681f  mov     [rsp+7D8h+var_5C0], rax
0x180176827  lea     rdx, [rsp+7D8h+var_5C0]
0x18017682f  lea     rcx, [rsp+7D8h+var_760]; struct winrt::param::hstring *
0x180176834  call    ?Parse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonObject::Parse(winrt::param::hstring const &)
0x180176839  nop
0x18017683a  lea     rcx, [rsp+7D8h+var_688]
0x180176842  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180176847  cmp     [rsp+7D8h+var_760], rsi
0x18017684c  jz      loc_1801769BA
0x180176852  lea     rcx, [rsp+7D8h+var_760]
0x180176857  call    ?Size@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Size(void)
0x18017685c  test    eax, eax
0x18017685e  jz      loc_1801769BA
0x180176864  mov     rax, [r14]
0x180176867  inc     dword ptr [rax+44h]
0x18017686a  mov     rax, [r14]
0x18017686d  mov     ecx, [rax+44h]
0x180176870  xorps   xmm1, xmm1
0x180176873  cvtsi2sd xmm1, rcx
0x180176878  lea     rcx, [rsp+7D8h+var_680]
0x180176880  call    ?CreateNumberValue@JsonValue@Json@Data@Windows@winrt@@SA@N@Z; winrt::Windows::Data::Json::JsonValue::CreateNumberValue(double)
0x180176885  mov     rbx, rax
0x180176888  lea     rdx, aSystemattemptc_0; "systemAttemptCount"
0x18017688f  lea     rcx, [rsp+7D8h+var_3D8]; this
0x180176897  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18017689c  mov     r8, rbx
0x18017689f  lea     rdx, [rsp+7D8h+var_3D8]
0x1801768a7  lea     rcx, [rsp+7D8h+var_760]
0x1801768ac  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x1801768b1  nop
0x1801768b2  lea     rcx, [rsp+7D8h+var_680]; void *
0x1801768ba  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1801768bf  lea     rdx, [rsp+7D8h+var_678]
0x1801768c7  lea     rcx, [rsp+7D8h+var_760]
0x1801768cc  call    ?Stringify@?$consume_Windows_Data_Json_IJsonValue@UIJsonArray@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonArray>::Stringify(void)
0x1801768d1  mov     rbx, rax
0x1801768d4  mov     [rsp+7D8h+var_518], rdi
0x1801768dc  mov     [rsp+7D8h+var_510], 2Ch ; ','
0x1801768e8  lea     rdx, aInstallqueue2L; "InstallQueue2::_LoadCheckpointsWorker"
0x1801768ef  lea     rcx, [rsp+7D8h+var_3D8]
0x1801768f7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801768fc  nop
0x1801768fd  lea     rdx, aOnecoreuapEndu_22; "onecoreuap\\enduser\\winstore\\installs"...
0x180176904  lea     rcx, [rsp+7D8h+var_398]
0x18017690c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180176911  nop
0x180176912  mov     [rsp+7D8h+var_7B0], rbx
0x180176917  lea     rax, [rsp+7D8h+var_518]
0x18017691f  mov     [rsp+7D8h+var_7B8], rax
0x180176924  lea     r8, [rsp+7D8h+var_3D8]
0x18017692c  mov     edx, 132Ch
0x180176931  lea     rcx, [rsp+7D8h+var_398]
0x180176939  call    ??$Log@Uhstring@winrt@@@Logging@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I0W4Level@0@AEBV?$basic_string_view@GU?$char_traits@G@std@@@2@$$QEAUhstring@winrt@@@Z; Logging::Log<winrt::hstring>(std::string const &,uint,std::string const &,Logging::Level,std::basic_string_view<ushort> const &,winrt::hstring &&)
0x18017693e  nop
0x18017693f  lea     rcx, [rsp+7D8h+var_398]
0x180176947  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18017694c  nop
0x18017694d  lea     rcx, [rsp+7D8h+var_3D8]
0x180176955  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18017695a  nop
0x18017695b  lea     rcx, [rsp+7D8h+var_678]
0x180176963  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180176968  lea     rdx, [rsp+7D8h+var_668]
0x180176970  lea     rcx, [rsp+7D8h+var_760]
0x180176975  call    ?Stringify@?$consume_Windows_Data_Json_IJsonValue@UIJsonArray@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonArray>::Stringify(void)
0x18017697a  nop
0x18017697b  mov     rdx, rax
0x18017697e  lea     rcx, [rsp+7D8h+var_670]
0x180176986  call    ?CreateIBufferFromString@@YA?AUIBuffer@Streams@Storage@Windows@winrt@@AEBUhstring@5@@Z; CreateIBufferFromString(winrt::hstring const &)
0x18017698b  mov     rcx, [r14]
0x18017698e  add     rcx, 30h ; '0'
0x180176992  mov     rdx, rax
0x180176995  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x18017699a  lea     rcx, [rsp+7D8h+var_670]; void *
0x1801769a2  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1801769a7  nop
0x1801769a8  lea     rcx, [rsp+7D8h+var_668]
0x1801769b0  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1801769b5  jmp     loc_180176A49
0x1801769ba  lea     rax, aCheckpointdata; "checkpointDataJsonObj is null or empty."...
0x1801769c1  mov     [rsp+7D8h+var_588], rax
0x1801769c9  mov     [rsp+7D8h+var_580], 47h ; 'G'
0x1801769d5  lea     rdx, aInstallqueue2L; "InstallQueue2::_LoadCheckpointsWorker"
0x1801769dc  lea     rcx, [rsp+7D8h+var_398]
0x1801769e4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801769e9  nop
0x1801769ea  lea     rdx, aOnecoreuapEndu_22; "onecoreuap\\enduser\\winstore\\installs"...
0x1801769f1  lea     rcx, [rsp+7D8h+var_3D8]
0x1801769f9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801769fe  nop
0x1801769ff  lea     rax, [rsp+7D8h+var_588]
0x180176a07  mov     [rsp+7D8h+var_7B8], rax
0x180176a0c  mov     r9d, 2
0x180176a12  lea     r8, [rsp+7D8h+var_398]
0x180176a1a  mov     edx, 1326h
0x180176a1f  lea     rcx, [rsp+7D8h+var_3D8]
0x180176a27  call    ??$Log@$$V@Logging@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I0W4Level@0@AEBV?$basic_string_view@GU?$char_traits@G@std@@@2@@Z; Logging::Log<>(std::string const &,uint,std::string const &,Logging::Level,std::basic_string_view<ushort> const &)
0x180176a2c  nop
0x180176a2d  lea     rcx, [rsp+7D8h+var_3D8]
0x180176a35  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180176a3a  nop
0x180176a3b  lea     rcx, [rsp+7D8h+var_398]
0x180176a43  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180176a48  nop
0x180176a49  lea     rcx, [rsp+7D8h+var_760]; void *
0x180176a4e  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180176a53  jmp     loc_180176AE7
0x180176a58  lea     rax, aCheckpointdata_1; "CheckpointDataBlob is null or empty. Ca"...
0x180176a5f  mov     [rsp+7D8h+var_578], rax
0x180176a67  mov     [rsp+7D8h+var_570], 44h ; 'D'
0x180176a73  lea     rdx, aInstallqueue2L; "InstallQueue2::_LoadCheckpointsWorker"
0x180176a7a  lea     rcx, [rsp+7D8h+var_398]
0x180176a82  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180176a87  nop
0x180176a88  lea     rdx, aOnecoreuapEndu_22; "onecoreuap\\enduser\\winstore\\installs"...
0x180176a8f  lea     rcx, [rsp+7D8h+var_3D8]
0x180176a97  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180176a9c  nop
0x180176a9d  lea     rax, [rsp+7D8h+var_578]
0x180176aa5  mov     [rsp+7D8h+var_7B8], rax
0x180176aaa  mov     r9d, 2
0x180176ab0  lea     r8, [rsp+7D8h+var_398]
0x180176ab8  mov     edx, 131Fh
0x180176abd  lea     rcx, [rsp+7D8h+var_3D8]
0x180176ac5  call    ??$Log@$$V@Logging@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I0W4Level@0@AEBV?$basic_string_view@GU?$char_traits@G@std@@@2@@Z; Logging::Log<>(std::string const &,uint,std::string const &,Logging::Level,std::basic_string_view<ushort> const &)
0x180176aca  nop
0x180176acb  lea     rcx, [rsp+7D8h+var_3D8]
0x180176ad3  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180176ad8  nop
0x180176ad9  lea     rcx, [rsp+7D8h+var_398]
0x180176ae1  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180176ae6  nop
0x180176ae7  jmp     loc_180176D66
0x180176aec  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IncrementAttemptCountForRetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IncrementAttemptCountForRetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IncrementAttemptCountForRetry> `wil::Feature<__WilFeatureTraits_Feature_IncrementAttemptCountForRetry>::GetImpl(void)'::`2'::impl
0x180176af3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_IncrementAttemptCountForRetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IncrementAttemptCountForRetry>::__private_IsEnabled(void)
0x180176af8  test    al, al
0x180176afa  jz      loc_180176D70
0x180176b00  mov     rax, [r14]
0x180176b03  mov     rcx, [rax+30h]
0x180176b07  mov     [rsp+7D8h+var_778], rcx
0x180176b0c  lea     rcx, [rsp+7D8h+var_778]; this
0x180176b11  call    ?add_ref@IUnknown@Foundation@Windows@winrt@@AEBAXXZ; winrt::Windows::Foundation::IUnknown::add_ref(void)
0x180176b16  nop
0x180176b17  mov     [rsp+7D8h+var_780], rsi
0x180176b1c  lea     rdx, [rsp+7D8h+var_780]
0x180176b21  lea     rcx, [rsp+7D8h+var_778]
0x180176b26  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180176b2b  test    al, al
0x180176b2d  jz      short loc_180176B48
0x180176b2f  mov     [rsp+7D8h+var_6E8], rsi
0x180176b37  lea     rax, [rsp+7D8h+var_6E8]
0x180176b3f  or      r15d, 1
0x180176b43  mov     rcx, rsi
0x180176b46  jmp     short loc_180176BA5
0x180176b48  lea     rcx, [rsp+7D8h+var_778]
0x180176b4d  call    ?data@?$consume_Windows_Storage_Streams_IBuffer@UIBuffer@Streams@Storage@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Storage_Streams_IBuffer<winrt::Windows::Storage::Streams::IBuffer>::data(void)
0x180176b52  mov     rbx, rax
0x180176b55  lea     rcx, [rsp+7D8h+var_778]
0x180176b5a  call    ?GetNetworkConnectivityLevel@?$consume_Windows_Networking_Connectivity_IConnectionProfile@UIConnectionProfile@Connectivity@Networking@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Networking_Connectivity_IConnectionProfile<winrt::Windows::Networking::Connectivity::IConnectionProfile>::GetNetworkConnectivityLevel(void)
0x180176b5f  shr     eax, 1
0x180176b61  mov     r8d, eax; unsigned int
0x180176b64  mov     rdx, rbx; unsigned __int16 *
0x180176b67  lea     rcx, [rsp+7D8h+var_658]; this
0x180176b6f  call    ??0hstring@winrt@@QEAA@PEBGI@Z; winrt::hstring::hstring(ushort const *,uint)
0x180176b74  nop
0x180176b75  or      r15d, 2
0x180176b79  mov     [rsp+7D8h+var_788], r15d
0x180176b7e  mov     rax, [rax]
0x180176b81  mov     [rsp+7D8h+var_5C0], rax
0x180176b89  lea     rdx, [rsp+7D8h+var_5C0]
0x180176b91  lea     rcx, [rsp+7D8h+var_660]; struct winrt::param::hstring *
0x180176b99  call    ?Parse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonObject::Parse(winrt::param::hstring const &)
0x180176b9e  or      r15d, 4
  ... truncated ...
```
