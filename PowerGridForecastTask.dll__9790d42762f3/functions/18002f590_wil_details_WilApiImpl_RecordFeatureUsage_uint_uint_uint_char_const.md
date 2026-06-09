# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18002f590`
- end: `0x18002f6b0`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180029980`
- `0x18002bcec`
- `0x18002c09c`
- `0x18002c7b4`
- `0x18002c9b0`
- `0x18002f590`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f67c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f67c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002f665`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002f665`

## string_xrefs

- `0x18002f65e`: `ntdll.dll`

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
         && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180046098[25], qword_180046098);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180046098);
  }
}

```

## disassembly

```asm
0x18002f590  sub     rsp, 38h
0x18002f594  mov     eax, r8d
0x18002f597  mov     r8d, edx
0x18002f59a  btr     r8d, 1Fh; unsigned __int16
0x18002f59f  test    ecx, ecx
0x18002f5a1  jnz     short loc_18002F5FF
0x18002f5a3  test    eax, eax
0x18002f5a5  jnz     short loc_18002F5FF
0x18002f5a7  test    r8d, r8d
0x18002f5aa  jnz     short loc_18002F5FF
0x18002f5ac  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x18002f5b3  jnz     short loc_18002F5FA
0x18002f5b5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18002f5bc  test    rax, rax
0x18002f5bf  jz      short loc_18002F5CA
0x18002f5c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f5c6  test    al, al
0x18002f5c8  jnz     short loc_18002F5FA
0x18002f5ca  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18002f5d1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18002f5d6  test    al, al
0x18002f5d8  jz      short loc_18002F5FA
0x18002f5da  mov     rdx, cs:qword_180046098; SRWLock
0x18002f5e1  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18002f5e8  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18002f5ed  mov     rcx, cs:qword_180046098; SRWLock
0x18002f5f4  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18002f5f9  nop
0x18002f5fa  jmp     loc_18002F6AB
0x18002f5ff  bt      r8d, 1Eh
0x18002f604  jnb     short loc_18002F61C
0x18002f606  mov     r9d, eax; unsigned int
0x18002f609  mov     edx, ecx; unsigned int
0x18002f60b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18002f612  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18002f617  jmp     loc_18002F6AB
0x18002f61c  test    eax, eax
0x18002f61e  jnz     short loc_18002F69A
0x18002f620  cmp     r8d, 0FEh
0x18002f627  jz      short loc_18002F69A
0x18002f629  mov     [rsp+38h+var_18], 0
0x18002f632  mov     dword ptr [rsp+38h+var_18], ecx
0x18002f636  mov     word ptr [rsp+38h+var_18+4], r8w
0x18002f63c  test    edx, edx
0x18002f63e  jns     short loc_18002F646
0x18002f640  or      word ptr [rsp+38h+var_18+6], 1
0x18002f646  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18002f64d  test    rax, rax
0x18002f650  jnz     short loc_18002F68E
0x18002f652  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002f659  test    rax, rax
0x18002f65c  jnz     short loc_18002F672
0x18002f65e  lea     rcx, ModuleName; "ntdll.dll"
0x18002f665  call    cs:__imp_GetModuleHandleW
0x18002f66b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002f672  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18002f679  mov     rcx, rax; hModule
0x18002f67c  call    cs:__imp_GetProcAddress
0x18002f682  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18002f689  test    rax, rax
0x18002f68c  jz      short loc_18002F6AB
0x18002f68e  lea     rcx, [rsp+38h+var_18]
0x18002f693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f698  jmp     short loc_18002F6AB
0x18002f69a  mov     r9, rax
0x18002f69d  mov     edx, ecx
0x18002f69f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18002f6a6  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18002f6ab  add     rsp, 38h
0x18002f6af  retn
```
