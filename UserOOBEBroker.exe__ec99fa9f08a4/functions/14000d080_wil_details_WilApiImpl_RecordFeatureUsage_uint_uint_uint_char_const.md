# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x14000d080`
- end: `0x14000d1a0`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x140008f64`
- `0x14000a86c`
- `0x14000aba0`
- `0x14000b288`
- `0x14000b440`
- `0x14000d080`
- `0x14000f010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000d16c`
- `KERNEL32!GetProcAddress` at `0x14000d16c`
- `KERNEL32!GetModuleHandleW` at `0x14000d155`
- `KERNEL32!GetModuleHandleW` at `0x14000d155`

## string_xrefs

- `0x14000d14e`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_1400170B0[25], qword_1400170B0);
    wil::details_abi::FeatureStateData::RecordUsage(qword_1400170B0);
  }
}

```

## disassembly

```asm
0x14000d080  sub     rsp, 38h
0x14000d084  mov     eax, r8d
0x14000d087  mov     r8d, edx
0x14000d08a  btr     r8d, 1Fh; unsigned __int16
0x14000d08f  test    ecx, ecx
0x14000d091  jnz     short loc_14000D0EF
0x14000d093  test    eax, eax
0x14000d095  jnz     short loc_14000D0EF
0x14000d097  test    r8d, r8d
0x14000d09a  jnz     short loc_14000D0EF
0x14000d09c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x14000d0a3  jnz     short loc_14000D0EA
0x14000d0a5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000d0ac  test    rax, rax
0x14000d0af  jz      short loc_14000D0BA
0x14000d0b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d0b6  test    al, al
0x14000d0b8  jnz     short loc_14000D0EA
0x14000d0ba  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14000d0c1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14000d0c6  test    al, al
0x14000d0c8  jz      short loc_14000D0EA
0x14000d0ca  mov     rdx, cs:qword_1400170B0; SRWLock
0x14000d0d1  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x14000d0d8  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x14000d0dd  mov     rcx, cs:qword_1400170B0; SRWLock
0x14000d0e4  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14000d0e9  nop
0x14000d0ea  jmp     loc_14000D19B
0x14000d0ef  bt      r8d, 1Eh
0x14000d0f4  jnb     short loc_14000D10C
0x14000d0f6  mov     r9d, eax; unsigned int
0x14000d0f9  mov     edx, ecx; unsigned int
0x14000d0fb  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x14000d102  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x14000d107  jmp     loc_14000D19B
0x14000d10c  test    eax, eax
0x14000d10e  jnz     short loc_14000D18A
0x14000d110  cmp     r8d, 0FEh
0x14000d117  jz      short loc_14000D18A
0x14000d119  mov     [rsp+38h+var_18], 0
0x14000d122  mov     dword ptr [rsp+38h+var_18], ecx
0x14000d126  mov     word ptr [rsp+38h+var_18+4], r8w
0x14000d12c  test    edx, edx
0x14000d12e  jns     short loc_14000D136
0x14000d130  or      word ptr [rsp+38h+var_18+6], 1
0x14000d136  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x14000d13d  test    rax, rax
0x14000d140  jnz     short loc_14000D17E
0x14000d142  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000d149  test    rax, rax
0x14000d14c  jnz     short loc_14000D162
0x14000d14e  lea     rcx, ModuleName; "ntdll.dll"
0x14000d155  call    cs:__imp_GetModuleHandleW
0x14000d15b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000d162  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x14000d169  mov     rcx, rax; hModule
0x14000d16c  call    cs:__imp_GetProcAddress
0x14000d172  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x14000d179  test    rax, rax
0x14000d17c  jz      short loc_14000D19B
0x14000d17e  lea     rcx, [rsp+38h+var_18]
0x14000d183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d188  jmp     short loc_14000D19B
0x14000d18a  mov     r9, rax
0x14000d18d  mov     edx, ecx
0x14000d18f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000d196  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x14000d19b  add     rsp, 38h
0x14000d19f  retn
```
