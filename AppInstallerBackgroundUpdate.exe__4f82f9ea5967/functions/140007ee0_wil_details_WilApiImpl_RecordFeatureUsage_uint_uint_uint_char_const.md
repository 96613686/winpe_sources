# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x140007ee0`
- end: `0x140008000`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x14000645c`
- `0x14000691c`
- `0x1400069e0`
- `0x140006d90`
- `0x140006f14`
- `0x140007ee0`
- `0x140009010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007fb5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007fb5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140007fcc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140007fcc`

## string_xrefs

- `0x140007fae`: `ntdll.dll`

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
         && wil::details::FeatureStateManager::EnsureStateData((RTL_SRWLOCK *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_14000D028[25], qword_14000D028);
    wil::details_abi::FeatureStateData::RecordUsage(qword_14000D028);
  }
}

```

## disassembly

```asm
0x140007ee0  sub     rsp, 38h
0x140007ee4  mov     eax, r8d
0x140007ee7  mov     r8d, edx
0x140007eea  btr     r8d, 1Fh; unsigned __int16
0x140007eef  test    ecx, ecx
0x140007ef1  jnz     short loc_140007F4F
0x140007ef3  test    eax, eax
0x140007ef5  jnz     short loc_140007F4F
0x140007ef7  test    r8d, r8d
0x140007efa  jnz     short loc_140007F4F
0x140007efc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x140007f03  jnz     short loc_140007F4A
0x140007f05  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140007f0c  test    rax, rax
0x140007f0f  jz      short loc_140007F1A
0x140007f11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007f16  test    al, al
0x140007f18  jnz     short loc_140007F4A
0x140007f1a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x140007f21  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x140007f26  test    al, al
0x140007f28  jz      short loc_140007F4A
0x140007f2a  mov     rdx, cs:qword_14000D028; SRWLock
0x140007f31  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x140007f38  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x140007f3d  mov     rcx, cs:qword_14000D028; SRWLock
0x140007f44  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x140007f49  nop
0x140007f4a  jmp     loc_140007FFB
0x140007f4f  bt      r8d, 1Eh
0x140007f54  jnb     short loc_140007F6C
0x140007f56  mov     r9d, eax; unsigned int
0x140007f59  mov     edx, ecx; unsigned int
0x140007f5b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x140007f62  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x140007f67  jmp     loc_140007FFB
0x140007f6c  test    eax, eax
0x140007f6e  jnz     short loc_140007FEA
0x140007f70  cmp     r8d, 0FEh
0x140007f77  jz      short loc_140007FEA
0x140007f79  mov     [rsp+38h+var_18], 0
0x140007f82  mov     dword ptr [rsp+38h+var_18], ecx
0x140007f86  mov     word ptr [rsp+38h+var_18+4], r8w
0x140007f8c  test    edx, edx
0x140007f8e  jns     short loc_140007F96
0x140007f90  or      word ptr [rsp+38h+var_18+6], 1
0x140007f96  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x140007f9d  test    rax, rax
0x140007fa0  jnz     short loc_140007FDE
0x140007fa2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140007fa9  test    rax, rax
0x140007fac  jnz     short loc_140007FC2
0x140007fae  lea     rcx, ModuleName; "ntdll.dll"
0x140007fb5  call    cs:__imp_GetModuleHandleW
0x140007fbb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140007fc2  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x140007fc9  mov     rcx, rax; hModule
0x140007fcc  call    cs:__imp_GetProcAddress
0x140007fd2  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x140007fd9  test    rax, rax
0x140007fdc  jz      short loc_140007FFB
0x140007fde  lea     rcx, [rsp+38h+var_18]
0x140007fe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007fe8  jmp     short loc_140007FFB
0x140007fea  mov     r9, rax
0x140007fed  mov     edx, ecx
0x140007fef  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x140007ff6  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x140007ffb  add     rsp, 38h
0x140007fff  retn
```
