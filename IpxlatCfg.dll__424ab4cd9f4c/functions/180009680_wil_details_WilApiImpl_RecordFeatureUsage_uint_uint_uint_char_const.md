# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180009680`
- end: `0x1800097a0`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1800053e4`
- `0x180006b74`
- `0x180006d78`
- `0x180007364`
- `0x180007560`
- `0x180009680`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000976c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000976c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009755`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009755`

## string_xrefs

- `0x18000974e`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_1800230B8[25], qword_1800230B8);
    wil::details_abi::FeatureStateData::RecordUsage(qword_1800230B8);
  }
}

```

## disassembly

```asm
0x180009680  sub     rsp, 38h
0x180009684  mov     eax, r8d
0x180009687  mov     r8d, edx
0x18000968a  btr     r8d, 1Fh; unsigned __int16
0x18000968f  test    ecx, ecx
0x180009691  jnz     short loc_1800096EF
0x180009693  test    eax, eax
0x180009695  jnz     short loc_1800096EF
0x180009697  test    r8d, r8d
0x18000969a  jnz     short loc_1800096EF
0x18000969c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x1800096a3  jnz     short loc_1800096EA
0x1800096a5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800096ac  test    rax, rax
0x1800096af  jz      short loc_1800096BA
0x1800096b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096b6  test    al, al
0x1800096b8  jnz     short loc_1800096EA
0x1800096ba  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x1800096c1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800096c6  test    al, al
0x1800096c8  jz      short loc_1800096EA
0x1800096ca  mov     rdx, cs:qword_1800230B8; SRWLock
0x1800096d1  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800096d8  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x1800096dd  mov     rcx, cs:qword_1800230B8; SRWLock
0x1800096e4  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800096e9  nop
0x1800096ea  jmp     loc_18000979B
0x1800096ef  bt      r8d, 1Eh
0x1800096f4  jnb     short loc_18000970C
0x1800096f6  mov     r9d, eax; unsigned int
0x1800096f9  mov     edx, ecx; unsigned int
0x1800096fb  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180009702  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180009707  jmp     loc_18000979B
0x18000970c  test    eax, eax
0x18000970e  jnz     short loc_18000978A
0x180009710  cmp     r8d, 0FEh
0x180009717  jz      short loc_18000978A
0x180009719  mov     [rsp+38h+var_18], 0
0x180009722  mov     dword ptr [rsp+38h+var_18], ecx
0x180009726  mov     word ptr [rsp+38h+var_18+4], r8w
0x18000972c  test    edx, edx
0x18000972e  jns     short loc_180009736
0x180009730  or      word ptr [rsp+38h+var_18+6], 1
0x180009736  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000973d  test    rax, rax
0x180009740  jnz     short loc_18000977E
0x180009742  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009749  test    rax, rax
0x18000974c  jnz     short loc_180009762
0x18000974e  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180009755  call    cs:__imp_GetModuleHandleW
0x18000975b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009762  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180009769  mov     rcx, rax; hModule
0x18000976c  call    cs:__imp_GetProcAddress
0x180009772  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180009779  test    rax, rax
0x18000977c  jz      short loc_18000979B
0x18000977e  lea     rcx, [rsp+38h+var_18]
0x180009783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009788  jmp     short loc_18000979B
0x18000978a  mov     r9, rax
0x18000978d  mov     edx, ecx
0x18000978f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180009796  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000979b  add     rsp, 38h
0x18000979f  retn
```
