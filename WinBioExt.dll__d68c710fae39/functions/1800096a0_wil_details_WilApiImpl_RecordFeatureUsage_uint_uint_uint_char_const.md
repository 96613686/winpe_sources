# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x1800096a0`
- end: `0x1800097c0`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180007c00`
- `0x1800080c0`
- `0x180008184`
- `0x180008534`
- `0x1800086b8`
- `0x1800096a0`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009775`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009775`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000978c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000978c`

## string_xrefs

- `0x18000976e`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180010028[25], qword_180010028);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180010028);
  }
}

```

## disassembly

```asm
0x1800096a0  sub     rsp, 38h
0x1800096a4  mov     eax, r8d
0x1800096a7  mov     r8d, edx
0x1800096aa  btr     r8d, 1Fh; unsigned __int16
0x1800096af  test    ecx, ecx
0x1800096b1  jnz     short loc_18000970F
0x1800096b3  test    eax, eax
0x1800096b5  jnz     short loc_18000970F
0x1800096b7  test    r8d, r8d
0x1800096ba  jnz     short loc_18000970F
0x1800096bc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x1800096c3  jnz     short loc_18000970A
0x1800096c5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800096cc  test    rax, rax
0x1800096cf  jz      short loc_1800096DA
0x1800096d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096d6  test    al, al
0x1800096d8  jnz     short loc_18000970A
0x1800096da  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x1800096e1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800096e6  test    al, al
0x1800096e8  jz      short loc_18000970A
0x1800096ea  mov     rdx, cs:qword_180010028; SRWLock
0x1800096f1  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800096f8  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x1800096fd  mov     rcx, cs:qword_180010028; SRWLock
0x180009704  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180009709  nop
0x18000970a  jmp     loc_1800097BB
0x18000970f  bt      r8d, 1Eh
0x180009714  jnb     short loc_18000972C
0x180009716  mov     r9d, eax; unsigned int
0x180009719  mov     edx, ecx; unsigned int
0x18000971b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180009722  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180009727  jmp     loc_1800097BB
0x18000972c  test    eax, eax
0x18000972e  jnz     short loc_1800097AA
0x180009730  cmp     r8d, 0FEh
0x180009737  jz      short loc_1800097AA
0x180009739  mov     [rsp+38h+var_18], 0
0x180009742  mov     dword ptr [rsp+38h+var_18], ecx
0x180009746  mov     word ptr [rsp+38h+var_18+4], r8w
0x18000974c  test    edx, edx
0x18000974e  jns     short loc_180009756
0x180009750  or      word ptr [rsp+38h+var_18+6], 1
0x180009756  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000975d  test    rax, rax
0x180009760  jnz     short loc_18000979E
0x180009762  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009769  test    rax, rax
0x18000976c  jnz     short loc_180009782
0x18000976e  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180009775  call    cs:__imp_GetModuleHandleW
0x18000977b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009782  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180009789  mov     rcx, rax; hModule
0x18000978c  call    cs:__imp_GetProcAddress
0x180009792  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180009799  test    rax, rax
0x18000979c  jz      short loc_1800097BB
0x18000979e  lea     rcx, [rsp+38h+var_18]
0x1800097a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097a8  jmp     short loc_1800097BB
0x1800097aa  mov     r9, rax
0x1800097ad  mov     edx, ecx
0x1800097af  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800097b6  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1800097bb  add     rsp, 38h
0x1800097bf  retn
```
