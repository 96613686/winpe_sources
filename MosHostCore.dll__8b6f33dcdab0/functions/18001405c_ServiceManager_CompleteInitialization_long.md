# ServiceManager::CompleteInitialization(long)

- ea: `0x18001405c`
- end: `0x1800142bd`
- name: `?CompleteInitialization@ServiceManager@@QEAAXJ@Z`
- size: `609`
- prototype: `void __fastcall(ServiceManager *__hidden this, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180011420`

## callees

- `0x180003410`
- `0x180003f7c`
- `0x180009c04`
- `0x180009d0c`
- `0x180009db4`
- `0x18001405c`
- `0x180014c00`
- `0x180015ed0`
- `0x18001a088`
- `0x18001b1a4`
- `0x18001b610`
- `0x18001db8c`
- `0x18001eec4`
- `0x1800228ec`
- `0x1800229b8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180014284`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180014284`
- `MosStorage!MosStorageGetCurrentLocation` at `0x1800140b4`
- `MosStorage!MosStorageGetCurrentLocation` at `0x1800140b4`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x1800140d3`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001425a`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001427a`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x1800140d3`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001425a`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001427a`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180014165`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180014165`
- `ZTrace_Maps!ZTraceHelper` at `0x180014145`
- `ZTrace_Maps!ZTraceHelper` at `0x1800141c1`
- `ZTrace_Maps!ZTraceHelper` at `0x180014202`
- `ZTrace_Maps!ZTraceHelper` at `0x180014145`
- `ZTrace_Maps!ZTraceHelper` at `0x1800141c1`
- `ZTrace_Maps!ZTraceHelper` at `0x180014202`

## string_xrefs

- `0x1800140ba`: `ServiceManager::CompleteInitialization`
- `0x180014133`: `[MosHost] Service - Startup - initializing ODML complete`
- `0x1800141ad`: `[MosHost] Service - Startup - Update is required`
- `0x1800141ee`: `[MosHost] Service - Startup - initializing ODML failed`

## pseudocode

```c
void __fastcall ServiceManager::CompleteInitialization(ServiceManager *this, int a2)
{
  RTL_CONDITION_VARIABLE *v4; // rbp
  int CurrentLocation; // eax
  unsigned __int64 v6; // rdx
  unsigned __int8 v7; // cl
  bool v8; // si
  OfflineMapsTelemetry *v9; // rax
  int v10; // eax
  int v11; // r8d
  int v12; // eax
  int updated; // eax
  _BYTE v14[16]; // [rsp+30h] [rbp-6A8h] BYREF
  _BYTE v15[4]; // [rsp+40h] [rbp-698h] BYREF
  int v16; // [rsp+44h] [rbp-694h]
  unsigned int v17; // [rsp+254h] [rbp-484h]
  unsigned int v18; // [rsp+6A0h] [rbp-38h]

  v4 = (RTL_CONDITION_VARIABLE *)((char *)this + 3400);
  CriticalSectionWithConditionVariable::Lock((char *)this + 3400, v14);
  memset_0(v15, 0, 0x670u);
  CurrentLocation = MosStorageGetCurrentLocation((struct _STORAGE_DEVICE_DATA *)v15);
  if ( CurrentLocation < 0 )
    ZTraceReportIgnore(CurrentLocation, "ServiceManager::CompleteInitialization", 1964, this);
  v8 = v16 != 0;
  if ( OfflineMapsTelemetry::IsEnabled(v7, v6) )
  {
    v9 = OfflineMapsTelemetry::Instance();
    OfflineMapsTelemetry::OfflineMapLoaderInitialized_(v9, v8, v17, v18, a2);
  }
  ServiceWatchdog::Stop((ServiceManager *)((char *)this + 3944));
  if ( a2 < 0 )
  {
    if ( a2 == -2080374762 )
    {
      *((_DWORD *)this + 882) = 4;
      ZTraceHelper(
        2,
        "ServiceManager::CompleteInitialization",
        1988,
        this,
        "[MosHost] Service - Startup - Update is required");
      v10 = ServiceManager::RegisterTransferCallbacks(this);
      if ( v10 < 0 )
      {
        v11 = 1992;
        goto LABEL_8;
      }
      *((_QWORD *)this + 442) = 13;
    }
    else
    {
      *((_DWORD *)this + 882) = 2;
      ZTraceHelper(
        0,
        "ServiceManager::CompleteInitialization",
        1999,
        this,
        "[MosHost] Service - Startup - initializing ODML failed");
      *((_DWORD *)this + 884) = 0;
      *((_DWORD *)this + 885) = a2;
    }
    ServiceManager::FireOdmlStateChange(this);
    goto LABEL_17;
  }
  *((_DWORD *)this + 882) = 5;
  ZTraceHelper(
    5,
    "ServiceManager::CompleteInitialization",
    1973,
    this,
    "[MosHost] Service - Startup - initializing ODML complete");
  v10 = ServiceManager::RegisterTransferCallbacks(this);
  if ( v10 >= 0 )
  {
    *((_QWORD *)this + 442) = 1;
    ServiceManager::FireOdmlStateChange(this);
    v10 = ServiceManager::ProcessStartupOperations(this);
    if ( v10 >= 0 )
      goto LABEL_17;
    v11 = 1983;
  }
  else
  {
    v11 = 1977;
  }
LABEL_8:
  ZTraceReportPropagation(v10, "ServiceManager::CompleteInitialization", v11, this);
LABEL_17:
  if ( (unsigned __int8)ClientsTracker::HasClientsOf((char *)this + 3816, 2) )
  {
    if ( !*((_DWORD *)this + 881) )
    {
      v12 = ServiceManager::DetachClient((__int64)this, 2u, 0);
      if ( v12 < 0 )
        ZTraceReportIgnore(v12, "ServiceManager::CompleteInitialization", 2009, this);
    }
  }
  updated = ServiceManager::UpdateTransferPolicies(this);
  if ( updated < 0 )
    ZTraceReportIgnore(updated, "ServiceManager::CompleteInitialization", 2013, this);
  WakeAllConditionVariable(v4 + 5);
  RelockableGate::~RelockableGate((RelockableGate *)v14);
}

```

## disassembly

```asm
0x18001405c  mov     [rsp+arg_8], rbx
0x180014061  mov     [rsp+arg_10], rbp
0x180014066  push    rsi
0x180014067  push    rdi
0x180014068  push    r15
0x18001406a  sub     rsp, 6C0h
0x180014071  mov     rax, cs:__security_cookie
0x180014078  xor     rax, rsp
0x18001407b  mov     [rsp+6D8h+var_28], rax
0x180014083  mov     edi, edx
0x180014085  mov     rbx, rcx
0x180014088  lea     rbp, [rcx+0D48h]
0x18001408f  lea     rdx, [rsp+6D8h+var_6A8]
0x180014094  mov     rcx, rbp
0x180014097  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x18001409c  nop
0x18001409d  xor     edx, edx; Val
0x18001409f  mov     r8d, 670h; Size
0x1800140a5  lea     rcx, [rsp+6D8h+var_698]; void *
0x1800140aa  call    memset_0
0x1800140af  lea     rcx, [rsp+6D8h+var_698]
0x1800140b4  call    cs:__imp_?MosStorageGetCurrentLocation@@YAJPEAU_STORAGE_DEVICE_DATA@@@Z; MosStorageGetCurrentLocation(_STORAGE_DEVICE_DATA *)
0x1800140ba  lea     r15, aServicemanager_71; "ServiceManager::CompleteInitialization"
0x1800140c1  test    eax, eax
0x1800140c3  jns     short loc_1800140D9
0x1800140c5  mov     r9, rbx
0x1800140c8  mov     r8d, 7ACh
0x1800140ce  mov     rdx, r15
0x1800140d1  mov     ecx, eax
0x1800140d3  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x1800140d9  cmp     [rsp+6D8h+var_694], 0
0x1800140de  setnz   sil
0x1800140e2  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x1800140e7  test    al, al
0x1800140e9  jz      short loc_18001410F
0x1800140eb  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x1800140f0  mov     [rsp+6D8h+var_6B8], edi; int
0x1800140f4  mov     r9d, [rsp+6D8h+var_38]; unsigned int
0x1800140fc  mov     r8d, [rsp+6D8h+var_484]; unsigned int
0x180014104  mov     dl, sil; bool
0x180014107  mov     rcx, rax; this
0x18001410a  call    ?OfflineMapLoaderInitialized_@OfflineMapsTelemetry@@QEAAX_NIIJ@Z; OfflineMapsTelemetry::OfflineMapLoaderInitialized_(bool,uint,uint,long)
0x18001410f  lea     rcx, [rbx+0F68h]; this
0x180014116  call    ?Stop@ServiceWatchdog@@QEAAXXZ; ServiceWatchdog::Stop(void)
0x18001411b  mov     esi, 2
0x180014120  mov     r9, rbx
0x180014123  mov     rdx, r15
0x180014126  test    edi, edi
0x180014128  js      short loc_18001419B
0x18001412a  lea     ecx, [rsi+3]
0x18001412d  mov     [rbx+0DC8h], ecx
0x180014133  lea     rax, aMoshostService_9; "[MosHost] Service - Startup - initializ"...
0x18001413a  mov     qword ptr [rsp+6D8h+var_6B8], rax
0x18001413f  mov     r8d, 7B5h
0x180014145  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x18001414b  mov     rcx, rbx; this
0x18001414e  call    ?RegisterTransferCallbacks@ServiceManager@@AEAAJXZ; ServiceManager::RegisterTransferCallbacks(void)
0x180014153  test    eax, eax
0x180014155  jns     short loc_180014170
0x180014157  mov     r8d, 7B9h
0x18001415d  mov     r9, rbx
0x180014160  mov     rdx, r15
0x180014163  mov     ecx, eax
0x180014165  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001416b  jmp     loc_180014220
0x180014170  mov     qword ptr [rbx+0DD0h], 1
0x18001417b  mov     rcx, rbx; this
0x18001417e  call    ?FireOdmlStateChange@ServiceManager@@AEAAXXZ; ServiceManager::FireOdmlStateChange(void)
0x180014183  mov     rcx, rbx; this
0x180014186  call    ?ProcessStartupOperations@ServiceManager@@AEAAJXZ; ServiceManager::ProcessStartupOperations(void)
0x18001418b  test    eax, eax
0x18001418d  jns     loc_180014220
0x180014193  mov     r8d, 7BFh
0x180014199  jmp     short loc_18001415D
0x18001419b  cmp     edi, 84000016h
0x1800141a1  jnz     short loc_1800141E8
0x1800141a3  mov     dword ptr [rbx+0DC8h], 4
0x1800141ad  lea     rax, aMoshostService_6; "[MosHost] Service - Startup - Update is"...
0x1800141b4  mov     qword ptr [rsp+6D8h+var_6B8], rax
0x1800141b9  mov     r8d, 7C4h
0x1800141bf  mov     ecx, esi
0x1800141c1  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x1800141c7  mov     rcx, rbx; this
0x1800141ca  call    ?RegisterTransferCallbacks@ServiceManager@@AEAAJXZ; ServiceManager::RegisterTransferCallbacks(void)
0x1800141cf  test    eax, eax
0x1800141d1  jns     short loc_1800141DB
0x1800141d3  mov     r8d, 7C8h
0x1800141d9  jmp     short loc_18001415D
0x1800141db  mov     qword ptr [rbx+0DD0h], 0Dh
0x1800141e6  jmp     short loc_180014218
0x1800141e8  mov     [rbx+0DC8h], esi
0x1800141ee  lea     rax, aMoshostService_0; "[MosHost] Service - Startup - initializ"...
0x1800141f5  mov     qword ptr [rsp+6D8h+var_6B8], rax
0x1800141fa  mov     r8d, 7CFh
0x180014200  xor     ecx, ecx
0x180014202  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x180014208  mov     dword ptr [rbx+0DD0h], 0
0x180014212  mov     [rbx+0DD4h], edi
0x180014218  mov     rcx, rbx; this
0x18001421b  call    ?FireOdmlStateChange@ServiceManager@@AEAAXXZ; ServiceManager::FireOdmlStateChange(void)
0x180014220  lea     rcx, [rbx+0EE8h]
0x180014227  mov     edx, esi
0x180014229  call    ?HasClientsOf@ClientsTracker@@QEAA_NW4MapsClientType@@@Z; ClientsTracker::HasClientsOf(MapsClientType)
0x18001422e  test    al, al
0x180014230  jz      short loc_180014260
0x180014232  cmp     dword ptr [rbx+0DC4h], 0
0x180014239  jnz     short loc_180014260
0x18001423b  xor     r8d, r8d
0x18001423e  mov     edx, esi
0x180014240  mov     rcx, rbx
0x180014243  call    ?DetachClient@ServiceManager@@UEAAJW4MapsClientType@@K@Z; ServiceManager::DetachClient(MapsClientType,ulong)
0x180014248  test    eax, eax
0x18001424a  jns     short loc_180014260
0x18001424c  mov     r9, rbx
0x18001424f  mov     r8d, 7D9h
0x180014255  mov     rdx, r15
0x180014258  mov     ecx, eax
0x18001425a  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x180014260  mov     rcx, rbx; this
0x180014263  call    ?UpdateTransferPolicies@ServiceManager@@AEAAJXZ; ServiceManager::UpdateTransferPolicies(void)
0x180014268  test    eax, eax
0x18001426a  jns     short loc_180014280
0x18001426c  mov     r9, rbx
0x18001426f  mov     r8d, 7DDh
0x180014275  mov     rdx, r15
0x180014278  mov     ecx, eax
0x18001427a  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x180014280  lea     rcx, [rbp+28h]; ConditionVariable
0x180014284  call    cs:__imp_WakeAllConditionVariable
0x18001428a  nop
0x18001428b  lea     rcx, [rsp+6D8h+var_6A8]; this
0x180014290  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x180014295  mov     rcx, [rsp+6D8h+var_28]
0x18001429d  xor     rcx, rsp; StackCookie
0x1800142a0  call    __security_check_cookie
0x1800142a5  lea     r11, [rsp+6D8h+var_18]
0x1800142ad  mov     rbx, [r11+28h]
0x1800142b1  mov     rbp, [r11+30h]
0x1800142b5  mov     rsp, r11
0x1800142b8  pop     r15
0x1800142ba  pop     rdi
0x1800142bb  pop     rsi
0x1800142bc  retn
```
