# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180008230`
- end: `0x180008350`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1800044f4`
- `0x180005ad4`
- `0x180005c3c`
- `0x180006064`
- `0x180006220`
- `0x180008230`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000831c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000831c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008305`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008305`

## string_xrefs

- `0x1800082fe`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180014018[25], qword_180014018);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180014018);
  }
}

```

## disassembly

```asm
0x180008230  sub     rsp, 38h
0x180008234  mov     eax, r8d
0x180008237  mov     r8d, edx
0x18000823a  btr     r8d, 1Fh; unsigned __int16
0x18000823f  test    ecx, ecx
0x180008241  jnz     short loc_18000829F
0x180008243  test    eax, eax
0x180008245  jnz     short loc_18000829F
0x180008247  test    r8d, r8d
0x18000824a  jnz     short loc_18000829F
0x18000824c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180008253  jnz     short loc_18000829A
0x180008255  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000825c  test    rax, rax
0x18000825f  jz      short loc_18000826A
0x180008261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008266  test    al, al
0x180008268  jnz     short loc_18000829A
0x18000826a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180008271  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180008276  test    al, al
0x180008278  jz      short loc_18000829A
0x18000827a  mov     rdx, cs:qword_180014018; SRWLock
0x180008281  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180008288  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000828d  mov     rcx, cs:qword_180014018; SRWLock
0x180008294  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180008299  nop
0x18000829a  jmp     loc_18000834B
0x18000829f  bt      r8d, 1Eh
0x1800082a4  jnb     short loc_1800082BC
0x1800082a6  mov     r9d, eax; unsigned int
0x1800082a9  mov     edx, ecx; unsigned int
0x1800082ab  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x1800082b2  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x1800082b7  jmp     loc_18000834B
0x1800082bc  test    eax, eax
0x1800082be  jnz     short loc_18000833A
0x1800082c0  cmp     r8d, 0FEh
0x1800082c7  jz      short loc_18000833A
0x1800082c9  mov     [rsp+38h+var_18], 0
0x1800082d2  mov     dword ptr [rsp+38h+var_18], ecx
0x1800082d6  mov     word ptr [rsp+38h+var_18+4], r8w
0x1800082dc  test    edx, edx
0x1800082de  jns     short loc_1800082E6
0x1800082e0  or      word ptr [rsp+38h+var_18+6], 1
0x1800082e6  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x1800082ed  test    rax, rax
0x1800082f0  jnz     short loc_18000832E
0x1800082f2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800082f9  test    rax, rax
0x1800082fc  jnz     short loc_180008312
0x1800082fe  lea     rcx, ModuleName; "ntdll.dll"
0x180008305  call    cs:__imp_GetModuleHandleW
0x18000830b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008312  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180008319  mov     rcx, rax; hModule
0x18000831c  call    cs:__imp_GetProcAddress
0x180008322  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180008329  test    rax, rax
0x18000832c  jz      short loc_18000834B
0x18000832e  lea     rcx, [rsp+38h+var_18]
0x180008333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008338  jmp     short loc_18000834B
0x18000833a  mov     r9, rax
0x18000833d  mov     edx, ecx
0x18000833f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180008346  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000834b  add     rsp, 38h
0x18000834f  retn
```
