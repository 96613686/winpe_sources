# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180011aa0`
- end: `0x180011bc0`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000c7e0`
- `0x18000e55c`
- `0x18000ea9c`
- `0x18000f0a4`
- `0x18000f2a0`
- `0x180011aa0`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011b75`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011b75`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011b8c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011b8c`

## string_xrefs

- `0x180011b6e`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180042170[25], qword_180042170);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180042170);
  }
}

```

## disassembly

```asm
0x180011aa0  sub     rsp, 38h
0x180011aa4  mov     eax, r8d
0x180011aa7  mov     r8d, edx
0x180011aaa  btr     r8d, 1Fh; unsigned __int16
0x180011aaf  test    ecx, ecx
0x180011ab1  jnz     short loc_180011B0F
0x180011ab3  test    eax, eax
0x180011ab5  jnz     short loc_180011B0F
0x180011ab7  test    r8d, r8d
0x180011aba  jnz     short loc_180011B0F
0x180011abc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180011ac3  jnz     short loc_180011B0A
0x180011ac5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180011acc  test    rax, rax
0x180011acf  jz      short loc_180011ADA
0x180011ad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ad6  test    al, al
0x180011ad8  jnz     short loc_180011B0A
0x180011ada  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180011ae1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180011ae6  test    al, al
0x180011ae8  jz      short loc_180011B0A
0x180011aea  mov     rdx, cs:qword_180042170; SRWLock
0x180011af1  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180011af8  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180011afd  mov     rcx, cs:qword_180042170; SRWLock
0x180011b04  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180011b09  nop
0x180011b0a  jmp     loc_180011BBB
0x180011b0f  bt      r8d, 1Eh
0x180011b14  jnb     short loc_180011B2C
0x180011b16  mov     r9d, eax; unsigned int
0x180011b19  mov     edx, ecx; unsigned int
0x180011b1b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180011b22  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180011b27  jmp     loc_180011BBB
0x180011b2c  test    eax, eax
0x180011b2e  jnz     short loc_180011BAA
0x180011b30  cmp     r8d, 0FEh
0x180011b37  jz      short loc_180011BAA
0x180011b39  mov     [rsp+38h+var_18], 0
0x180011b42  mov     dword ptr [rsp+38h+var_18], ecx
0x180011b46  mov     word ptr [rsp+38h+var_18+4], r8w
0x180011b4c  test    edx, edx
0x180011b4e  jns     short loc_180011B56
0x180011b50  or      word ptr [rsp+38h+var_18+6], 1
0x180011b56  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180011b5d  test    rax, rax
0x180011b60  jnz     short loc_180011B9E
0x180011b62  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180011b69  test    rax, rax
0x180011b6c  jnz     short loc_180011B82
0x180011b6e  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180011b75  call    cs:__imp_GetModuleHandleW
0x180011b7b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180011b82  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180011b89  mov     rcx, rax; hModule
0x180011b8c  call    cs:__imp_GetProcAddress
0x180011b92  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180011b99  test    rax, rax
0x180011b9c  jz      short loc_180011BBB
0x180011b9e  lea     rcx, [rsp+38h+var_18]
0x180011ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ba8  jmp     short loc_180011BBB
0x180011baa  mov     r9, rax
0x180011bad  mov     edx, ecx
0x180011baf  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180011bb6  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180011bbb  add     rsp, 38h
0x180011bbf  retn
```
