# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x14000a210`
- end: `0x14000a33b`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `299`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x140004c64`
- `0x14000749c`
- `0x1400077a0`
- `0x140007f14`
- `0x140008100`
- `0x14000a210`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000a307`
- `KERNEL32!GetProcAddress` at `0x14000a307`
- `KERNEL32!GetModuleHandleW` at `0x14000a2f0`
- `KERNEL32!GetModuleHandleW` at `0x14000a2f0`

## string_xrefs

- `0x14000a2e9`: `ntdll.dll`

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
         && wil::details::FeatureStateManager::EnsureStateData((RTL_SRWLOCK *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_1400203C8[25], qword_1400203C8);
    wil::details_abi::FeatureStateData::RecordUsage(qword_1400203C8);
  }
}

```

## disassembly

```asm
0x14000a210  sub     rsp, 38h
0x14000a214  mov     eax, r8d
0x14000a217  mov     r8d, edx
0x14000a21a  btr     r8d, 1Fh; unsigned __int16
0x14000a21f  test    ecx, ecx
0x14000a221  jnz     short loc_14000A28A
0x14000a223  test    eax, eax
0x14000a225  jnz     short loc_14000A28A
0x14000a227  test    r8d, r8d
0x14000a22a  jnz     short loc_14000A28A
0x14000a22c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x14000a233  jnz     loc_14000A336
0x14000a239  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000a240  test    rax, rax
0x14000a243  jz      short loc_14000A252
0x14000a245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a24a  test    al, al
0x14000a24c  jnz     loc_14000A336
0x14000a252  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14000a259  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14000a25e  test    al, al
0x14000a260  jz      loc_14000A336
0x14000a266  mov     rdx, cs:qword_1400203C8; SRWLock
0x14000a26d  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x14000a274  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x14000a279  mov     rcx, cs:qword_1400203C8; SRWLock
0x14000a280  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14000a285  jmp     loc_14000A336
0x14000a28a  bt      r8d, 1Eh
0x14000a28f  jnb     short loc_14000A2A7
0x14000a291  mov     edx, ecx; unsigned int
0x14000a293  mov     r9d, eax; unsigned int
0x14000a296  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x14000a29d  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x14000a2a2  jmp     loc_14000A336
0x14000a2a7  test    eax, eax
0x14000a2a9  jnz     short loc_14000A325
0x14000a2ab  cmp     r8d, 0FEh
0x14000a2b2  jz      short loc_14000A325
0x14000a2b4  mov     [rsp+38h+var_18], 0
0x14000a2bd  mov     dword ptr [rsp+38h+var_18], ecx
0x14000a2c1  mov     word ptr [rsp+38h+var_18+4], r8w
0x14000a2c7  test    edx, edx
0x14000a2c9  jns     short loc_14000A2D1
0x14000a2cb  or      word ptr [rsp+38h+var_18+6], 1
0x14000a2d1  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x14000a2d8  test    rax, rax
0x14000a2db  jnz     short loc_14000A319
0x14000a2dd  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000a2e4  test    rax, rax
0x14000a2e7  jnz     short loc_14000A2FD
0x14000a2e9  lea     rcx, ModuleName; "ntdll.dll"
0x14000a2f0  call    cs:__imp_GetModuleHandleW
0x14000a2f6  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000a2fd  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x14000a304  mov     rcx, rax; hModule
0x14000a307  call    cs:__imp_GetProcAddress
0x14000a30d  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x14000a314  test    rax, rax
0x14000a317  jz      short loc_14000A336
0x14000a319  lea     rcx, [rsp+38h+var_18]
0x14000a31e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a323  jmp     short loc_14000A336
0x14000a325  mov     edx, ecx
0x14000a327  mov     r9, rax
0x14000a32a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000a331  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x14000a336  add     rsp, 38h
0x14000a33a  retn
```
