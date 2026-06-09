# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x14000b650`
- end: `0x14000b770`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1400083a4`
- `0x140009164`
- `0x1400092cc`
- `0x140009680`
- `0x140009804`
- `0x14000b650`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000b725`
- `KERNEL32!GetModuleHandleW` at `0x14000b725`
- `KERNEL32!GetProcAddress` at `0x14000b73c`
- `KERNEL32!GetProcAddress` at `0x14000b73c`

## string_xrefs

- `0x14000b71e`: `ntdll.dll`

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
         && wil::details::FeatureStateManager::EnsureStateData((RTL_SRWLOCK *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_140018028[25], qword_140018028);
    wil::details_abi::FeatureStateData::RecordUsage(qword_140018028);
  }
}

```

## disassembly

```asm
0x14000b650  sub     rsp, 38h
0x14000b654  mov     eax, r8d
0x14000b657  mov     r8d, edx
0x14000b65a  btr     r8d, 1Fh; unsigned __int16
0x14000b65f  test    ecx, ecx
0x14000b661  jnz     short loc_14000B6BF
0x14000b663  test    eax, eax
0x14000b665  jnz     short loc_14000B6BF
0x14000b667  test    r8d, r8d
0x14000b66a  jnz     short loc_14000B6BF
0x14000b66c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x14000b673  jnz     short loc_14000B6BA
0x14000b675  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000b67c  test    rax, rax
0x14000b67f  jz      short loc_14000B68A
0x14000b681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b686  test    al, al
0x14000b688  jnz     short loc_14000B6BA
0x14000b68a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14000b691  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14000b696  test    al, al
0x14000b698  jz      short loc_14000B6BA
0x14000b69a  mov     rdx, cs:qword_140018028; SRWLock
0x14000b6a1  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x14000b6a8  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x14000b6ad  mov     rcx, cs:qword_140018028; SRWLock
0x14000b6b4  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14000b6b9  nop
0x14000b6ba  jmp     loc_14000B76B
0x14000b6bf  bt      r8d, 1Eh
0x14000b6c4  jnb     short loc_14000B6DC
0x14000b6c6  mov     r9d, eax; unsigned int
0x14000b6c9  mov     edx, ecx; unsigned int
0x14000b6cb  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x14000b6d2  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x14000b6d7  jmp     loc_14000B76B
0x14000b6dc  test    eax, eax
0x14000b6de  jnz     short loc_14000B75A
0x14000b6e0  cmp     r8d, 0FEh
0x14000b6e7  jz      short loc_14000B75A
0x14000b6e9  mov     [rsp+38h+var_18], 0
0x14000b6f2  mov     dword ptr [rsp+38h+var_18], ecx
0x14000b6f6  mov     word ptr [rsp+38h+var_18+4], r8w
0x14000b6fc  test    edx, edx
0x14000b6fe  jns     short loc_14000B706
0x14000b700  or      word ptr [rsp+38h+var_18+6], 1
0x14000b706  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x14000b70d  test    rax, rax
0x14000b710  jnz     short loc_14000B74E
0x14000b712  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b719  test    rax, rax
0x14000b71c  jnz     short loc_14000B732
0x14000b71e  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14000b725  call    cs:__imp_GetModuleHandleW
0x14000b72b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b732  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x14000b739  mov     rcx, rax; hModule
0x14000b73c  call    cs:__imp_GetProcAddress
0x14000b742  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x14000b749  test    rax, rax
0x14000b74c  jz      short loc_14000B76B
0x14000b74e  lea     rcx, [rsp+38h+var_18]
0x14000b753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b758  jmp     short loc_14000B76B
0x14000b75a  mov     r9, rax
0x14000b75d  mov     edx, ecx
0x14000b75f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000b766  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x14000b76b  add     rsp, 38h
0x14000b76f  retn
```
