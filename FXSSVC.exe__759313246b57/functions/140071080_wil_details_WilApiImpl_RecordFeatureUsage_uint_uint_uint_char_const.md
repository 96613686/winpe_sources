# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x140071080`
- end: `0x1400711b9`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `313`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x14006d07c`
- `0x14006e940`
- `0x14006eaf0`
- `0x14006eeb4`
- `0x14006f098`
- `0x140071080`
- `0x14008b010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14007117a`
- `KERNEL32!GetProcAddress` at `0x14007117a`
- `KERNEL32!GetModuleHandleW` at `0x14007115d`
- `KERNEL32!GetModuleHandleW` at `0x14007115d`

## string_xrefs

- `0x140071156`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&SRWLock[25], SRWLock);
    wil::details_abi::FeatureStateData::RecordUsage(SRWLock);
  }
}

```

## disassembly

```asm
0x140071080  sub     rsp, 38h
0x140071084  mov     eax, r8d
0x140071087  mov     r8d, edx
0x14007108a  btr     r8d, 1Fh; unsigned __int16
0x14007108f  test    ecx, ecx
0x140071091  jnz     short loc_1400710F0
0x140071093  test    eax, eax
0x140071095  jnz     short loc_1400710F0
0x140071097  test    r8d, r8d
0x14007109a  jnz     short loc_1400710F0
0x14007109c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x1400710a3  jnz     short loc_1400710EA
0x1400710a5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1400710ac  test    rax, rax
0x1400710af  jz      short loc_1400710BA
0x1400710b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400710b6  test    al, al
0x1400710b8  jnz     short loc_1400710EA
0x1400710ba  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x1400710c1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1400710c6  test    al, al
0x1400710c8  jz      short loc_1400710EA
0x1400710ca  mov     rdx, cs:SRWLock; SRWLock
0x1400710d1  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1400710d8  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x1400710dd  mov     rcx, cs:SRWLock; SRWLock
0x1400710e4  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1400710e9  nop
0x1400710ea  add     rsp, 38h
0x1400710ee  retn
0x1400710f0  bt      r8d, 1Eh
0x1400710f5  jnb     short loc_14007110C
0x1400710f7  mov     r9d, eax; unsigned int
0x1400710fa  mov     edx, ecx; unsigned int
0x1400710fc  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x140071103  add     rsp, 38h
0x140071107  jmp     ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x14007110c  test    eax, eax
0x14007110e  jnz     loc_1400711A2
0x140071114  cmp     r8d, 0FEh
0x14007111b  jz      loc_1400711A2
0x140071121  mov     [rsp+38h+var_18], 0
0x14007112a  mov     dword ptr [rsp+38h+var_18], ecx
0x14007112e  mov     word ptr [rsp+38h+var_18+4], r8w
0x140071134  test    edx, edx
0x140071136  jns     short loc_14007113E
0x140071138  or      word ptr [rsp+38h+var_18+6], 1
0x14007113e  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x140071145  test    rax, rax
0x140071148  jnz     short loc_140071192
0x14007114a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140071151  test    rax, rax
0x140071154  jnz     short loc_140071170
0x140071156  lea     rcx, ModuleName; "ntdll.dll"
0x14007115d  call    cs:__imp_GetModuleHandleW
0x140071164  nop     dword ptr [rax+rax+00h]
0x140071169  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140071170  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x140071177  mov     rcx, rax; hModule
0x14007117a  call    cs:__imp_GetProcAddress
0x140071181  nop     dword ptr [rax+rax+00h]
0x140071186  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x14007118d  test    rax, rax
0x140071190  jz      short loc_1400711B3
0x140071192  lea     rcx, [rsp+38h+var_18]
0x140071197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007119c  add     rsp, 38h
0x1400711a0  retn
0x1400711a2  mov     r9, rax
0x1400711a5  mov     edx, ecx
0x1400711a7  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1400711ae  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1400711b3  add     rsp, 38h
0x1400711b7  retn
```
