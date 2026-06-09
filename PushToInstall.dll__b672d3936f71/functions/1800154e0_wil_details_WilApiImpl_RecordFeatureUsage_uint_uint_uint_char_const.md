# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x1800154e0`
- end: `0x180015600`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180012c0c`
- `0x180013620`
- `0x180013780`
- `0x180013eb0`
- `0x180014070`
- `0x1800154e0`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800155b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800155b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800155cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800155cc`

## string_xrefs

- `0x1800155ae`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180065348[25], qword_180065348);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180065348);
  }
}

```

## disassembly

```asm
0x1800154e0  sub     rsp, 38h
0x1800154e4  mov     eax, r8d
0x1800154e7  mov     r8d, edx
0x1800154ea  btr     r8d, 1Fh; unsigned __int16
0x1800154ef  test    ecx, ecx
0x1800154f1  jnz     short loc_18001554F
0x1800154f3  test    eax, eax
0x1800154f5  jnz     short loc_18001554F
0x1800154f7  test    r8d, r8d
0x1800154fa  jnz     short loc_18001554F
0x1800154fc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180015503  jnz     short loc_18001554A
0x180015505  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001550c  test    rax, rax
0x18001550f  jz      short loc_18001551A
0x180015511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015516  test    al, al
0x180015518  jnz     short loc_18001554A
0x18001551a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180015521  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180015526  test    al, al
0x180015528  jz      short loc_18001554A
0x18001552a  mov     rdx, cs:qword_180065348; SRWLock
0x180015531  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180015538  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18001553d  mov     rcx, cs:qword_180065348; SRWLock
0x180015544  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180015549  nop
0x18001554a  jmp     loc_1800155FB
0x18001554f  bt      r8d, 1Eh
0x180015554  jnb     short loc_18001556C
0x180015556  mov     r9d, eax; unsigned int
0x180015559  mov     edx, ecx; unsigned int
0x18001555b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180015562  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180015567  jmp     loc_1800155FB
0x18001556c  test    eax, eax
0x18001556e  jnz     short loc_1800155EA
0x180015570  cmp     r8d, 0FEh
0x180015577  jz      short loc_1800155EA
0x180015579  mov     [rsp+38h+var_18], 0
0x180015582  mov     dword ptr [rsp+38h+var_18], ecx
0x180015586  mov     word ptr [rsp+38h+var_18+4], r8w
0x18001558c  test    edx, edx
0x18001558e  jns     short loc_180015596
0x180015590  or      word ptr [rsp+38h+var_18+6], 1
0x180015596  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18001559d  test    rax, rax
0x1800155a0  jnz     short loc_1800155DE
0x1800155a2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800155a9  test    rax, rax
0x1800155ac  jnz     short loc_1800155C2
0x1800155ae  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800155b5  call    cs:__imp_GetModuleHandleW
0x1800155bb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800155c2  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x1800155c9  mov     rcx, rax; hModule
0x1800155cc  call    cs:__imp_GetProcAddress
0x1800155d2  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x1800155d9  test    rax, rax
0x1800155dc  jz      short loc_1800155FB
0x1800155de  lea     rcx, [rsp+38h+var_18]
0x1800155e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155e8  jmp     short loc_1800155FB
0x1800155ea  mov     r9, rax
0x1800155ed  mov     edx, ecx
0x1800155ef  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800155f6  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1800155fb  add     rsp, 38h
0x1800155ff  retn
```
