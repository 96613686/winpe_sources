# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180015df0`
- end: `0x180015f10`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1800118f4`
- `0x18001380c`
- `0x180013e70`
- `0x180014558`
- `0x180014710`
- `0x180015df0`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015edc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015edc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015ec5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015ec5`

## string_xrefs

- `0x180015ebe`: `ntdll.dll`

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
         && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_1800271B0[25], qword_1800271B0);
    wil::details_abi::FeatureStateData::RecordUsage(qword_1800271B0);
  }
}

```

## disassembly

```asm
0x180015df0  sub     rsp, 38h
0x180015df4  mov     eax, r8d
0x180015df7  mov     r8d, edx
0x180015dfa  btr     r8d, 1Fh; unsigned __int16
0x180015dff  test    ecx, ecx
0x180015e01  jnz     short loc_180015E5F
0x180015e03  test    eax, eax
0x180015e05  jnz     short loc_180015E5F
0x180015e07  test    r8d, r8d
0x180015e0a  jnz     short loc_180015E5F
0x180015e0c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180015e13  jnz     short loc_180015E5A
0x180015e15  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180015e1c  test    rax, rax
0x180015e1f  jz      short loc_180015E2A
0x180015e21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e26  test    al, al
0x180015e28  jnz     short loc_180015E5A
0x180015e2a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180015e31  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180015e36  test    al, al
0x180015e38  jz      short loc_180015E5A
0x180015e3a  mov     rdx, cs:qword_1800271B0; SRWLock
0x180015e41  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180015e48  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180015e4d  mov     rcx, cs:qword_1800271B0; SRWLock
0x180015e54  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180015e59  nop
0x180015e5a  jmp     loc_180015F0B
0x180015e5f  bt      r8d, 1Eh
0x180015e64  jnb     short loc_180015E7C
0x180015e66  mov     r9d, eax; unsigned int
0x180015e69  mov     edx, ecx; unsigned int
0x180015e6b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180015e72  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180015e77  jmp     loc_180015F0B
0x180015e7c  test    eax, eax
0x180015e7e  jnz     short loc_180015EFA
0x180015e80  cmp     r8d, 0FEh
0x180015e87  jz      short loc_180015EFA
0x180015e89  mov     [rsp+38h+var_18], 0
0x180015e92  mov     dword ptr [rsp+38h+var_18], ecx
0x180015e96  mov     word ptr [rsp+38h+var_18+4], r8w
0x180015e9c  test    edx, edx
0x180015e9e  jns     short loc_180015EA6
0x180015ea0  or      word ptr [rsp+38h+var_18+6], 1
0x180015ea6  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180015ead  test    rax, rax
0x180015eb0  jnz     short loc_180015EEE
0x180015eb2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180015eb9  test    rax, rax
0x180015ebc  jnz     short loc_180015ED2
0x180015ebe  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180015ec5  call    cs:__imp_GetModuleHandleW
0x180015ecb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180015ed2  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180015ed9  mov     rcx, rax; hModule
0x180015edc  call    cs:__imp_GetProcAddress
0x180015ee2  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180015ee9  test    rax, rax
0x180015eec  jz      short loc_180015F0B
0x180015eee  lea     rcx, [rsp+38h+var_18]
0x180015ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ef8  jmp     short loc_180015F0B
0x180015efa  mov     r9, rax
0x180015efd  mov     edx, ecx
0x180015eff  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180015f06  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180015f0b  add     rsp, 38h
0x180015f0f  retn
```
