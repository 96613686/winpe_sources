# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x1800097c0`
- end: `0x1800098eb`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `299`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1800063b4`
- `0x180007994`
- `0x180007afc`
- `0x180007ec4`
- `0x18000807c`
- `0x1800097c0`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800098b7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800098b7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800098a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800098a0`

## string_xrefs

- `0x180009899`: `ntdll.dll`

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
      ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180011048[25], qword_180011048);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180011048);
  }
}

```

## disassembly

```asm
0x1800097c0  sub     rsp, 38h
0x1800097c4  mov     eax, r8d
0x1800097c7  mov     r8d, edx
0x1800097ca  btr     r8d, 1Fh; unsigned __int16
0x1800097cf  test    ecx, ecx
0x1800097d1  jnz     short loc_18000983A
0x1800097d3  test    eax, eax
0x1800097d5  jnz     short loc_18000983A
0x1800097d7  test    r8d, r8d
0x1800097da  jnz     short loc_18000983A
0x1800097dc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x1800097e3  jnz     loc_1800098E6
0x1800097e9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800097f0  test    rax, rax
0x1800097f3  jz      short loc_180009802
0x1800097f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097fa  test    al, al
0x1800097fc  jnz     loc_1800098E6
0x180009802  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180009809  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000980e  test    al, al
0x180009810  jz      loc_1800098E6
0x180009816  mov     rdx, cs:qword_180011048; SRWLock
0x18000981d  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180009824  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180009829  mov     rcx, cs:qword_180011048; SRWLock
0x180009830  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180009835  jmp     loc_1800098E6
0x18000983a  bt      r8d, 1Eh
0x18000983f  jnb     short loc_180009857
0x180009841  mov     edx, ecx; unsigned int
0x180009843  mov     r9d, eax; unsigned int
0x180009846  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000984d  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180009852  jmp     loc_1800098E6
0x180009857  test    eax, eax
0x180009859  jnz     short loc_1800098D5
0x18000985b  cmp     r8d, 0FEh
0x180009862  jz      short loc_1800098D5
0x180009864  mov     [rsp+38h+var_18], 0
0x18000986d  mov     dword ptr [rsp+38h+var_18], ecx
0x180009871  mov     word ptr [rsp+38h+var_18+4], r8w
0x180009877  test    edx, edx
0x180009879  jns     short loc_180009881
0x18000987b  or      word ptr [rsp+38h+var_18+6], 1
0x180009881  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180009888  test    rax, rax
0x18000988b  jnz     short loc_1800098C9
0x18000988d  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009894  test    rax, rax
0x180009897  jnz     short loc_1800098AD
0x180009899  lea     rcx, ModuleName; "ntdll.dll"
0x1800098a0  call    cs:__imp_GetModuleHandleW
0x1800098a6  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800098ad  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x1800098b4  mov     rcx, rax; hModule
0x1800098b7  call    cs:__imp_GetProcAddress
0x1800098bd  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x1800098c4  test    rax, rax
0x1800098c7  jz      short loc_1800098E6
0x1800098c9  lea     rcx, [rsp+38h+var_18]
0x1800098ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098d3  jmp     short loc_1800098E6
0x1800098d5  mov     edx, ecx
0x1800098d7  mov     r9, rax
0x1800098da  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800098e1  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1800098e6  add     rsp, 38h
0x1800098ea  retn
```
