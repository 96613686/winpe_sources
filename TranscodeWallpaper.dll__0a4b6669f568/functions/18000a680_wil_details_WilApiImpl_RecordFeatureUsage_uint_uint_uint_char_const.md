# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000a680`
- end: `0x18000a7a0`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180008084`
- `0x180008b7c`
- `0x180008c40`
- `0x180008ff0`
- `0x180009174`
- `0x18000a680`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a76c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a76c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a755`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a755`

## string_xrefs

- `0x18000a74e`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180016098[25], qword_180016098);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180016098);
  }
}

```

## disassembly

```asm
0x18000a680  sub     rsp, 38h
0x18000a684  mov     eax, r8d
0x18000a687  mov     r8d, edx
0x18000a68a  btr     r8d, 1Fh; unsigned __int16
0x18000a68f  test    ecx, ecx
0x18000a691  jnz     short loc_18000A6EF
0x18000a693  test    eax, eax
0x18000a695  jnz     short loc_18000A6EF
0x18000a697  test    r8d, r8d
0x18000a69a  jnz     short loc_18000A6EF
0x18000a69c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x18000a6a3  jnz     short loc_18000A6EA
0x18000a6a5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000a6ac  test    rax, rax
0x18000a6af  jz      short loc_18000A6BA
0x18000a6b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6b6  test    al, al
0x18000a6b8  jnz     short loc_18000A6EA
0x18000a6ba  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000a6c1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000a6c6  test    al, al
0x18000a6c8  jz      short loc_18000A6EA
0x18000a6ca  mov     rdx, cs:qword_180016098; SRWLock
0x18000a6d1  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000a6d8  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000a6dd  mov     rcx, cs:qword_180016098; SRWLock
0x18000a6e4  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000a6e9  nop
0x18000a6ea  jmp     loc_18000A79B
0x18000a6ef  bt      r8d, 1Eh
0x18000a6f4  jnb     short loc_18000A70C
0x18000a6f6  mov     r9d, eax; unsigned int
0x18000a6f9  mov     edx, ecx; unsigned int
0x18000a6fb  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000a702  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18000a707  jmp     loc_18000A79B
0x18000a70c  test    eax, eax
0x18000a70e  jnz     short loc_18000A78A
0x18000a710  cmp     r8d, 0FEh
0x18000a717  jz      short loc_18000A78A
0x18000a719  mov     [rsp+38h+var_18], 0
0x18000a722  mov     dword ptr [rsp+38h+var_18], ecx
0x18000a726  mov     word ptr [rsp+38h+var_18+4], r8w
0x18000a72c  test    edx, edx
0x18000a72e  jns     short loc_18000A736
0x18000a730  or      word ptr [rsp+38h+var_18+6], 1
0x18000a736  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000a73d  test    rax, rax
0x18000a740  jnz     short loc_18000A77E
0x18000a742  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a749  test    rax, rax
0x18000a74c  jnz     short loc_18000A762
0x18000a74e  lea     rcx, ModuleName; "ntdll.dll"
0x18000a755  call    cs:__imp_GetModuleHandleW
0x18000a75b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a762  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000a769  mov     rcx, rax; hModule
0x18000a76c  call    cs:__imp_GetProcAddress
0x18000a772  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000a779  test    rax, rax
0x18000a77c  jz      short loc_18000A79B
0x18000a77e  lea     rcx, [rsp+38h+var_18]
0x18000a783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a788  jmp     short loc_18000A79B
0x18000a78a  mov     r9, rax
0x18000a78d  mov     edx, ecx
0x18000a78f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000a796  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000a79b  add     rsp, 38h
0x18000a79f  retn
```
