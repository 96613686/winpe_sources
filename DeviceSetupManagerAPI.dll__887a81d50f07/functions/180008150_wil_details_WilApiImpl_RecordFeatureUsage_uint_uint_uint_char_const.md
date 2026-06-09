# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180008150`
- end: `0x180008270`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180004634`
- `0x180005c14`
- `0x180005d7c`
- `0x180006164`
- `0x180006320`
- `0x180008150`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000823c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000823c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008225`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008225`

## string_xrefs

- `0x18000821e`: `ntdll.dll`

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
         && wil::details::FeatureStateManager::EnsureStateData((RTL_SRWLOCK *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180017248[25], qword_180017248);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180017248);
  }
}

```

## disassembly

```asm
0x180008150  sub     rsp, 38h
0x180008154  mov     eax, r8d
0x180008157  mov     r8d, edx
0x18000815a  btr     r8d, 1Fh; unsigned __int16
0x18000815f  test    ecx, ecx
0x180008161  jnz     short loc_1800081BF
0x180008163  test    eax, eax
0x180008165  jnz     short loc_1800081BF
0x180008167  test    r8d, r8d
0x18000816a  jnz     short loc_1800081BF
0x18000816c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180008173  jnz     short loc_1800081BA
0x180008175  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000817c  test    rax, rax
0x18000817f  jz      short loc_18000818A
0x180008181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008186  test    al, al
0x180008188  jnz     short loc_1800081BA
0x18000818a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180008191  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180008196  test    al, al
0x180008198  jz      short loc_1800081BA
0x18000819a  mov     rdx, cs:qword_180017248; SRWLock
0x1800081a1  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800081a8  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x1800081ad  mov     rcx, cs:qword_180017248; SRWLock
0x1800081b4  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800081b9  nop
0x1800081ba  jmp     loc_18000826B
0x1800081bf  bt      r8d, 1Eh
0x1800081c4  jnb     short loc_1800081DC
0x1800081c6  mov     r9d, eax; unsigned int
0x1800081c9  mov     edx, ecx; unsigned int
0x1800081cb  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x1800081d2  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x1800081d7  jmp     loc_18000826B
0x1800081dc  test    eax, eax
0x1800081de  jnz     short loc_18000825A
0x1800081e0  cmp     r8d, 0FEh
0x1800081e7  jz      short loc_18000825A
0x1800081e9  mov     [rsp+38h+var_18], 0
0x1800081f2  mov     dword ptr [rsp+38h+var_18], ecx
0x1800081f6  mov     word ptr [rsp+38h+var_18+4], r8w
0x1800081fc  test    edx, edx
0x1800081fe  jns     short loc_180008206
0x180008200  or      word ptr [rsp+38h+var_18+6], 1
0x180008206  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000820d  test    rax, rax
0x180008210  jnz     short loc_18000824E
0x180008212  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008219  test    rax, rax
0x18000821c  jnz     short loc_180008232
0x18000821e  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180008225  call    cs:__imp_GetModuleHandleW
0x18000822b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008232  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180008239  mov     rcx, rax; hModule
0x18000823c  call    cs:__imp_GetProcAddress
0x180008242  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180008249  test    rax, rax
0x18000824c  jz      short loc_18000826B
0x18000824e  lea     rcx, [rsp+38h+var_18]
0x180008253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008258  jmp     short loc_18000826B
0x18000825a  mov     r9, rax
0x18000825d  mov     edx, ecx
0x18000825f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180008266  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000826b  add     rsp, 38h
0x18000826f  retn
```
