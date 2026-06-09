# SystemSettings::BatteryUsageHandlers::CBatteryGraphSingleton::~CBatteryGraphSingleton(void)

- ea: `0x180024398`
- end: `0x18002442f`
- name: `??1CBatteryGraphSingleton@BatteryUsageHandlers@SystemSettings@@UEAA@XZ`
- size: `151`
- prototype: `void __fastcall(SystemSettings::BatteryUsageHandlers::CBatteryGraphSingleton *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180024600`
- `0x180059cf0`

## callees

- `0x18000d4dc`
- `0x180024020`
- `0x180024078`
- `0x1800240d0`
- `0x180024398`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002441c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002441c`

## pseudocode

```c
void __fastcall SystemSettings::BatteryUsageHandlers::CBatteryGraphSingleton::~CBatteryGraphSingleton(
        SystemSettings::BatteryUsageHandlers::CBatteryGraphSingleton *this,
        __int64 a2)
{
  __int64 v3; // rdx
  void *v4; // rcx

  *(_QWORD *)this = &SystemSettings::BatteryUsageHandlers::CBatteryGraphSingleton::`vftable';
  SrumCache<EnergyEstimationRow>::~SrumCache<EnergyEstimationRow>((__int64)this + 448, a2);
  SrumCache<BatteryDrainRow>::~SrumCache<BatteryDrainRow>((__int64)this + 312, v3);
  v4 = (void *)*((_QWORD *)this + 35);
  if ( v4 )
  {
    std::_Deallocate<16>(v4, (struct std::nothrow_t *)(8 * ((__int64)(*((_QWORD *)this + 37) - (_QWORD)v4) >> 3)));
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
0x180024398  push    rbx
0x18002439a  sub     rsp, 20h
0x18002439e  lea     rax, ??_7CBatteryGraphSingleton@BatteryUsageHandlers@SystemSettings@@6B@; const SystemSettings::BatteryUsageHandlers::CBatteryGraphSingleton::`vftable'
0x1800243a5  mov     rbx, rcx
0x1800243a8  mov     [rcx], rax
0x1800243ab  add     rcx, 1C0h
0x1800243b2  call    ??1?$SrumCache@UEnergyEstimationRow@@@@QEAA@XZ; SrumCache<EnergyEstimationRow>::~SrumCache<EnergyEstimationRow>(void)
0x1800243b7  lea     rcx, [rbx+138h]
0x1800243be  call    ??1?$SrumCache@UBatteryDrainRow@@@@QEAA@XZ; SrumCache<BatteryDrainRow>::~SrumCache<BatteryDrainRow>(void)
0x1800243c3  mov     rcx, [rbx+118h]
0x1800243ca  test    rcx, rcx
0x1800243cd  jz      short loc_180024415
0x1800243cf  mov     rax, [rbx+128h]
0x1800243d6  mov     rdx, 6DB6DB6DB6DB6DB7h
0x1800243e0  sub     rax, rcx
0x1800243e3  sar     rax, 3
0x1800243e7  imul    rax, rdx
0x1800243eb  imul    rdx, rax, 38h ; '8'
0x1800243ef  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800243f4  mov     qword ptr [rbx+118h], 0
0x1800243ff  mov     qword ptr [rbx+120h], 0
0x18002440a  mov     qword ptr [rbx+128h], 0
0x180024415  lea     rcx, [rbx+0E8h]; lpCriticalSection
0x18002441c  call    cs:__imp_DeleteCriticalSection
0x180024422  mov     rcx, rbx
0x180024425  add     rsp, 20h
0x180024429  pop     rbx
0x18002442a  jmp     ??1?$CSingletonHelper@W4BatteryUsageNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@UEAA@XZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::~CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>(void)
```
