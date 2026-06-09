# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x1800278c0`
- end: `0x1800279eb`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `299`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180024394`
- `0x180025ab4`
- `0x180025c1c`
- `0x180026004`
- `0x1800261bc`
- `0x1800278c0`
- `0x18005d010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800279a0`
- `KERNEL32!GetModuleHandleW` at `0x1800279a0`
- `KERNEL32!GetProcAddress` at `0x1800279b7`
- `KERNEL32!GetProcAddress` at `0x1800279b7`

## string_xrefs

- `0x180027999`: `ntdll.dll`

## pseudocode

```c
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
        goto LABEL_19;
      ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
      if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
      {
        ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
        `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
      }
      ProcAddress = GetProcAddress(ModuleHandleW, "RtlNotifyFeatureUsage");
      g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)ProcAddress;
      if ( ProcAddress )
LABEL_19:
        ((void (__fastcall *)(int *))ProcAddress)(&v7);
    }
  }
  else if ( !wil::details::g_processShutdownInProgress
         && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress())
         && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180072198[25], qword_180072198);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180072198);
  }
}

```

## disassembly

```asm
0x1800278c0  sub     rsp, 38h
0x1800278c4  mov     eax, r8d
0x1800278c7  mov     r8d, edx
0x1800278ca  btr     r8d, 1Fh; unsigned __int16
0x1800278cf  test    ecx, ecx
0x1800278d1  jnz     short loc_18002793A
0x1800278d3  test    eax, eax
0x1800278d5  jnz     short loc_18002793A
0x1800278d7  test    r8d, r8d
0x1800278da  jnz     short loc_18002793A
0x1800278dc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x1800278e3  jnz     loc_1800279E6
0x1800278e9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800278f0  test    rax, rax
0x1800278f3  jz      short loc_180027902
0x1800278f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278fa  test    al, al
0x1800278fc  jnz     loc_1800279E6
0x180027902  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180027909  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18002790e  test    al, al
0x180027910  jz      loc_1800279E6
0x180027916  mov     rdx, cs:qword_180072198; SRWLock
0x18002791d  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180027924  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180027929  mov     rcx, cs:qword_180072198; SRWLock
0x180027930  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180027935  jmp     loc_1800279E6
0x18002793a  bt      r8d, 1Eh
0x18002793f  jnb     short loc_180027957
0x180027941  mov     edx, ecx; unsigned int
0x180027943  mov     r9d, eax; unsigned int
0x180027946  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18002794d  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180027952  jmp     loc_1800279E6
0x180027957  test    eax, eax
0x180027959  jnz     short loc_1800279D5
0x18002795b  cmp     r8d, 0FEh
0x180027962  jz      short loc_1800279D5
0x180027964  mov     [rsp+38h+var_18], 0
0x18002796d  mov     dword ptr [rsp+38h+var_18], ecx
0x180027971  mov     word ptr [rsp+38h+var_18+4], r8w
0x180027977  test    edx, edx
0x180027979  jns     short loc_180027981
0x18002797b  or      word ptr [rsp+38h+var_18+6], 1
0x180027981  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180027988  test    rax, rax
0x18002798b  jnz     short loc_1800279C9
0x18002798d  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180027994  test    rax, rax
0x180027997  jnz     short loc_1800279AD
0x180027999  lea     rcx, aNtdllDll; "ntdll.dll"
0x1800279a0  call    cs:__imp_GetModuleHandleW
0x1800279a6  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800279ad  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x1800279b4  mov     rcx, rax; hModule
0x1800279b7  call    cs:__imp_GetProcAddress
0x1800279bd  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x1800279c4  test    rax, rax
0x1800279c7  jz      short loc_1800279E6
0x1800279c9  lea     rcx, [rsp+38h+var_18]
0x1800279ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279d3  jmp     short loc_1800279E6
0x1800279d5  mov     edx, ecx
0x1800279d7  mov     r9, rax
0x1800279da  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800279e1  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1800279e6  add     rsp, 38h
0x1800279ea  retn
```
