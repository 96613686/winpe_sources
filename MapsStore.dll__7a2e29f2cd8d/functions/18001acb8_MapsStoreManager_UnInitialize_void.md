# MapsStoreManager::UnInitialize(void)

- ea: `0x18001acb8`
- end: `0x18001aef4`
- name: `?UnInitialize@MapsStoreManager@@QEAAJXZ`
- size: `572`
- prototype: `__int64 __fastcall(MapsStoreManager *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180011b00`

## callees

- `0x18000d460`
- `0x1800125bc`
- `0x180012890`
- `0x180017d20`
- `0x180017d4c`
- `0x1800182cc`
- `0x180019f3c`
- `0x18001ac70`
- `0x18001acb8`
- `0x18001af80`
- `0x18001b9e0`
- `0x18001d8c4`
- `0x18001d9ac`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ad23`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ad54`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ae5d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ae9f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ad23`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ad54`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ae5d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ae9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ad72`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ae92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001aece`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001aedf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ad72`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ae92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001aece`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001aedf`
- `mapsbtsvc!MapsBackgroundTransferService_FreeJob` at `0x18001ad62`
- `mapsbtsvc!MapsBackgroundTransferService_FreeJob` at `0x18001ad62`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001ace4`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001ad0d`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001ace4`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001ad0d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MapsStoreManager::UnInitialize(std::_Ref_count_base **this)
{
  int v2; // eax
  int v3; // eax
  std::_Ref_count_base *v4; // rcx
  std::_Ref_count_base *v5; // rdx
  std::_Ref_count_base *v6; // rcx
  std::_Ref_count_base *v7; // rdx
  std::_Ref_count_base *v8; // rcx
  MapsStorePal::MapsStoreLocalSettingsInitializer *v9; // rdi
  MapsStorePal::MapsStorePerformanceTracerInitializer *v10; // rcx

  v2 = MapsStoreManager::SuspendInstallation((MapsStoreManager *)this);
  if ( v2 < 0 )
    ZTraceReportIgnore(v2, "MapsStoreManager::UnInitialize", 207, this);
  v3 = MapsStoreManager::WaitStoreOperation((MapsStoreManager *)this, 0x7530u);
  if ( v3 < 0 )
    ZTraceReportIgnore(v3, "MapsStoreManager::UnInitialize", 208, this);
  MapsStoreManager::CancelGridRequestsAndWait((MapsStoreManager *)this);
  EnterCriticalSection((LPCRITICAL_SECTION)this);
  v4 = this[46];
  if ( v4 )
    (*(void (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v4 + 24LL))(v4);
  EnterCriticalSection(&stru_1800E49F0);
  MapsBackgroundTransferService_FreeJob((void *)qword_1800E4A18);
  qword_1800E4A18 = 0;
  LeaveCriticalSection(&stru_1800E49F0);
  v5 = this[18];
  this[18] = 0;
  if ( v5 )
    std::default_delete<MapControl::RegionManager>::operator()();
  std::unique_ptr<MapRegionNode>::reset(this + 73, 0);
  std::shared_ptr<MapControl::GenerationsManager>::reset(this + 71);
  std::shared_ptr<MapControl::GenerationsManager>::reset(this + 40);
  std::shared_ptr<MapControl::GenerationsManager>::reset(this + 46);
  this[16] = 0;
  v6 = this[17];
  this[17] = 0;
  if ( v6 )
    std::_Ref_count_base::_Decref(v6);
  std::shared_ptr<MapControl::GenerationsManager>::reset(this + 42);
  v7 = this[14];
  this[14] = 0;
  if ( v7 )
    std::default_delete<Pal::NetworkRequestImpl>::operator()();
  this[78] = 0;
  v8 = this[79];
  this[79] = 0;
  if ( v8 )
    std::_Ref_count_base::_Decref(v8);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 15);
  this[55] = 0;
  this[56] = 0;
  this[57] = 0;
  this[58] = 0;
  this[59] = 0;
  *((_DWORD *)this + 121) = 0;
  if ( *((_BYTE *)this + 41) )
  {
    EnterCriticalSection(&Pal::PrivateSingleton<MapsStorePal::MapsStoreLocalSettingsInitializer,>::sInstanceMutex);
    if ( !--Pal::PrivateSingleton<MapsStorePal::MapsStoreLocalSettingsInitializer,>::sInstanceCount )
    {
      v9 = (MapsStorePal::MapsStoreLocalSettingsInitializer *)_InterlockedExchange64(
                                                                &Pal::PrivateSingleton<MapsStorePal::MapsStoreLocalSettingsInitializer,>::sInstance,
                                                                0);
      if ( v9 )
      {
        MapsStorePal::MapsStoreLocalSettingsInitializer::~MapsStoreLocalSettingsInitializer(v9);
        operator delete(v9);
      }
    }
    LeaveCriticalSection(&Pal::PrivateSingleton<MapsStorePal::MapsStoreLocalSettingsInitializer,>::sInstanceMutex);
    EnterCriticalSection(&Pal::PrivateSingleton<MapsStorePal::MapsStorePerformanceTracerInitializer,>::sInstanceMutex);
    if ( !--Pal::PrivateSingleton<MapsStorePal::MapsStorePerformanceTracerInitializer,>::sInstanceCount )
    {
      v10 = (MapsStorePal::MapsStorePerformanceTracerInitializer *)_InterlockedExchange64(
                                                                     &Pal::PrivateSingleton<MapsStorePal::MapsStorePerformanceTracerInitializer,>::sInstance,
                                                                     0);
      if ( v10 )
        MapsStorePal::MapsStorePerformanceTracerInitializer::`vector deleting destructor'(v10, 1u);
    }
    LeaveCriticalSection(&Pal::PrivateSingleton<MapsStorePal::MapsStorePerformanceTracerInitializer,>::sInstanceMutex);
    *((_BYTE *)this + 41) = 0;
  }
  *((_BYTE *)this + 40) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)this);
  return 0;
}

```

## disassembly

```asm
0x18001acb8  mov     [rsp+arg_10], rbx
0x18001acbd  push    rbp
0x18001acbe  push    rsi
0x18001acbf  push    rdi
0x18001acc0  sub     rsp, 20h
0x18001acc4  mov     rbx, rcx
0x18001acc7  call    ?SuspendInstallation@MapsStoreManager@@QEAAJXZ; MapsStoreManager::SuspendInstallation(void)
0x18001accc  xor     ebp, ebp
0x18001acce  test    eax, eax
0x18001acd0  jns     short loc_18001ACEA
0x18001acd2  mov     r9, rbx
0x18001acd5  mov     r8d, 0CFh
0x18001acdb  lea     rdx, aMapsstoremanag_1; "MapsStoreManager::UnInitialize"
0x18001ace2  mov     ecx, eax
0x18001ace4  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18001acea  mov     edx, 7530h; unsigned int
0x18001acef  mov     rcx, rbx; this
0x18001acf2  call    ?WaitStoreOperation@MapsStoreManager@@QEAAJK@Z; MapsStoreManager::WaitStoreOperation(ulong)
0x18001acf7  test    eax, eax
0x18001acf9  jns     short loc_18001AD13
0x18001acfb  mov     r9, rbx
0x18001acfe  mov     r8d, 0D0h
0x18001ad04  lea     rdx, aMapsstoremanag_1; "MapsStoreManager::UnInitialize"
0x18001ad0b  mov     ecx, eax
0x18001ad0d  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18001ad13  mov     rcx, rbx; this
0x18001ad16  call    ?CancelGridRequestsAndWait@MapsStoreManager@@AEAAXXZ; MapsStoreManager::CancelGridRequestsAndWait(void)
0x18001ad1b  mov     [rsp+38h+arg_0], rbx
0x18001ad20  mov     rcx, rbx; lpCriticalSection
0x18001ad23  call    cs:__imp_EnterCriticalSection
0x18001ad29  nop
0x18001ad2a  lea     rdi, [rbx+170h]
0x18001ad31  mov     rcx, [rdi]
0x18001ad34  test    rcx, rcx
0x18001ad37  jz      short loc_18001AD45
0x18001ad39  mov     rax, [rcx]
0x18001ad3c  mov     rax, [rax+18h]
0x18001ad40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad45  lea     rsi, stru_1800E49F0
0x18001ad4c  mov     [rsp+38h+arg_8], rsi
0x18001ad51  mov     rcx, rsi; lpCriticalSection
0x18001ad54  call    cs:__imp_EnterCriticalSection
0x18001ad5a  nop
0x18001ad5b  mov     rcx, cs:qword_1800E4A18
0x18001ad62  call    cs:__imp_?MapsBackgroundTransferService_FreeJob@@YAXPEAX@Z; MapsBackgroundTransferService_FreeJob(void *)
0x18001ad68  mov     cs:qword_1800E4A18, rbp
0x18001ad6f  mov     rcx, rsi; lpCriticalSection
0x18001ad72  call    cs:__imp_LeaveCriticalSection
0x18001ad78  mov     rdx, [rbx+90h]
0x18001ad7f  mov     [rbx+90h], rbp
0x18001ad86  test    rdx, rdx
0x18001ad89  jz      short loc_18001AD90
0x18001ad8b  call    ??R?$default_delete@VRegionManager@MapControl@@@std@@QEBAXPEAVRegionManager@MapControl@@@Z; std::default_delete<MapControl::RegionManager>::operator()(MapControl::RegionManager *)
0x18001ad90  lea     rcx, [rbx+248h]
0x18001ad97  xor     edx, edx
0x18001ad99  call    ?reset@?$unique_ptr@VMapRegionNode@@U?$default_delete@VMapRegionNode@@@std@@@std@@QEAAXPEAVMapRegionNode@@@Z; std::unique_ptr<MapRegionNode>::reset(MapRegionNode *)
0x18001ad9e  lea     rcx, [rbx+238h]
0x18001ada5  call    ?reset@?$shared_ptr@VGenerationsManager@MapControl@@@std@@QEAAXXZ; std::shared_ptr<MapControl::GenerationsManager>::reset(void)
0x18001adaa  lea     rcx, [rbx+140h]
0x18001adb1  call    ?reset@?$shared_ptr@VGenerationsManager@MapControl@@@std@@QEAAXXZ; std::shared_ptr<MapControl::GenerationsManager>::reset(void)
0x18001adb6  mov     rcx, rdi
0x18001adb9  call    ?reset@?$shared_ptr@VGenerationsManager@MapControl@@@std@@QEAAXXZ; std::shared_ptr<MapControl::GenerationsManager>::reset(void)
0x18001adbe  mov     [rbx+80h], rbp
0x18001adc5  mov     rcx, [rbx+88h]; this
0x18001adcc  mov     [rbx+88h], rbp
0x18001add3  test    rcx, rcx
0x18001add6  jz      short loc_18001ADDD
0x18001add8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001addd  lea     rcx, [rbx+150h]
0x18001ade4  call    ?reset@?$shared_ptr@VGenerationsManager@MapControl@@@std@@QEAAXXZ; std::shared_ptr<MapControl::GenerationsManager>::reset(void)
0x18001ade9  mov     rdx, [rbx+70h]
0x18001aded  mov     [rbx+70h], rbp
0x18001adf1  test    rdx, rdx
0x18001adf4  jz      short loc_18001ADFB
0x18001adf6  call    ??R?$default_delete@VNetworkRequestImpl@Pal@@@std@@QEBAXPEAVNetworkRequestImpl@Pal@@@Z; std::default_delete<Pal::NetworkRequestImpl>::operator()(Pal::NetworkRequestImpl *)
0x18001adfb  mov     [rbx+270h], rbp
0x18001ae02  mov     rcx, [rbx+278h]; this
0x18001ae09  mov     [rbx+278h], rbp
0x18001ae10  test    rcx, rcx
0x18001ae13  jz      short loc_18001AE1A
0x18001ae15  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001ae1a  lea     rcx, [rbx+78h]
0x18001ae1e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ae23  mov     [rbx+1B8h], rbp
0x18001ae2a  mov     [rbx+1C0h], rbp
0x18001ae31  mov     [rbx+1C8h], rbp
0x18001ae38  mov     [rbx+1D0h], rbp
0x18001ae3f  mov     [rbx+1D8h], rbp
0x18001ae46  mov     [rbx+1E4h], ebp
0x18001ae4c  cmp     [rbx+29h], bpl
0x18001ae50  jz      loc_18001AED8
0x18001ae56  lea     rcx, ?sInstanceMutex@?$PrivateSingleton@VMapsStoreLocalSettingsInitializer@MapsStorePal@@$$V@Pal@@0VMutex@2@A; lpCriticalSection
0x18001ae5d  call    cs:__imp_EnterCriticalSection
0x18001ae63  sub     cs:?sInstanceCount@?$PrivateSingleton@VMapsStoreLocalSettingsInitializer@MapsStorePal@@$$V@Pal@@0HA, 1; int Pal::PrivateSingleton<MapsStorePal::MapsStoreLocalSettingsInitializer,>::sInstanceCount
0x18001ae6a  jnz     short loc_18001AE8B
0x18001ae6c  mov     rdi, rbp
0x18001ae6f  xchg    rdi, cs:?sInstance@?$PrivateSingleton@VMapsStoreLocalSettingsInitializer@MapsStorePal@@$$V@Pal@@0U?$atomic@PEAVMapsStoreLocalSettingsInitializer@MapsStorePal@@@std@@A; std::atomic<MapsStorePal::MapsStoreLocalSettingsInitializer *> Pal::PrivateSingleton<MapsStorePal::MapsStoreLocalSettingsInitializer,>::sInstance
0x18001ae76  test    rdi, rdi
0x18001ae79  jz      short loc_18001AE8B
0x18001ae7b  mov     rcx, rdi; this
0x18001ae7e  call    ??1MapsStoreLocalSettingsInitializer@MapsStorePal@@QEAA@XZ; MapsStorePal::MapsStoreLocalSettingsInitializer::~MapsStoreLocalSettingsInitializer(void)
0x18001ae83  mov     rcx, rdi; Block
0x18001ae86  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ae8b  lea     rcx, ?sInstanceMutex@?$PrivateSingleton@VMapsStoreLocalSettingsInitializer@MapsStorePal@@$$V@Pal@@0VMutex@2@A; lpCriticalSection
0x18001ae92  call    cs:__imp_LeaveCriticalSection
0x18001ae98  lea     rcx, ?sInstanceMutex@?$PrivateSingleton@VMapsStorePerformanceTracerInitializer@MapsStorePal@@$$V@Pal@@0VMutex@2@A; lpCriticalSection
0x18001ae9f  call    cs:__imp_EnterCriticalSection
0x18001aea5  sub     cs:?sInstanceCount@?$PrivateSingleton@VMapsStorePerformanceTracerInitializer@MapsStorePal@@$$V@Pal@@0HA, 1; int Pal::PrivateSingleton<MapsStorePal::MapsStorePerformanceTracerInitializer,>::sInstanceCount
0x18001aeac  jnz     short loc_18001AEC7
0x18001aeae  mov     rcx, rbp
0x18001aeb1  xchg    rcx, cs:?sInstance@?$PrivateSingleton@VMapsStorePerformanceTracerInitializer@MapsStorePal@@$$V@Pal@@0U?$atomic@PEAVMapsStorePerformanceTracerInitializer@MapsStorePal@@@std@@A; this
0x18001aeb8  test    rcx, rcx
0x18001aebb  jz      short loc_18001AEC7
0x18001aebd  mov     edx, 1; unsigned int
0x18001aec2  call    ??_EMapsStorePerformanceTracerInitializer@MapsStorePal@@UEAAPEAXI@Z; MapsStorePal::MapsStorePerformanceTracerInitializer::`vector deleting destructor'(uint)
0x18001aec7  lea     rcx, ?sInstanceMutex@?$PrivateSingleton@VMapsStorePerformanceTracerInitializer@MapsStorePal@@$$V@Pal@@0VMutex@2@A; lpCriticalSection
0x18001aece  call    cs:__imp_LeaveCriticalSection
0x18001aed4  mov     [rbx+29h], bpl
0x18001aed8  mov     [rbx+28h], bpl
0x18001aedc  mov     rcx, rbx; lpCriticalSection
0x18001aedf  call    cs:__imp_LeaveCriticalSection
0x18001aee5  xor     eax, eax
0x18001aee7  mov     rbx, [rsp+38h+arg_10]
0x18001aeec  add     rsp, 20h
0x18001aef0  pop     rdi
0x18001aef1  pop     rsi
0x18001aef2  pop     rbp
0x18001aef3  retn
```
