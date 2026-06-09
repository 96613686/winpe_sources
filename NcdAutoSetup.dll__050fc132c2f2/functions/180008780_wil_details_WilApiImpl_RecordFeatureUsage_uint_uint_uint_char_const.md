# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180008780`
- end: `0x1800088ab`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `299`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180004624`
- `0x180005e2c`
- `0x18000604c`
- `0x180006414`
- `0x1800065cc`
- `0x180008780`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008860`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008860`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008877`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008877`

## string_xrefs

- `0x180008859`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_18001A290[25], qword_18001A290);
    wil::details_abi::FeatureStateData::RecordUsage(qword_18001A290);
  }
}

```

## disassembly

```asm
0x180008780  sub     rsp, 38h
0x180008784  mov     eax, r8d
0x180008787  mov     r8d, edx
0x18000878a  btr     r8d, 1Fh; unsigned __int16
0x18000878f  test    ecx, ecx
0x180008791  jnz     short loc_1800087FA
0x180008793  test    eax, eax
0x180008795  jnz     short loc_1800087FA
0x180008797  test    r8d, r8d
0x18000879a  jnz     short loc_1800087FA
0x18000879c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x1800087a3  jnz     loc_1800088A6
0x1800087a9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800087b0  test    rax, rax
0x1800087b3  jz      short loc_1800087C2
0x1800087b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087ba  test    al, al
0x1800087bc  jnz     loc_1800088A6
0x1800087c2  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x1800087c9  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800087ce  test    al, al
0x1800087d0  jz      loc_1800088A6
0x1800087d6  mov     rdx, cs:qword_18001A290; SRWLock
0x1800087dd  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800087e4  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x1800087e9  mov     rcx, cs:qword_18001A290; SRWLock
0x1800087f0  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800087f5  jmp     loc_1800088A6
0x1800087fa  bt      r8d, 1Eh
0x1800087ff  jnb     short loc_180008817
0x180008801  mov     edx, ecx; unsigned int
0x180008803  mov     r9d, eax; unsigned int
0x180008806  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000880d  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180008812  jmp     loc_1800088A6
0x180008817  test    eax, eax
0x180008819  jnz     short loc_180008895
0x18000881b  cmp     r8d, 0FEh
0x180008822  jz      short loc_180008895
0x180008824  mov     [rsp+38h+var_18], 0
0x18000882d  mov     dword ptr [rsp+38h+var_18], ecx
0x180008831  mov     word ptr [rsp+38h+var_18+4], r8w
0x180008837  test    edx, edx
0x180008839  jns     short loc_180008841
0x18000883b  or      word ptr [rsp+38h+var_18+6], 1
0x180008841  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180008848  test    rax, rax
0x18000884b  jnz     short loc_180008889
0x18000884d  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008854  test    rax, rax
0x180008857  jnz     short loc_18000886D
0x180008859  lea     rcx, ModuleName; "ntdll.dll"
0x180008860  call    cs:__imp_GetModuleHandleW
0x180008866  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000886d  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180008874  mov     rcx, rax; hModule
0x180008877  call    cs:__imp_GetProcAddress
0x18000887d  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180008884  test    rax, rax
0x180008887  jz      short loc_1800088A6
0x180008889  lea     rcx, [rsp+38h+var_18]
0x18000888e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008893  jmp     short loc_1800088A6
0x180008895  mov     edx, ecx
0x180008897  mov     r9, rax
0x18000889a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800088a1  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1800088a6  add     rsp, 38h
0x1800088aa  retn
```
