# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000a620`
- end: `0x18000a740`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180006b04`
- `0x1800080e4`
- `0x18000824c`
- `0x180008634`
- `0x1800087f0`
- `0x18000a620`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a70c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a70c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a6f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a6f5`

## string_xrefs

- `0x18000a6ee`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_1800130A8[25], qword_1800130A8);
    wil::details_abi::FeatureStateData::RecordUsage(qword_1800130A8);
  }
}

```

## disassembly

```asm
0x18000a620  sub     rsp, 38h
0x18000a624  mov     eax, r8d
0x18000a627  mov     r8d, edx
0x18000a62a  btr     r8d, 1Fh; unsigned __int16
0x18000a62f  test    ecx, ecx
0x18000a631  jnz     short loc_18000A68F
0x18000a633  test    eax, eax
0x18000a635  jnz     short loc_18000A68F
0x18000a637  test    r8d, r8d
0x18000a63a  jnz     short loc_18000A68F
0x18000a63c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x18000a643  jnz     short loc_18000A68A
0x18000a645  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000a64c  test    rax, rax
0x18000a64f  jz      short loc_18000A65A
0x18000a651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a656  test    al, al
0x18000a658  jnz     short loc_18000A68A
0x18000a65a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000a661  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000a666  test    al, al
0x18000a668  jz      short loc_18000A68A
0x18000a66a  mov     rdx, cs:qword_1800130A8; SRWLock
0x18000a671  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000a678  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000a67d  mov     rcx, cs:qword_1800130A8; SRWLock
0x18000a684  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000a689  nop
0x18000a68a  jmp     loc_18000A73B
0x18000a68f  bt      r8d, 1Eh
0x18000a694  jnb     short loc_18000A6AC
0x18000a696  mov     r9d, eax; unsigned int
0x18000a699  mov     edx, ecx; unsigned int
0x18000a69b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000a6a2  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18000a6a7  jmp     loc_18000A73B
0x18000a6ac  test    eax, eax
0x18000a6ae  jnz     short loc_18000A72A
0x18000a6b0  cmp     r8d, 0FEh
0x18000a6b7  jz      short loc_18000A72A
0x18000a6b9  mov     [rsp+38h+var_18], 0
0x18000a6c2  mov     dword ptr [rsp+38h+var_18], ecx
0x18000a6c6  mov     word ptr [rsp+38h+var_18+4], r8w
0x18000a6cc  test    edx, edx
0x18000a6ce  jns     short loc_18000A6D6
0x18000a6d0  or      word ptr [rsp+38h+var_18+6], 1
0x18000a6d6  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000a6dd  test    rax, rax
0x18000a6e0  jnz     short loc_18000A71E
0x18000a6e2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a6e9  test    rax, rax
0x18000a6ec  jnz     short loc_18000A702
0x18000a6ee  lea     rcx, ModuleName; "ntdll.dll"
0x18000a6f5  call    cs:__imp_GetModuleHandleW
0x18000a6fb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a702  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000a709  mov     rcx, rax; hModule
0x18000a70c  call    cs:__imp_GetProcAddress
0x18000a712  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000a719  test    rax, rax
0x18000a71c  jz      short loc_18000A73B
0x18000a71e  lea     rcx, [rsp+38h+var_18]
0x18000a723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a728  jmp     short loc_18000A73B
0x18000a72a  mov     r9, rax
0x18000a72d  mov     edx, ecx
0x18000a72f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000a736  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000a73b  add     rsp, 38h
0x18000a73f  retn
```
