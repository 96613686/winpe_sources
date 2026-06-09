# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000e610`
- end: `0x18000e730`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000a498`
- `0x18000cacc`
- `0x18000cd10`
- `0x18000d09c`
- `0x18000d220`
- `0x18000e610`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e6fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e6fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e6e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e6e5`

## string_xrefs

- `0x18000e6de`: `ntdll.dll`

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
      ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180022078[25], qword_180022078);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180022078);
  }
}

```

## disassembly

```asm
0x18000e610  sub     rsp, 38h
0x18000e614  mov     eax, r8d
0x18000e617  mov     r8d, edx
0x18000e61a  btr     r8d, 1Fh; unsigned __int16
0x18000e61f  test    ecx, ecx
0x18000e621  jnz     short loc_18000E67F
0x18000e623  test    eax, eax
0x18000e625  jnz     short loc_18000E67F
0x18000e627  test    r8d, r8d
0x18000e62a  jnz     short loc_18000E67F
0x18000e62c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x18000e633  jnz     short loc_18000E67A
0x18000e635  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000e63c  test    rax, rax
0x18000e63f  jz      short loc_18000E64A
0x18000e641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e646  test    al, al
0x18000e648  jnz     short loc_18000E67A
0x18000e64a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000e651  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000e656  test    al, al
0x18000e658  jz      short loc_18000E67A
0x18000e65a  mov     rdx, cs:qword_180022078; SRWLock
0x18000e661  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000e668  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000e66d  mov     rcx, cs:qword_180022078; SRWLock
0x18000e674  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000e679  nop
0x18000e67a  jmp     loc_18000E72B
0x18000e67f  bt      r8d, 1Eh
0x18000e684  jnb     short loc_18000E69C
0x18000e686  mov     r9d, eax; unsigned int
0x18000e689  mov     edx, ecx; unsigned int
0x18000e68b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000e692  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18000e697  jmp     loc_18000E72B
0x18000e69c  test    eax, eax
0x18000e69e  jnz     short loc_18000E71A
0x18000e6a0  cmp     r8d, 0FEh
0x18000e6a7  jz      short loc_18000E71A
0x18000e6a9  mov     [rsp+38h+var_18], 0
0x18000e6b2  mov     dword ptr [rsp+38h+var_18], ecx
0x18000e6b6  mov     word ptr [rsp+38h+var_18+4], r8w
0x18000e6bc  test    edx, edx
0x18000e6be  jns     short loc_18000E6C6
0x18000e6c0  or      word ptr [rsp+38h+var_18+6], 1
0x18000e6c6  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000e6cd  test    rax, rax
0x18000e6d0  jnz     short loc_18000E70E
0x18000e6d2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e6d9  test    rax, rax
0x18000e6dc  jnz     short loc_18000E6F2
0x18000e6de  lea     rcx, ModuleName; "ntdll.dll"
0x18000e6e5  call    cs:__imp_GetModuleHandleW
0x18000e6eb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e6f2  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000e6f9  mov     rcx, rax; hModule
0x18000e6fc  call    cs:__imp_GetProcAddress
0x18000e702  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000e709  test    rax, rax
0x18000e70c  jz      short loc_18000E72B
0x18000e70e  lea     rcx, [rsp+38h+var_18]
0x18000e713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e718  jmp     short loc_18000E72B
0x18000e71a  mov     r9, rax
0x18000e71d  mov     edx, ecx
0x18000e71f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000e726  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000e72b  add     rsp, 38h
0x18000e72f  retn
```
