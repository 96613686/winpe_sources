# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x1800081a0`
- end: `0x1800082cb`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `299`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180004674`
- `0x180005de4`
- `0x180005fe8`
- `0x180006584`
- `0x180006770`
- `0x1800081a0`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008297`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008297`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008280`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008280`

## string_xrefs

- `0x180008279`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_18002F258[25], qword_18002F258);
    wil::details_abi::FeatureStateData::RecordUsage(qword_18002F258);
  }
}

```

## disassembly

```asm
0x1800081a0  sub     rsp, 38h
0x1800081a4  mov     eax, r8d
0x1800081a7  mov     r8d, edx
0x1800081aa  btr     r8d, 1Fh; unsigned __int16
0x1800081af  test    ecx, ecx
0x1800081b1  jnz     short loc_18000821A
0x1800081b3  test    eax, eax
0x1800081b5  jnz     short loc_18000821A
0x1800081b7  test    r8d, r8d
0x1800081ba  jnz     short loc_18000821A
0x1800081bc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x1800081c3  jnz     loc_1800082C6
0x1800081c9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800081d0  test    rax, rax
0x1800081d3  jz      short loc_1800081E2
0x1800081d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081da  test    al, al
0x1800081dc  jnz     loc_1800082C6
0x1800081e2  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x1800081e9  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800081ee  test    al, al
0x1800081f0  jz      loc_1800082C6
0x1800081f6  mov     rdx, cs:qword_18002F258; SRWLock
0x1800081fd  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180008204  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180008209  mov     rcx, cs:qword_18002F258; SRWLock
0x180008210  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180008215  jmp     loc_1800082C6
0x18000821a  bt      r8d, 1Eh
0x18000821f  jnb     short loc_180008237
0x180008221  mov     edx, ecx; unsigned int
0x180008223  mov     r9d, eax; unsigned int
0x180008226  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000822d  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180008232  jmp     loc_1800082C6
0x180008237  test    eax, eax
0x180008239  jnz     short loc_1800082B5
0x18000823b  cmp     r8d, 0FEh
0x180008242  jz      short loc_1800082B5
0x180008244  mov     [rsp+38h+var_18], 0
0x18000824d  mov     dword ptr [rsp+38h+var_18], ecx
0x180008251  mov     word ptr [rsp+38h+var_18+4], r8w
0x180008257  test    edx, edx
0x180008259  jns     short loc_180008261
0x18000825b  or      word ptr [rsp+38h+var_18+6], 1
0x180008261  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180008268  test    rax, rax
0x18000826b  jnz     short loc_1800082A9
0x18000826d  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008274  test    rax, rax
0x180008277  jnz     short loc_18000828D
0x180008279  lea     rcx, ModuleName; "ntdll.dll"
0x180008280  call    cs:__imp_GetModuleHandleW
0x180008286  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000828d  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180008294  mov     rcx, rax; hModule
0x180008297  call    cs:__imp_GetProcAddress
0x18000829d  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x1800082a4  test    rax, rax
0x1800082a7  jz      short loc_1800082C6
0x1800082a9  lea     rcx, [rsp+38h+var_18]
0x1800082ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082b3  jmp     short loc_1800082C6
0x1800082b5  mov     edx, ecx
0x1800082b7  mov     r9, rax
0x1800082ba  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800082c1  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1800082c6  add     rsp, 38h
0x1800082ca  retn
```
