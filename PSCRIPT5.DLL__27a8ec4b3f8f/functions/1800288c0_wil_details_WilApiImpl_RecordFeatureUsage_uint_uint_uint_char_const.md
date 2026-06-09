# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x1800288c0`
- end: `0x180028a02`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `322`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180024f9c`
- `0x180026790`
- `0x180026940`
- `0x180026d04`
- `0x180026ee8`
- `0x1800288c0`
- `0x18005f010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800289a6`
- `KERNEL32!GetModuleHandleW` at `0x1800289a6`
- `KERNEL32!GetProcAddress` at `0x1800289c3`
- `KERNEL32!GetProcAddress` at `0x1800289c3`

## string_xrefs

- `0x18002899f`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details::WilApiImpl_RecordFeatureUsage(wil::details *this, int a2, unsigned int a3)
{
  unsigned int v4; // r8d
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v7; // [rsp+20h] [rbp-18h] BYREF
  int v8; // [rsp+24h] [rbp-14h]

  v4 = a2 & 0x7FFFFFFF;
  if ( (_DWORD)this || a3 || v4 )
  {
    if ( (a2 & 0x40000000) != 0 )
    {
      wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        (RTL_SRWLOCK *)&wil::details::g_featureStateManager,
        (int)this,
        a2,
        a3);
    }
    else if ( a3 || v4 == 254 )
    {
      wil::details::FeatureStateManager::RecordFeatureUsage(
        (__int64)&wil::details::g_featureStateManager,
        (unsigned int)this,
        v4,
        a3);
    }
    else
    {
      v7 = (int)this;
      v8 = (unsigned __int16)a2;
      if ( a2 < 0 )
        HIWORD(v8) |= 1u;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlNotifyFeatureUsage;
      if ( g_wil_details_pfnRtlNotifyFeatureUsage )
        goto LABEL_19;
      ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
      if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
      {
        ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
        `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
      }
      ProcAddress = GetProcAddress(ModuleHandleW, "RtlNotifyFeatureUsage");
      g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)ProcAddress;
      if ( ProcAddress )
LABEL_19:
        ((void (__fastcall *)(int *))ProcAddress)(&v7);
    }
  }
  else if ( !wil::details::g_processShutdownInProgress
         && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress())
         && wil::details::FeatureStateManager::EnsureStateData((RTL_SRWLOCK *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&SRWLock[25], SRWLock);
    wil::details_abi::FeatureStateData::RecordUsage(SRWLock);
  }
}

```

## disassembly

```asm
0x1800288c0  sub     rsp, 38h
0x1800288c4  mov     eax, r8d
0x1800288c7  mov     r8d, edx
0x1800288ca  btr     r8d, 1Fh; unsigned __int16
0x1800288cf  test    ecx, ecx
0x1800288d1  jnz     short loc_180028939
0x1800288d3  test    eax, eax
0x1800288d5  jnz     short loc_180028939
0x1800288d7  test    r8d, r8d
0x1800288da  jnz     short loc_180028939
0x1800288dc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x1800288e3  jnz     loc_1800289FC
0x1800288e9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800288f0  test    rax, rax
0x1800288f3  jz      short loc_180028902
0x1800288f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288fa  test    al, al
0x1800288fc  jnz     loc_1800289FC
0x180028902  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180028909  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18002890e  test    al, al
0x180028910  jz      loc_1800289FC
0x180028916  mov     rdx, cs:SRWLock; SRWLock
0x18002891d  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180028924  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180028929  mov     rcx, cs:SRWLock; SRWLock
0x180028930  add     rsp, 38h
0x180028934  jmp     ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180028939  bt      r8d, 1Eh
0x18002893e  jnb     short loc_180028955
0x180028940  mov     edx, ecx; unsigned int
0x180028942  mov     r9d, eax; unsigned int
0x180028945  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18002894c  add     rsp, 38h
0x180028950  jmp     ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180028955  test    eax, eax
0x180028957  jnz     loc_1800289EB
0x18002895d  cmp     r8d, 0FEh
0x180028964  jz      loc_1800289EB
0x18002896a  mov     [rsp+38h+var_18], 0
0x180028973  mov     dword ptr [rsp+38h+var_18], ecx
0x180028977  mov     word ptr [rsp+38h+var_18+4], r8w
0x18002897d  test    edx, edx
0x18002897f  jns     short loc_180028987
0x180028981  or      word ptr [rsp+38h+var_18+6], 1
0x180028987  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18002898e  test    rax, rax
0x180028991  jnz     short loc_1800289DB
0x180028993  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002899a  test    rax, rax
0x18002899d  jnz     short loc_1800289B9
0x18002899f  lea     rcx, aNtdllDll; "ntdll.dll"
0x1800289a6  call    cs:__imp_GetModuleHandleW
0x1800289ad  nop     dword ptr [rax+rax+00h]
0x1800289b2  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800289b9  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x1800289c0  mov     rcx, rax; hModule
0x1800289c3  call    cs:__imp_GetProcAddress
0x1800289ca  nop     dword ptr [rax+rax+00h]
0x1800289cf  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x1800289d6  test    rax, rax
0x1800289d9  jz      short loc_1800289FC
0x1800289db  lea     rcx, [rsp+38h+var_18]
0x1800289e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289e5  add     rsp, 38h
0x1800289e9  retn
0x1800289eb  mov     edx, ecx
0x1800289ed  mov     r9, rax
0x1800289f0  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800289f7  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1800289fc  add     rsp, 38h
0x180028a00  retn
```
