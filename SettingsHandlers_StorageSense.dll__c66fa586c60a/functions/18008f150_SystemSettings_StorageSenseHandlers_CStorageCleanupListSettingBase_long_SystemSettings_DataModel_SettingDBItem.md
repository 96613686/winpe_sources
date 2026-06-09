# SystemSettings::StorageSenseHandlers::CStorageCleanupListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>::Invoke(HWND__ *)

- ea: `0x18008f150`
- end: `0x1800900bb`
- name: `?Invoke@?$CStorageCleanupListSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAUIUser@System@Windows@@PEAPEAUISettingItem@23@@Z@StorageSenseHandlers@SystemSettings@@UEAAJPEAUHWND__@@@Z`
- size: `3947`
- prototype: `__int64 __fastcall(SystemSettings::DataModel::CSettingBase *this)`
- caller_count: `0`
- callee_count: `44`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000171c`
- `0x1800042a8`
- `0x180004550`
- `0x180006e50`
- `0x180007a00`
- `0x1800084bc`
- `0x18000c964`
- `0x18001a530`
- `0x18001fc0c`
- `0x18001fe08`
- `0x180020fe0`
- `0x1800248c0`
- `0x1800292a8`
- `0x18002ee18`
- `0x180035c0c`
- `0x180043f48`
- `0x18004ef90`
- `0x18005c450`
- `0x18005fa88`
- `0x18007a184`
- `0x180085af8`
- `0x180085cf0`
- `0x180086b90`
- `0x180086be8`
- `0x180086c40`
- `0x180088054`
- `0x1800884d0`
- `0x18008c2e4`
- `0x18008c730`
- `0x18008ca50`
- `0x18008cb50`
- `0x18008f150`
- `0x180090a3c`
- `0x180091780`
- `0x180091eb8`
- `0x180092f10`
- `0x180092f7c`
- `0x1800933bc`
- `0x180093408`
- `0x1800b3484`
- `0x1800b34dc`
- `0x1800b450c`
- `0x1800c1928`
- `0x1800e3010`

## import_xrefs

- `ntdll!RtlInitializeCorrelationVector` at `0x18008f210`
- `ntdll!RtlInitializeCorrelationVector` at `0x18008f210`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18008f1f2`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18008f1f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008f442`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008f6e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008f442`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008f6e5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18008f5b9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18008f980`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18008f5b9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18008f980`
- `ext-ms-win-storage-sense-l1-1-0!TriggerStorageCleanup` at `0x18008f588`
- `ext-ms-win-storage-sense-l1-1-0!TriggerStorageCleanup` at `0x18008f588`
- `ext-ms-win-storage-sense-l1-1-0!GetStorageDeviceInfo` at `0x18008f521`
- `ext-ms-win-storage-sense-l1-1-0!GetStorageDeviceInfo` at `0x18008f521`
- `ext-ms-win-storage-sense-l1-2-2!GetStorageDeviceSize` at `0x18008f227`
- `ext-ms-win-storage-sense-l1-2-2!GetStorageDeviceSize` at `0x18008f918`
- `ext-ms-win-storage-sense-l1-2-2!GetStorageDeviceSize` at `0x18008f227`
- `ext-ms-win-storage-sense-l1-2-2!GetStorageDeviceSize` at `0x18008f918`
- `ext-ms-win-shell-shell32-l1-2-2!SHEmptyRecycleBinW` at `0x18008f541`
- `ext-ms-win-shell-shell32-l1-2-2!SHEmptyRecycleBinW` at `0x18008f541`

## pseudocode

```c
__int64 __fastcall SystemSettings::StorageSenseHandlers::CStorageCleanupListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>::Invoke(
        SystemSettings::DataModel::CSettingBase *this)
{
  int v2; // esi
  double v3; // xmm6_8
  double v4; // xmm7_8
  char *v5; // r13
  int Size; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  struct SystemSettings::StorageSenseHandlers::CStorageCleanupListHandlerSingleton *Instance; // rbx
  std::_Ref_count_base **v10; // rax
  _QWORD *v11; // r15
  __int64 v12; // rax
  _QWORD *v13; // r14
  __int64 v14; // rax
  unsigned int v15; // r12d
  unsigned int v16; // r13d
  __int64 v17; // rbx
  int v18; // eax
  SystemSettings::StorageSenseHandlers::CStorageCleanupItem *v19; // rsi
  __int64 *v20; // rbx
  unsigned __int64 Category; // rax
  SystemSettings::DataModel *v22; // rax
  unsigned __int16 **v23; // r8
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rdx
  unsigned int v27; // r13d
  unsigned int *v28; // r12
  unsigned int v29; // ebx
  unsigned int v30; // r12d
  HRESULT v31; // eax
  int v32; // ebx
  SystemSettings::StorageSenseHandlers::CStorSvcHandler *v33; // rcx
  __int64 v34; // rdx
  const struct _tlgProvider_t *v35; // r8
  int v36; // r8d
  int v37; // r9d
  unsigned int v38; // ebx
  PCWSTR StringRawBuffer; // rcx
  unsigned int v40; // eax
  unsigned int v41; // r13d
  __int64 v42; // rdx
  int v43; // eax
  __int64 v44; // rdx
  _BYTE *v45; // rcx
  unsigned int v46; // ebx
  __int64 v47; // rax
  struct SystemSettings::StorageSenseHandlers::CStorageCleanupListHandlerSingleton *v48; // rax
  __int64 v49; // r8
  __int64 v50; // rcx
  __int64 v51; // rdx
  struct SystemSettings::StorageSenseHandlers::CStorageCleanupListHandlerSingleton *v52; // rbx
  std::_Ref_count_base **v53; // rax
  _DWORD *v54; // rbx
  _DWORD *v55; // r12
  unsigned int v56; // eax
  __int64 v57; // rdx
  __int64 v58; // r8
  SystemSettings::StorageSenseHandlers::CStorSvcHandler *v59; // rcx
  __int64 v60; // rbx
  __int64 v61; // rsi
  const struct _tlgProvider_t *v62; // rax
  int v63; // r8d
  int v64; // r9d
  int v65; // r12d
  unsigned __int64 v66; // rcx
  const struct _tlgProvider_t *v67; // rax
  __int64 v68; // rdx
  const struct _tlgProvider_t *v69; // r8
  int v70; // r9d
  _BYTE v72[4]; // [rsp+D8h] [rbp-80h] BYREF
  _WORD v73[2]; // [rsp+DCh] [rbp-7Ch] BYREF
  char v74; // [rsp+E0h] [rbp-78h]
  unsigned int v75; // [rsp+E4h] [rbp-74h] BYREF
  unsigned int v76; // [rsp+E8h] [rbp-70h] BYREF
  int v77; // [rsp+ECh] [rbp-6Ch] BYREF
  unsigned int ItemCheckedCount; // [rsp+F0h] [rbp-68h] BYREF
  unsigned int v79; // [rsp+F4h] [rbp-64h]
  int v80; // [rsp+F8h] [rbp-60h]
  unsigned int v81; // [rsp+FCh] [rbp-5Ch]
  int v82; // [rsp+100h] [rbp-58h] BYREF
  unsigned int v83; // [rsp+104h] [rbp-54h] BYREF
  unsigned int v84; // [rsp+108h] [rbp-50h]
  unsigned __int16 v85[4]; // [rsp+110h] [rbp-48h] BYREF
  std::_Ref_count_base **v86; // [rsp+118h] [rbp-40h] BYREF
  SystemSettings::StorageSenseHandlers::CStorageCleanupItem *v87; // [rsp+120h] [rbp-38h] BYREF
  __int64 v88; // [rsp+128h] [rbp-30h] BYREF
  std::_Ref_count_base *v89[2]; // [rsp+130h] [rbp-28h] BYREF
  __int64 v90; // [rsp+140h] [rbp-18h] BYREF
  __int64 v91; // [rsp+148h] [rbp-10h] BYREF
  __int128 v92; // [rsp+150h] [rbp-8h] BYREF
  __int64 v93; // [rsp+160h] [rbp+8h]
  __int64 v94; // [rsp+168h] [rbp+10h] BYREF
  SystemSettings::StorageSenseHandlers::CStorageCleanupItem *v95; // [rsp+170h] [rbp+18h] BYREF
  __int64 v96; // [rsp+178h] [rbp+20h] BYREF
  __int128 v97; // [rsp+180h] [rbp+28h] BYREF
  __int64 v98; // [rsp+190h] [rbp+38h]
  __int64 v99; // [rsp+198h] [rbp+40h] BYREF
  SystemSettings::StorageSenseHandlers::CStorageCleanupItem *v100; // [rsp+1A0h] [rbp+48h] BYREF
  __int64 v101; // [rsp+1A8h] [rbp+50h] BYREF
  char *v102; // [rsp+1B0h] [rbp+58h] BYREF
  std::_Ref_count_base *v103; // [rsp+1B8h] [rbp+60h]
  _BYTE *v104; // [rsp+1C0h] [rbp+68h] BYREF
  int v105; // [rsp+1C8h] [rbp+70h]
  _WORD *v106; // [rsp+1D0h] [rbp+78h] BYREF
  int v107; // [rsp+1D8h] [rbp+80h]
  __int128 v108; // [rsp+1E8h] [rbp+90h]
  __int128 v109; // [rsp+1F8h] [rbp+A0h]
  __int128 v110; // [rsp+208h] [rbp+B0h]
  __int128 v111; // [rsp+218h] [rbp+C0h]
  __int128 v112; // [rsp+228h] [rbp+D0h]
  __int128 v113; // [rsp+238h] [rbp+E0h]
  __int128 v114; // [rsp+248h] [rbp+F0h]
  __int128 v115; // [rsp+258h] [rbp+100h]
  __int16 v116; // [rsp+268h] [rbp+110h]
  _BYTE *v117; // [rsp+278h] [rbp+120h] BYREF
  _BYTE v118[12]; // [rsp+280h] [rbp+128h]
  GUID pguid; // [rsp+290h] [rbp+138h] BYREF
  WCHAR pszRootPath[8]; // [rsp+2A8h] [rbp+150h] BYREF
  __int128 v121; // [rsp+2B8h] [rbp+160h]
  __int128 v122; // [rsp+2C8h] [rbp+170h]
  __int128 v123; // [rsp+2D8h] [rbp+180h]
  __int128 v124; // [rsp+2E8h] [rbp+190h]
  __int128 v125; // [rsp+2F8h] [rbp+1A0h]
  __int128 v126; // [rsp+308h] [rbp+1B0h]
  __int128 v127; // [rsp+318h] [rbp+1C0h]
  __int16 v128; // [rsp+328h] [rbp+1D0h]
  _BYTE v129[336]; // [rsp+708h] [rbp+5B0h] BYREF
  _BYTE v130[96]; // [rsp+858h] [rbp+700h] BYREF

  v2 = 0;
  v75 = 0;
  LOBYTE(v73[0]) = 0;
  v93 = 0;
  v84 = 0;
  v76 = 0;
  v81 = 0;
  v80 = 0;
  v79 = 0;
  v3 = 0.0;
  v91 = 0;
  v4 = 0.0;
  v92 = 0u;
  v95 = 0;
  v96 = 0;
  v74 = 0;
  memset_0(v130, -1, sizeof(v130));
  v97 = 0;
  v98 = 0;
  pguid = 0;
  CoCreateGuid(&pguid);
  v5 = (char *)this + 746;
  RtlInitializeCorrelationVector((char *)this + 746, 2, &pguid);
  GetStorageDeviceSize((char *)this + 488, 0, (char *)&v92 + 8, &v95);
  Size = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::get_Size(
           *((_QWORD *)this + 74),
           &v75);
  v7 = v75;
  if ( Size < 0 )
    v7 = 0;
  v75 = v7;
  *(_WORD *)((char *)this + 505) = 256;
  *((_BYTE *)this + 507) = 0;
  *(_QWORD *)((char *)this + 524) = 2;
  SystemSettings::StorageSenseHandlers::CStorageCleanupListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::_SetContext(
    this,
    0,
    2,
    0);
  LOBYTE(v8) = 1;
  SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::SetIsOperationRunning(
    &qword_18018A990[34 * *((int *)this + 96)],
    v8,
    0);
  SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_180111EA8);
  SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_180112038);
  if ( (unsigned __int8)SystemSettings::StorageSenseHandlers::StorageSenseUtils::IsSystemVolume(
                          *((unsigned int *)this + 94),
                          *((unsigned int *)this + 95)) )
  {
    Instance = SystemSettings::StorageSenseHandlers::CStorageCleanupListHandlerSingleton::GetInstance();
    v10 = (std::_Ref_count_base **)std::make_shared<SystemSettings::StorageSenseHandlers::CleanupListOperationStarted,>(&v117);
    *(_OWORD *)v89 = 0;
    v89[0] = *v10;
    v89[1] = v10[1];
    *v10 = 0;
    v10[1] = 0;
    v88 = (__int64)v89;
    SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent> const &>::_Notify<_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_>(
      Instance,
      &v88);
    if ( v89[1] )
      std::_Ref_count_base::_Decref(v89[1]);
    if ( *(_QWORD *)v118 )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)v118);
    v7 = v75;
  }
  SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSensePurge::Start<__int64 &,CORRELATION_VECTOR &,CORRELATION_VECTOR &>(v129);
  v11 = (_QWORD *)((char *)this + 328);
  v12 = *((_QWORD *)this + 41);
  if ( v12 != *((_QWORD *)this + 42) )
    *((_QWORD *)this + 42) = v12;
  v13 = (_QWORD *)((char *)this + 352);
  v14 = *((_QWORD *)this + 44);
  if ( v14 != *((_QWORD *)this + 45) )
    *((_QWORD *)this + 45) = v14;
  v88 = 0;
  ItemCheckedCount = SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::GetItemCheckedCount(&qword_18018A990[34 * *((int *)this + 96)]);
  v15 = 0;
  LODWORD(v90) = 0;
  if ( !v7 )
    goto LABEL_67;
  v16 = 0;
  while ( !*((_BYTE *)this + 520) )
  {
    v87 = 0;
    v17 = *((_QWORD *)this + 74);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v87);
    v18 = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(
            v17,
            v15,
            &v87);
    v77 = v18;
    v19 = v87;
    *((_BYTE *)v87 + 280) = 0;
    if ( v18 < 0 )
      goto LABEL_62;
    v20 = &qword_18018A990[34 * *((int *)this + 96)];
    Category = SystemSettings::StorageSenseHandlers::CStorageCleanupItem::GetCategory(v19);
    v72[0] = 0;
    SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::GetIsItemChecked(
      v20,
      Category,
      v72);
    if ( !v72[0] )
      goto LABEL_62;
    if ( IsDesktopSKU() )
    {
      v38 = *((_DWORD *)this + 131);
      StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)v19 + 30), 0);
      v40 = 100 * v16;
      v41 = ItemCheckedCount;
      SystemSettings::StorageSenseHandlers::CStorageCleanupListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::_SetContext(
        this,
        StringRawBuffer,
        v38,
        v40 / ItemCheckedCount);
      LOBYTE(v42) = 1;
      SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::SetIsOperationRunning(
        &qword_18018A990[34 * *((int *)this + 96)],
        v42,
        0);
      v108 = *(_OWORD *)((char *)this + 746);
      v109 = *(_OWORD *)((char *)this + 762);
      v110 = *(_OWORD *)((char *)this + 778);
      v111 = *(_OWORD *)((char *)this + 794);
      v112 = *(_OWORD *)((char *)this + 810);
      v113 = *(_OWORD *)((char *)this + 826);
      v114 = *(_OWORD *)((char *)this + 842);
      v115 = *(_OWORD *)((char *)this + 858);
      v116 = *((_WORD *)this + 437);
      v43 = SystemSettings::StorageSenseHandlers::CStorageCleanupItem::Cleanup(v19, (__int64)&v88);
      v84 = v43;
      if ( !v88 )
      {
        v44 = 272LL * v76;
        v45 = (_BYTE *)*v13;
        v3 = v3 + *(double *)(v44 + *v13 + 240);
        v91 = *(_QWORD *)&v3;
        v4 = v4 + *(double *)&v45[v44 + 248];
        *(double *)&v92 = v4;
      }
      v46 = ++v76;
      *((_BYTE *)v19 + 280) = 1;
      if ( v43 < 0 )
      {
        ++v80;
      }
      else
      {
        v47 = *((_QWORD *)v19 + 34);
        LOBYTE(v73[0]) = 1;
        ++v81;
        if ( v47 )
        {
          ++v79;
          v93 += v47;
        }
        else if ( *((_QWORD *)&v97 + 1) == v98 )
        {
          std::vector<unsigned int>::_Emplace_reallocate<unsigned int const &>(&v97, *((_QWORD *)&v97 + 1), &v90);
        }
        else
        {
          **((_DWORD **)&v97 + 1) = v15;
          *((_QWORD *)&v97 + 1) += 4LL;
        }
      }
      if ( (unsigned __int8)SystemSettings::StorageSenseHandlers::StorageSenseUtils::IsSystemVolume(
                              *((unsigned int *)this + 94),
                              *((unsigned int *)this + 95)) )
      {
        std::make_shared<SystemSettings::StorageSenseHandlers::CleanupListOperationProgress,>(v89);
        *((_DWORD *)v89[0] + 2) = 100 * v46 / v41;
        v48 = SystemSettings::StorageSenseHandlers::CStorageCleanupListHandlerSingleton::GetInstance();
        std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent>::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent>(
          &v102,
          v89,
          v48);
        v86 = (std::_Ref_count_base **)&v102;
        SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent> const &>::_Notify<_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_>(
          v49,
          &v86);
        if ( v103 )
          std::_Ref_count_base::_Decref(v103);
        if ( v89[1] )
          std::_Ref_count_base::_Decref(v89[1]);
      }
      goto LABEL_62;
    }
    *(_QWORD *)v85 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      v85,
      0);
    v22 = (SystemSettings::DataModel *)WindowsGetStringRawBuffer(*((HSTRING *)v19 + 30), 0);
    if ( (int)SystemSettings::DataModel::GetResourceStringById(v22, v85, v23) >= 0 )
    {
      SystemSettings::StorageSenseHandlers::CStorageCleanupListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::_SetContext(
        this,
        *(_QWORD *)v85,
        *((unsigned int *)this + 131),
        100 * v16 / ItemCheckedCount);
      LOBYTE(v26) = 1;
      SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::SetIsOperationRunning(
        &qword_18018A990[34 * *((int *)this + 96)],
        v26,
        0);
      LOBYTE(v73[0]) = 1;
      v27 = SystemSettings::StorageSenseHandlers::CStorageCleanupItem::GetCategory(v19);
      v28 = (unsigned int *)*((_QWORD *)this + 33);
      if ( v28 )
      {
        v29 = *v28;
        v30 = v28[1];
      }
      else
      {
        v29 = 0;
        v30 = 0;
      }
      if ( v27 == 19 )
      {
        LODWORD(v117) = 20;
        *(_QWORD *)&v118[4] = 0;
        goto LABEL_34;
      }
      if ( v27 == 17 )
      {
        memset_0(&pszRootPath[2], 0, 0x454u);
        wcscpy(pszRootPath, L"ј");
        if ( (int)GetStorageDeviceInfo(v29, v30, pszRootPath) >= 0 && (unsigned __int8)IsSHEmptyRecycleBinWPresent() )
        {
          v31 = SHEmptyRecycleBinW(0, &pszRootPath[2], 7u);
          goto LABEL_35;
        }
        v32 = -2147467263;
      }
      else
      {
        if ( v27 == 20 )
        {
          *(_DWORD *)&v118[4] = 1;
          *(_DWORD *)&v118[8] = 1;
        }
        else
        {
          if ( v27 != 13 )
          {
            v32 = v77;
            goto LABEL_39;
          }
          *(_DWORD *)&v118[4] = 0;
          *(_DWORD *)&v118[8] = 5;
        }
        LODWORD(v117) = 20;
LABEL_34:
        HIDWORD(v117) = v29;
        *(_DWORD *)v118 = v30;
        v31 = TriggerStorageCleanup(&v117);
LABEL_35:
        v32 = v31;
        *((_BYTE *)v19 + 280) = 1;
      }
LABEL_39:
      Sleep(0xC8u);
      SystemSettings::StorageSenseHandlers::CStorSvcHandler::RefreshQueries(v33);
      SystemSettings::StorageSenseHandlers::CStorageCleanupItem::RefreshSize(v19, 0);
      SystemSettings::DataModel::CSettingBase::OnValueChanged(v19, (const unsigned __int16 *)&stru_1801068F0);
      if ( !*((_QWORD *)v19 + 34) && *((_BYTE *)v19 + 280) == 1 )
      {
        if ( *((_QWORD *)&v97 + 1) == v98 )
        {
          std::vector<unsigned int>::_Emplace_reallocate<unsigned int const &>(&v97, *((_QWORD *)&v97 + 1), &v90);
        }
        else
        {
          **((_DWORD **)&v97 + 1) = v90;
          *((_QWORD *)&v97 + 1) += 4LL;
        }
      }
      v77 = 0;
      SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::EnumToNode(v27, &v77);
      v35 = SettingsHandlersStorageSenseLogging::Provider();
      if ( *(_DWORD *)v35 && (unsigned __int8)tlgKeywordOn(v35, 0x400000000000LL) )
      {
        v94 = 0x1000000;
        v72[0] = 5;
        v86 = (std::_Ref_count_base **)SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::EnumToString(v27);
        v82 = v32;
        v83 = v27;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(
          v36,
          (unsigned int)&unk_1801531E0,
          v36,
          v37,
          (__int64)&v83,
          (__int64)&v77,
          (__int64)&v82,
          (__int64)&v86,
          (__int64)v72,
          (__int64)&v94);
      }
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(
        v85,
        v34,
        v35);
LABEL_62:
      v15 = v90;
      goto LABEL_63;
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(
      v85,
      v24,
      v25);
LABEL_63:
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v87);
    LODWORD(v90) = ++v15;
    v16 = v15;
    v2 = 0;
    if ( v15 >= v75 )
      goto LABEL_66;
  }
  *((_BYTE *)this + 520) = 0;
  *((_WORD *)this + 253) = 256;
  *((_DWORD *)this + 132) = 2;
  v74 = 1;
LABEL_66:
  v5 = (char *)this + 746;
LABEL_67:
  GetStorageDeviceSize((char *)this + 488, 0, (char *)&v92 + 8, &v96);
  v50 = *((_QWORD *)this + 75);
  if ( v50 )
    (*(void (__fastcall **)(__int64, __int64, _BYTE *))(*(_QWORD *)v50 + 104LL))(v50, 12, v130);
  SystemSettings::StorageSenseHandlers::CStorageCleanupListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::_SetContext(
    this,
    0,
    *((unsigned int *)this + 131),
    100);
  LOBYTE(v51) = 1;
  SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::SetIsOperationRunning(
    &qword_18018A990[34 * *((int *)this + 96)],
    v51,
    0);
  Sleep(0xC8u);
  if ( (unsigned __int8)SystemSettings::StorageSenseHandlers::StorageSenseUtils::IsSystemVolume(
                          *((unsigned int *)this + 94),
                          *((unsigned int *)this + 95)) )
  {
    v52 = SystemSettings::StorageSenseHandlers::CStorageCleanupListHandlerSingleton::GetInstance();
    v53 = (std::_Ref_count_base **)std::make_shared<SystemSettings::StorageSenseHandlers::CleanupListOperationFinished,>(&v117);
    *(_OWORD *)v89 = 0;
    v89[0] = *v53;
    v89[1] = v53[1];
    *v53 = 0;
    v53[1] = 0;
    v86 = v89;
    SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent> const &>::_Notify<_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_>(
      v52,
      &v86);
    if ( v89[1] )
      std::_Ref_count_base::_Decref(v89[1]);
    if ( *(_QWORD *)v118 )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)v118);
  }
  v55 = (_DWORD *)*((_QWORD *)&v97 + 1);
  v54 = (_DWORD *)v97;
  if ( (_QWORD)v97 != *((_QWORD *)&v97 + 1) )
  {
    v56 = v75;
    do
    {
      v57 = (unsigned int)(*v54 - v2);
      if ( (unsigned int)v57 < v56 )
      {
        Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::RemoveAtInternal(
          *((_QWORD *)this + 74),
          v57,
          0);
        ++v2;
        v56 = v75;
      }
      ++v54;
    }
    while ( v54 != v55 );
  }
  SystemSettings::StorageSenseHandlers::CStorageCleanupListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>::_Sort(this);
  SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_18010EDA8);
  *((_BYTE *)this + 505) = 1;
  *((_DWORD *)this + 131) = 0;
  SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_180112038);
  LOBYTE(v58) = 1;
  SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::SetIsOperationRunning(
    &qword_18018A990[34 * *((int *)this + 96)],
    0,
    v58);
  if ( LOBYTE(v73[0]) && *((_QWORD *)this + 33) )
    SystemSettings::StorageSenseHandlers::CStorSvcHandler::RefreshQueries(v59);
  v60 = v91;
  v61 = v92;
  if ( 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)this + 42) - *((_QWORD *)this + 41)) >> 6) )
  {
    v73[0] = -21845 * ((__int64)(*((_QWORD *)this + 42) - *((_QWORD *)this + 41)) >> 6);
    v62 = SettingsHandlersStorageSenseLogging::Provider();
    if ( *(_DWORD *)v62 && (unsigned __int8)tlgKeywordOn(v62, 0x400000000000LL) )
    {
      v104 = (_BYTE *)*v11;
      v105 = 192 * v73[0];
      v106 = v73;
      v107 = 2;
      v86 = (std::_Ref_count_base **)((char *)this + 747);
      v94 = (__int64)this + 617;
      *(_QWORD *)&v92 = *((_QWORD *)this + 62);
      v117 = v130;
      *(_WORD *)v118 = 12;
      v72[0] = v74;
      v91 = v96;
      v87 = v95;
      *(_QWORD *)v85 = *((_QWORD *)&v92 + 1);
      v83 = v79;
      v82 = v80;
      ItemCheckedCount = v81;
      v65 = v76;
      v77 = v76;
      v75 = v84;
      v90 = v61;
      v100 = (SystemSettings::StorageSenseHandlers::CStorageCleanupItem *)v60;
      LOWORD(v76) = v73[0];
      v101 = v88;
      v99 = v93;
      v102 = (char *)this + 488;
      v89[0] = (std::_Ref_count_base *)0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<8>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(
        v63,
        (unsigned int)&dword_180152FFC,
        v63,
        v64,
        (__int64)v89,
        (__int64)&v102,
        (__int64)&v99,
        (__int64)&v101,
        (__int64)&v76,
        (__int64)&v100,
        (__int64)&v90,
        (__int64)&v75,
        (__int64)&v77,
        (__int64)&ItemCheckedCount,
        (__int64)&v82,
        (__int64)&v83,
        (__int64)v85,
        (__int64)&v87,
        (__int64)&v91,
        (__int64)v72,
        (__int64)&v117,
        (__int64)&v92,
        (__int64)&v94,
        (__int64)&v86,
        (__int64)&v106,
        (__int64)&v104);
    }
    else
    {
      v65 = v76;
    }
    if ( *((_QWORD *)this + 41) != *((_QWORD *)this + 42) )
      *((_QWORD *)this + 42) = *v11;
    std::vector<SystemSettings::StorageSenseHandlers::PluginCleanupStart>::shrink_to_fit((char *)this + 328);
  }
  else
  {
    v65 = v76;
  }
  v66 = 0xF0F0F0F0F0F0F0F1uLL;
  if ( 0xF0F0F0F0F0F0F0F1uLL * ((__int64)(*((_QWORD *)this + 45) - *((_QWORD *)this + 44)) >> 4) )
  {
    v73[0] = -3855 * ((__int64)(*((_QWORD *)this + 45) - *((_QWORD *)this + 44)) >> 4);
    v67 = SettingsHandlersStorageSenseLogging::Provider();
    v69 = v67;
    if ( *(_DWORD *)v67 && (unsigned __int8)tlgKeywordOn(v67, 0x400000000000LL) )
    {
      v117 = (_BYTE *)*v13;
      *(_DWORD *)v118 = 272 * v73[0];
      v106 = v73;
      v107 = 2;
      v89[0] = (SystemSettings::DataModel::CSettingBase *)((char *)this + 747);
      v102 = (char *)this + 617;
      v99 = *((_QWORD *)this + 62);
      v104 = v130;
      LOWORD(v105) = 12;
      v72[0] = v74;
      v101 = v96;
      v100 = v95;
      v86 = (std::_Ref_count_base **)*((_QWORD *)&v92 + 1);
      v83 = v79;
      v82 = v80;
      ItemCheckedCount = v81;
      v77 = v65;
      v75 = v84;
      v94 = v61;
      *(_QWORD *)&v92 = v60;
      LOWORD(v76) = v73[0];
      v91 = v88;
      v88 = v93;
      v87 = (SystemSettings::DataModel::CSettingBase *)((char *)this + 488);
      *(_QWORD *)v85 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<8>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(
        (_DWORD)v69,
        (unsigned int)&word_18015325E,
        (_DWORD)v69,
        v70,
        (__int64)v85,
        (__int64)&v87,
        (__int64)&v88,
        (__int64)&v91,
        (__int64)&v76,
        (__int64)&v92,
        (__int64)&v94,
        (__int64)&v75,
        (__int64)&v77,
        (__int64)&ItemCheckedCount,
        (__int64)&v82,
        (__int64)&v83,
        (__int64)&v86,
        (__int64)&v100,
        (__int64)&v101,
        (__int64)v72,
        (__int64)&v104,
        (__int64)&v99,
        (__int64)&v102,
        (__int64)v89,
        (__int64)&v106,
        (__int64)&v117);
    }
    if ( *((_QWORD *)this + 44) != *((_QWORD *)this + 45) )
      *((_QWORD *)this + 45) = *v13;
    std::vector<SystemSettings::StorageSenseHandlers::PluginCleanupStop>::shrink_to_fit((char *)this + 352, v68, v69);
  }
  v108 = *(_OWORD *)v5;
  v109 = *((_OWORD *)v5 + 1);
  v110 = *((_OWORD *)v5 + 2);
  v111 = *((_OWORD *)v5 + 3);
  v112 = *((_OWORD *)v5 + 4);
  v113 = *((_OWORD *)v5 + 5);
  v114 = *((_OWORD *)v5 + 6);
  v115 = *((_OWORD *)v5 + 7);
  v116 = *((_WORD *)v5 + 64);
  *(_OWORD *)pszRootPath = *(_OWORD *)((char *)this + 616);
  v121 = *(_OWORD *)((char *)this + 632);
  v122 = *(_OWORD *)((char *)this + 648);
  v123 = *(_OWORD *)((char *)this + 664);
  v124 = *(_OWORD *)((char *)this + 680);
  v125 = *(_OWORD *)((char *)this + 696);
  v126 = *(_OWORD *)((char *)this + 712);
  v127 = *(_OWORD *)((char *)this + 728);
  v128 = *((_WORD *)this + 372);
  SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSensePurge::Stop(
    v66,
    (char *)this + 488,
    v93,
    v84,
    v65,
    v81,
    v80,
    v79,
    *((_QWORD *)&v92 + 1),
    v95,
    v96,
    *((_QWORD *)this + 62),
    v130);
  SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSensePurge::~StorageSensePurge((SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSensePurge *)v129);
  std::vector<unsigned int>::_Tidy(&v97);
  return 0;
}

```

## disassembly

```asm
0x18008f150  mov     rax, rsp
0x18008f153  push    rbp
0x18008f154  push    rbx
0x18008f155  push    rsi
0x18008f156  push    rdi
0x18008f157  push    r12
0x18008f159  push    r13
0x18008f15b  push    r14
0x18008f15d  push    r15
0x18008f15f  lea     rbp, [rax-7D8h]
0x18008f166  sub     rsp, 8E8h
0x18008f16d  movaps  xmmword ptr [rax-58h], xmm6
0x18008f171  movaps  xmmword ptr [rax-68h], xmm7
0x18008f175  mov     rax, cs:__security_cookie
0x18008f17c  xor     rax, rsp
0x18008f17f  mov     [rbp+7D0h+var_70], rax
0x18008f186  mov     rdi, rcx
0x18008f189  xor     esi, esi
0x18008f18b  mov     [rbp+7D0h+var_844], esi
0x18008f18e  mov     byte ptr [rbp+7D0h+var_84C], sil
0x18008f192  mov     [rbp+7D0h+var_7C8], rsi
0x18008f196  mov     [rbp+7D0h+var_820], esi
0x18008f199  mov     [rbp+7D0h+var_840], esi
0x18008f19c  mov     [rbp+7D0h+var_82C], esi
0x18008f19f  mov     [rbp+7D0h+var_830], esi
0x18008f1a2  mov     [rbp+7D0h+var_834], esi
0x18008f1a5  xorps   xmm6, xmm6
0x18008f1a8  movsd   [rbp+7D0h+var_7E0], xmm6
0x18008f1ad  xorps   xmm7, xmm7
0x18008f1b0  movsd   qword ptr [rbp+7D0h+var_7D8], xmm7
0x18008f1b5  mov     [rbp+7D0h+var_7B8], rsi
0x18008f1b9  mov     [rbp+7D0h+var_7B0], rsi
0x18008f1bd  mov     qword ptr [rbp+7D0h+var_7D8+8], rsi
0x18008f1c1  mov     [rbp+7D0h+var_848], sil
0x18008f1c5  lea     r8d, [rsi+60h]; Size
0x18008f1c9  or      edx, 0FFFFFFFFh; Val
0x18008f1cc  lea     rcx, [rbp+7D0h+var_D0]; void *
0x18008f1d3  call    memset_0
0x18008f1d8  xorps   xmm0, xmm0
0x18008f1db  movdqu  [rbp+7D0h+var_7A8], xmm0
0x18008f1e0  mov     [rbp+7D0h+var_798], rsi
0x18008f1e4  movups  xmmword ptr [rbp+7D0h+pguid.Data1], xmm0
0x18008f1eb  lea     rcx, [rbp+7D0h+pguid]; pguid
0x18008f1f2  call    cs:__imp_CoCreateGuid
0x18008f1f8  lea     r13, [rdi+2EAh]
0x18008f1ff  lea     r8, [rbp+7D0h+pguid]
0x18008f206  lea     r14d, [rsi+2]
0x18008f20a  mov     edx, r14d
0x18008f20d  mov     rcx, r13
0x18008f210  call    cs:__imp_RtlInitializeCorrelationVector
0x18008f216  lea     rcx, [rdi+1E8h]
0x18008f21d  lea     r9, [rbp+7D0h+var_7B8]
0x18008f221  lea     r8, [rbp+7D0h+var_7D8+8]
0x18008f225  xor     edx, edx
0x18008f227  call    cs:__imp_GetStorageDeviceSize
0x18008f22d  lea     rdx, [rbp+7D0h+var_844]
0x18008f231  mov     rcx, [rdi+250h]
0x18008f238  call    ?get_Size@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJPEAI@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::get_Size(uint *)
0x18008f23d  mov     ebx, [rbp+7D0h+var_844]
0x18008f240  test    eax, eax
0x18008f242  cmovs   ebx, esi
0x18008f245  mov     [rbp+7D0h+var_844], ebx
0x18008f248  mov     word ptr [rdi+1F9h], 100h
0x18008f251  mov     [rdi+1FBh], sil
0x18008f258  mov     [rdi+20Ch], r14
0x18008f25f  xor     r9d, r9d
0x18008f262  mov     r8d, r14d
0x18008f265  xor     edx, edx
0x18008f267  mov     rcx, rdi
0x18008f26a  call    ?_SetContext@?$CStorageCleanupListSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@StorageSenseHandlers@SystemSettings@@AEAAXPEBGW4CleanupOperation@23@I@Z; SystemSettings::StorageSenseHandlers::CStorageCleanupListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::_SetContext(ushort const *,SystemSettings::StorageSenseHandlers::CleanupOperation,uint)
0x18008f26f  movsxd  rax, dword ptr [rdi+180h]
0x18008f276  imul    rcx, rax, 110h
0x18008f27d  lea     r12, qword_18018A990
0x18008f284  add     rcx, r12
0x18008f287  xor     r8d, r8d
0x18008f28a  mov     dl, 1
0x18008f28c  call    ?SetIsOperationRunning@?$CListOperationSingleton@_K@SingletonHelpers@StorageSenseHandlers@SystemSettings@@QEAAX_N0@Z; SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::SetIsOperationRunning(bool,bool)
0x18008f291  lea     rdx, stru_180111EA8; unsigned __int16 *
0x18008f298  mov     rcx, rdi; this
0x18008f29b  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x18008f2a0  lea     rdx, stru_180112038; unsigned __int16 *
0x18008f2a7  mov     rcx, rdi; this
0x18008f2aa  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x18008f2af  mov     edx, [rdi+17Ch]
0x18008f2b5  mov     ecx, [rdi+178h]
0x18008f2bb  call    ?IsSystemVolume@StorageSenseUtils@StorageSenseHandlers@SystemSettings@@YA_NW4_STORAGE_DEVICE_TYPE@@K@Z; SystemSettings::StorageSenseHandlers::StorageSenseUtils::IsSystemVolume(_STORAGE_DEVICE_TYPE,ulong)
0x18008f2c0  test    al, al
0x18008f2c2  jz      short loc_18008F331
0x18008f2c4  call    ?GetInstance@CStorageCleanupListHandlerSingleton@StorageSenseHandlers@SystemSettings@@SAPEAV123@XZ; SystemSettings::StorageSenseHandlers::CStorageCleanupListHandlerSingleton::GetInstance(void)
0x18008f2c9  mov     rbx, rax
0x18008f2cc  lea     rcx, [rbp+7D0h+var_6B0]
0x18008f2d3  call    ??$make_shared@UCleanupListOperationStarted@StorageSenseHandlers@SystemSettings@@$$V@std@@YA?AV?$shared_ptr@UCleanupListOperationStarted@StorageSenseHandlers@SystemSettings@@@0@XZ; std::make_shared<SystemSettings::StorageSenseHandlers::CleanupListOperationStarted,>(void)
0x18008f2d8  mov     rcx, rax
0x18008f2db  xorps   xmm0, xmm0
0x18008f2de  movdqu  xmmword ptr [rbp+7D0h+var_7F8], xmm0
0x18008f2e3  mov     rax, [rax]
0x18008f2e6  mov     [rbp+7D0h+var_7F8], rax
0x18008f2ea  mov     rax, [rcx+8]
0x18008f2ee  mov     [rbp+7D0h+var_7F8+8], rax
0x18008f2f2  mov     [rcx], rsi
0x18008f2f5  mov     [rcx+8], rsi
0x18008f2f9  lea     rax, [rbp+7D0h+var_7F8]
0x18008f2fd  mov     [rbp+7D0h+var_800], rax
0x18008f301  lea     rdx, [rbp+7D0h+var_800]
0x18008f305  mov     rcx, rbx
0x18008f308  call    ??$_Notify@V_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_@@@?$CSingletonHelper@AEBV?$shared_ptr@UCleanupListHandlerEvent@StorageSenseHandlers@SystemSettings@@@std@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_@@@Z; SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent> const &>::_Notify<_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_>(_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_ const &)
0x18008f30d  nop
0x18008f30e  mov     rcx, [rbp+7D0h+var_7F8+8]; this
0x18008f312  test    rcx, rcx
0x18008f315  jz      short loc_18008F31D
0x18008f317  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008f31c  nop
0x18008f31d  mov     rcx, [rbp+7D0h+var_6A8]; this
0x18008f324  test    rcx, rcx
0x18008f327  jz      short loc_18008F32E
0x18008f329  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008f32e  mov     ebx, [rbp+7D0h+var_844]
0x18008f331  lea     rcx, [rbp+7D0h+var_220]
0x18008f338  call    ??$Start@AEA_JAEAUCORRELATION_VECTOR@@AEAU1@@StorageSensePurge@SSTelemetry@Internal@StorageSenseHandlers@SystemSettings@@SA?AV01234@AEA_JAEAUCORRELATION_VECTOR@@1@Z; SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSensePurge::Start<__int64 &,CORRELATION_VECTOR &,CORRELATION_VECTOR &>(__int64 &,CORRELATION_VECTOR &,CORRELATION_VECTOR &)
0x18008f33d  nop
0x18008f33e  lea     r15, [rdi+148h]
0x18008f345  mov     rax, [r15]
0x18008f348  cmp     rax, [r15+8]
0x18008f34c  jz      short loc_18008F352
0x18008f34e  mov     [r15+8], rax
0x18008f352  lea     r14, [rdi+160h]
0x18008f359  mov     rax, [r14]
0x18008f35c  cmp     rax, [r14+8]
0x18008f360  jz      short loc_18008F366
0x18008f362  mov     [r14+8], rax
0x18008f366  mov     [rbp+7D0h+var_800], rsi
0x18008f36a  movsxd  rax, dword ptr [rdi+180h]
0x18008f371  imul    rcx, rax, 110h
0x18008f378  add     rcx, r12
0x18008f37b  call    ?GetItemCheckedCount@?$CListOperationSingleton@_K@SingletonHelpers@StorageSenseHandlers@SystemSettings@@QEAAIXZ; SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::GetItemCheckedCount(void)
0x18008f380  mov     [rbp+7D0h+var_838], eax
0x18008f383  mov     r12d, esi
0x18008f386  mov     dword ptr [rbp+7D0h+var_7E8], esi
0x18008f389  test    ebx, ebx
0x18008f38b  jz      loc_18008F907
0x18008f391  mov     r13d, esi
0x18008f394  mov     al, [rdi+208h]
0x18008f39a  nop
0x18008f39b  test    al, al
0x18008f39d  jnz     loc_18008F8E1
0x18008f3a3  mov     [rbp+7D0h+var_808], rsi
0x18008f3a7  mov     rbx, [rdi+250h]
0x18008f3ae  lea     rcx, [rbp+7D0h+var_808]
0x18008f3b2  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18008f3b7  lea     r8, [rbp+7D0h+var_808]
0x18008f3bb  mov     edx, r12d
0x18008f3be  mov     rcx, rbx
0x18008f3c1  call    ?GetAt@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJIPEAPEAUISettingItem@DataModel@SystemSettings@@@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(uint,SystemSettings::DataModel::ISettingItem * *)
0x18008f3c6  mov     [rbp+7D0h+var_83C], eax
0x18008f3c9  mov     rsi, [rbp+7D0h+var_808]
0x18008f3cd  mov     byte ptr [rsi+118h], 0
0x18008f3d4  test    eax, eax
0x18008f3d6  js      loc_18008F8B9
0x18008f3dc  movsxd  rax, dword ptr [rdi+180h]
0x18008f3e3  imul    rbx, rax, 110h
0x18008f3ea  lea     rax, qword_18018A990
0x18008f3f1  add     rbx, rax
0x18008f3f4  mov     rcx, rsi; this
0x18008f3f7  call    ?GetCategory@CStorageCleanupItem@StorageSenseHandlers@SystemSettings@@QEAA_KXZ; SystemSettings::StorageSenseHandlers::CStorageCleanupItem::GetCategory(void)
0x18008f3fc  mov     [rbp+7D0h+var_850], 0
0x18008f400  lea     r8, [rbp+7D0h+var_850]
0x18008f404  mov     rdx, rax
0x18008f407  mov     rcx, rbx
0x18008f40a  call    ?GetIsItemChecked@?$CListOperationSingleton@_K@SingletonHelpers@StorageSenseHandlers@SystemSettings@@QEAAJ_KAEA_N@Z; SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::GetIsItemChecked(unsigned __int64,bool &)
0x18008f40f  cmp     [rbp+7D0h+var_850], 0
0x18008f413  jz      loc_18008F8B9
0x18008f419  call    ?IsDesktopSKU@@YA_NXZ; IsDesktopSKU(void)
0x18008f41e  test    al, al
0x18008f420  jnz     loc_18008F6D6
0x18008f426  mov     qword ptr [rbp+7D0h+var_818], 0
0x18008f42e  xor     edx, edx
0x18008f430  lea     rcx, [rbp+7D0h+var_818]
0x18008f434  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18008f439  xor     edx, edx; length
0x18008f43b  mov     rcx, [rsi+0F0h]; string
0x18008f442  call    cs:__imp_WindowsGetStringRawBuffer
0x18008f448  lea     rdx, [rbp+7D0h+var_818]; unsigned __int16 *
0x18008f44c  mov     rcx, rax; this
0x18008f44f  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAG@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,ushort * *)
0x18008f454  test    eax, eax
0x18008f456  jns     short loc_18008F467
0x18008f458  lea     rcx, [rbp+7D0h+var_818]
0x18008f45c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18008f461  nop
0x18008f462  jmp     loc_18008F8BD
0x18008f467  imul    eax, r13d, 64h ; 'd'
0x18008f46b  xor     edx, edx
0x18008f46d  div     [rbp+7D0h+var_838]
0x18008f470  mov     r9d, eax
0x18008f473  mov     r8d, [rdi+20Ch]
0x18008f47a  mov     rdx, qword ptr [rbp+7D0h+var_818]
0x18008f47e  mov     rcx, rdi
0x18008f481  call    ?_SetContext@?$CStorageCleanupListSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@StorageSenseHandlers@SystemSettings@@AEAAXPEBGW4CleanupOperation@23@I@Z; SystemSettings::StorageSenseHandlers::CStorageCleanupListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::_SetContext(ushort const *,SystemSettings::StorageSenseHandlers::CleanupOperation,uint)
0x18008f486  movsxd  rax, dword ptr [rdi+180h]
0x18008f48d  imul    rcx, rax, 110h
0x18008f494  lea     rax, qword_18018A990
0x18008f49b  add     rcx, rax
0x18008f49e  xor     r8d, r8d
0x18008f4a1  mov     dl, 1
0x18008f4a3  call    ?SetIsOperationRunning@?$CListOperationSingleton@_K@SingletonHelpers@StorageSenseHandlers@SystemSettings@@QEAAX_N0@Z; SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::SetIsOperationRunning(bool,bool)
0x18008f4a8  mov     byte ptr [rbp+7D0h+var_84C], 1
0x18008f4ac  mov     rcx, rsi; this
0x18008f4af  call    ?GetCategory@CStorageCleanupItem@StorageSenseHandlers@SystemSettings@@QEAA_KXZ; SystemSettings::StorageSenseHandlers::CStorageCleanupItem::GetCategory(void)
0x18008f4b4  mov     r13, rax
0x18008f4b7  mov     r12, [rdi+108h]
0x18008f4be  xor     eax, eax
0x18008f4c0  test    r12, r12
0x18008f4c3  jz      short loc_18008F4D0
0x18008f4c5  mov     ebx, [r12]
0x18008f4c9  mov     r12d, [r12+4]
0x18008f4ce  jmp     short loc_18008F4D5
0x18008f4d0  mov     ebx, eax
0x18008f4d2  mov     r12d, eax
0x18008f4d5  cmp     r13d, 13h
0x18008f4d9  jnz     short loc_18008F4F1
0x18008f4db  mov     dword ptr [rbp+7D0h+var_6B0], 14h
0x18008f4e5  mov     [rbp+7D0h+var_6A8+4], rax
0x18008f4ec  jmp     loc_18008F574
0x18008f4f1  cmp     r13d, 11h
0x18008f4f5  jnz     short loc_18008F550
0x18008f4f7  xor     edx, edx; Val
0x18008f4f9  mov     r8d, 454h; Size
0x18008f4ff  lea     rcx, [rbp+7D0h+pszRootPath+4]; void *
0x18008f506  call    memset_0
0x18008f50b  mov     dword ptr [rbp+7D0h+pszRootPath], 458h
0x18008f515  lea     r8, [rbp+7D0h+pszRootPath]
0x18008f51c  mov     edx, r12d
0x18008f51f  mov     ecx, ebx
0x18008f521  call    cs:__imp_GetStorageDeviceInfo
0x18008f527  test    eax, eax
0x18008f529  js      short loc_18008F549
0x18008f52b  call    IsSHEmptyRecycleBinWPresent
0x18008f530  test    al, al
0x18008f532  jz      short loc_18008F549
0x18008f534  lea     r8d, [r13-0Ah]; dwFlags
0x18008f538  lea     rdx, [rbp+7D0h+pszRootPath+4]; pszRootPath
0x18008f53f  xor     ecx, ecx; hwnd
0x18008f541  call    cs:__imp_SHEmptyRecycleBinW
0x18008f547  jmp     short loc_18008F58E
0x18008f549  mov     ebx, 80004001h
0x18008f54e  jmp     short loc_18008F5B4
0x18008f550  mov     ecx, 14h
0x18008f555  cmp     r13d, ecx
0x18008f558  jnz     short loc_18008F599
0x18008f55a  mov     dword ptr [rbp+7D0h+var_6A8+4], 1
0x18008f564  mov     [rbp+7D0h+var_6A0], 1
0x18008f56e  mov     dword ptr [rbp+7D0h+var_6B0], ecx
0x18008f574  mov     dword ptr [rbp+7D0h+var_6B0+4], ebx
0x18008f57a  mov     dword ptr [rbp+7D0h+var_6A8], r12d
0x18008f581  lea     rcx, [rbp+7D0h+var_6B0]
0x18008f588  call    cs:__imp_TriggerStorageCleanup
0x18008f58e  mov     ebx, eax
0x18008f590  mov     byte ptr [rsi+118h], 1
0x18008f597  jmp     short loc_18008F5B4
0x18008f599  cmp     r13d, 0Dh
0x18008f59d  jnz     short loc_18008F5B1
0x18008f59f  mov     dword ptr [rbp+7D0h+var_6A8+4], eax
0x18008f5a5  mov     [rbp+7D0h+var_6A0], 5
0x18008f5af  jmp     short loc_18008F56E
0x18008f5b1  mov     ebx, [rbp+7D0h+var_83C]
0x18008f5b4  mov     ecx, 0C8h; dwMilliseconds
0x18008f5b9  call    cs:__imp_Sleep
0x18008f5bf  call    ?RefreshQueries@CStorSvcHandler@StorageSenseHandlers@SystemSettings@@QEAAJXZ; SystemSettings::StorageSenseHandlers::CStorSvcHandler::RefreshQueries(void)
0x18008f5c4  mov     [rsp+920h+var_900], 0; __int64
0x18008f5cd  xor     r9d, r9d
0x18008f5d0  xor     r8d, r8d
0x18008f5d3  xor     edx, edx
0x18008f5d5  mov     rcx, rsi; this
0x18008f5d8  call    ?RefreshSize@CStorageCleanupItem@StorageSenseHandlers@SystemSettings@@QEAAJW4CleanupItemSizeRefreshOperationKind@23@PEAV?$vector@UPluginScanStart@StorageSenseHandlers@SystemSettings@@V?$allocator@UPluginScanStart@StorageSenseHandlers@SystemSettings@@@std@@@std@@PEAV?$vector@UPluginScanStop@StorageSenseHandlers@SystemSettings@@V?$allocator@UPluginScanStop@StorageSenseHandlers@SystemSettings@@@std@@@6@PEA_K@Z; SystemSettings::StorageSenseHandlers::CStorageCleanupItem::RefreshSize(SystemSettings::StorageSenseHandlers::CleanupItemSizeRefreshOperationKind,std::vector<SystemSettings::StorageSenseHandlers::PluginScanStart> *,std::vector<SystemSettings::StorageSenseHandlers::PluginScanStop> *,unsigned __int64 *)
0x18008f5dd  lea     rdx, stru_1801068F0; unsigned __int16 *
0x18008f5e4  mov     rcx, rsi; this
0x18008f5e7  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x18008f5ec  cmp     qword ptr [rsi+110h], 0
0x18008f5f4  jnz     short loc_18008F622
0x18008f5f6  cmp     byte ptr [rsi+118h], 1
0x18008f5fd  jnz     short loc_18008F622
0x18008f5ff  mov     rdx, qword ptr [rbp+7D0h+var_7A8+8]
0x18008f603  cmp     rdx, [rbp+7D0h+var_798]
0x18008f607  jz      short loc_18008F615
0x18008f609  mov     eax, dword ptr [rbp+7D0h+var_7E8]
0x18008f60c  mov     [rdx], eax
0x18008f60e  add     qword ptr [rbp+7D0h+var_7A8+8], 4
0x18008f613  jmp     short loc_18008F622
0x18008f615  lea     r8, [rbp+7D0h+var_7E8]
0x18008f619  lea     rcx, [rbp+7D0h+var_7A8]
0x18008f61d  call    ??$_Emplace_reallocate@AEBI@?$vector@IV?$allocator@I@std@@@std@@AEAAPEAIQEAIAEBI@Z; std::vector<uint>::_Emplace_reallocate<uint const &>(uint * const,uint const &)
0x18008f622  mov     [rbp+7D0h+var_83C], 0
0x18008f629  lea     rdx, [rbp+7D0h+var_83C]
0x18008f62d  mov     ecx, r13d
0x18008f630  call    ?EnumToNode@StorageSenseCategoriesEx@StorageSenseHandlers@SystemSettings@@YAJW4StorageSenseBreakdownCategoryEx@123@PEAW4_DATA_TYPE_NODE@@@Z; SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::EnumToNode(SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::StorageSenseBreakdownCategoryEx,_DATA_TYPE_NODE *)
0x18008f635  call    ?Provider@SettingsHandlersStorageSenseLogging@@SAPEBU_tlgProvider_t@@XZ; SettingsHandlersStorageSenseLogging::Provider(void)
0x18008f63a  mov     r8, rax
0x18008f63d  mov     eax, [rax]
0x18008f63f  test    eax, eax
0x18008f641  jz      loc_18008F6C8
  ... truncated ...
```
