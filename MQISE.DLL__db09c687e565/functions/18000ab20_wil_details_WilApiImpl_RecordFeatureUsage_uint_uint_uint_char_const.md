# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000ab20`
- end: `0x18000ac41`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `289`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1800059dc`
- `0x180007ca4`
- `0x180007f44`
- `0x180008704`
- `0x180008900`
- `0x18000ab20`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000abf5`
- `KERNEL32!GetModuleHandleW` at `0x18000abf5`
- `KERNEL32!GetProcAddress` at `0x18000ac0c`
- `KERNEL32!GetProcAddress` at `0x18000ac0c`

## string_xrefs

- `0x18000abee`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180017038[25], qword_180017038);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180017038);
  }
}

```

## disassembly

```asm
0x18000ab20  sub     rsp, 38h
0x18000ab24  mov     eax, r8d
0x18000ab27  mov     r8d, edx
0x18000ab2a  btr     r8d, 1Fh; unsigned __int16
0x18000ab2f  test    ecx, ecx
0x18000ab31  jnz     short loc_18000AB8F
0x18000ab33  test    eax, eax
0x18000ab35  jnz     short loc_18000AB8F
0x18000ab37  test    r8d, r8d
0x18000ab3a  jnz     short loc_18000AB8F
0x18000ab3c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x18000ab43  jnz     short loc_18000AB8A
0x18000ab45  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000ab4c  test    rax, rax
0x18000ab4f  jz      short loc_18000AB5A
0x18000ab51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab56  test    al, al
0x18000ab58  jnz     short loc_18000AB8A
0x18000ab5a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000ab61  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000ab66  test    al, al
0x18000ab68  jz      short loc_18000AB8A
0x18000ab6a  mov     rdx, cs:qword_180017038; SRWLock
0x18000ab71  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000ab78  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000ab7d  mov     rcx, cs:qword_180017038; SRWLock
0x18000ab84  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000ab89  nop
0x18000ab8a  jmp     loc_18000AC3C
0x18000ab8f  bt      r8d, 1Eh
0x18000ab94  jnb     short loc_18000ABAC
0x18000ab96  mov     r9d, eax; unsigned int
0x18000ab99  mov     edx, ecx; unsigned int
0x18000ab9b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000aba2  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18000aba7  jmp     loc_18000AC3C
0x18000abac  test    eax, eax
0x18000abae  jnz     short loc_18000AC2B
0x18000abb0  cmp     r8d, 0FEh
0x18000abb7  jz      short loc_18000AC2B
0x18000abb9  mov     [rsp+38h+var_18], 0
0x18000abc2  mov     dword ptr [rsp+38h+var_18], ecx
0x18000abc6  mov     word ptr [rsp+38h+var_18+4], r8w
0x18000abcc  test    edx, edx
0x18000abce  jns     short loc_18000ABD6
0x18000abd0  or      word ptr [rsp+38h+var_18+6], 1
0x18000abd6  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000abdd  test    rax, rax
0x18000abe0  jnz     short loc_18000AC1F
0x18000abe2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000abe9  test    rax, rax
0x18000abec  jnz     short loc_18000AC02
0x18000abee  lea     rcx, ModuleName; "ntdll.dll"
0x18000abf5  call    cs:__imp_GetModuleHandleW
0x18000abfb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ac02  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000ac09  mov     rcx, rax; hModule
0x18000ac0c  call    cs:__imp_GetProcAddress
0x18000ac12  nop
0x18000ac13  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000ac1a  test    rax, rax
0x18000ac1d  jz      short loc_18000AC3C
0x18000ac1f  lea     rcx, [rsp+38h+var_18]
0x18000ac24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac29  jmp     short loc_18000AC3C
0x18000ac2b  mov     r9, rax
0x18000ac2e  mov     edx, ecx
0x18000ac30  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000ac37  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000ac3c  add     rsp, 38h
0x18000ac40  retn
```
