# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x1800099c0`
- end: `0x180009ae9`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `297`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180005834`
- `0x180007028`
- `0x1800072cc`
- `0x180007884`
- `0x180007a48`
- `0x1800099c0`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180009a9e`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180009a9e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180009ab5`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180009ab5`

## string_xrefs

- `0x180009a97`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details::WilApiImpl_RecordFeatureUsage(wil::details *this, int a2, unsigned int a3)
{
  unsigned int v4; // r8d
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v7; // [rsp+20h] [rbp-18h] BYREF
  int v8; // [rsp+24h] [rbp-14h]
  __int64 v9; // [rsp+28h] [rbp-10h]

  v9 = -2;
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
         && (!wil::details::g_pfnDllShutdownInProgress
          || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress(this))
         && wil::details::FeatureStateManager::EnsureStateData((RTL_SRWLOCK *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180025408[25], qword_180025408);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180025408);
  }
}

```

## disassembly

```asm
0x1800099c0  sub     rsp, 38h
0x1800099c4  mov     [rsp+38h+var_10], 0FFFFFFFFFFFFFFFEh
0x1800099cd  mov     eax, r8d
0x1800099d0  mov     r8d, edx
0x1800099d3  btr     r8d, 1Fh; unsigned __int16
0x1800099d8  test    ecx, ecx
0x1800099da  jnz     short loc_180009A38
0x1800099dc  test    eax, eax
0x1800099de  jnz     short loc_180009A38
0x1800099e0  test    r8d, r8d
0x1800099e3  jnz     short loc_180009A38
0x1800099e5  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x1800099ec  jnz     short loc_180009A33
0x1800099ee  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800099f5  test    rax, rax
0x1800099f8  jz      short loc_180009A03
0x1800099fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099ff  test    al, al
0x180009a01  jnz     short loc_180009A33
0x180009a03  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180009a0a  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180009a0f  test    al, al
0x180009a11  jz      short loc_180009A33
0x180009a13  mov     rdx, cs:qword_180025408; SRWLock
0x180009a1a  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180009a21  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180009a26  mov     rcx, cs:qword_180025408; SRWLock
0x180009a2d  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180009a32  nop
0x180009a33  jmp     loc_180009AE4
0x180009a38  bt      r8d, 1Eh
0x180009a3d  jnb     short loc_180009A55
0x180009a3f  mov     r9d, eax; unsigned int
0x180009a42  mov     edx, ecx; unsigned int
0x180009a44  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180009a4b  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180009a50  jmp     loc_180009AE4
0x180009a55  test    eax, eax
0x180009a57  jnz     short loc_180009AD3
0x180009a59  cmp     r8d, 0FEh
0x180009a60  jz      short loc_180009AD3
0x180009a62  mov     [rsp+38h+var_18], 0
0x180009a6b  mov     dword ptr [rsp+38h+var_18], ecx
0x180009a6f  mov     word ptr [rsp+38h+var_18+4], r8w
0x180009a75  test    edx, edx
0x180009a77  jns     short loc_180009A7F
0x180009a79  or      word ptr [rsp+38h+var_18+6], 1
0x180009a7f  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180009a86  test    rax, rax
0x180009a89  jnz     short loc_180009AC7
0x180009a8b  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009a92  test    rax, rax
0x180009a95  jnz     short loc_180009AAB
0x180009a97  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180009a9e  call    cs:__imp_GetModuleHandleW
0x180009aa4  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009aab  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180009ab2  mov     rcx, rax; hModule
0x180009ab5  call    cs:__imp_GetProcAddress
0x180009abb  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180009ac2  test    rax, rax
0x180009ac5  jz      short loc_180009AE4
0x180009ac7  lea     rcx, [rsp+38h+var_18]
0x180009acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ad1  jmp     short loc_180009AE4
0x180009ad3  mov     r9, rax
0x180009ad6  mov     edx, ecx
0x180009ad8  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180009adf  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180009ae4  add     rsp, 38h
0x180009ae8  retn
```
