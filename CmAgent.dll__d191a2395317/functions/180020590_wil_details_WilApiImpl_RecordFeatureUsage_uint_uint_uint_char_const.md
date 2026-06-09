# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180020590`
- end: `0x1800206c1`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `305`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18001698c`
- `0x1800188f0`
- `0x1800197cc`
- `0x180019d60`
- `0x180019f04`
- `0x180020590`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180020669`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180020669`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020686`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020686`

## string_xrefs

- `0x180020662`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
        goto LABEL_20;
      ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
      if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
      {
        ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
        `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
      }
      ProcAddress = GetProcAddress(ModuleHandleW, "RtlNotifyFeatureUsage");
      g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)ProcAddress;
      if ( ProcAddress )
LABEL_20:
        ((void (__fastcall *)(int *))ProcAddress)(&v7);
    }
  }
  else if ( !wil::details::g_processShutdownInProgress
         && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress())
         && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_18004B200[25], qword_18004B200);
    wil::details_abi::FeatureStateData::RecordUsage(qword_18004B200);
  }
}

```

## disassembly

```asm
0x180020590  sub     rsp, 38h
0x180020594  mov     eax, r8d
0x180020597  mov     r8d, edx
0x18002059a  btr     r8d, 1Fh; unsigned __int16
0x18002059f  test    ecx, ecx
0x1800205a1  jnz     short loc_1800205FF
0x1800205a3  test    eax, eax
0x1800205a5  jnz     short loc_1800205FF
0x1800205a7  test    r8d, r8d
0x1800205aa  jnz     short loc_1800205FF
0x1800205ac  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x1800205b3  jnz     short loc_1800205FA
0x1800205b5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800205bc  test    rax, rax
0x1800205bf  jz      short loc_1800205CA
0x1800205c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800205c6  test    al, al
0x1800205c8  jnz     short loc_1800205FA
0x1800205ca  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x1800205d1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800205d6  test    al, al
0x1800205d8  jz      short loc_1800205FA
0x1800205da  mov     rdx, cs:qword_18004B200; SRWLock
0x1800205e1  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800205e8  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x1800205ed  mov     rcx, cs:qword_18004B200; SRWLock
0x1800205f4  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800205f9  nop
0x1800205fa  jmp     loc_1800206BB
0x1800205ff  bt      r8d, 1Eh
0x180020604  jnb     short loc_18002061C
0x180020606  mov     r9d, eax; unsigned int
0x180020609  mov     edx, ecx; unsigned int
0x18002060b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180020612  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180020617  jmp     loc_1800206BB
0x18002061c  test    eax, eax
0x18002061e  jnz     loc_1800206AA
0x180020624  cmp     r8d, 0FEh
0x18002062b  jz      short loc_1800206AA
0x18002062d  mov     [rsp+38h+var_18], 0
0x180020636  mov     dword ptr [rsp+38h+var_18], ecx
0x18002063a  mov     word ptr [rsp+38h+var_18+4], r8w
0x180020640  test    edx, edx
0x180020642  jns     short loc_18002064A
0x180020644  or      word ptr [rsp+38h+var_18+6], 1
0x18002064a  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180020651  test    rax, rax
0x180020654  jnz     short loc_18002069E
0x180020656  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x18002065d  test    rax, rax
0x180020660  jnz     short loc_18002067C
0x180020662  lea     rcx, ModuleName; "ntdll.dll"
0x180020669  call    cs:__imp_GetModuleHandleW
0x180020670  nop     dword ptr [rax+rax+00h]
0x180020675  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x18002067c  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180020683  mov     rcx, rax; hModule
0x180020686  call    cs:__imp_GetProcAddress
0x18002068d  nop     dword ptr [rax+rax+00h]
0x180020692  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180020699  test    rax, rax
0x18002069c  jz      short loc_1800206BB
0x18002069e  lea     rcx, [rsp+38h+var_18]
0x1800206a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800206a8  jmp     short loc_1800206BB
0x1800206aa  mov     r9, rax
0x1800206ad  mov     edx, ecx
0x1800206af  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800206b6  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1800206bb  add     rsp, 38h
0x1800206bf  retn
```
