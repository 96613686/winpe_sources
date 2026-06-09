# SystemSettings::BatteryUsageHandlers::CBatteryGraphSingleton2::~CBatteryGraphSingleton2(void)

- ea: `0x1800242d4`
- end: `0x18002438f`
- name: `??1CBatteryGraphSingleton2@BatteryUsageHandlers@SystemSettings@@UEAA@XZ`
- size: `187`
- prototype: `void __fastcall(SystemSettings::BatteryUsageHandlers::CBatteryGraphSingleton2 *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x1800245c0`
- `0x180059cd0`

## callees

- `0x18000d4dc`
- `0x18001e570`
- `0x180024020`
- `0x180024078`
- `0x1800240d0`
- `0x180024128`
- `0x1800242d4`
- `0x18002450c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002437c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002437c`

## pseudocode

```c
void __fastcall SystemSettings::BatteryUsageHandlers::CBatteryGraphSingleton2::~CBatteryGraphSingleton2(
        SystemSettings::BatteryUsageHandlers::CBatteryGraphSingleton2 *this)
{
  __int64 v2; // rdx
  __int64 v3; // rdx
  __int64 v4; // rdx
  void *v5; // rcx

  *(_QWORD *)this = &SystemSettings::BatteryUsageHandlers::CBatteryGraphSingleton2::`vftable';
  std::thread::~thread((SystemSettings::BatteryUsageHandlers::CBatteryGraphSingleton2 *)((char *)this + 832));
  SrumCache<EnergyUsageRow>::~SrumCache<EnergyUsageRow>((__int64)this + 616, v2);
  std::vector<EnergyUsageBucket>::_Tidy((char *)this + 592);
  SrumCache<EnergyEstimationRow>::~SrumCache<EnergyEstimationRow>((__int64)this + 448, v3);
  SrumCache<BatteryDrainRow>::~SrumCache<BatteryDrainRow>((__int64)this + 312, v4);
  v5 = (void *)*((_QWORD *)this + 35);
  if ( v5 )
  {
    std::_Deallocate<16>(v5, (struct std::nothrow_t *)(8 * ((__int64)(*((_QWORD *)this + 37) - (_QWORD)v5) >> 3)));
    *((_QWORD *)this + 35) = 0;
    *((_QWORD *)this + 36) = 0;
    *((_QWORD *)this + 37) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::~CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>((__int64)this);
}

```

## disassembly

```asm
0x1800242d4  push    rbx
0x1800242d6  sub     rsp, 20h
0x1800242da  mov     rbx, rcx
0x1800242dd  lea     rax, ??_7CBatteryGraphSingleton2@BatteryUsageHandlers@SystemSettings@@6B@; const SystemSettings::BatteryUsageHandlers::CBatteryGraphSingleton2::`vftable'
0x1800242e4  mov     [rcx], rax
0x1800242e7  add     rcx, 340h; this
0x1800242ee  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x1800242f3  lea     rcx, [rbx+268h]
0x1800242fa  call    ??1?$SrumCache@UEnergyUsageRow@@@@QEAA@XZ; SrumCache<EnergyUsageRow>::~SrumCache<EnergyUsageRow>(void)
0x1800242ff  lea     rcx, [rbx+250h]
0x180024306  call    ?_Tidy@?$vector@UEnergyUsageBucket@@V?$allocator@UEnergyUsageBucket@@@std@@@std@@AEAAXXZ; std::vector<EnergyUsageBucket>::_Tidy(void)
0x18002430b  lea     rcx, [rbx+1C0h]
0x180024312  call    ??1?$SrumCache@UEnergyEstimationRow@@@@QEAA@XZ; SrumCache<EnergyEstimationRow>::~SrumCache<EnergyEstimationRow>(void)
0x180024317  lea     rcx, [rbx+138h]
0x18002431e  call    ??1?$SrumCache@UBatteryDrainRow@@@@QEAA@XZ; SrumCache<BatteryDrainRow>::~SrumCache<BatteryDrainRow>(void)
0x180024323  mov     rcx, [rbx+118h]
0x18002432a  test    rcx, rcx
0x18002432d  jz      short loc_180024375
0x18002432f  mov     rax, [rbx+128h]
0x180024336  sub     rax, rcx
0x180024339  sar     rax, 3
0x18002433d  mov     rdx, 6DB6DB6DB6DB6DB7h
0x180024347  imul    rax, rdx
0x18002434b  imul    rdx, rax, 38h ; '8'
0x18002434f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180024354  mov     qword ptr [rbx+118h], 0
0x18002435f  mov     qword ptr [rbx+120h], 0
0x18002436a  mov     qword ptr [rbx+128h], 0
0x180024375  lea     rcx, [rbx+0E8h]; lpCriticalSection
0x18002437c  call    cs:__imp_DeleteCriticalSection
0x180024382  mov     rcx, rbx
0x180024385  add     rsp, 20h
0x180024389  pop     rbx
0x18002438a  jmp     ??1?$CSingletonHelper@W4BatteryUsageNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@UEAA@XZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::~CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>(void)
```
