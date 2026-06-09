# SystemSettings::StorageSenseHandlers::CBreakdownCollectionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::RefreshDiskScan(void)

- ea: `0x180059620`
- end: `0x180059ae7`
- name: `?RefreshDiskScan@?$CBreakdownCollectionSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@StorageSenseHandlers@SystemSettings@@IEAAJXZ`
- size: `1223`
- prototype: `__int64 __fastcall(SystemSettings::DataModel::CSettingBase *this)`
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180051b10`
- `0x180051d50`

## callees

- `0x180006e50`
- `0x180007a00`
- `0x18000c964`
- `0x18000e6cc`
- `0x18001a530`
- `0x1800248c0`
- `0x1800581f0`
- `0x1800585dc`
- `0x18005905c`
- `0x180059620`
- `0x18005ac14`
- `0x18005ae50`
- `0x18005b0a0`
- `0x18005c034`
- `0x18005cdb4`
- `0x1800b5588`
- `0x1800b5634`
- `0x1800c12d0`
- `0x1800c15d4`
- `0x1800c19ac`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005994b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005994b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800598a4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800598a4`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180059961`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180059961`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180059875`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180059875`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180059a50`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180059a50`
- `ext-ms-win-storage-sense-l1-1-0!FindNextStorageTypeEx` at `0x1800599a8`
- `ext-ms-win-storage-sense-l1-1-0!FindNextStorageTypeEx` at `0x1800599a8`
- `ext-ms-win-storage-sense-l1-1-0!SelectStorageVolumeEx` at `0x1800597d6`
- `ext-ms-win-storage-sense-l1-1-0!SelectStorageVolumeEx` at `0x1800597d6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::StorageSenseHandlers::CBreakdownCollectionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::RefreshDiskScan(
        SystemSettings::DataModel::CSettingBase *this)
{
  char IsEnabled; // al
  __int64 v3; // rcx
  __int64 v4; // rdx
  char IsDiskScanning; // al
  __int64 v6; // rcx
  int Size; // ebx
  __int64 v8; // rdx
  DWORD dwLowDateTime; // r15d
  char v11; // al
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  _BYTE *v17; // rcx
  char v18; // r12
  __int64 v19; // rax
  DWORD i; // r14d
  __int64 v21; // rbx
  __int64 v22; // rdx
  int v23; // eax
  int v24; // ecx
  DWORD j; // r14d
  __int64 v26; // rbx
  bool v27; // sf
  int k; // ebx
  __int64 v29; // rcx
  DWORD m; // r14d
  __int64 v31; // rbx
  struct _FILETIME v32; // rbx
  SystemSettings::StorageSenseHandlers::CStorSvcHandler *v33; // rcx
  int v34; // [rsp+20h] [rbp-E0h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-C0h] BYREF
  int Reply; // [rsp+48h] [rbp-B8h] BYREF
  void *v37; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v38; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v39; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v40; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v41[2]; // [rsp+70h] [rbp-90h] BYREF
  _RPC_ASYNC_STATE pAsync; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  Reply = 0;
  SystemTimeAsFileTime.dwLowDateTime = 0;
  v38 = 0;
  v39 = 0;
  v41[0] = 0;
  v40 = 0;
  v37 = 0;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1>::GetImpl'::`2'::impl);
  v3 = *((int *)this + 72);
  v4 = *((unsigned int *)this + 73);
  if ( IsEnabled )
    IsDiskScanning = SystemSettings::StorageSenseHandlers::IsDiskScanning(v3, v4);
  else
    IsDiskScanning = byte_18018B850[31 * v3 + v4];
  if ( IsDiskScanning )
    return 0;
  v6 = *((_QWORD *)this + 26);
  if ( !v6 )
    return 0;
  Size = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::get_Size(
           v6,
           &SystemTimeAsFileTime);
  if ( Size < 0 )
  {
    v8 = 1227;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\breakdownpages.cpp",
      (const char *)(unsigned int)Size,
      v34);
    return (unsigned int)Size;
  }
  dwLowDateTime = SystemTimeAsFileTime.dwLowDateTime;
  if ( !SystemTimeAsFileTime.dwLowDateTime )
  {
    Size = -2147418113;
    v8 = 1228;
    goto LABEL_8;
  }
  v11 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1>::GetImpl'::`2'::impl);
  v12 = *((int *)this + 72);
  v13 = *((unsigned int *)this + 73);
  if ( v11 )
  {
    if ( !(unsigned __int8)SystemSettings::StorageSenseHandlers::IsValidDiskIndex(v12, v13) )
      return 2147942487LL;
    LOBYTE(v16) = 1;
    v18 = SystemSettings::StorageSenseHandlers::SetDiskScanning(v15, v14, v16);
    if ( !v18 )
      return 0;
  }
  else
  {
    v18 = 0;
    v17 = &byte_18018B850[31 * v12 + v13];
    *v17 = 1;
  }
  Reply = SystemSettings::StorageSenseHandlers::CStorSvcHandler::Get(
            v17,
            1,
            *((unsigned int *)this + 72),
            *((unsigned int *)this + 73),
            &v37);
  if ( Reply < 0 )
    goto LABEL_43;
  Reply = SelectStorageVolumeEx(v37, *((unsigned int *)this + 72), *((unsigned int *)this + 73), 0, 0, 1, &v38, &v39);
  if ( Reply < 0 )
    goto LABEL_43;
  v19 = v38;
  *((_QWORD *)this + 41) = v38;
  *((_QWORD *)this + 40) = v19 - v39;
  for ( i = 0; i < dwLowDateTime; ++i )
  {
    SystemTimeAsFileTime = 0;
    v21 = *((_QWORD *)this + 26);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&SystemTimeAsFileTime);
    if ( (int)Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(
                v21,
                i,
                &SystemTimeAsFileTime) >= 0 )
    {
      LOBYTE(v22) = 1;
      (*(void (__fastcall **)(struct _FILETIME, __int64))(**(_QWORD **)&SystemTimeAsFileTime + 168LL))(
        SystemTimeAsFileTime,
        v22);
    }
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&SystemTimeAsFileTime);
  }
  memset_0(&pAsync, 0, sizeof(pAsync));
  v23 = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( v23 > 0 )
    v23 = (unsigned __int16)v23 | 0x80070000;
  Reply = v23;
  if ( v23 < 0 )
    goto LABEL_46;
  pAsync.UserInfo = 0;
  pAsync.NotificationType = RpcNotificationTypeEvent;
  pAsync.u.APC.NotificationRoutine = (PFN_RPCNOTIFICATION_ROUTINE)CreateEventW(0, 0, 0, 0);
  if ( pAsync.u.APC.NotificationRoutine )
  {
    if ( (unsigned int)SystemSettings::StorageSenseHandlers::CBreakdownCollectionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>::RpcHelper(
                         v24,
                         (unsigned int)&pAsync,
                         (_DWORD)v37,
                         (unsigned int)v41,
                         (__int64)&v40) )
    {
      Reply = -2147467259;
      goto LABEL_46;
    }
    while ( WaitForSingleObject(pAsync.u.APC.NotificationRoutine, 0x1F4u) == 258 )
    {
      for ( j = 0; j < dwLowDateTime; ++j )
      {
        SystemTimeAsFileTime = 0;
        v26 = *((_QWORD *)this + 26);
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&SystemTimeAsFileTime);
        if ( (int)Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(
                    v26,
                    j,
                    &SystemTimeAsFileTime) >= 0 )
          SystemSettings::StorageSenseHandlers::CBreakdownItemSetting::UpdateInProgressOperation(
            *(SystemSettings::StorageSenseHandlers::CBreakdownItemSetting **)&SystemTimeAsFileTime,
            v37);
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&SystemTimeAsFileTime);
      }
    }
    if ( !RpcAsyncCompleteCall(&pAsync, &Reply) )
    {
      v27 = Reply < 0;
      if ( Reply )
        goto LABEL_44;
      for ( k = 1; k < 34; ++k )
      {
        SystemTimeAsFileTime = 0;
        FindNextStorageTypeEx(v37, (unsigned int)k, &word_180106450, &SystemTimeAsFileTime, v41, &v40);
      }
      SystemSettings::StorageSenseHandlers::CStorSvcHandler::ClearHandleInUseState(
        v29,
        1,
        *((unsigned int *)this + 72),
        *((unsigned int *)this + 73));
      for ( m = 0; m < dwLowDateTime; ++m )
      {
        SystemTimeAsFileTime = 0;
        v31 = *((_QWORD *)this + 26);
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&SystemTimeAsFileTime);
        if ( (int)Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(
                    v31,
                    m,
                    &SystemTimeAsFileTime) >= 0 )
        {
          v32 = SystemTimeAsFileTime;
          SystemSettings::StorageSenseHandlers::CBreakdownItemSetting::RefreshCachedValues(
            *(SystemSettings::StorageSenseHandlers::CBreakdownItemSetting **)&SystemTimeAsFileTime,
            1);
          (*(void (__fastcall **)(struct _FILETIME, _QWORD))(**(_QWORD **)&v32 + 168LL))(v32, 0);
        }
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&SystemTimeAsFileTime);
      }
    }
LABEL_43:
    v27 = Reply < 0;
LABEL_44:
    if ( !v27 )
    {
      SystemTimeAsFileTime = 0;
      Reply = SystemSettings::StorageSenseHandlers::CBreakdownCollectionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>::SortCategories(this);
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))SystemSettings::StorageSenseHandlers::StorageSenseCategories::SetStorageDeviceLastDiskScanTimeStamp)(
        *((unsigned int *)this + 72),
        *((unsigned int *)this + 73),
        SystemTimeAsFileTime);
      SystemSettings::StorageSenseHandlers::StorageSenseCategories::SetStorageDeviceLastFreeDiskSizeCached(
        *((unsigned int *)this + 72),
        *((unsigned int *)this + 73),
        *((_QWORD *)this + 41) - *((_QWORD *)this + 40));
    }
    goto LABEL_46;
  }
  Reply = -2147024882;
LABEL_46:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1>::GetImpl'::`2'::impl) )
  {
    if ( v18 )
      SystemSettings::StorageSenseHandlers::SetDiskScanning(
        *((unsigned int *)this + 72),
        *((unsigned int *)this + 73),
        0);
  }
  else
  {
    v33 = (SystemSettings::StorageSenseHandlers::CStorSvcHandler *)&byte_18018B850[31 * *((int *)this + 72)
                                                                                 + *((unsigned int *)this + 73)];
    *(_BYTE *)v33 = 0;
  }
  SystemSettings::StorageSenseHandlers::CStorSvcHandler::RefreshTimestamp(v33);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x180059620  push    rbp
0x180059622  push    rbx
0x180059623  push    rsi
0x180059624  push    rdi
0x180059625  push    r12
0x180059627  push    r13
0x180059629  push    r14
0x18005962b  push    r15
0x18005962d  lea     rbp, [rsp-8]
0x180059632  sub     rsp, 108h
0x180059639  mov     rax, cs:__security_cookie
0x180059640  xor     rax, rsp
0x180059643  mov     [rbp+40h+var_50], rax
0x180059647  mov     rdi, rcx
0x18005964a  xor     r13d, r13d
0x18005964d  mov     [rsp+140h+Reply], r13d
0x180059652  mov     [rsp+140h+SystemTimeAsFileTime.dwLowDateTime], r13d
0x180059657  mov     [rsp+140h+var_E8], r13
0x18005965c  mov     [rsp+140h+var_E0], r13
0x180059661  mov     [rsp+140h+var_D0], r13
0x180059666  mov     [rsp+140h+var_D8], r13
0x18005966b  mov     [rsp+140h+var_F0], r13
0x180059670  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1> `wil::Feature<__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1>::GetImpl(void)'::`2'::impl
0x180059677  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1>::__private_IsEnabled(void)
0x18005967c  movsxd  rcx, dword ptr [rdi+120h]
0x180059683  mov     edx, [rdi+124h]
0x180059689  lea     rsi, byte_18018B850
0x180059690  test    al, al
0x180059692  jz      short loc_18005969B
0x180059694  call    SystemSettings__StorageSenseHandlers__IsDiskScanning
0x180059699  jmp     short loc_1800596A6
0x18005969b  imul    rcx, 1Fh
0x18005969f  add     rcx, rdx
0x1800596a2  mov     al, [rcx+rsi]
0x1800596a5  nop
0x1800596a6  test    al, al
0x1800596a8  jnz     loc_180059741
0x1800596ae  mov     rcx, [rdi+0D0h]
0x1800596b5  test    rcx, rcx
0x1800596b8  jz      loc_180059741
0x1800596be  lea     rdx, [rsp+140h+SystemTimeAsFileTime]
0x1800596c3  call    ?get_Size@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJPEAI@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::get_Size(uint *)
0x1800596c8  mov     ebx, eax
0x1800596ca  test    eax, eax
0x1800596cc  jns     short loc_1800596EA
0x1800596ce  mov     edx, 4CBh; void *
0x1800596d3  lea     r8, aOnecoreuapShel_17; "onecoreuap\\shell\\coresettinghandlers"...
0x1800596da  mov     r9d, ebx; char *
0x1800596dd  mov     rcx, [rbp+48h]; this
0x1800596e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800596e6  mov     eax, ebx
0x1800596e8  jmp     short loc_180059743
0x1800596ea  mov     r15d, [rsp+140h+SystemTimeAsFileTime.dwLowDateTime]
0x1800596ef  test    r15d, r15d
0x1800596f2  jnz     short loc_180059700
0x1800596f4  mov     ebx, 8000FFFFh
0x1800596f9  mov     edx, 4CCh
0x1800596fe  jmp     short loc_1800596D3
0x180059700  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1> `wil::Feature<__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1>::GetImpl(void)'::`2'::impl
0x180059707  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1>::__private_IsEnabled(void)
0x18005970c  movsxd  rcx, dword ptr [rdi+120h]
0x180059713  mov     edx, [rdi+124h]
0x180059719  test    al, al
0x18005971b  jz      short loc_180059763
0x18005971d  call    SystemSettings__StorageSenseHandlers__IsValidDiskIndex
0x180059722  test    al, al
0x180059724  jnz     short loc_18005972D
0x180059726  mov     eax, 80070057h
0x18005972b  jmp     short loc_180059743
0x18005972d  mov     esi, 1
0x180059732  mov     r8b, sil
0x180059735  call    SystemSettings__StorageSenseHandlers__SetDiskScanning
0x18005973a  mov     r12b, al
0x18005973d  test    al, al
0x18005973f  jnz     short loc_180059779
0x180059741  xor     eax, eax
0x180059743  mov     rcx, [rbp+40h+var_50]
0x180059747  xor     rcx, rsp; StackCookie
0x18005974a  call    __security_check_cookie
0x18005974f  add     rsp, 108h
0x180059756  pop     r15
0x180059758  pop     r14
0x18005975a  pop     r13
0x18005975c  pop     r12
0x18005975e  pop     rdi
0x18005975f  pop     rsi
0x180059760  pop     rbx
0x180059761  pop     rbp
0x180059762  retn
0x180059763  mov     r12b, r13b
0x180059766  imul    rcx, 1Fh
0x18005976a  add     rcx, rdx
0x18005976d  add     rcx, rsi
0x180059770  mov     esi, 1
0x180059775  mov     eax, esi
0x180059777  xchg    al, [rcx]
0x180059779  lea     rax, [rsp+140h+var_F0]
0x18005977e  mov     [rsp+140h+var_120], rax
0x180059783  mov     r9d, [rdi+124h]
0x18005978a  mov     r8d, [rdi+120h]
0x180059791  mov     edx, esi
0x180059793  call    ?Get@CStorSvcHandler@StorageSenseHandlers@SystemSettings@@QEAAJW4_STORAGE_SELECTVOL_FLAGS@@W4_STORAGE_DEVICE_TYPE@@KPEAPEAX@Z; SystemSettings::StorageSenseHandlers::CStorSvcHandler::Get(_STORAGE_SELECTVOL_FLAGS,_STORAGE_DEVICE_TYPE,ulong,void * *)
0x180059798  mov     [rsp+140h+Reply], eax
0x18005979c  test    eax, eax
0x18005979e  js      loc_180059A33
0x1800597a4  lea     rax, [rsp+140h+var_E0]
0x1800597a9  mov     [rsp+140h+var_108], rax
0x1800597ae  lea     rax, [rsp+140h+var_E8]
0x1800597b3  mov     [rsp+140h+var_110], rax
0x1800597b8  mov     dword ptr [rsp+140h+var_118], esi
0x1800597bc  mov     [rsp+140h+var_120], r13
0x1800597c1  xor     r9d, r9d
0x1800597c4  mov     r8d, [rdi+124h]
0x1800597cb  mov     edx, [rdi+120h]
0x1800597d1  mov     rcx, [rsp+140h+var_F0]
0x1800597d6  call    cs:__imp_SelectStorageVolumeEx
0x1800597dc  mov     [rsp+140h+Reply], eax
0x1800597e0  test    eax, eax
0x1800597e2  js      loc_180059A33
0x1800597e8  mov     rax, [rsp+140h+var_E8]
0x1800597ed  mov     [rdi+148h], rax
0x1800597f4  sub     rax, [rsp+140h+var_E0]
0x1800597f9  mov     [rdi+140h], rax
0x180059800  mov     r14d, r13d
0x180059803  test    r15d, r15d
0x180059806  jz      short loc_18005985C
0x180059808  mov     qword ptr [rsp+140h+SystemTimeAsFileTime.dwLowDateTime], r13
0x18005980d  mov     rbx, [rdi+0D0h]
0x180059814  lea     rcx, [rsp+140h+SystemTimeAsFileTime]
0x180059819  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18005981e  lea     r8, [rsp+140h+SystemTimeAsFileTime]
0x180059823  mov     edx, r14d
0x180059826  mov     rcx, rbx
0x180059829  call    ?GetAt@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJIPEAPEAUISettingItem@DataModel@SystemSettings@@@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(uint,SystemSettings::DataModel::ISettingItem * *)
0x18005982e  test    eax, eax
0x180059830  js      short loc_18005984A
0x180059832  mov     rcx, qword ptr [rsp+140h+SystemTimeAsFileTime.dwLowDateTime]
0x180059837  mov     rax, [rcx]
0x18005983a  mov     dl, sil
0x18005983d  mov     rax, [rax+0A8h]
0x180059844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059849  nop
0x18005984a  lea     rcx, [rsp+140h+SystemTimeAsFileTime]
0x18005984f  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180059854  add     r14d, esi
0x180059857  cmp     r14d, r15d
0x18005985a  jb      short loc_180059808
0x18005985c  mov     ebx, 70h ; 'p'
0x180059861  mov     r8d, ebx; Size
0x180059864  xor     edx, edx; Val
0x180059866  lea     rcx, [rbp+40h+pAsync]; void *
0x18005986a  call    memset_0
0x18005986f  mov     edx, ebx; Size
0x180059871  lea     rcx, [rbp+40h+pAsync]; pAsync
0x180059875  call    cs:__imp_RpcAsyncInitializeHandle
0x18005987b  test    eax, eax
0x18005987d  jle     short loc_180059887
0x18005987f  movzx   eax, ax
0x180059882  or      eax, 80070000h
0x180059887  mov     [rsp+140h+Reply], eax
0x18005988b  test    eax, eax
0x18005988d  js      loc_180059A8B
0x180059893  mov     [rbp+40h+pAsync.UserInfo], r13
0x180059897  mov     [rbp+40h+pAsync.NotificationType], esi
0x18005989a  xor     r9d, r9d; lpName
0x18005989d  xor     r8d, r8d; bInitialState
0x1800598a0  xor     edx, edx; bManualReset
0x1800598a2  xor     ecx, ecx; lpEventAttributes
0x1800598a4  call    cs:__imp_CreateEventW
0x1800598aa  mov     qword ptr [rbp+40h+pAsync.u], rax
0x1800598ae  test    rax, rax
0x1800598b1  jnz     short loc_1800598C0
0x1800598b3  mov     [rsp+140h+Reply], 8007000Eh
0x1800598bb  jmp     loc_180059A8B
0x1800598c0  lea     rax, [rsp+140h+var_D8]
0x1800598c5  mov     [rsp+140h+var_120], rax
0x1800598ca  lea     r9, [rsp+140h+var_D0]
0x1800598cf  mov     r8, [rsp+140h+var_F0]
0x1800598d4  lea     rdx, [rbp+40h+pAsync]
0x1800598d8  call    ?RpcHelper@?$CBreakdownCollectionSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAUIUser@System@Windows@@PEAPEAUISettingItem@23@@Z@StorageSenseHandlers@SystemSettings@@IEAAKPEAU_RPC_ASYNC_STATE@@PEAXPEA_K2@Z; SystemSettings::StorageSenseHandlers::CBreakdownCollectionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>::RpcHelper(_RPC_ASYNC_STATE *,void *,unsigned __int64 *,unsigned __int64 *)
0x1800598dd  test    eax, eax
0x1800598df  jz      short loc_180059942
0x1800598e1  mov     [rsp+140h+Reply], 80004005h
0x1800598e9  jmp     loc_180059A8B
0x1800598ee  mov     r14d, r13d
0x1800598f1  test    r15d, r15d
0x1800598f4  jz      short loc_180059942
0x1800598f6  mov     qword ptr [rsp+140h+SystemTimeAsFileTime.dwLowDateTime], r13
0x1800598fb  mov     rbx, [rdi+0D0h]
0x180059902  lea     rcx, [rsp+140h+SystemTimeAsFileTime]
0x180059907  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18005990c  lea     r8, [rsp+140h+SystemTimeAsFileTime]
0x180059911  mov     edx, r14d
0x180059914  mov     rcx, rbx
0x180059917  call    ?GetAt@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJIPEAPEAUISettingItem@DataModel@SystemSettings@@@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(uint,SystemSettings::DataModel::ISettingItem * *)
0x18005991c  test    eax, eax
0x18005991e  js      short loc_180059930
0x180059920  mov     rdx, [rsp+140h+var_F0]; void *
0x180059925  mov     rcx, qword ptr [rsp+140h+SystemTimeAsFileTime.dwLowDateTime]; this
0x18005992a  call    ?UpdateInProgressOperation@CBreakdownItemSetting@StorageSenseHandlers@SystemSettings@@QEAAJPEAX@Z; SystemSettings::StorageSenseHandlers::CBreakdownItemSetting::UpdateInProgressOperation(void *)
0x18005992f  nop
0x180059930  lea     rcx, [rsp+140h+SystemTimeAsFileTime]
0x180059935  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18005993a  add     r14d, esi
0x18005993d  cmp     r14d, r15d
0x180059940  jb      short loc_1800598F6
0x180059942  mov     edx, 1F4h; dwMilliseconds
0x180059947  mov     rcx, qword ptr [rbp+40h+pAsync.u]; hHandle
0x18005994b  call    cs:__imp_WaitForSingleObject
0x180059951  cmp     eax, 102h
0x180059956  jz      short loc_1800598EE
0x180059958  lea     rdx, [rsp+140h+Reply]; Reply
0x18005995d  lea     rcx, [rbp+40h+pAsync]; pAsync
0x180059961  call    cs:__imp_RpcAsyncCompleteCall
0x180059967  test    eax, eax
0x180059969  jnz     loc_180059A33
0x18005996f  cmp     [rsp+140h+Reply], r13d
0x180059974  jnz     loc_180059A38
0x18005997a  mov     ebx, esi
0x18005997c  mov     qword ptr [rsp+140h+SystemTimeAsFileTime.dwLowDateTime], r13
0x180059981  lea     rax, [rsp+140h+var_D8]
0x180059986  mov     [rsp+140h+var_118], rax
0x18005998b  lea     rax, [rsp+140h+var_D0]
0x180059990  mov     [rsp+140h+var_120], rax
0x180059995  lea     r9, [rsp+140h+SystemTimeAsFileTime]
0x18005999a  lea     r8, word_180106450
0x1800599a1  mov     edx, ebx
0x1800599a3  mov     rcx, [rsp+140h+var_F0]
0x1800599a8  call    cs:__imp_FindNextStorageTypeEx
0x1800599ae  add     ebx, esi
0x1800599b0  cmp     ebx, 22h ; '"'
0x1800599b3  jl      short loc_18005997C
0x1800599b5  mov     r9d, [rdi+124h]
0x1800599bc  mov     r8d, [rdi+120h]
0x1800599c3  mov     edx, esi
0x1800599c5  call    ?ClearHandleInUseState@CStorSvcHandler@StorageSenseHandlers@SystemSettings@@QEAAJW4_STORAGE_SELECTVOL_FLAGS@@W4_STORAGE_DEVICE_TYPE@@K@Z; SystemSettings::StorageSenseHandlers::CStorSvcHandler::ClearHandleInUseState(_STORAGE_SELECTVOL_FLAGS,_STORAGE_DEVICE_TYPE,ulong)
0x1800599ca  mov     r14d, r13d
0x1800599cd  test    r15d, r15d
0x1800599d0  jz      short loc_180059A33
0x1800599d2  mov     qword ptr [rsp+140h+SystemTimeAsFileTime.dwLowDateTime], r13
0x1800599d7  mov     rbx, [rdi+0D0h]
0x1800599de  lea     rcx, [rsp+140h+SystemTimeAsFileTime]
0x1800599e3  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800599e8  lea     r8, [rsp+140h+SystemTimeAsFileTime]
0x1800599ed  mov     edx, r14d
0x1800599f0  mov     rcx, rbx
0x1800599f3  call    ?GetAt@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJIPEAPEAUISettingItem@DataModel@SystemSettings@@@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(uint,SystemSettings::DataModel::ISettingItem * *)
0x1800599f8  test    eax, eax
0x1800599fa  js      short loc_180059A21
0x1800599fc  mov     rbx, qword ptr [rsp+140h+SystemTimeAsFileTime.dwLowDateTime]
0x180059a01  mov     dl, sil; bool
0x180059a04  mov     rcx, rbx; this
0x180059a07  call    ?RefreshCachedValues@CBreakdownItemSetting@StorageSenseHandlers@SystemSettings@@QEAAX_N@Z; SystemSettings::StorageSenseHandlers::CBreakdownItemSetting::RefreshCachedValues(bool)
0x180059a0c  mov     rax, [rbx]
0x180059a0f  xor     edx, edx
0x180059a11  mov     rcx, rbx
0x180059a14  mov     rax, [rax+0A8h]
0x180059a1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059a20  nop
0x180059a21  lea     rcx, [rsp+140h+SystemTimeAsFileTime]
0x180059a26  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180059a2b  add     r14d, esi
0x180059a2e  cmp     r14d, r15d
0x180059a31  jb      short loc_1800599D2
0x180059a33  cmp     [rsp+140h+Reply], r13d
0x180059a38  jl      short loc_180059A8B
0x180059a3a  mov     qword ptr [rsp+140h+SystemTimeAsFileTime.dwLowDateTime], r13
0x180059a3f  mov     rcx, rdi; this
0x180059a42  call    ?SortCategories@?$CBreakdownCollectionSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAUIUser@System@Windows@@PEAPEAUISettingItem@23@@Z@StorageSenseHandlers@SystemSettings@@IEAAJXZ; SystemSettings::StorageSenseHandlers::CBreakdownCollectionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>::SortCategories(void)
0x180059a47  mov     [rsp+140h+Reply], eax
0x180059a4b  lea     rcx, [rsp+140h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180059a50  call    cs:__imp_GetSystemTimeAsFileTime
0x180059a56  mov     r8, qword ptr [rsp+140h+SystemTimeAsFileTime.dwLowDateTime]
0x180059a5b  mov     edx, [rdi+124h]
0x180059a61  mov     ecx, [rdi+120h]
0x180059a67  call    ?SetStorageDeviceLastDiskScanTimeStamp@StorageSenseCategories@StorageSenseHandlers@SystemSettings@@YAJW4_STORAGE_DEVICE_TYPE@@KU_FILETIME@@@Z; SystemSettings::StorageSenseHandlers::StorageSenseCategories::SetStorageDeviceLastDiskScanTimeStamp(_STORAGE_DEVICE_TYPE,ulong,_FILETIME)
0x180059a6c  mov     r8, [rdi+148h]
0x180059a73  sub     r8, [rdi+140h]
0x180059a7a  mov     edx, [rdi+124h]
0x180059a80  mov     ecx, [rdi+120h]
0x180059a86  call    ?SetStorageDeviceLastFreeDiskSizeCached@StorageSenseCategories@StorageSenseHandlers@SystemSettings@@YAJW4_STORAGE_DEVICE_TYPE@@K_K@Z; SystemSettings::StorageSenseHandlers::StorageSenseCategories::SetStorageDeviceLastFreeDiskSizeCached(_STORAGE_DEVICE_TYPE,ulong,unsigned __int64)
0x180059a8b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1> `wil::Feature<__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1>::GetImpl(void)'::`2'::impl
0x180059a92  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CleanupStorageSettingsTestViolationsRound1>::__private_IsEnabled(void)
0x180059a97  test    al, al
0x180059a99  jz      short loc_180059AB6
0x180059a9b  test    r12b, r12b
0x180059a9e  jz      short loc_180059AD9
0x180059aa0  xor     r8d, r8d
0x180059aa3  mov     edx, [rdi+124h]
0x180059aa9  mov     ecx, [rdi+120h]
0x180059aaf  call    SystemSettings__StorageSenseHandlers__SetDiskScanning
0x180059ab4  jmp     short loc_180059AD9
0x180059ab6  movsxd  rax, dword ptr [rdi+120h]
0x180059abd  imul    rcx, rax, 1Fh
0x180059ac1  mov     eax, [rdi+124h]
0x180059ac7  add     rcx, rax
0x180059aca  lea     rax, byte_18018B850
0x180059ad1  add     rcx, rax; this
0x180059ad4  mov     eax, r13d
0x180059ad7  xchg    al, [rcx]
  ... truncated ...
```
