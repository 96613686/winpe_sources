# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000ffd0`
- end: `0x1800100fd`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `301`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000b1a4`
- `0x18000cf9c`
- `0x18000d2c8`
- `0x18000d854`
- `0x18000da84`
- `0x18000ffd0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800100bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800100bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800100a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800100a2`

## string_xrefs

- `0x18001009b`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::WilApiImpl_RecordFeatureUsage(wil::details *this, int a2, unsigned int a3)
{
  unsigned int v4; // edx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v7; // [rsp+20h] [rbp-18h] BYREF
  int v8; // [rsp+24h] [rbp-14h]

  v4 = a2 & 0x7FFFFFFF;
  if ( (_DWORD)this || a3 || v4 )
  {
    if ( (v4 & 0x40000000) != 0 )
    {
      wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        (RTL_SRWLOCK *)&wil::details::g_featureStateManager,
        (int)this,
        v4,
        a3);
    }
    else if ( a3 || v4 == 254 )
    {
      wil::details::FeatureStateManager::RecordFeatureUsage(
        &wil::details::g_featureStateManager,
        (unsigned int)this,
        v4,
        a3);
    }
    else
    {
      v7 = (int)this;
      v8 = (unsigned __int16)v4;
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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_18003C080[25], qword_18003C080);
    wil::details_abi::FeatureStateData::RecordUsage(qword_18003C080);
  }
}

```

## disassembly

```asm
0x18000ffd0  sub     rsp, 38h
0x18000ffd4  mov     eax, edx
0x18000ffd6  btr     edx, 1Fh
0x18000ffda  test    ecx, ecx
0x18000ffdc  jnz     short loc_180010039
0x18000ffde  test    r8d, r8d
0x18000ffe1  jnz     short loc_180010039
0x18000ffe3  test    edx, edx
0x18000ffe5  jnz     short loc_180010039
0x18000ffe7  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, dl; bool wil::details::g_processShutdownInProgress
0x18000ffed  jnz     short loc_180010034
0x18000ffef  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000fff6  test    rax, rax
0x18000fff9  jz      short loc_180010004
0x18000fffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010000  test    al, al
0x180010002  jnz     short loc_180010034
0x180010004  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18001000b  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180010010  test    al, al
0x180010012  jz      short loc_180010034
0x180010014  mov     rdx, cs:qword_18003C080; SRWLock
0x18001001b  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180010022  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180010027  mov     rcx, cs:qword_18003C080; SRWLock
0x18001002e  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180010033  nop
0x180010034  jmp     loc_1800100F7
0x180010039  bt      edx, 1Eh
0x18001003d  jnb     short loc_180010059
0x18001003f  mov     r9d, r8d; unsigned int
0x180010042  movzx   r8d, dx; unsigned __int16
0x180010046  mov     edx, ecx; unsigned int
0x180010048  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18001004f  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180010054  jmp     loc_1800100F7
0x180010059  test    r8d, r8d
0x18001005c  jnz     loc_1800100E3
0x180010062  cmp     edx, 0FEh
0x180010068  jz      short loc_1800100E3
0x18001006a  and     [rsp+38h+var_18], 0
0x180010070  mov     dword ptr [rsp+38h+var_18], ecx
0x180010074  mov     word ptr [rsp+38h+var_18+4], dx
0x180010079  test    eax, eax
0x18001007b  jns     short loc_180010083
0x18001007d  or      word ptr [rsp+38h+var_18+6], 1
0x180010083  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18001008a  test    rax, rax
0x18001008d  jnz     short loc_1800100D7
0x18001008f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180010096  test    rax, rax
0x180010099  jnz     short loc_1800100B5
0x18001009b  lea     rcx, aNtdllDll; "ntdll.dll"
0x1800100a2  call    cs:__imp_GetModuleHandleW
0x1800100a9  nop     dword ptr [rax+rax+00h]
0x1800100ae  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800100b5  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x1800100bc  mov     rcx, rax; hModule
0x1800100bf  call    cs:__imp_GetProcAddress
0x1800100c6  nop     dword ptr [rax+rax+00h]
0x1800100cb  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x1800100d2  test    rax, rax
0x1800100d5  jz      short loc_1800100F7
0x1800100d7  lea     rcx, [rsp+38h+var_18]
0x1800100dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100e1  jmp     short loc_1800100F7
0x1800100e3  mov     r9d, r8d
0x1800100e6  mov     r8d, edx
0x1800100e9  mov     edx, ecx
0x1800100eb  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800100f2  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1800100f7  add     rsp, 38h
0x1800100fb  retn
```
