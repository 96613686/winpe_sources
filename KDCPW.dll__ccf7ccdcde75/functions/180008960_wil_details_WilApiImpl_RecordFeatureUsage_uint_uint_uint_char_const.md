# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180008960`
- end: `0x180008a8b`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `299`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180004564`
- `0x1800060e4`
- `0x1800062e8`
- `0x180006a44`
- `0x180006c30`
- `0x180008960`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008a57`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008a57`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008a40`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008a40`

## string_xrefs

- `0x180008a39`: `ntdll.dll`

## pseudocode

```c
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
         && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_1800120D8[25], qword_1800120D8);
    wil::details_abi::FeatureStateData::RecordUsage(qword_1800120D8);
  }
}

```

## disassembly

```asm
0x180008960  sub     rsp, 38h
0x180008964  mov     eax, r8d
0x180008967  mov     r8d, edx
0x18000896a  btr     r8d, 1Fh; unsigned __int16
0x18000896f  test    ecx, ecx
0x180008971  jnz     short loc_1800089DA
0x180008973  test    eax, eax
0x180008975  jnz     short loc_1800089DA
0x180008977  test    r8d, r8d
0x18000897a  jnz     short loc_1800089DA
0x18000897c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180008983  jnz     loc_180008A86
0x180008989  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180008990  test    rax, rax
0x180008993  jz      short loc_1800089A2
0x180008995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000899a  test    al, al
0x18000899c  jnz     loc_180008A86
0x1800089a2  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x1800089a9  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800089ae  test    al, al
0x1800089b0  jz      loc_180008A86
0x1800089b6  mov     rdx, cs:qword_1800120D8; SRWLock
0x1800089bd  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800089c4  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x1800089c9  mov     rcx, cs:qword_1800120D8; SRWLock
0x1800089d0  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800089d5  jmp     loc_180008A86
0x1800089da  bt      r8d, 1Eh
0x1800089df  jnb     short loc_1800089F7
0x1800089e1  mov     edx, ecx; unsigned int
0x1800089e3  mov     r9d, eax; unsigned int
0x1800089e6  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x1800089ed  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x1800089f2  jmp     loc_180008A86
0x1800089f7  test    eax, eax
0x1800089f9  jnz     short loc_180008A75
0x1800089fb  cmp     r8d, 0FEh
0x180008a02  jz      short loc_180008A75
0x180008a04  mov     [rsp+38h+var_18], 0
0x180008a0d  mov     dword ptr [rsp+38h+var_18], ecx
0x180008a11  mov     word ptr [rsp+38h+var_18+4], r8w
0x180008a17  test    edx, edx
0x180008a19  jns     short loc_180008A21
0x180008a1b  or      word ptr [rsp+38h+var_18+6], 1
0x180008a21  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180008a28  test    rax, rax
0x180008a2b  jnz     short loc_180008A69
0x180008a2d  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008a34  test    rax, rax
0x180008a37  jnz     short loc_180008A4D
0x180008a39  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180008a40  call    cs:__imp_GetModuleHandleW
0x180008a46  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008a4d  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180008a54  mov     rcx, rax; hModule
0x180008a57  call    cs:__imp_GetProcAddress
0x180008a5d  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180008a64  test    rax, rax
0x180008a67  jz      short loc_180008A86
0x180008a69  lea     rcx, [rsp+38h+var_18]
0x180008a6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a73  jmp     short loc_180008A86
0x180008a75  mov     edx, ecx
0x180008a77  mov     r9, rax
0x180008a7a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180008a81  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180008a86  add     rsp, 38h
0x180008a8a  retn
```
