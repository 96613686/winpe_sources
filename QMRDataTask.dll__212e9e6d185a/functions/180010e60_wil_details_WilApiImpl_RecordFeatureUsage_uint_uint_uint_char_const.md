# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180010e60`
- end: `0x180010f80`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1800077c8`
- `0x18000c054`
- `0x18000c6bc`
- `0x18000cdd4`
- `0x18000cfd0`
- `0x180010e60`
- `0x180015010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180010f4c`
- `KERNEL32!GetProcAddress` at `0x180010f4c`
- `KERNEL32!GetModuleHandleW` at `0x180010f35`
- `KERNEL32!GetModuleHandleW` at `0x180010f35`

## string_xrefs

- `0x180010f2e`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180023110[25], qword_180023110);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180023110);
  }
}

```

## disassembly

```asm
0x180010e60  sub     rsp, 38h
0x180010e64  mov     eax, r8d
0x180010e67  mov     r8d, edx
0x180010e6a  btr     r8d, 1Fh; unsigned __int16
0x180010e6f  test    ecx, ecx
0x180010e71  jnz     short loc_180010ECF
0x180010e73  test    eax, eax
0x180010e75  jnz     short loc_180010ECF
0x180010e77  test    r8d, r8d
0x180010e7a  jnz     short loc_180010ECF
0x180010e7c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180010e83  jnz     short loc_180010ECA
0x180010e85  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180010e8c  test    rax, rax
0x180010e8f  jz      short loc_180010E9A
0x180010e91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e96  test    al, al
0x180010e98  jnz     short loc_180010ECA
0x180010e9a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180010ea1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180010ea6  test    al, al
0x180010ea8  jz      short loc_180010ECA
0x180010eaa  mov     rdx, cs:qword_180023110; SRWLock
0x180010eb1  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180010eb8  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180010ebd  mov     rcx, cs:qword_180023110; SRWLock
0x180010ec4  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180010ec9  nop
0x180010eca  jmp     loc_180010F7B
0x180010ecf  bt      r8d, 1Eh
0x180010ed4  jnb     short loc_180010EEC
0x180010ed6  mov     r9d, eax; unsigned int
0x180010ed9  mov     edx, ecx; unsigned int
0x180010edb  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180010ee2  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180010ee7  jmp     loc_180010F7B
0x180010eec  test    eax, eax
0x180010eee  jnz     short loc_180010F6A
0x180010ef0  cmp     r8d, 0FEh
0x180010ef7  jz      short loc_180010F6A
0x180010ef9  mov     [rsp+38h+var_18], 0
0x180010f02  mov     dword ptr [rsp+38h+var_18], ecx
0x180010f06  mov     word ptr [rsp+38h+var_18+4], r8w
0x180010f0c  test    edx, edx
0x180010f0e  jns     short loc_180010F16
0x180010f10  or      word ptr [rsp+38h+var_18+6], 1
0x180010f16  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180010f1d  test    rax, rax
0x180010f20  jnz     short loc_180010F5E
0x180010f22  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180010f29  test    rax, rax
0x180010f2c  jnz     short loc_180010F42
0x180010f2e  lea     rcx, ModuleName; "ntdll.dll"
0x180010f35  call    cs:__imp_GetModuleHandleW
0x180010f3b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180010f42  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180010f49  mov     rcx, rax; hModule
0x180010f4c  call    cs:__imp_GetProcAddress
0x180010f52  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180010f59  test    rax, rax
0x180010f5c  jz      short loc_180010F7B
0x180010f5e  lea     rcx, [rsp+38h+var_18]
0x180010f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f68  jmp     short loc_180010F7B
0x180010f6a  mov     r9, rax
0x180010f6d  mov     edx, ecx
0x180010f6f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180010f76  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180010f7b  add     rsp, 38h
0x180010f7f  retn
```
