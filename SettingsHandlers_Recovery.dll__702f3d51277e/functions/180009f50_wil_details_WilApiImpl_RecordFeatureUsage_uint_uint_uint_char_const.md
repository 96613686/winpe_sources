# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180009f50`
- end: `0x18000a070`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180005a90`
- `0x180007294`
- `0x180007518`
- `0x180007b04`
- `0x180007d00`
- `0x180009f50`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a03c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a03c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a025`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a025`

## string_xrefs

- `0x18000a01e`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::WilApiImpl_RecordFeatureUsage(wil::details *this, int a2, unsigned int a3)
{
  __int64 v3; // rax
  __int64 v4; // r8
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v7; // [rsp+20h] [rbp-18h] BYREF
  int v8; // [rsp+24h] [rbp-14h]

  v3 = a3;
  v4 = (unsigned int)a2;
  LODWORD(v4) = a2 & 0x7FFFFFFF;
  if ( (_DWORD)this || (_DWORD)v3 || (_DWORD)v4 )
  {
    if ( (a2 & 0x40000000) != 0 )
    {
      wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        (RTL_SRWLOCK *)&wil::details::g_featureStateManager,
        (int)this,
        a2,
        v3);
    }
    else if ( (_DWORD)v3 || (_DWORD)v4 == 254 )
    {
      wil::details::FeatureStateManager::RecordFeatureUsage(
        &wil::details::g_featureStateManager,
        (unsigned int)this,
        v4,
        v3);
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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_1800520D8[25], qword_1800520D8);
    wil::details_abi::FeatureStateData::RecordUsage(qword_1800520D8);
  }
}

```

## disassembly

```asm
0x180009f50  sub     rsp, 38h
0x180009f54  mov     eax, r8d
0x180009f57  mov     r8d, edx
0x180009f5a  btr     r8d, 1Fh; unsigned __int16
0x180009f5f  test    ecx, ecx
0x180009f61  jnz     short loc_180009FBF
0x180009f63  test    eax, eax
0x180009f65  jnz     short loc_180009FBF
0x180009f67  test    r8d, r8d
0x180009f6a  jnz     short loc_180009FBF
0x180009f6c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180009f73  jnz     short loc_180009FBA
0x180009f75  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180009f7c  test    rax, rax
0x180009f7f  jz      short loc_180009F8A
0x180009f81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f86  test    al, al
0x180009f88  jnz     short loc_180009FBA
0x180009f8a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180009f91  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180009f96  test    al, al
0x180009f98  jz      short loc_180009FBA
0x180009f9a  mov     rdx, cs:qword_1800520D8; SRWLock
0x180009fa1  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180009fa8  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180009fad  mov     rcx, cs:qword_1800520D8; SRWLock
0x180009fb4  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180009fb9  nop
0x180009fba  jmp     loc_18000A06B
0x180009fbf  bt      r8d, 1Eh
0x180009fc4  jnb     short loc_180009FDC
0x180009fc6  mov     r9d, eax; unsigned int
0x180009fc9  mov     edx, ecx; unsigned int
0x180009fcb  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180009fd2  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180009fd7  jmp     loc_18000A06B
0x180009fdc  test    eax, eax
0x180009fde  jnz     short loc_18000A05A
0x180009fe0  cmp     r8d, 0FEh
0x180009fe7  jz      short loc_18000A05A
0x180009fe9  mov     [rsp+38h+var_18], 0
0x180009ff2  mov     dword ptr [rsp+38h+var_18], ecx
0x180009ff6  mov     word ptr [rsp+38h+var_18+4], r8w
0x180009ffc  test    edx, edx
0x180009ffe  jns     short loc_18000A006
0x18000a000  or      word ptr [rsp+38h+var_18+6], 1
0x18000a006  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000a00d  test    rax, rax
0x18000a010  jnz     short loc_18000A04E
0x18000a012  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a019  test    rax, rax
0x18000a01c  jnz     short loc_18000A032
0x18000a01e  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000a025  call    cs:__imp_GetModuleHandleW
0x18000a02b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a032  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000a039  mov     rcx, rax; hModule
0x18000a03c  call    cs:__imp_GetProcAddress
0x18000a042  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000a049  test    rax, rax
0x18000a04c  jz      short loc_18000A06B
0x18000a04e  lea     rcx, [rsp+38h+var_18]
0x18000a053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a058  jmp     short loc_18000A06B
0x18000a05a  mov     r9, rax
0x18000a05d  mov     edx, ecx
0x18000a05f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000a066  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000a06b  add     rsp, 38h
0x18000a06f  retn
```
