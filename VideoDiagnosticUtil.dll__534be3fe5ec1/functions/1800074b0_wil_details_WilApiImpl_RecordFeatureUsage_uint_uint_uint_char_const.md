# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x1800074b0`
- end: `0x1800075f2`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `322`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180003ce4`
- `0x180005044`
- `0x1800055b8`
- `0x18000595c`
- `0x180005b40`
- `0x1800074b0`
- `0x18000a010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800075b3`
- `KERNEL32!GetProcAddress` at `0x1800075b3`
- `KERNEL32!GetModuleHandleW` at `0x180007596`
- `KERNEL32!GetModuleHandleW` at `0x180007596`

## string_xrefs

- `0x18000758f`: `ntdll.dll`

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
        &wil::details::g_featureStateManager,
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
      ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&SRWLock[25], SRWLock);
    wil::details_abi::FeatureStateData::RecordUsage(SRWLock);
  }
}

```

## disassembly

```asm
0x1800074b0  sub     rsp, 38h
0x1800074b4  mov     eax, r8d
0x1800074b7  mov     r8d, edx
0x1800074ba  btr     r8d, 1Fh; unsigned __int16
0x1800074bf  test    ecx, ecx
0x1800074c1  jnz     short loc_180007529
0x1800074c3  test    eax, eax
0x1800074c5  jnz     short loc_180007529
0x1800074c7  test    r8d, r8d
0x1800074ca  jnz     short loc_180007529
0x1800074cc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x1800074d3  jnz     loc_1800075EC
0x1800074d9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800074e0  test    rax, rax
0x1800074e3  jz      short loc_1800074F2
0x1800074e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074ea  test    al, al
0x1800074ec  jnz     loc_1800075EC
0x1800074f2  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x1800074f9  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800074fe  test    al, al
0x180007500  jz      loc_1800075EC
0x180007506  mov     rdx, cs:SRWLock; SRWLock
0x18000750d  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180007514  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180007519  mov     rcx, cs:SRWLock; SRWLock
0x180007520  add     rsp, 38h
0x180007524  jmp     ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180007529  bt      r8d, 1Eh
0x18000752e  jnb     short loc_180007545
0x180007530  mov     edx, ecx; unsigned int
0x180007532  mov     r9d, eax; unsigned int
0x180007535  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000753c  add     rsp, 38h
0x180007540  jmp     ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180007545  test    eax, eax
0x180007547  jnz     loc_1800075DB
0x18000754d  cmp     r8d, 0FEh
0x180007554  jz      loc_1800075DB
0x18000755a  mov     [rsp+38h+var_18], 0
0x180007563  mov     dword ptr [rsp+38h+var_18], ecx
0x180007567  mov     word ptr [rsp+38h+var_18+4], r8w
0x18000756d  test    edx, edx
0x18000756f  jns     short loc_180007577
0x180007571  or      word ptr [rsp+38h+var_18+6], 1
0x180007577  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000757e  test    rax, rax
0x180007581  jnz     short loc_1800075CB
0x180007583  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000758a  test    rax, rax
0x18000758d  jnz     short loc_1800075A9
0x18000758f  lea     rcx, ModuleName; "ntdll.dll"
0x180007596  call    cs:__imp_GetModuleHandleW
0x18000759d  nop     dword ptr [rax+rax+00h]
0x1800075a2  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800075a9  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x1800075b0  mov     rcx, rax; hModule
0x1800075b3  call    cs:__imp_GetProcAddress
0x1800075ba  nop     dword ptr [rax+rax+00h]
0x1800075bf  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x1800075c6  test    rax, rax
0x1800075c9  jz      short loc_1800075EC
0x1800075cb  lea     rcx, [rsp+38h+var_18]
0x1800075d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075d5  add     rsp, 38h
0x1800075d9  retn
0x1800075db  mov     edx, ecx
0x1800075dd  mov     r9, rax
0x1800075e0  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800075e7  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1800075ec  add     rsp, 38h
0x1800075f0  retn
```
