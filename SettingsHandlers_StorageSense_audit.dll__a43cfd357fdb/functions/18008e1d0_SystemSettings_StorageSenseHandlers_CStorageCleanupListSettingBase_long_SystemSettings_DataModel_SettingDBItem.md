# SystemSettings::StorageSenseHandlers::CStorageCleanupListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::Invoke(HWND__ *)

- ea: `0x18008e1d0`
- end: `0x18008f13b`
- name: `?Invoke@?$CStorageCleanupListSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@StorageSenseHandlers@SystemSettings@@UEAAJPEAUHWND__@@@Z`
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
- `0x18008e1d0`
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

- `ntdll!RtlInitializeCorrelationVector` at `0x18008e290`
- `ntdll!RtlInitializeCorrelationVector` at `0x18008e290`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18008e272`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18008e272`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e4c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e765`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e4c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e765`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18008e639`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18008ea00`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18008e639`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18008ea00`
- `ext-ms-win-storage-sense-l1-1-0!TriggerStorageCleanup` at `0x18008e608`
- `ext-ms-win-storage-sense-l1-1-0!TriggerStorageCleanup` at `0x18008e608`
- `ext-ms-win-storage-sense-l1-1-0!GetStorageDeviceInfo` at `0x18008e5a1`
- `ext-ms-win-storage-sense-l1-1-0!GetStorageDeviceInfo` at `0x18008e5a1`
- `ext-ms-win-storage-sense-l1-2-2!GetStorageDeviceSize` at `0x18008e2a7`
- `ext-ms-win-storage-sense-l1-2-2!GetStorageDeviceSize` at `0x18008e998`
- `ext-ms-win-storage-sense-l1-2-2!GetStorageDeviceSize` at `0x18008e2a7`
- `ext-ms-win-storage-sense-l1-2-2!GetStorageDeviceSize` at `0x18008e998`
- `ext-ms-win-shell-shell32-l1-2-2!SHEmptyRecycleBinW` at `0x18008e5c1`
- `ext-ms-win-shell-shell32-l1-2-2!SHEmptyRecycleBinW` at `0x18008e5c1`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall SystemSettings::StorageSenseHandlers::CStorageCleanupListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::Invoke(
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
  char *v20; // rbx
  unsigned __int64 Category; // rax
  SystemSettings::DataModel *v22; // rax
  unsigned __int16 **v23; // r8
  __int64 v24; // rdx
  unsigned int v25; // r13d
  unsigned int *v26; // r12
  unsigned int v27; // ebx
  unsigned int v28; // r12d
  HRESULT v29; // eax
  int v30; // ebx
  SystemSettings::StorageSenseHandlers::CStorSvcHandler *v31; // rcx
  const struct _tlgProvider_t *v32; // r8
  int v33; // r8d
  int v34; // r9d
  unsigned int v35; // ebx
  PCWSTR StringRawBuffer; // rcx
  unsigned int v37; // eax
  unsigned int v38; // r13d
  __int64 v39; // rdx
  int v40; // eax
  __int64 v41; // rdx
  _BYTE *v42; // rcx
  unsigned int v43; // ebx
  __int64 v44; // rax
  struct SystemSettings::StorageSenseHandlers::CStorageCleanupListHandlerSingleton *v45; // rax
  __int64 v46; // r8
  __int64 v47; // rcx
  __int64 v48; // rdx
  struct SystemSettings::StorageSenseHandlers::CStorageCleanupListHandlerSingleton *v49; // rbx
  std::_Ref_count_base **v50; // rax
  _DWORD *v51; // rbx
  _DWORD *v52; // r12
  unsigned int v53; // eax
  __int64 v54; // rdx
  __int64 v55; // r8
  SystemSettings::StorageSenseHandlers::CStorSvcHandler *v56; // rcx
  __int64 v57; // rbx
  __int64 v58; // rsi
  const struct _tlgProvider_t *v59; // rax
  int v60; // r8d
  int v61; // r9d
  int v62; // r12d
  unsigned __int64 v63; // rcx
  const struct _tlgProvider_t *v64; // rax
  __int64 v65; // rdx
  const struct _tlgProvider_t *v66; // r8
  int v67; // r9d
  _BYTE v69[4]; // [rsp+D8h] [rbp-80h] BYREF
  _WORD v70[2]; // [rsp+DCh] [rbp-7Ch] BYREF
  char v71; // [rsp+E0h] [rbp-78h]
  unsigned int v72; // [rsp+E4h] [rbp-74h] BYREF
  unsigned int v73; // [rsp+E8h] [rbp-70h] BYREF
  int v74; // [rsp+ECh] [rbp-6Ch] BYREF
  unsigned int ItemCheckedCount; // [rsp+F0h] [rbp-68h] BYREF
  unsigned int v76; // [rsp+F4h] [rbp-64h]
  int v77; // [rsp+F8h] [rbp-60h]
  unsigned int v78; // [rsp+FCh] [rbp-5Ch]
  int v79; // [rsp+100h] [rbp-58h] BYREF
  unsigned int v80; // [rsp+104h] [rbp-54h] BYREF
  unsigned int v81; // [rsp+108h] [rbp-50h]
  unsigned __int16 v82[4]; // [rsp+110h] [rbp-48h] BYREF
  std::_Ref_count_base **v83; // [rsp+118h] [rbp-40h] BYREF
  SystemSettings::StorageSenseHandlers::CStorageCleanupItem *v84; // [rsp+120h] [rbp-38h] BYREF
  __int64 v85; // [rsp+128h] [rbp-30h] BYREF
  std::_Ref_count_base *v86[2]; // [rsp+130h] [rbp-28h] BYREF
  __int64 v87; // [rsp+140h] [rbp-18h] BYREF
  __int64 v88; // [rsp+148h] [rbp-10h] BYREF
  __int128 v89; // [rsp+150h] [rbp-8h] BYREF
  __int64 v90; // [rsp+160h] [rbp+8h]
  __int64 v91; // [rsp+168h] [rbp+10h] BYREF
  SystemSettings::StorageSenseHandlers::CStorageCleanupItem *v92; // [rsp+170h] [rbp+18h] BYREF
  __int64 v93; // [rsp+178h] [rbp+20h] BYREF
  __int128 v94; // [rsp+180h] [rbp+28h] BYREF
  __int64 v95; // [rsp+190h] [rbp+38h]
  __int64 v96; // [rsp+198h] [rbp+40h] BYREF
  SystemSettings::StorageSenseHandlers::CStorageCleanupItem *v97; // [rsp+1A0h] [rbp+48h] BYREF
  __int64 v98; // [rsp+1A8h] [rbp+50h] BYREF
  char *v99; // [rsp+1B0h] [rbp+58h] BYREF
  std::_Ref_count_base *v100; // [rsp+1B8h] [rbp+60h]
  _BYTE *v101; // [rsp+1C0h] [rbp+68h] BYREF
  int v102; // [rsp+1C8h] [rbp+70h]
  _WORD *v103; // [rsp+1D0h] [rbp+78h] BYREF
  int v104; // [rsp+1D8h] [rbp+80h]
  __int128 v105; // [rsp+1E8h] [rbp+90h] BYREF
  __int128 v106; // [rsp+1F8h] [rbp+A0h]
  __int128 v107; // [rsp+208h] [rbp+B0h]
  __int128 v108; // [rsp+218h] [rbp+C0h]
  __int128 v109; // [rsp+228h] [rbp+D0h]
  __int128 v110; // [rsp+238h] [rbp+E0h]
  __int128 v111; // [rsp+248h] [rbp+F0h]
  __int128 v112; // [rsp+258h] [rbp+100h]
  __int16 v113; // [rsp+268h] [rbp+110h]
  _BYTE *v114; // [rsp+278h] [rbp+120h] BYREF
  _BYTE v115[12]; // [rsp+280h] [rbp+128h]
  GUID pguid; // [rsp+290h] [rbp+138h] BYREF
  WCHAR pszRootPath[8]; // [rsp+2A8h] [rbp+150h] BYREF
  __int128 v118; // [rsp+2B8h] [rbp+160h]
  __int128 v119; // [rsp+2C8h] [rbp+170h]
  __int128 v120; // [rsp+2D8h] [rbp+180h]
  __int128 v121; // [rsp+2E8h] [rbp+190h]
  __int128 v122; // [rsp+2F8h] [rbp+1A0h]
  __int128 v123; // [rsp+308h] [rbp+1B0h]
  __int128 v124; // [rsp+318h] [rbp+1C0h]
  __int16 v125; // [rsp+328h] [rbp+1D0h]
  _BYTE v126[336]; // [rsp+708h] [rbp+5B0h] BYREF
  _BYTE v127[96]; // [rsp+858h] [rbp+700h] BYREF

  v2 = 0;
  v72 = 0;
  LOBYTE(v70[0]) = 0;
  v90 = 0;
  v81 = 0;
  v73 = 0;
  v78 = 0;
  v77 = 0;
  v76 = 0;
  v3 = 0.0;
  v88 = 0;
  v4 = 0.0;
  v89 = 0u;
  v92 = 0;
  v93 = 0;
  v71 = 0;
  memset_0(v127, -1, sizeof(v127));
  v94 = 0;
  v95 = 0;
  pguid = 0;
  CoCreateGuid(&pguid);
  v5 = (char *)this + 746;
  RtlInitializeCorrelationVector((char *)this + 746, 2, &pguid);
  GetStorageDeviceSize((char *)this + 488, 0, (char *)&v89 + 8, &v92);
  Size = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::get_Size(
           *((_QWORD *)this + 74),
           &v72);
  v7 = v72;
  if ( Size < 0 )
    v7 = 0;
  v72 = v7;
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
    (char *)&unk_18018A990 + 272 * *((int *)this + 96),
    v8,
    0);
  SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_180111EA8);
  SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_180112038);
  if ( (unsigned __int8)SystemSettings::StorageSenseHandlers::StorageSenseUtils::IsSystemVolume(
                          *((unsigned int *)this + 94),
                          *((unsigned int *)this + 95)) )
  {
    Instance = SystemSettings::StorageSenseHandlers::CStorageCleanupListHandlerSingleton::GetInstance();
    v10 = (std::_Ref_count_base **)std::make_shared<SystemSettings::StorageSenseHandlers::CleanupListOperationStarted,>(&v114);
    *(_OWORD *)v86 = 0;
    v86[0] = *v10;
    v86[1] = v10[1];
    *v10 = 0;
    v10[1] = 0;
    v85 = (__int64)v86;
    SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent> const &>::_Notify<_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_>(
      Instance,
      &v85);
    if ( v86[1] )
      std::_Ref_count_base::_Decref(v86[1]);
    if ( *(_QWORD *)v115 )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)v115);
    v7 = v72;
  }
  SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSensePurge::Start<__int64 &,CORRELATION_VECTOR &,CORRELATION_VECTOR &>(v126);
  v11 = (_QWORD *)((char *)this + 328);
  v12 = *((_QWORD *)this + 41);
  if ( v12 != *((_QWORD *)this + 42) )
    *((_QWORD *)this + 42) = v12;
  v13 = (_QWORD *)((char *)this + 352);
  v14 = *((_QWORD *)this + 44);
  if ( v14 != *((_QWORD *)this + 45) )
    *((_QWORD *)this + 45) = v14;
  v85 = 0;
  ItemCheckedCount = SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::GetItemCheckedCount((char *)&unk_18018A990 + 272 * *((int *)this + 96));
  v15 = 0;
  LODWORD(v87) = 0;
  if ( !v7 )
    goto LABEL_67;
  v16 = 0;
  while ( !*((_BYTE *)this + 520) )
  {
    v84 = 0;
    v17 = *((_QWORD *)this + 74);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v84);
    v18 = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(
            v17,
            v15,
            &v84);
    v74 = v18;
    v19 = v84;
    *((_BYTE *)v84 + 280) = 0;
    if ( v18 < 0 )
      goto LABEL_62;
    v20 = (char *)&unk_18018A990 + 272 * *((int *)this + 96);
    Category = SystemSettings::StorageSenseHandlers::CStorageCleanupItem::GetCategory(v19);
    v69[0] = 0;
    SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::GetIsItemChecked(
      v20,
      Category,
      v69);
    if ( !v69[0] )
      goto LABEL_62;
    if ( IsDesktopSKU() )
    {
      v35 = *((_DWORD *)this + 131);
      StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)v19 + 30), 0);
      v37 = 100 * v16;
      v38 = ItemCheckedCount;
      SystemSettings::StorageSenseHandlers::CStorageCleanupListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::_SetContext(
        this,
        StringRawBuffer,
        v35,
        v37 / ItemCheckedCount);
      LOBYTE(v39) = 1;
      SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::SetIsOperationRunning(
        (char *)&unk_18018A990 + 272 * *((int *)this + 96),
        v39,
        0);
      v105 = *(_OWORD *)((char *)this + 746);
      v106 = *(_OWORD *)((char *)this + 762);
      v107 = *(_OWORD *)((char *)this + 778);
      v108 = *(_OWORD *)((char *)this + 794);
      v109 = *(_OWORD *)((char *)this + 810);
      v110 = *(_OWORD *)((char *)this + 826);
      v111 = *(_OWORD *)((char *)this + 842);
      v112 = *(_OWORD *)((char *)this + 858);
      v113 = *((_WORD *)this + 437);
      v40 = SystemSettings::StorageSenseHandlers::CStorageCleanupItem::Cleanup(
              v19,
              (__int64)&v105,
              (__int64)this + 328,
              (unsigned __int64)this + 352,
              &v85);
      v81 = v40;
      if ( !v85 )
      {
        v41 = 272LL * v73;
        v42 = (_BYTE *)*v13;
        v3 = v3 + *(double *)(v41 + *v13 + 240);
        v88 = *(_QWORD *)&v3;
        v4 = v4 + *(double *)&v42[v41 + 248];
        *(double *)&v89 = v4;
      }
      v43 = ++v73;
      *((_BYTE *)v19 + 280) = 1;
      if ( v40 < 0 )
      {
        ++v77;
      }
      else
      {
        v44 = *((_QWORD *)v19 + 34);
        LOBYTE(v70[0]) = 1;
        ++v78;
        if ( v44 )
        {
          ++v76;
          v90 += v44;
        }
        else if ( *((_QWORD *)&v94 + 1) == v95 )
        {
          std::vector<unsigned int>::_Emplace_reallocate<unsigned int const &>(&v94, *((_QWORD *)&v94 + 1), &v87);
        }
        else
        {
          **((_DWORD **)&v94 + 1) = v15;
          *((_QWORD *)&v94 + 1) += 4LL;
        }
      }
      if ( (unsigned __int8)SystemSettings::StorageSenseHandlers::StorageSenseUtils::IsSystemVolume(
                              *((unsigned int *)this + 94),
                              *((unsigned int *)this + 95)) )
      {
        std::make_shared<SystemSettings::StorageSenseHandlers::CleanupListOperationProgress,>(v86);
        *((_DWORD *)v86[0] + 2) = 100 * v43 / v38;
        v45 = SystemSettings::StorageSenseHandlers::CStorageCleanupListHandlerSingleton::GetInstance();
        std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent>::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent>(
          &v99,
          v86,
          v45);
        v83 = (std::_Ref_count_base **)&v99;
        SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent> const &>::_Notify<_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_>(
          v46,
          &v83);
        if ( v100 )
          std::_Ref_count_base::_Decref(v100);
        if ( v86[1] )
          std::_Ref_count_base::_Decref(v86[1]);
      }
      goto LABEL_62;
    }
    *(_QWORD *)v82 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      v82,
      0);
    v22 = (SystemSettings::DataModel *)WindowsGetStringRawBuffer(*((HSTRING *)v19 + 30), 0);
    if ( (int)SystemSettings::DataModel::GetResourceStringById(v22, v82, v23) >= 0 )
    {
      SystemSettings::StorageSenseHandlers::CStorageCleanupListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::_SetContext(
        this,
        *(_QWORD *)v82,
        *((unsigned int *)this + 131),
        100 * v16 / ItemCheckedCount);
      LOBYTE(v24) = 1;
      SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::SetIsOperationRunning(
        (char *)&unk_18018A990 + 272 * *((int *)this + 96),
        v24,
        0);
      LOBYTE(v70[0]) = 1;
      v25 = SystemSettings::StorageSenseHandlers::CStorageCleanupItem::GetCategory(v19);
      v26 = (unsigned int *)*((_QWORD *)this + 33);
      if ( v26 )
      {
        v27 = *v26;
        v28 = v26[1];
      }
      else
      {
        v27 = 0;
        v28 = 0;
      }
      if ( v25 == 19 )
      {
        LODWORD(v114) = 20;
        *(_QWORD *)&v115[4] = 0;
        goto LABEL_34;
      }
      if ( v25 == 17 )
      {
        memset_0(&pszRootPath[2], 0, 0x454u);
        wcscpy(pszRootPath, L"ј");
        if ( (int)GetStorageDeviceInfo(v27, v28, pszRootPath) >= 0 && (unsigned __int8)IsSHEmptyRecycleBinWPresent() )
        {
          v29 = SHEmptyRecycleBinW(0, &pszRootPath[2], 7u);
          goto LABEL_35;
        }
        v30 = -2147467263;
      }
      else
      {
        if ( v25 == 20 )
        {
          *(_DWORD *)&v115[4] = 1;
          *(_DWORD *)&v115[8] = 1;
        }
        else
        {
          if ( v25 != 13 )
          {
            v30 = v74;
            goto LABEL_39;
          }
          *(_DWORD *)&v115[4] = 0;
          *(_DWORD *)&v115[8] = 5;
        }
        LODWORD(v114) = 20;
LABEL_34:
        HIDWORD(v114) = v27;
        *(_DWORD *)v115 = v28;
        v29 = TriggerStorageCleanup(&v114);
LABEL_35:
        v30 = v29;
        *((_BYTE *)v19 + 280) = 1;
      }
LABEL_39:
      Sleep(0xC8u);
      SystemSettings::StorageSenseHandlers::CStorSvcHandler::RefreshQueries(v31);
      SystemSettings::StorageSenseHandlers::CStorageCleanupItem::RefreshSize(v19, 0, 0, 0, 0);
      SystemSettings::DataModel::CSettingBase::OnValueChanged(v19, (const unsigned __int16 *)&stru_1801068F0);
      if ( !*((_QWORD *)v19 + 34) && *((_BYTE *)v19 + 280) == 1 )
      {
        if ( *((_QWORD *)&v94 + 1) == v95 )
        {
          std::vector<unsigned int>::_Emplace_reallocate<unsigned int const &>(&v94, *((_QWORD *)&v94 + 1), &v87);
        }
        else
        {
          **((_DWORD **)&v94 + 1) = v87;
          *((_QWORD *)&v94 + 1) += 4LL;
        }
      }
      v74 = 0;
      SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::EnumToNode(v25, &v74);
      v32 = SettingsHandlersStorageSenseLogging::Provider();
      if ( *(_DWORD *)v32 && (unsigned __int8)tlgKeywordOn(v32, 0x400000000000LL) )
      {
        v91 = 0x1000000;
        v69[0] = 5;
        v83 = (std::_Ref_count_base **)SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::EnumToString(v25);
        v79 = v30;
        v80 = v25;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(
          v33,
          (unsigned int)&unk_180153D6A,
          v33,
          v34,
          (__int64)&v80,
          (__int64)&v74,
          (__int64)&v79,
          (__int64)&v83,
          (__int64)v69,
          (__int64)&v91);
      }
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)v82);
LABEL_62:
      v15 = v87;
      goto LABEL_63;
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)v82);
LABEL_63:
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v84);
    LODWORD(v87) = ++v15;
    v16 = v15;
    v2 = 0;
    if ( v15 >= v72 )
      goto LABEL_66;
  }
  *((_BYTE *)this + 520) = 0;
  *((_WORD *)this + 253) = 256;
  *((_DWORD *)this + 132) = 2;
  v71 = 1;
LABEL_66:
  v5 = (char *)this + 746;
LABEL_67:
  GetStorageDeviceSize((char *)this + 488, 0, (char *)&v89 + 8, &v93);
  v47 = *((_QWORD *)this + 75);
  if ( v47 )
    (*(void (__fastcall **)(__int64, __int64, _BYTE *))(*(_QWORD *)v47 + 104LL))(v47, 12, v127);
  SystemSettings::StorageSenseHandlers::CStorageCleanupListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::_SetContext(
    this,
    0,
    *((unsigned int *)this + 131),
    100);
  LOBYTE(v48) = 1;
  SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::SetIsOperationRunning(
    (char *)&unk_18018A990 + 272 * *((int *)this + 96),
    v48,
    0);
  Sleep(0xC8u);
  if ( (unsigned __int8)SystemSettings::StorageSenseHandlers::StorageSenseUtils::IsSystemVolume(
                          *((unsigned int *)this + 94),
                          *((unsigned int *)this + 95)) )
  {
    v49 = SystemSettings::StorageSenseHandlers::CStorageCleanupListHandlerSingleton::GetInstance();
    v50 = (std::_Ref_count_base **)std::make_shared<SystemSettings::StorageSenseHandlers::CleanupListOperationFinished,>(&v114);
    *(_OWORD *)v86 = 0;
    v86[0] = *v50;
    v86[1] = v50[1];
    *v50 = 0;
    v50[1] = 0;
    v83 = v86;
    SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent> const &>::_Notify<_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_>(
      v49,
      &v83);
    if ( v86[1] )
      std::_Ref_count_base::_Decref(v86[1]);
    if ( *(_QWORD *)v115 )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)v115);
  }
  v52 = (_DWORD *)*((_QWORD *)&v94 + 1);
  v51 = (_DWORD *)v94;
  if ( (_QWORD)v94 != *((_QWORD *)&v94 + 1) )
  {
    v53 = v72;
    do
    {
      v54 = (unsigned int)(*v51 - v2);
      if ( (unsigned int)v54 < v53 )
      {
        Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::RemoveAtInternal(
          *((_QWORD *)this + 74),
          v54,
          0);
        ++v2;
        v53 = v72;
      }
      ++v51;
    }
    while ( v51 != v52 );
  }
  SystemSettings::StorageSenseHandlers::CStorageCleanupListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>::_Sort(this);
  SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_18010EDA8);
  *((_BYTE *)this + 505) = 1;
  *((_DWORD *)this + 131) = 0;
  SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_180112038);
  LOBYTE(v55) = 1;
  SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::SetIsOperationRunning(
    (char *)&unk_18018A990 + 272 * *((int *)this + 96),
    0,
    v55);
  if ( LOBYTE(v70[0]) && *((_QWORD *)this + 33) )
    SystemSettings::StorageSenseHandlers::CStorSvcHandler::RefreshQueries(v56);
  v57 = v88;
  v58 = v89;
  if ( 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)this + 42) - *((_QWORD *)this + 41)) >> 6) )
  {
    v70[0] = -21845 * ((__int64)(*((_QWORD *)this + 42) - *((_QWORD *)this + 41)) >> 6);
    v59 = SettingsHandlersStorageSenseLogging::Provider();
    if ( *(_DWORD *)v59 && (unsigned __int8)tlgKeywordOn(v59, 0x400000000000LL) )
    {
      v101 = (_BYTE *)*v11;
      v102 = 192 * v70[0];
      v103 = v70;
      v104 = 2;
      v83 = (std::_Ref_count_base **)((char *)this + 747);
      v91 = (__int64)this + 617;
      *(_QWORD *)&v89 = *((_QWORD *)this + 62);
      v114 = v127;
      *(_WORD *)v115 = 12;
      v69[0] = v71;
      v88 = v93;
      v84 = v92;
      *(_QWORD *)v82 = *((_QWORD *)&v89 + 1);
      v80 = v76;
      v79 = v77;
      ItemCheckedCount = v78;
      v62 = v73;
      v74 = v73;
      v72 = v81;
      v87 = v58;
      v97 = (SystemSettings::StorageSenseHandlers::CStorageCleanupItem *)v57;
      LOWORD(v73) = v70[0];
      v98 = v85;
      v96 = v90;
      v99 = (char *)this + 488;
      v86[0] = (std::_Ref_count_base *)0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<8>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(
        v60,
        (unsigned int)&unk_180153B86,
        v60,
        v61,
        (__int64)v86,
        (__int64)&v99,
        (__int64)&v96,
        (__int64)&v98,
        (__int64)&v73,
        (__int64)&v97,
        (__int64)&v87,
        (__int64)&v72,
        (__int64)&v74,
        (__int64)&ItemCheckedCount,
        (__int64)&v79,
        (__int64)&v80,
        (__int64)v82,
        (__int64)&v84,
        (__int64)&v88,
        (__int64)v69,
        (__int64)&v114,
        (__int64)&v89,
        (__int64)&v91,
        (__int64)&v83,
        (__int64)&v103,
        (__int64)&v101);
    }
    else
    {
      v62 = v73;
    }
    if ( *((_QWORD *)this + 41) != *((_QWORD *)this + 42) )
      *((_QWORD *)this + 42) = *v11;
    std::vector<SystemSettings::StorageSenseHandlers::PluginCleanupStart>::shrink_to_fit((char *)this + 328);
  }
  else
  {
    v62 = v73;
  }
  v63 = 0xF0F0F0F0F0F0F0F1uLL;
  if ( 0xF0F0F0F0F0F0F0F1uLL * ((__int64)(*((_QWORD *)this + 45) - *((_QWORD *)this + 44)) >> 4) )
  {
    v70[0] = -3855 * ((__int64)(*((_QWORD *)this + 45) - *((_QWORD *)this + 44)) >> 4);
    v64 = SettingsHandlersStorageSenseLogging::Provider();
    v66 = v64;
    if ( *(_DWORD *)v64 && (unsigned __int8)tlgKeywordOn(v64, 0x400000000000LL) )
    {
      v114 = (_BYTE *)*v13;
      *(_DWORD *)v115 = 272 * v70[0];
      v103 = v70;
      v104 = 2;
      v86[0] = (SystemSettings::DataModel::CSettingBase *)((char *)this + 747);
      v99 = (char *)this + 617;
      v96 = *((_QWORD *)this + 62);
      v101 = v127;
      LOWORD(v102) = 12;
      v69[0] = v71;
      v98 = v93;
      v97 = v92;
      v83 = (std::_Ref_count_base **)*((_QWORD *)&v89 + 1);
      v80 = v76;
      v79 = v77;
      ItemCheckedCount = v78;
      v74 = v62;
      v72 = v81;
      v91 = v58;
      *(_QWORD *)&v89 = v57;
      LOWORD(v73) = v70[0];
      v88 = v85;
      v85 = v90;
      v84 = (SystemSettings::DataModel::CSettingBase *)((char *)this + 488);
      *(_QWORD *)v82 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<8>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(
        (_DWORD)v66,
        (unsigned int)&unk_1801538E8,
        (_DWORD)v66,
        v67,
        (__int64)v82,
        (__int64)&v84,
        (__int64)&v85,
        (__int64)&v88,
        (__int64)&v73,
        (__int64)&v89,
        (__int64)&v91,
        (__int64)&v72,
        (__int64)&v74,
        (__int64)&ItemCheckedCount,
        (__int64)&v79,
        (__int64)&v80,
        (__int64)&v83,
        (__int64)&v97,
        (__int64)&v98,
        (__int64)v69,
        (__int64)&v101,
        (__int64)&v96,
        (__int64)&v99,
        (__int64)v86,
        (__int64)&v103,
        (__int64)&v114);
    }
    if ( *((_QWORD *)this + 44) != *((_QWORD *)this + 45) )
      *((_QWORD *)this + 45) = *v13;
    std::vector<SystemSettings::StorageSenseHandlers::PluginCleanupStop>::shrink_to_fit((char *)this + 352, v65, v66);
  }
  v105 = *(_OWORD *)v5;
  v106 = *((_OWORD *)v5 + 1);
  v107 = *((_OWORD *)v5 + 2);
  v108 = *((_OWORD *)v5 + 3);
  v109 = *((_OWORD *)v5 + 4);
  v110 = *((_OWORD *)v5 + 5);
  v111 = *((_OWORD *)v5 + 6);
  v112 = *((_OWORD *)v5 + 7);
  v113 = *((_WORD *)v5 + 64);
  *(_OWORD *)pszRootPath = *(_OWORD *)((char *)this + 616);
  v118 = *(_OWORD *)((char *)this + 632);
  v119 = *(_OWORD *)((char *)this + 648);
  v120 = *(_OWORD *)((char *)this + 664);
  v121 = *(_OWORD *)((char *)this + 680);
  v122 = *(_OWORD *)((char *)this + 696);
  v123 = *(_OWORD *)((char *)this + 712);
  v124 = *(_OWORD *)((char *)this + 728);
  v125 = *((_WORD *)this + 372);
  SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSensePurge::Stop(
    v63,
    (char *)this + 488,
    v90,
    v81,
    v62,
    v78,
    v77,
    v76,
    *((_QWORD *)&v89 + 1),
    v92,
    v93,
    *((_QWORD *)this + 62),
    v127);
  SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSensePurge::~StorageSensePurge((SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSensePurge *)v126);
  std::vector<unsigned int>::_Tidy(&v94);
  return 0;
}

```

## disassembly

```asm
0x18008e1d0  mov     rax, rsp
0x18008e1d3  push    rbp
0x18008e1d4  push    rbx
0x18008e1d5  push    rsi
0x18008e1d6  push    rdi
0x18008e1d7  push    r12
0x18008e1d9  push    r13
0x18008e1db  push    r14
0x18008e1dd  push    r15
0x18008e1df  lea     rbp, [rax-7D8h]
0x18008e1e6  sub     rsp, 8E8h
0x18008e1ed  movaps  xmmword ptr [rax-58h], xmm6
0x18008e1f1  movaps  xmmword ptr [rax-68h], xmm7
0x18008e1f5  mov     rax, cs:__security_cookie
0x18008e1fc  xor     rax, rsp
0x18008e1ff  mov     [rbp+7D0h+var_70], rax
0x18008e206  mov     rdi, rcx
0x18008e209  xor     esi, esi
0x18008e20b  mov     [rbp+7D0h+var_844], esi
0x18008e20e  mov     byte ptr [rbp+7D0h+var_84C], sil
0x18008e212  mov     [rbp+7D0h+var_7C8], rsi
0x18008e216  mov     [rbp+7D0h+var_820], esi
0x18008e219  mov     [rbp+7D0h+var_840], esi
0x18008e21c  mov     [rbp+7D0h+var_82C], esi
0x18008e21f  mov     [rbp+7D0h+var_830], esi
0x18008e222  mov     [rbp+7D0h+var_834], esi
0x18008e225  xorps   xmm6, xmm6
0x18008e228  movsd   [rbp+7D0h+var_7E0], xmm6
0x18008e22d  xorps   xmm7, xmm7
0x18008e230  movsd   qword ptr [rbp+7D0h+var_7D8], xmm7
0x18008e235  mov     [rbp+7D0h+var_7B8], rsi
0x18008e239  mov     [rbp+7D0h+var_7B0], rsi
0x18008e23d  mov     qword ptr [rbp+7D0h+var_7D8+8], rsi
0x18008e241  mov     [rbp+7D0h+var_848], sil
0x18008e245  lea     r8d, [rsi+60h]; Size
0x18008e249  or      edx, 0FFFFFFFFh; Val
0x18008e24c  lea     rcx, [rbp+7D0h+var_D0]; void *
0x18008e253  call    memset_0
0x18008e258  xorps   xmm0, xmm0
0x18008e25b  movdqu  [rbp+7D0h+var_7A8], xmm0
0x18008e260  mov     [rbp+7D0h+var_798], rsi
0x18008e264  movups  xmmword ptr [rbp+7D0h+pguid.Data1], xmm0
0x18008e26b  lea     rcx, [rbp+7D0h+pguid]; pguid
0x18008e272  call    cs:__imp_CoCreateGuid
0x18008e278  lea     r13, [rdi+2EAh]
0x18008e27f  lea     r8, [rbp+7D0h+pguid]
0x18008e286  lea     r14d, [rsi+2]
0x18008e28a  mov     edx, r14d
0x18008e28d  mov     rcx, r13
0x18008e290  call    cs:__imp_RtlInitializeCorrelationVector
0x18008e296  lea     rcx, [rdi+1E8h]
0x18008e29d  lea     r9, [rbp+7D0h+var_7B8]
0x18008e2a1  lea     r8, [rbp+7D0h+var_7D8+8]
0x18008e2a5  xor     edx, edx
0x18008e2a7  call    cs:__imp_GetStorageDeviceSize
0x18008e2ad  lea     rdx, [rbp+7D0h+var_844]
0x18008e2b1  mov     rcx, [rdi+250h]
0x18008e2b8  call    ?get_Size@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJPEAI@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::get_Size(uint *)
0x18008e2bd  mov     ebx, [rbp+7D0h+var_844]
0x18008e2c0  test    eax, eax
0x18008e2c2  cmovs   ebx, esi
0x18008e2c5  mov     [rbp+7D0h+var_844], ebx
0x18008e2c8  mov     word ptr [rdi+1F9h], 100h
0x18008e2d1  mov     [rdi+1FBh], sil
0x18008e2d8  mov     [rdi+20Ch], r14
0x18008e2df  xor     r9d, r9d
0x18008e2e2  mov     r8d, r14d
0x18008e2e5  xor     edx, edx
0x18008e2e7  mov     rcx, rdi
0x18008e2ea  call    ?_SetContext@?$CStorageCleanupListSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@StorageSenseHandlers@SystemSettings@@AEAAXPEBGW4CleanupOperation@23@I@Z; SystemSettings::StorageSenseHandlers::CStorageCleanupListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::_SetContext(ushort const *,SystemSettings::StorageSenseHandlers::CleanupOperation,uint)
0x18008e2ef  movsxd  rax, dword ptr [rdi+180h]
0x18008e2f6  imul    rcx, rax, 110h
0x18008e2fd  lea     r12, unk_18018A990
0x18008e304  add     rcx, r12
0x18008e307  xor     r8d, r8d
0x18008e30a  mov     dl, 1
0x18008e30c  call    ?SetIsOperationRunning@?$CListOperationSingleton@_K@SingletonHelpers@StorageSenseHandlers@SystemSettings@@QEAAX_N0@Z; SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::SetIsOperationRunning(bool,bool)
0x18008e311  lea     rdx, stru_180111EA8; unsigned __int16 *
0x18008e318  mov     rcx, rdi; this
0x18008e31b  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x18008e320  lea     rdx, stru_180112038; unsigned __int16 *
0x18008e327  mov     rcx, rdi; this
0x18008e32a  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x18008e32f  mov     edx, [rdi+17Ch]
0x18008e335  mov     ecx, [rdi+178h]
0x18008e33b  call    ?IsSystemVolume@StorageSenseUtils@StorageSenseHandlers@SystemSettings@@YA_NW4_STORAGE_DEVICE_TYPE@@K@Z; SystemSettings::StorageSenseHandlers::StorageSenseUtils::IsSystemVolume(_STORAGE_DEVICE_TYPE,ulong)
0x18008e340  test    al, al
0x18008e342  jz      short loc_18008E3B1
0x18008e344  call    ?GetInstance@CStorageCleanupListHandlerSingleton@StorageSenseHandlers@SystemSettings@@SAPEAV123@XZ; SystemSettings::StorageSenseHandlers::CStorageCleanupListHandlerSingleton::GetInstance(void)
0x18008e349  mov     rbx, rax
0x18008e34c  lea     rcx, [rbp+7D0h+var_6B0]
0x18008e353  call    ??$make_shared@UCleanupListOperationStarted@StorageSenseHandlers@SystemSettings@@$$V@std@@YA?AV?$shared_ptr@UCleanupListOperationStarted@StorageSenseHandlers@SystemSettings@@@0@XZ; std::make_shared<SystemSettings::StorageSenseHandlers::CleanupListOperationStarted,>(void)
0x18008e358  mov     rcx, rax
0x18008e35b  xorps   xmm0, xmm0
0x18008e35e  movdqu  xmmword ptr [rbp+7D0h+var_7F8], xmm0
0x18008e363  mov     rax, [rax]
0x18008e366  mov     [rbp+7D0h+var_7F8], rax
0x18008e36a  mov     rax, [rcx+8]
0x18008e36e  mov     [rbp+7D0h+var_7F8+8], rax
0x18008e372  mov     [rcx], rsi
0x18008e375  mov     [rcx+8], rsi
0x18008e379  lea     rax, [rbp+7D0h+var_7F8]
0x18008e37d  mov     [rbp+7D0h+var_800], rax
0x18008e381  lea     rdx, [rbp+7D0h+var_800]
0x18008e385  mov     rcx, rbx
0x18008e388  call    ??$_Notify@V_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_@@@?$CSingletonHelper@AEBV?$shared_ptr@UCleanupListHandlerEvent@StorageSenseHandlers@SystemSettings@@@std@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_@@@Z; SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent> const &>::_Notify<_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_>(_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_ const &)
0x18008e38d  nop
0x18008e38e  mov     rcx, [rbp+7D0h+var_7F8+8]; this
0x18008e392  test    rcx, rcx
0x18008e395  jz      short loc_18008E39D
0x18008e397  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008e39c  nop
0x18008e39d  mov     rcx, [rbp+7D0h+var_6A8]; this
0x18008e3a4  test    rcx, rcx
0x18008e3a7  jz      short loc_18008E3AE
0x18008e3a9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008e3ae  mov     ebx, [rbp+7D0h+var_844]
0x18008e3b1  lea     rcx, [rbp+7D0h+var_220]
0x18008e3b8  call    ??$Start@AEA_JAEAUCORRELATION_VECTOR@@AEAU1@@StorageSensePurge@SSTelemetry@Internal@StorageSenseHandlers@SystemSettings@@SA?AV01234@AEA_JAEAUCORRELATION_VECTOR@@1@Z; SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSensePurge::Start<__int64 &,CORRELATION_VECTOR &,CORRELATION_VECTOR &>(__int64 &,CORRELATION_VECTOR &,CORRELATION_VECTOR &)
0x18008e3bd  nop
0x18008e3be  lea     r15, [rdi+148h]
0x18008e3c5  mov     rax, [r15]
0x18008e3c8  cmp     rax, [r15+8]
0x18008e3cc  jz      short loc_18008E3D2
0x18008e3ce  mov     [r15+8], rax
0x18008e3d2  lea     r14, [rdi+160h]
0x18008e3d9  mov     rax, [r14]
0x18008e3dc  cmp     rax, [r14+8]
0x18008e3e0  jz      short loc_18008E3E6
0x18008e3e2  mov     [r14+8], rax
0x18008e3e6  mov     [rbp+7D0h+var_800], rsi
0x18008e3ea  movsxd  rax, dword ptr [rdi+180h]
0x18008e3f1  imul    rcx, rax, 110h
0x18008e3f8  add     rcx, r12
0x18008e3fb  call    ?GetItemCheckedCount@?$CListOperationSingleton@_K@SingletonHelpers@StorageSenseHandlers@SystemSettings@@QEAAIXZ; SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::GetItemCheckedCount(void)
0x18008e400  mov     [rbp+7D0h+var_838], eax
0x18008e403  mov     r12d, esi
0x18008e406  mov     dword ptr [rbp+7D0h+var_7E8], esi
0x18008e409  test    ebx, ebx
0x18008e40b  jz      loc_18008E987
0x18008e411  mov     r13d, esi
0x18008e414  mov     al, [rdi+208h]
0x18008e41a  nop
0x18008e41b  test    al, al
0x18008e41d  jnz     loc_18008E961
0x18008e423  mov     [rbp+7D0h+var_808], rsi
0x18008e427  mov     rbx, [rdi+250h]
0x18008e42e  lea     rcx, [rbp+7D0h+var_808]
0x18008e432  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18008e437  lea     r8, [rbp+7D0h+var_808]
0x18008e43b  mov     edx, r12d
0x18008e43e  mov     rcx, rbx
0x18008e441  call    ?GetAt@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJIPEAPEAUISettingItem@DataModel@SystemSettings@@@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(uint,SystemSettings::DataModel::ISettingItem * *)
0x18008e446  mov     [rbp+7D0h+var_83C], eax
0x18008e449  mov     rsi, [rbp+7D0h+var_808]
0x18008e44d  mov     byte ptr [rsi+118h], 0
0x18008e454  test    eax, eax
0x18008e456  js      loc_18008E939
0x18008e45c  movsxd  rax, dword ptr [rdi+180h]
0x18008e463  imul    rbx, rax, 110h
0x18008e46a  lea     rax, unk_18018A990
0x18008e471  add     rbx, rax
0x18008e474  mov     rcx, rsi; this
0x18008e477  call    ?GetCategory@CStorageCleanupItem@StorageSenseHandlers@SystemSettings@@QEAA_KXZ; SystemSettings::StorageSenseHandlers::CStorageCleanupItem::GetCategory(void)
0x18008e47c  mov     [rbp+7D0h+var_850], 0
0x18008e480  lea     r8, [rbp+7D0h+var_850]
0x18008e484  mov     rdx, rax
0x18008e487  mov     rcx, rbx
0x18008e48a  call    ?GetIsItemChecked@?$CListOperationSingleton@_K@SingletonHelpers@StorageSenseHandlers@SystemSettings@@QEAAJ_KAEA_N@Z; SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::GetIsItemChecked(unsigned __int64,bool &)
0x18008e48f  cmp     [rbp+7D0h+var_850], 0
0x18008e493  jz      loc_18008E939
0x18008e499  call    ?IsDesktopSKU@@YA_NXZ; IsDesktopSKU(void)
0x18008e49e  test    al, al
0x18008e4a0  jnz     loc_18008E756
0x18008e4a6  mov     qword ptr [rbp+7D0h+var_818], 0
0x18008e4ae  xor     edx, edx
0x18008e4b0  lea     rcx, [rbp+7D0h+var_818]
0x18008e4b4  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18008e4b9  xor     edx, edx; length
0x18008e4bb  mov     rcx, [rsi+0F0h]; string
0x18008e4c2  call    cs:__imp_WindowsGetStringRawBuffer
0x18008e4c8  lea     rdx, [rbp+7D0h+var_818]; unsigned __int16 *
0x18008e4cc  mov     rcx, rax; this
0x18008e4cf  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAG@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,ushort * *)
0x18008e4d4  test    eax, eax
0x18008e4d6  jns     short loc_18008E4E7
0x18008e4d8  lea     rcx, [rbp+7D0h+var_818]
0x18008e4dc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18008e4e1  nop
0x18008e4e2  jmp     loc_18008E93D
0x18008e4e7  imul    eax, r13d, 64h ; 'd'
0x18008e4eb  xor     edx, edx
0x18008e4ed  div     [rbp+7D0h+var_838]
0x18008e4f0  mov     r9d, eax
0x18008e4f3  mov     r8d, [rdi+20Ch]
0x18008e4fa  mov     rdx, qword ptr [rbp+7D0h+var_818]
0x18008e4fe  mov     rcx, rdi
0x18008e501  call    ?_SetContext@?$CStorageCleanupListSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@StorageSenseHandlers@SystemSettings@@AEAAXPEBGW4CleanupOperation@23@I@Z; SystemSettings::StorageSenseHandlers::CStorageCleanupListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::_SetContext(ushort const *,SystemSettings::StorageSenseHandlers::CleanupOperation,uint)
0x18008e506  movsxd  rax, dword ptr [rdi+180h]
0x18008e50d  imul    rcx, rax, 110h
0x18008e514  lea     rax, unk_18018A990
0x18008e51b  add     rcx, rax
0x18008e51e  xor     r8d, r8d
0x18008e521  mov     dl, 1
0x18008e523  call    ?SetIsOperationRunning@?$CListOperationSingleton@_K@SingletonHelpers@StorageSenseHandlers@SystemSettings@@QEAAX_N0@Z; SystemSettings::StorageSenseHandlers::SingletonHelpers::CListOperationSingleton<unsigned __int64>::SetIsOperationRunning(bool,bool)
0x18008e528  mov     byte ptr [rbp+7D0h+var_84C], 1
0x18008e52c  mov     rcx, rsi; this
0x18008e52f  call    ?GetCategory@CStorageCleanupItem@StorageSenseHandlers@SystemSettings@@QEAA_KXZ; SystemSettings::StorageSenseHandlers::CStorageCleanupItem::GetCategory(void)
0x18008e534  mov     r13, rax
0x18008e537  mov     r12, [rdi+108h]
0x18008e53e  xor     eax, eax
0x18008e540  test    r12, r12
0x18008e543  jz      short loc_18008E550
0x18008e545  mov     ebx, [r12]
0x18008e549  mov     r12d, [r12+4]
0x18008e54e  jmp     short loc_18008E555
0x18008e550  mov     ebx, eax
0x18008e552  mov     r12d, eax
0x18008e555  cmp     r13d, 13h
0x18008e559  jnz     short loc_18008E571
0x18008e55b  mov     dword ptr [rbp+7D0h+var_6B0], 14h
0x18008e565  mov     [rbp+7D0h+var_6A8+4], rax
0x18008e56c  jmp     loc_18008E5F4
0x18008e571  cmp     r13d, 11h
0x18008e575  jnz     short loc_18008E5D0
0x18008e577  xor     edx, edx; Val
0x18008e579  mov     r8d, 454h; Size
0x18008e57f  lea     rcx, [rbp+7D0h+pszRootPath+4]; void *
0x18008e586  call    memset_0
0x18008e58b  mov     dword ptr [rbp+7D0h+pszRootPath], 458h
0x18008e595  lea     r8, [rbp+7D0h+pszRootPath]
0x18008e59c  mov     edx, r12d
0x18008e59f  mov     ecx, ebx
0x18008e5a1  call    cs:__imp_GetStorageDeviceInfo
0x18008e5a7  test    eax, eax
0x18008e5a9  js      short loc_18008E5C9
0x18008e5ab  call    IsSHEmptyRecycleBinWPresent
0x18008e5b0  test    al, al
0x18008e5b2  jz      short loc_18008E5C9
0x18008e5b4  lea     r8d, [r13-0Ah]; dwFlags
0x18008e5b8  lea     rdx, [rbp+7D0h+pszRootPath+4]; pszRootPath
0x18008e5bf  xor     ecx, ecx; hwnd
0x18008e5c1  call    cs:__imp_SHEmptyRecycleBinW
0x18008e5c7  jmp     short loc_18008E60E
0x18008e5c9  mov     ebx, 80004001h
0x18008e5ce  jmp     short loc_18008E634
0x18008e5d0  mov     ecx, 14h
0x18008e5d5  cmp     r13d, ecx
0x18008e5d8  jnz     short loc_18008E619
0x18008e5da  mov     dword ptr [rbp+7D0h+var_6A8+4], 1
0x18008e5e4  mov     [rbp+7D0h+var_6A0], 1
0x18008e5ee  mov     dword ptr [rbp+7D0h+var_6B0], ecx
0x18008e5f4  mov     dword ptr [rbp+7D0h+var_6B0+4], ebx
0x18008e5fa  mov     dword ptr [rbp+7D0h+var_6A8], r12d
0x18008e601  lea     rcx, [rbp+7D0h+var_6B0]
0x18008e608  call    cs:__imp_TriggerStorageCleanup
0x18008e60e  mov     ebx, eax
0x18008e610  mov     byte ptr [rsi+118h], 1
0x18008e617  jmp     short loc_18008E634
0x18008e619  cmp     r13d, 0Dh
0x18008e61d  jnz     short loc_18008E631
0x18008e61f  mov     dword ptr [rbp+7D0h+var_6A8+4], eax
0x18008e625  mov     [rbp+7D0h+var_6A0], 5
0x18008e62f  jmp     short loc_18008E5EE
0x18008e631  mov     ebx, [rbp+7D0h+var_83C]
0x18008e634  mov     ecx, 0C8h; dwMilliseconds
0x18008e639  call    cs:__imp_Sleep
0x18008e63f  call    ?RefreshQueries@CStorSvcHandler@StorageSenseHandlers@SystemSettings@@QEAAJXZ; SystemSettings::StorageSenseHandlers::CStorSvcHandler::RefreshQueries(void)
0x18008e644  mov     [rsp+920h+var_900], 0; __int64
0x18008e64d  xor     r9d, r9d
0x18008e650  xor     r8d, r8d
0x18008e653  xor     edx, edx
0x18008e655  mov     rcx, rsi; this
0x18008e658  call    ?RefreshSize@CStorageCleanupItem@StorageSenseHandlers@SystemSettings@@QEAAJW4CleanupItemSizeRefreshOperationKind@23@PEAV?$vector@UPluginScanStart@StorageSenseHandlers@SystemSettings@@V?$allocator@UPluginScanStart@StorageSenseHandlers@SystemSettings@@@std@@@std@@PEAV?$vector@UPluginScanStop@StorageSenseHandlers@SystemSettings@@V?$allocator@UPluginScanStop@StorageSenseHandlers@SystemSettings@@@std@@@6@PEA_K@Z; SystemSettings::StorageSenseHandlers::CStorageCleanupItem::RefreshSize(SystemSettings::StorageSenseHandlers::CleanupItemSizeRefreshOperationKind,std::vector<SystemSettings::StorageSenseHandlers::PluginScanStart> *,std::vector<SystemSettings::StorageSenseHandlers::PluginScanStop> *,unsigned __int64 *)
0x18008e65d  lea     rdx, stru_1801068F0; unsigned __int16 *
0x18008e664  mov     rcx, rsi; this
0x18008e667  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x18008e66c  cmp     qword ptr [rsi+110h], 0
0x18008e674  jnz     short loc_18008E6A2
0x18008e676  cmp     byte ptr [rsi+118h], 1
0x18008e67d  jnz     short loc_18008E6A2
0x18008e67f  mov     rdx, qword ptr [rbp+7D0h+var_7A8+8]
0x18008e683  cmp     rdx, [rbp+7D0h+var_798]
0x18008e687  jz      short loc_18008E695
0x18008e689  mov     eax, dword ptr [rbp+7D0h+var_7E8]
0x18008e68c  mov     [rdx], eax
0x18008e68e  add     qword ptr [rbp+7D0h+var_7A8+8], 4
0x18008e693  jmp     short loc_18008E6A2
0x18008e695  lea     r8, [rbp+7D0h+var_7E8]
0x18008e699  lea     rcx, [rbp+7D0h+var_7A8]
0x18008e69d  call    ??$_Emplace_reallocate@AEBI@?$vector@IV?$allocator@I@std@@@std@@AEAAPEAIQEAIAEBI@Z; std::vector<uint>::_Emplace_reallocate<uint const &>(uint * const,uint const &)
0x18008e6a2  mov     [rbp+7D0h+var_83C], 0
0x18008e6a9  lea     rdx, [rbp+7D0h+var_83C]
0x18008e6ad  mov     ecx, r13d
0x18008e6b0  call    ?EnumToNode@StorageSenseCategoriesEx@StorageSenseHandlers@SystemSettings@@YAJW4StorageSenseBreakdownCategoryEx@123@PEAW4_DATA_TYPE_NODE@@@Z; SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::EnumToNode(SystemSettings::StorageSenseHandlers::StorageSenseCategoriesEx::StorageSenseBreakdownCategoryEx,_DATA_TYPE_NODE *)
0x18008e6b5  call    ?Provider@SettingsHandlersStorageSenseLogging@@SAPEBU_tlgProvider_t@@XZ; SettingsHandlersStorageSenseLogging::Provider(void)
0x18008e6ba  mov     r8, rax
0x18008e6bd  mov     eax, [rax]
0x18008e6bf  test    eax, eax
0x18008e6c1  jz      loc_18008E748
  ... truncated ...
```
