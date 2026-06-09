# ServiceManager::DetachClient(MapsClientType,ulong)

- ea: `0x180014c00`
- end: `0x1800151f6`
- name: `?DetachClient@ServiceManager@@UEAAJW4MapsClientType@@K@Z`
- size: `1526`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int)`
- caller_count: `7`
- callee_count: `28`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180012cf0`
- `0x180013580`
- `0x180013870`
- `0x18001405c`
- `0x1800142c4`
- `0x18001ac90`
- `0x18001b068`

## callees

- `0x180003410`
- `0x180003f7c`
- `0x1800078d0`
- `0x180008110`
- `0x18000816c`
- `0x18000828c`
- `0x1800098a4`
- `0x180009938`
- `0x180009bb4`
- `0x180009c04`
- `0x180009c88`
- `0x180009d0c`
- `0x180009db4`
- `0x18000a538`
- `0x18000af6c`
- `0x18000b5d8`
- `0x18000fd58`
- `0x18001189c`
- `0x1800134b8`
- `0x180014c00`
- `0x180015898`
- `0x180015ed0`
- `0x180019d1c`
- `0x18001af8c`
- `0x18001b068`
- `0x18001db8c`
- `0x1800228ec`
- `0x1800229b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014cae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014cae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014cdc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014cec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014cdc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014cec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180014c8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180014c8f`
- `MosStorage!MosStorageGetCurrentLocation` at `0x180014d52`
- `MosStorage!MosStorageGetCurrentLocation` at `0x180014d52`
- `MosStorage!MosStorageGetDataDirectory` at `0x180014d7c`
- `MosStorage!MosStorageGetDataDirectory` at `0x180014d7c`
- `MosStorage!MosQueryPackagesFromPath` at `0x180014ddd`
- `MosStorage!MosQueryPackagesFromPath` at `0x180014ddd`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180014d6a`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180015055`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180015110`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180014d6a`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180015055`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180015110`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180014d94`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180014f03`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180014d94`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180014f03`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180014c6b`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180014c6b`

## string_xrefs

- `0x180014c5f`: `ServiceManager::DetachClient`
- `0x180014c78`: `ServiceManager::DetachClient`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ServiceManager::DetachClient(__int64 a1, unsigned int a2, unsigned int a3)
{
  unsigned int v6; // eax
  unsigned int v7; // edi
  int v8; // r15d
  __int64 ClientAppPackageFamilyName; // rax
  int CurrentLocation; // eax
  int DataDirectory; // eax
  int v12; // r8d
  __int64 v13; // rsi
  __int64 v14; // rdx
  const unsigned __int16 *v15; // r15
  bool v16; // r12
  unsigned __int64 v17; // rdx
  unsigned __int8 v18; // cl
  OfflineMapsTelemetry *v19; // rax
  int HasOperationOrRestoredData; // eax
  int v21; // r8d
  __int64 (__fastcall *v22)(ServiceManager *__hidden); // rax
  int updated; // eax
  int Operation; // eax
  int v25; // r8d
  bool v27; // [rsp+60h] [rbp-A0h] BYREF
  int v28[2]; // [rsp+70h] [rbp-90h] BYREF
  int v29; // [rsp+78h] [rbp-88h] BYREF
  int v30; // [rsp+7Ch] [rbp-84h]
  _BYTE v31[12]; // [rsp+80h] [rbp-80h] BYREF
  int v32; // [rsp+8Ch] [rbp-74h]
  int v33; // [rsp+90h] [rbp-70h] BYREF
  int v34; // [rsp+94h] [rbp-6Ch] BYREF
  int v35; // [rsp+98h] [rbp-68h] BYREF
  int v36; // [rsp+9Ch] [rbp-64h] BYREF
  __int64 v37; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v38; // [rsp+A8h] [rbp-58h]
  int v39[2]; // [rsp+B8h] [rbp-48h] BYREF
  int *v40; // [rsp+C0h] [rbp-40h]
  _BYTE v41[40]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v42[4]; // [rsp+F0h] [rbp-10h] BYREF
  int v43; // [rsp+F4h] [rbp-Ch]
  unsigned int v44; // [rsp+304h] [rbp+204h]
  unsigned int v45; // [rsp+750h] [rbp+650h]
  unsigned __int16 v46[264]; // [rsp+760h] [rbp+660h] BYREF

  CriticalSectionWithConditionVariable::Lock(a1 + 3400, v31);
  if ( *(_BYTE *)(a1 + 4315) )
  {
    v6 = ZTraceReportOrigination(-2147023641, "ServiceManager::DetachClient", 1500, (const void *)a1);
LABEL_3:
    v7 = v6;
    goto LABEL_73;
  }
  if ( !a2 )
  {
    if ( a3 == GetCurrentProcessId() || !a3 )
      __int2c();
    v28[0] = a3;
    v28[1] = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 3816));
    std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::find(
      a1 + 3856,
      v39,
      v28);
    if ( *(_QWORD *)v39 == *(_QWORD *)(a1 + 3864) )
    {
      if ( a1 != -3816 )
        LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 3816));
      v8 = 0;
    }
    else
    {
      v8 = *(_DWORD *)(*(_QWORD *)v39 + 32LL);
      if ( a1 != -3816 )
        LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 3816));
    }
    if ( v8 == 1 )
    {
      ClientAppPackageFamilyName = ClientsTracker::GetClientAppPackageFamilyName(a1 + 3816, a3, 0);
      std::wstring::wstring(v41, ClientAppPackageFamilyName);
      memset_0(v42, 0, 0x670u);
      v28[0] = 0;
      v39[0] = 0;
      v36 = 0;
      v35 = 0;
      v34 = 0;
      v33 = 0;
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,enum MapControl::DataOriginType>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,enum MapControl::DataOriginType>>>>>>(&v37);
      CurrentLocation = MosStorageGetCurrentLocation((struct _STORAGE_DEVICE_DATA *)v42);
      if ( CurrentLocation < 0 )
        ZTraceReportIgnore(CurrentLocation, "ServiceManager::DetachClient", 1520, (const void *)a1);
      DataDirectory = MosStorageGetDataDirectory(v46, 0x104u);
      if ( DataDirectory < 0 )
      {
        v12 = 1521;
LABEL_19:
        v7 = ZTraceReportPropagation(DataDirectory, "ServiceManager::DetachClient", v12, (const void *)a1);
        if ( v37 )
        {
          std::_Deallocate<16>(v37, (*((_QWORD *)&v38 + 1) - v37) & 0xFFFFFFFFFFFFFFFCuLL);
          v37 = 0;
          v38 = 0;
        }
        std::wstring::_Tidy_deallocate(v41);
        goto LABEL_73;
      }
      DataDirectory = MosQueryPackagesFromPath(v46, &v37, 0);
      if ( DataDirectory < 0 )
      {
        v12 = 1522;
        goto LABEL_19;
      }
      ClientsTracker::GetDataOriginTotals(a1 + 3816, a3, 0, v28, v39, &v36, &v35, &v34, &v33);
      v13 = v38 - v37;
      v15 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v41, v14);
      v16 = v43 != 0;
      if ( OfflineMapsTelemetry::IsEnabled(v18, v17) )
      {
        v19 = OfflineMapsTelemetry::Instance();
        OfflineMapsTelemetry::OfflineMapClientDisconnectedStats_(
          v19,
          v16,
          v44,
          v45,
          v15,
          v13 >> 2,
          v28[0],
          v39[0],
          v36,
          v35,
          v34,
          v33);
      }
      if ( v37 )
      {
        std::_Deallocate<16>(v37, (*((_QWORD *)&v38 + 1) - v37) & 0xFFFFFFFFFFFFFFFCuLL);
        v37 = 0;
        v38 = 0;
      }
      std::wstring::_Tidy_deallocate(v41);
    }
  }
  HasOperationOrRestoredData = ClientsTracker::Unregister(a1 + 3816, a3, a2);
  if ( HasOperationOrRestoredData < 0 )
  {
    v21 = 1545;
LABEL_31:
    v6 = ZTraceReportPropagation(HasOperationOrRestoredData, "ServiceManager::DetachClient", v21, (const void *)a1);
    goto LABEL_3;
  }
  if ( a2 )
  {
    switch ( a2 )
    {
      case 1u:
        *(_DWORD *)(a1 + 4328) = 0;
        if ( *(_BYTE *)(a1 + 4313) )
        {
          *(_BYTE *)(a1 + 4313) = 0;
          HasOperationOrRestoredData = ServiceManager::CancelOperationAndWait(a1, 2);
          if ( HasOperationOrRestoredData < 0 )
          {
            v21 = 1560;
            goto LABEL_31;
          }
        }
        else if ( !*(_DWORD *)(a1 + 3524) )
        {
          v27 = 0;
          HasOperationOrRestoredData = PackageManager::HasOperationOrRestoredData((PackageManager *)(a1 + 3568), &v27);
          if ( HasOperationOrRestoredData < 0 )
          {
            v21 = 1566;
            goto LABEL_31;
          }
          if ( v27 )
          {
            updated = ServiceManager::ProcessPackageOrUpdateOperation((ServiceManager *)a1);
            if ( updated < 0 )
              ZTraceReportIgnore(updated, "ServiceManager::DetachClient", 1571, (const void *)a1);
          }
        }
        break;
      case 3u:
        if ( (unsigned __int8)ClientsTracker::HasClientsOf(a1 + 3816, 1) )
        {
          HasOperationOrRestoredData = ServiceManager::EnsureServiceInitialized(a1, 3);
          if ( HasOperationOrRestoredData < 0 )
          {
            v21 = 1591;
            goto LABEL_31;
          }
        }
        else
        {
          *(_QWORD *)(a1 + 3536) = 0;
          ServiceManager::FireOdmlStateChange((ServiceManager *)a1);
        }
        break;
      case 5u:
        *(_QWORD *)v28 = 5;
        *(_QWORD *)v39 = v28;
        v40 = &v29;
        if ( !(unsigned __int8)ClientsTracker::HasClientsOf(a1 + 3816, v39) && *(_DWORD *)(a1 + 3524) == 10 )
        {
          v22 = ServiceManager::DoMigration;
LABEL_66:
          *(_QWORD *)v28 = v22;
          v29 = 0;
          v30 = v32;
          Threadpool::QueueThis<ServiceManager>(*(PTP_CALLBACK_ENVIRON *)(a1 + 3392));
          goto LABEL_67;
        }
        break;
    }
    goto LABEL_67;
  }
  if ( !(unsigned __int8)ClientsTracker::HasClientsOf(a1 + 3816, 0) )
  {
    if ( *(_DWORD *)(a1 + 3524) == 1 )
    {
      Operation = ServiceManager::ProcessPackageOrUpdateOperation((ServiceManager *)a1);
      if ( Operation >= 0 )
        goto LABEL_63;
      v25 = 1614;
    }
    else
    {
      if ( *(_DWORD *)(a1 + 3524) != 2 )
      {
        if ( *(_DWORD *)(a1 + 3524) == 10 && !(unsigned __int8)ClientsTracker::HasClientsOf(a1 + 3816, 5) )
        {
          *(_QWORD *)v28 = ServiceManager::DoMigration;
          v29 = 0;
          v30 = v32;
          Threadpool::QueueThis<ServiceManager>(*(PTP_CALLBACK_ENVIRON *)(a1 + 3392));
        }
        goto LABEL_63;
      }
      *(_DWORD *)(a1 + 3524) = 0;
      *(_QWORD *)(a1 + 3536) = 1;
      ServiceManager::FireOdmlStateChange((ServiceManager *)a1);
      Operation = ServiceManager::ProcessNextOperation((ServiceManager *)a1);
      if ( Operation >= 0 )
        goto LABEL_63;
      v25 = 1610;
    }
    ZTraceReportIgnore(Operation, "ServiceManager::DetachClient", v25, (const void *)a1);
  }
LABEL_63:
  if ( !ClientsTracker::HasClientsRequiringServiceInitialized((LPCRITICAL_SECTION)(a1 + 3816))
    && *(_DWORD *)(a1 + 4324) == 2 )
  {
    v22 = ServiceManager::EnsureCatalogLoaded;
    goto LABEL_66;
  }
LABEL_67:
  if ( (unsigned int)(*(_DWORD *)(a1 + 3528) - 3) <= 2 )
  {
    HasOperationOrRestoredData = ServiceManager::UpdateTransferPolicies((ServiceManager *)a1);
    if ( HasOperationOrRestoredData < 0 )
    {
      v21 = 1638;
      goto LABEL_31;
    }
  }
  v7 = 0;
  if ( a2 - 3 > 1 && !ClientsTracker::HasClientsRequiringServiceInitialized((LPCRITICAL_SECTION)(a1 + 3816)) )
  {
    *(_QWORD *)v28 = ServiceManager::TryUninitializeService;
    v29 = 0;
    v30 = v32;
    Threadpool::QueueThis<ServiceManager>(*(PTP_CALLBACK_ENVIRON *)(a1 + 3392));
  }
LABEL_73:
  RelockableGate::~RelockableGate((RelockableGate *)v31);
  return v7;
}

```

## disassembly

```asm
0x180014c00  mov     [rsp-8+arg_18], rbx
0x180014c05  push    rbp
0x180014c06  push    rsi
0x180014c07  push    rdi
0x180014c08  push    r12
0x180014c0a  push    r13
0x180014c0c  push    r14
0x180014c0e  push    r15
0x180014c10  lea     rbp, [rsp-880h]
0x180014c18  sub     rsp, 980h
0x180014c1f  mov     rax, cs:__security_cookie
0x180014c26  xor     rax, rsp
0x180014c29  mov     [rbp+8B0h+var_40], rax
0x180014c30  mov     r14d, r8d
0x180014c33  mov     r13d, edx
0x180014c36  mov     rbx, rcx
0x180014c39  add     rcx, 0D48h
0x180014c40  lea     rdx, [rbp+8B0h+var_930]
0x180014c44  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x180014c49  nop
0x180014c4a  xor     r12d, r12d
0x180014c4d  cmp     [rbx+10DBh], r12b
0x180014c54  jz      short loc_180014C78
0x180014c56  mov     r9, rbx
0x180014c59  mov     r8d, 5DCh
0x180014c5f  lea     rdx, aServicemanager_25; "ServiceManager::DetachClient"
0x180014c66  mov     ecx, 800704E7h
0x180014c6b  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x180014c71  mov     edi, eax
0x180014c73  jmp     loc_1800151C1
0x180014c78  lea     rdi, aServicemanager_25; "ServiceManager::DetachClient"
0x180014c7f  test    r13d, r13d
0x180014c82  jnz     loc_180014EDC
0x180014c88  lea     rsi, [rbx+0EE8h]
0x180014c8f  call    cs:__imp_GetCurrentProcessId
0x180014c95  cmp     r14d, eax
0x180014c98  jz      short loc_180014C9F
0x180014c9a  test    r14d, r14d
0x180014c9d  jnz     short loc_180014CA1
0x180014c9f  int     2Ch; Windows NT - assertion failure
0x180014ca1  mov     [rsp+9B0h+var_940], r14d
0x180014ca6  mov     [rsp+9B0h+var_940+4], r12d
0x180014cab  mov     rcx, rsi; lpCriticalSection
0x180014cae  call    cs:__imp_EnterCriticalSection
0x180014cb4  lea     rcx, [rsi+28h]
0x180014cb8  lea     r8, [rsp+9B0h+var_940]
0x180014cbd  lea     rdx, [rbp+8B0h+var_8F8]
0x180014cc1  call    ?find@?$_Hash@V?$_Umap_traits@UClientKey@ClientsTracker@@UClientValue@2@V?$_Uhash_compare@UClientKey@ClientsTracker@@UClientKeyHasher@2@U?$equal_to@UClientKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@@std@@@std@@@2@AEBUClientKey@ClientsTracker@@@Z; std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::find(ClientsTracker::ClientKey const &)
0x180014cc6  mov     rax, qword ptr [rbp+8B0h+var_8F8]
0x180014cca  cmp     rax, [rsi+30h]
0x180014cce  jz      short loc_180014CE4
0x180014cd0  mov     r15d, [rax+20h]
0x180014cd4  test    rsi, rsi
0x180014cd7  jz      short loc_180014CF5
0x180014cd9  mov     rcx, rsi; lpCriticalSection
0x180014cdc  call    cs:__imp_LeaveCriticalSection
0x180014ce2  jmp     short loc_180014CF5
0x180014ce4  test    rsi, rsi
0x180014ce7  jz      short loc_180014CF2
0x180014ce9  mov     rcx, rsi; lpCriticalSection
0x180014cec  call    cs:__imp_LeaveCriticalSection
0x180014cf2  mov     r15d, r12d
0x180014cf5  cmp     r15d, 1
0x180014cf9  jnz     loc_180014EDC
0x180014cff  xor     r8d, r8d
0x180014d02  mov     edx, r14d
0x180014d05  mov     rcx, rsi
0x180014d08  call    ?GetClientAppPackageFamilyName@ClientsTracker@@QEAAPEBGKW4MapsClientType@@@Z; ClientsTracker::GetClientAppPackageFamilyName(ulong,MapsClientType)
0x180014d0d  mov     rdx, rax
0x180014d10  lea     rcx, [rbp+8B0h+var_8E8]
0x180014d14  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180014d19  nop
0x180014d1a  xor     edx, edx; Val
0x180014d1c  mov     r8d, 670h; Size
0x180014d22  lea     rcx, [rbp+8B0h+var_8C0]; void *
0x180014d26  call    memset_0
0x180014d2b  mov     [rsp+9B0h+var_940], r12d
0x180014d30  mov     [rbp+8B0h+var_8F8], r12d
0x180014d34  mov     [rbp+8B0h+var_914], r12d
0x180014d38  mov     [rbp+8B0h+var_918], r12d
0x180014d3c  mov     [rbp+8B0h+var_91C], r12d
0x180014d40  mov     [rbp+8B0h+var_920], r12d
0x180014d44  lea     rcx, [rbp+8B0h+var_910]
0x180014d48  call    ??$?0AEBV?$allocator@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>>>>>(std::allocator<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>> const &)
0x180014d4d  nop
0x180014d4e  lea     rcx, [rbp+8B0h+var_8C0]
0x180014d52  call    cs:__imp_?MosStorageGetCurrentLocation@@YAJPEAU_STORAGE_DEVICE_DATA@@@Z; MosStorageGetCurrentLocation(_STORAGE_DEVICE_DATA *)
0x180014d58  test    eax, eax
0x180014d5a  jns     short loc_180014D70
0x180014d5c  mov     r9, rbx
0x180014d5f  mov     r8d, 5F0h
0x180014d65  mov     rdx, rdi
0x180014d68  mov     ecx, eax
0x180014d6a  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x180014d70  mov     edx, 104h
0x180014d75  lea     rcx, [rbp+8B0h+var_250]
0x180014d7c  call    cs:__imp_?MosStorageGetDataDirectory@@YAJPEAGK@Z; MosStorageGetDataDirectory(ushort *,ulong)
0x180014d82  test    eax, eax
0x180014d84  jns     short loc_180014DCF
0x180014d86  mov     r8d, 5F1h
0x180014d8c  mov     r9, rbx
0x180014d8f  mov     rdx, rdi
0x180014d92  mov     ecx, eax
0x180014d94  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180014d9a  mov     edi, eax
0x180014d9c  mov     rcx, [rbp+8B0h+var_910]
0x180014da0  test    rcx, rcx
0x180014da3  jz      short loc_180014DC1
0x180014da5  mov     rdx, qword ptr [rbp+8B0h+var_908+8]
0x180014da9  sub     rdx, rcx
0x180014dac  and     rdx, 0FFFFFFFFFFFFFFFCh
0x180014db0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180014db5  mov     [rbp+8B0h+var_910], r12
0x180014db9  xorps   xmm0, xmm0
0x180014dbc  movdqu  xmmword ptr [rbp-58h], xmm0
0x180014dc1  lea     rcx, [rbp+8B0h+var_8E8]
0x180014dc5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180014dca  jmp     loc_1800151C1
0x180014dcf  xor     r8d, r8d
0x180014dd2  lea     rdx, [rbp+8B0h+var_910]
0x180014dd6  lea     rcx, [rbp+8B0h+var_250]
0x180014ddd  call    cs:__imp_?MosQueryPackagesFromPath@@YAJPEBGPEAV?$vector@IV?$allocator@I@std@@@std@@W4StackMode@@@Z; MosQueryPackagesFromPath(ushort const *,std::vector<uint> *,StackMode)
0x180014de3  test    eax, eax
0x180014de5  jns     short loc_180014DEF
0x180014de7  mov     r8d, 5F2h
0x180014ded  jmp     short loc_180014D8C
0x180014def  lea     rax, [rbp+8B0h+var_920]
0x180014df3  mov     qword ptr [rsp+9B0h+var_970], rax
0x180014df8  lea     rax, [rbp+8B0h+var_91C]
0x180014dfc  mov     qword ptr [rsp+9B0h+var_978], rax
0x180014e01  lea     rax, [rbp+8B0h+var_918]
0x180014e05  mov     qword ptr [rsp+9B0h+var_980], rax
0x180014e0a  lea     rax, [rbp+8B0h+var_914]
0x180014e0e  mov     qword ptr [rsp+9B0h+var_988], rax
0x180014e13  lea     rax, [rbp+8B0h+var_8F8]
0x180014e17  mov     [rsp+9B0h+var_990], rax
0x180014e1c  lea     r9, [rsp+9B0h+var_940]
0x180014e21  xor     r8d, r8d
0x180014e24  mov     edx, r14d
0x180014e27  mov     rcx, rsi
0x180014e2a  call    ?GetDataOriginTotals@ClientsTracker@@QEAAXKW4MapsClientType@@PEAH11111@Z; ClientsTracker::GetDataOriginTotals(ulong,MapsClientType,int *,int *,int *,int *,int *,int *)
0x180014e2f  mov     rsi, qword ptr [rbp+8B0h+var_908]
0x180014e33  sub     rsi, [rbp+8B0h+var_910]
0x180014e37  lea     rcx, [rbp+8B0h+var_8E8]
0x180014e3b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180014e40  mov     r15, rax
0x180014e43  cmp     [rbp+8B0h+var_8BC], r12d
0x180014e47  setnz   r12b
0x180014e4b  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x180014e50  test    al, al
0x180014e52  jz      short loc_180014EAB
0x180014e54  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x180014e59  sar     rsi, 2
0x180014e5d  mov     ecx, [rbp+8B0h+var_920]
0x180014e60  mov     [rsp+9B0h+var_958], ecx; int
0x180014e64  mov     ecx, [rbp+8B0h+var_91C]
0x180014e67  mov     [rsp+9B0h+var_960], ecx; int
0x180014e6b  mov     ecx, [rbp+8B0h+var_918]
0x180014e6e  mov     [rsp+9B0h+var_968], ecx; int
0x180014e72  mov     ecx, [rbp+8B0h+var_914]
0x180014e75  mov     [rsp+9B0h+var_970], ecx; int
0x180014e79  mov     ecx, [rbp+8B0h+var_8F8]
0x180014e7c  mov     [rsp+9B0h+var_978], ecx; int
0x180014e80  mov     ecx, [rsp+9B0h+var_940]
0x180014e84  mov     [rsp+9B0h+var_980], ecx; int
0x180014e88  mov     [rsp+9B0h+var_988], esi; int
0x180014e8c  mov     [rsp+9B0h+var_990], r15; unsigned __int16 *
0x180014e91  mov     r9d, [rbp+8B0h+var_260]; unsigned int
0x180014e98  mov     r8d, [rbp+8B0h+var_6AC]; unsigned int
0x180014e9f  mov     dl, r12b; bool
0x180014ea2  mov     rcx, rax; this
0x180014ea5  call    ?OfflineMapClientDisconnectedStats_@OfflineMapsTelemetry@@QEAAX_NIIPEBGHHHHHHH@Z; OfflineMapsTelemetry::OfflineMapClientDisconnectedStats_(bool,uint,uint,ushort const *,int,int,int,int,int,int,int)
0x180014eaa  nop
0x180014eab  mov     rcx, [rbp+8B0h+var_910]
0x180014eaf  xor     r12d, r12d
0x180014eb2  test    rcx, rcx
0x180014eb5  jz      short loc_180014ED3
0x180014eb7  mov     rdx, qword ptr [rbp+8B0h+var_908+8]
0x180014ebb  sub     rdx, rcx
0x180014ebe  and     rdx, 0FFFFFFFFFFFFFFFCh
0x180014ec2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180014ec7  mov     [rbp+8B0h+var_910], r12
0x180014ecb  xorps   xmm0, xmm0
0x180014ece  movdqu  [rbp+8B0h+var_908], xmm0
0x180014ed3  lea     rcx, [rbp+8B0h+var_8E8]
0x180014ed7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180014edc  lea     rsi, [rbx+0EE8h]
0x180014ee3  mov     r8d, r13d
0x180014ee6  mov     edx, r14d
0x180014ee9  mov     rcx, rsi
0x180014eec  call    ?Unregister@ClientsTracker@@QEAAJKW4MapsClientType@@@Z; ClientsTracker::Unregister(ulong,MapsClientType)
0x180014ef1  test    eax, eax
0x180014ef3  jns     short loc_180014F0E
0x180014ef5  mov     r8d, 609h
0x180014efb  mov     r9, rbx
0x180014efe  mov     rdx, rdi
0x180014f01  mov     ecx, eax
0x180014f03  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180014f09  jmp     loc_180014C71
0x180014f0e  mov     ecx, r13d
0x180014f11  mov     r14d, 2
0x180014f17  test    r13d, r13d
0x180014f1a  jz      loc_180015060
0x180014f20  sub     ecx, 1
0x180014f23  jz      loc_180014FC5
0x180014f29  sub     ecx, r14d
0x180014f2c  jz      short loc_180014F7F
0x180014f2e  cmp     ecx, r14d
0x180014f31  jnz     loc_180015157
0x180014f37  mov     qword ptr [rsp+9B0h+var_940], 5
0x180014f40  lea     rax, [rsp+9B0h+var_940]
0x180014f45  mov     qword ptr [rbp+8B0h+var_8F8], rax
0x180014f49  lea     rax, [rsp+9B0h+var_938]
0x180014f4e  mov     [rbp+8B0h+var_8F0], rax
0x180014f52  lea     rdx, [rbp+8B0h+var_8F8]
0x180014f56  mov     rcx, rsi
0x180014f59  call    ?HasClientsOf@ClientsTracker@@QEAA_NAEBV?$initializer_list@W4MapsClientType@@@std@@@Z; ClientsTracker::HasClientsOf(std::initializer_list<MapsClientType> const &)
0x180014f5e  test    al, al
0x180014f60  jnz     loc_180015157
0x180014f66  cmp     dword ptr [rbx+0DC4h], 0Ah
0x180014f6d  jnz     loc_180015157
0x180014f73  lea     rax, ?DoMigration@ServiceManager@@AEAAJXZ; ServiceManager::DoMigration(void)
0x180014f7a  jmp     loc_180015132
0x180014f7f  mov     edx, 1
0x180014f84  mov     rcx, rsi
0x180014f87  call    ?HasClientsOf@ClientsTracker@@QEAA_NW4MapsClientType@@@Z; ClientsTracker::HasClientsOf(MapsClientType)
0x180014f8c  mov     rcx, rbx; this
0x180014f8f  test    al, al
0x180014f91  jz      short loc_180014FB0
0x180014f93  mov     edx, 3
0x180014f98  call    ?EnsureServiceInitialized@ServiceManager@@AEAAJW4MapsClientType@@@Z; ServiceManager::EnsureServiceInitialized(MapsClientType)
0x180014f9d  test    eax, eax
0x180014f9f  jns     loc_180015157
0x180014fa5  mov     r8d, 637h
0x180014fab  jmp     loc_180014EFB
0x180014fb0  mov     qword ptr [rbx+0DD0h], 0
0x180014fbb  call    ?FireOdmlStateChange@ServiceManager@@AEAAXXZ; ServiceManager::FireOdmlStateChange(void)
0x180014fc0  jmp     loc_180015157
0x180014fc5  mov     [rbx+10E8h], r12d
0x180014fcc  cmp     [rbx+10D9h], r12b
0x180014fd3  jz      short loc_180014FFA
0x180014fd5  mov     [rbx+10D9h], r12b
0x180014fdc  mov     edx, r14d
0x180014fdf  mov     rcx, rbx
0x180014fe2  call    ?CancelOperationAndWait@ServiceManager@@AEAAJW4CANCELLATION_TYPE@1@@Z; ServiceManager::CancelOperationAndWait(ServiceManager::CANCELLATION_TYPE)
0x180014fe7  test    eax, eax
0x180014fe9  jns     loc_180015157
0x180014fef  mov     r8d, 618h
0x180014ff5  jmp     loc_180014EFB
0x180014ffa  cmp     [rbx+0DC4h], r12d
0x180015001  jnz     loc_180015157
0x180015007  mov     [rsp+9B0h+var_950], r12b
0x18001500c  lea     rcx, [rbx+0DF0h]; this
0x180015013  lea     rdx, [rsp+9B0h+var_950]; bool *
0x180015018  call    ?HasOperationOrRestoredData@PackageManager@@QEAAJPEA_N@Z; PackageManager::HasOperationOrRestoredData(bool *)
0x18001501d  test    eax, eax
0x18001501f  jns     short loc_18001502C
0x180015021  mov     r8d, 61Eh
0x180015027  jmp     loc_180014EFB
0x18001502c  cmp     [rsp+9B0h+var_950], r12b
0x180015031  jz      loc_180015157
0x180015037  mov     rcx, rbx; this
0x18001503a  call    ?ProcessPackageOrUpdateOperation@ServiceManager@@AEAAJXZ; ServiceManager::ProcessPackageOrUpdateOperation(void)
0x18001503f  test    eax, eax
0x180015041  jns     loc_180015157
0x180015047  mov     r9, rbx
0x18001504a  mov     r8d, 623h
0x180015050  mov     rdx, rdi
0x180015053  mov     ecx, eax
0x180015055  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18001505b  jmp     loc_180015157
0x180015060  xor     edx, edx
0x180015062  mov     rcx, rsi
0x180015065  call    ?HasClientsOf@ClientsTracker@@QEAA_NW4MapsClientType@@@Z; ClientsTracker::HasClientsOf(MapsClientType)
0x18001506a  test    al, al
0x18001506c  jnz     loc_180015116
0x180015072  mov     ecx, [rbx+0DC4h]
0x180015078  sub     ecx, 1
0x18001507b  jz      short loc_1800150F6
0x18001507d  sub     ecx, 1
0x180015080  jz      short loc_1800150C8
0x180015082  cmp     ecx, 8
0x180015085  jnz     loc_180015116
0x18001508b  lea     edx, [rcx-3]
0x18001508e  mov     rcx, rsi
0x180015091  call    ?HasClientsOf@ClientsTracker@@QEAA_NW4MapsClientType@@@Z; ClientsTracker::HasClientsOf(MapsClientType)
0x180015096  test    al, al
0x180015098  jnz     short loc_180015116
0x18001509a  lea     rax, ?DoMigration@ServiceManager@@AEAAJXZ; ServiceManager::DoMigration(void)
0x1800150a1  mov     qword ptr [rsp+9B0h+var_940], rax
0x1800150a6  mov     [rsp+9B0h+var_938], r12d
0x1800150ab  mov     eax, [rbp+8B0h+var_924]
0x1800150ae  mov     [rsp+9B0h+var_934], eax
0x1800150b2  lea     r8, [rsp+9B0h+var_940]
0x1800150b7  mov     rdx, rbx
0x1800150ba  mov     rcx, [rbx+0D40h]; pcbe
0x1800150c1  call    ??$QueueThis@VServiceManager@@@Threadpool@@QEAAXPEAVServiceManager@@P81@EAAJXZ@Z; Threadpool::QueueThis<ServiceManager>(ServiceManager *,long (ServiceManager::*)(void))
0x1800150c6  jmp     short loc_180015116
0x1800150c8  mov     [rbx+0DC4h], r12d
0x1800150cf  mov     qword ptr [rbx+0DD0h], 1
  ... truncated ...
```
