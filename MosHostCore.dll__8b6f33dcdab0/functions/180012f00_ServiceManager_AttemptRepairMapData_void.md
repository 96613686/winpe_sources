# ServiceManager::AttemptRepairMapData(void)

- ea: `0x180012f00`
- end: `0x18001316e`
- name: `?AttemptRepairMapData@ServiceManager@@AEAAJXZ`
- size: `622`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, installer_update`

## callees

- `0x180003410`
- `0x180003f7c`
- `0x1800078d0`
- `0x18000828c`
- `0x180009d0c`
- `0x180009db4`
- `0x18000ea5c`
- `0x18001189c`
- `0x180012f00`
- `0x180013870`
- `0x180015ed0`
- `0x18001a4b8`
- `0x1800228ec`
- `0x1800229b8`
- `0x1800229d4`
- `0x180022a00`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800130d2`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800130d2`
- `MosStorage!MosStorageGetCurrentLocation` at `0x180012f7b`
- `MosStorage!MosStorageGetCurrentLocation` at `0x180012f7b`
- `MosStorage!MosQueryPackages` at `0x180012fcc`
- `MosStorage!MosQueryPackages` at `0x180012fcc`
- `MosStorage!MosStorageGetMapsRepairAttempts` at `0x180012fa5`
- `MosStorage!MosStorageGetMapsRepairAttempts` at `0x180012fa5`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180012f9a`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180012fe4`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180012f9a`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180012fe4`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180013068`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180013068`

## string_xrefs

- `0x180012f81`: `ServiceManager::AttemptRepairMapData`

## pseudocode

```c
__int64 __fastcall ServiceManager::AttemptRepairMapData(ServiceManager *this)
{
  int CurrentLocation; // eax
  int MapsRepairAttempts; // eax
  int v4; // r8d
  int v5; // eax
  int v6; // edi
  int v7; // ecx
  int v8; // eax
  __int64 v9; // rbx
  bool v10; // si
  unsigned __int64 v11; // rdx
  unsigned __int8 v12; // cl
  OfflineMapsTelemetry *v13; // rax
  unsigned int v15; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v16; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v17; // [rsp+40h] [rbp-C0h]
  __int64 v18; // [rsp+48h] [rbp-B8h]
  _BYTE v19[12]; // [rsp+50h] [rbp-B0h] BYREF
  int v20; // [rsp+5Ch] [rbp-A4h]
  __int64 (__fastcall *v21)(); // [rsp+60h] [rbp-A0h]
  int v22; // [rsp+68h] [rbp-98h]
  int v23; // [rsp+6Ch] [rbp-94h]
  _BYTE v24[4]; // [rsp+70h] [rbp-90h] BYREF
  int v25; // [rsp+74h] [rbp-8Ch]
  unsigned int v26; // [rsp+284h] [rbp+184h]
  unsigned int v27; // [rsp+6D0h] [rbp+5D0h]

  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,enum MapControl::DataOriginType>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,enum MapControl::DataOriginType>>>>>>(&v16);
  v15 = 0;
  memset_0(v24, 0, 0x670u);
  CriticalSectionWithConditionVariable::Lock((char *)this + 3400, v19);
  if ( !*((_BYTE *)this + 4312) )
    __int2c();
  CurrentLocation = MosStorageGetCurrentLocation((struct _STORAGE_DEVICE_DATA *)v24);
  if ( CurrentLocation < 0 )
    ZTraceReportIgnore(CurrentLocation, "ServiceManager::AttemptRepairMapData", 4051, this);
  MapsRepairAttempts = MosStorageGetMapsRepairAttempts(&v15);
  if ( MapsRepairAttempts < 0 )
  {
    v4 = 4055;
LABEL_15:
    v7 = MapsRepairAttempts;
    goto LABEL_16;
  }
  if ( v15 < 3 )
  {
    v5 = MosQueryPackages(&v16, *((unsigned int *)this + 1080));
    if ( v5 < 0 )
      ZTraceReportIgnore(v5, "ServiceManager::AttemptRepairMapData", 4061, this);
  }
  *((_DWORD *)this + 880) = 5;
  *((_DWORD *)this + 881) = 7;
  RelockableGate::Unlock((RelockableGate *)v19);
  v6 = ServiceManager::ClearMapData((RTL_CONDITION_VARIABLE *)this);
  RelockableGate::Relock((RelockableGate *)v19);
  if ( v6 >= 0 )
  {
    if ( v16 == v17 )
      goto LABEL_20;
    MapsRepairAttempts = PackageManager::AddPackagesToInstall((char *)this + 3568, (v17 - v16) >> 2, v16, 10);
    if ( MapsRepairAttempts >= 0 )
    {
      v21 =  ServiceManager::`vcall'{104,{flat}};
      v22 = 0;
      v23 = v20;
      Threadpool::QueueThis<ServiceManager>(*((PTP_CALLBACK_ENVIRON *)this + 424));
      goto LABEL_20;
    }
    v4 = 4083;
    goto LABEL_15;
  }
  v4 = 4075;
  v7 = v6;
LABEL_16:
  v8 = ZTraceReportPropagation(v7, "ServiceManager::AttemptRepairMapData", v4, this);
  v6 = v8;
  if ( v8 < 0 && !*((_DWORD *)this + 882) )
  {
    *((_DWORD *)this + 884) = 0;
    *((_DWORD *)this + 885) = v8;
    ServiceManager::FireOdmlStateChange(this);
  }
LABEL_20:
  *((_BYTE *)this + 4312) = 0;
  WakeAllConditionVariable((PCONDITION_VARIABLE)this + 430);
  v9 = v17 - v16;
  v10 = v25 != 0;
  if ( OfflineMapsTelemetry::IsEnabled(v12, v11) )
  {
    v13 = OfflineMapsTelemetry::Instance();
    OfflineMapsTelemetry::OfflineMapsAttemptRepair_(v13, v10, v26, v27, v9 >> 2, v6);
  }
  RelockableGate::~RelockableGate((RelockableGate *)v19);
  if ( v16 )
    std::_Deallocate<16>(v16, (v18 - v16) & 0xFFFFFFFFFFFFFFFCuLL);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180012f00  mov     [rsp-8+arg_8], rbx
0x180012f05  mov     [rsp-8+arg_10], rsi
0x180012f0a  push    rbp
0x180012f0b  push    rdi
0x180012f0c  push    r15
0x180012f0e  lea     rbp, [rsp-5F0h]
0x180012f16  sub     rsp, 6F0h
0x180012f1d  mov     rax, cs:__security_cookie
0x180012f24  xor     rax, rsp
0x180012f27  mov     [rbp+600h+var_20], rax
0x180012f2e  mov     rbx, rcx
0x180012f31  lea     rcx, [rsp+700h+var_6C8]
0x180012f36  call    ??$?0AEBV?$allocator@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>>>>>(std::allocator<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>> const &)
0x180012f3b  nop
0x180012f3c  mov     [rsp+700h+var_6D0], 0
0x180012f44  xor     edx, edx; Val
0x180012f46  mov     r8d, 670h; Size
0x180012f4c  lea     rcx, [rsp+700h+var_690]; void *
0x180012f51  call    memset_0
0x180012f56  lea     rsi, [rbx+0D48h]
0x180012f5d  lea     rdx, [rsp+700h+var_6B0]
0x180012f62  mov     rcx, rsi
0x180012f65  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x180012f6a  nop
0x180012f6b  cmp     byte ptr [rbx+10D8h], 0
0x180012f72  jnz     short loc_180012F76
0x180012f74  int     2Ch; Windows NT - assertion failure
0x180012f76  lea     rcx, [rsp+700h+var_690]
0x180012f7b  call    cs:__imp_?MosStorageGetCurrentLocation@@YAJPEAU_STORAGE_DEVICE_DATA@@@Z; MosStorageGetCurrentLocation(_STORAGE_DEVICE_DATA *)
0x180012f81  lea     r15, aServicemanager_73; "ServiceManager::AttemptRepairMapData"
0x180012f88  test    eax, eax
0x180012f8a  jns     short loc_180012FA0
0x180012f8c  mov     r9, rbx
0x180012f8f  mov     r8d, 0FD3h
0x180012f95  mov     rdx, r15
0x180012f98  mov     ecx, eax
0x180012f9a  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x180012fa0  lea     rcx, [rsp+700h+var_6D0]
0x180012fa5  call    cs:__imp_?MosStorageGetMapsRepairAttempts@@YAJPEAK@Z; MosStorageGetMapsRepairAttempts(ulong *)
0x180012fab  test    eax, eax
0x180012fad  jns     short loc_180012FBA
0x180012faf  mov     r8d, 0FD7h
0x180012fb5  jmp     loc_180013060
0x180012fba  cmp     [rsp+700h+var_6D0], 3
0x180012fbf  jnb     short loc_180012FEA
0x180012fc1  mov     edx, [rbx+10E0h]
0x180012fc7  lea     rcx, [rsp+700h+var_6C8]
0x180012fcc  call    cs:__imp_?MosQueryPackages@@YAJPEAV?$vector@IV?$allocator@I@std@@@std@@W4StackMode@@@Z; MosQueryPackages(std::vector<uint> *,StackMode)
0x180012fd2  test    eax, eax
0x180012fd4  jns     short loc_180012FEA
0x180012fd6  mov     r9, rbx
0x180012fd9  mov     r8d, 0FDDh
0x180012fdf  mov     rdx, r15
0x180012fe2  mov     ecx, eax
0x180012fe4  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x180012fea  mov     dword ptr [rbx+0DC0h], 5
0x180012ff4  mov     dword ptr [rbx+0DC4h], 7
0x180012ffe  lea     rcx, [rsp+700h+var_6B0]; this
0x180013003  call    ?Unlock@RelockableGate@@QEAAXXZ; RelockableGate::Unlock(void)
0x180013008  mov     rcx, rbx; this
0x18001300b  call    ?ClearMapData@ServiceManager@@AEAAJXZ; ServiceManager::ClearMapData(void)
0x180013010  mov     edi, eax
0x180013012  lea     rcx, [rsp+700h+var_6B0]; this
0x180013017  call    ?Relock@RelockableGate@@QEAAXXZ; RelockableGate::Relock(void)
0x18001301c  test    edi, edi
0x18001301e  jns     short loc_18001302A
0x180013020  mov     r8d, 0FEBh
0x180013026  mov     ecx, edi
0x180013028  jmp     short loc_180013062
0x18001302a  mov     rdx, [rsp+700h+var_6C0]
0x18001302f  mov     r8, [rsp+700h+var_6C8]
0x180013034  cmp     r8, rdx
0x180013037  jz      loc_1800130C7
0x18001303d  sub     rdx, r8
0x180013040  sar     rdx, 2
0x180013044  lea     rcx, [rbx+0DF0h]
0x18001304b  mov     r9d, 0Ah
0x180013051  call    ?AddPackagesToInstall@PackageManager@@QEAAJKPEBIW4MapsOperationTrigger@@@Z; PackageManager::AddPackagesToInstall(ulong,uint const *,MapsOperationTrigger)
0x180013056  test    eax, eax
0x180013058  jns     short loc_180013097
0x18001305a  mov     r8d, 0FF3h
0x180013060  mov     ecx, eax
0x180013062  mov     r9, rbx
0x180013065  mov     rdx, r15
0x180013068  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001306e  mov     edi, eax
0x180013070  test    eax, eax
0x180013072  jns     short loc_1800130C7
0x180013074  cmp     dword ptr [rbx+0DC8h], 0
0x18001307b  jnz     short loc_1800130C7
0x18001307d  mov     dword ptr [rbx+0DD0h], 0
0x180013087  mov     [rbx+0DD4h], eax
0x18001308d  mov     rcx, rbx; this
0x180013090  call    ?FireOdmlStateChange@ServiceManager@@AEAAXXZ; ServiceManager::FireOdmlStateChange(void)
0x180013095  jmp     short loc_1800130C7
0x180013097  lea     rax, ??_9ServiceManager@@$BGI@AA; [thunk]: ServiceManager::`vcall'{104,{flat}}
0x18001309e  mov     [rsp+700h+var_6A0], rax
0x1800130a3  mov     [rsp+700h+var_698], 0
0x1800130ab  mov     eax, [rsp+700h+var_6A4]
0x1800130af  mov     [rsp+700h+var_694], eax
0x1800130b3  lea     r8, [rsp+700h+var_6A0]
0x1800130b8  mov     rdx, rbx
0x1800130bb  mov     rcx, [rbx+0D40h]; pcbe
0x1800130c2  call    ??$QueueThis@VServiceManager@@@Threadpool@@QEAAXPEAVServiceManager@@P81@EAAJXZ@Z; Threadpool::QueueThis<ServiceManager>(ServiceManager *,long (ServiceManager::*)(void))
0x1800130c7  mov     byte ptr [rbx+10D8h], 0
0x1800130ce  lea     rcx, [rsi+28h]; ConditionVariable
0x1800130d2  call    cs:__imp_WakeAllConditionVariable
0x1800130d8  mov     rbx, [rsp+700h+var_6C0]
0x1800130dd  sub     rbx, [rsp+700h+var_6C8]
0x1800130e2  cmp     [rsp+700h+var_68C], 0
0x1800130e7  setnz   sil
0x1800130eb  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x1800130f0  test    al, al
0x1800130f2  jz      short loc_18001311F
0x1800130f4  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x1800130f9  sar     rbx, 2
0x1800130fd  mov     [rsp+700h+var_6D8], edi; int
0x180013101  mov     [rsp+700h+var_6E0], ebx; unsigned int
0x180013105  mov     r9d, [rbp+600h+var_30]; unsigned int
0x18001310c  mov     r8d, [rbp+600h+var_47C]; unsigned int
0x180013113  mov     dl, sil; bool
0x180013116  mov     rcx, rax; this
0x180013119  call    ?OfflineMapsAttemptRepair_@OfflineMapsTelemetry@@QEAAX_NIIKJ@Z; OfflineMapsTelemetry::OfflineMapsAttemptRepair_(bool,uint,uint,ulong,long)
0x18001311e  nop
0x18001311f  lea     rcx, [rsp+700h+var_6B0]; this
0x180013124  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x180013129  nop
0x18001312a  mov     rcx, [rsp+700h+var_6C8]
0x18001312f  test    rcx, rcx
0x180013132  jz      short loc_180013145
0x180013134  mov     rdx, [rsp+700h+var_6B8]
0x180013139  sub     rdx, rcx
0x18001313c  and     rdx, 0FFFFFFFFFFFFFFFCh
0x180013140  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180013145  mov     eax, edi
0x180013147  mov     rcx, [rbp+600h+var_20]
0x18001314e  xor     rcx, rsp; StackCookie
0x180013151  call    __security_check_cookie
0x180013156  lea     r11, [rsp+700h+var_10]
0x18001315e  mov     rbx, [r11+28h]
0x180013162  mov     rsi, [r11+30h]
0x180013166  mov     rsp, r11
0x180013169  pop     r15
0x18001316b  pop     rdi
0x18001316c  pop     rbp
0x18001316d  retn
```
