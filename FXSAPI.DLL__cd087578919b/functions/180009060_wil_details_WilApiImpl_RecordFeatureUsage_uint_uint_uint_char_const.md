# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180009060`
- end: `0x180009199`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `313`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000410c`
- `0x180006180`
- `0x180006790`
- `0x180006b54`
- `0x180006d38`
- `0x180009060`
- `0x18003e010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000915a`
- `KERNEL32!GetProcAddress` at `0x18000915a`
- `KERNEL32!GetModuleHandleW` at `0x18000913d`
- `KERNEL32!GetModuleHandleW` at `0x18000913d`

## string_xrefs

- `0x180009136`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_18004E040[25], qword_18004E040);
    wil::details_abi::FeatureStateData::RecordUsage(qword_18004E040);
  }
}

```

## disassembly

```asm
0x180009060  sub     rsp, 38h
0x180009064  mov     eax, r8d
0x180009067  mov     r8d, edx
0x18000906a  btr     r8d, 1Fh; unsigned __int16
0x18000906f  test    ecx, ecx
0x180009071  jnz     short loc_1800090D0
0x180009073  test    eax, eax
0x180009075  jnz     short loc_1800090D0
0x180009077  test    r8d, r8d
0x18000907a  jnz     short loc_1800090D0
0x18000907c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180009083  jnz     short loc_1800090CA
0x180009085  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000908c  test    rax, rax
0x18000908f  jz      short loc_18000909A
0x180009091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009096  test    al, al
0x180009098  jnz     short loc_1800090CA
0x18000909a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x1800090a1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800090a6  test    al, al
0x1800090a8  jz      short loc_1800090CA
0x1800090aa  mov     rdx, cs:qword_18004E040; SRWLock
0x1800090b1  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800090b8  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x1800090bd  mov     rcx, cs:qword_18004E040; SRWLock
0x1800090c4  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800090c9  nop
0x1800090ca  add     rsp, 38h
0x1800090ce  retn
0x1800090d0  bt      r8d, 1Eh
0x1800090d5  jnb     short loc_1800090EC
0x1800090d7  mov     r9d, eax; unsigned int
0x1800090da  mov     edx, ecx; unsigned int
0x1800090dc  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x1800090e3  add     rsp, 38h
0x1800090e7  jmp     ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x1800090ec  test    eax, eax
0x1800090ee  jnz     loc_180009182
0x1800090f4  cmp     r8d, 0FEh
0x1800090fb  jz      loc_180009182
0x180009101  mov     [rsp+38h+var_18], 0
0x18000910a  mov     dword ptr [rsp+38h+var_18], ecx
0x18000910e  mov     word ptr [rsp+38h+var_18+4], r8w
0x180009114  test    edx, edx
0x180009116  jns     short loc_18000911E
0x180009118  or      word ptr [rsp+38h+var_18+6], 1
0x18000911e  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180009125  test    rax, rax
0x180009128  jnz     short loc_180009172
0x18000912a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009131  test    rax, rax
0x180009134  jnz     short loc_180009150
0x180009136  lea     rcx, ModuleName; "ntdll.dll"
0x18000913d  call    cs:__imp_GetModuleHandleW
0x180009144  nop     dword ptr [rax+rax+00h]
0x180009149  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009150  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180009157  mov     rcx, rax; hModule
0x18000915a  call    cs:__imp_GetProcAddress
0x180009161  nop     dword ptr [rax+rax+00h]
0x180009166  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000916d  test    rax, rax
0x180009170  jz      short loc_180009193
0x180009172  lea     rcx, [rsp+38h+var_18]
0x180009177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000917c  add     rsp, 38h
0x180009180  retn
0x180009182  mov     r9, rax
0x180009185  mov     edx, ecx
0x180009187  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000918e  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180009193  add     rsp, 38h
0x180009197  retn
```
