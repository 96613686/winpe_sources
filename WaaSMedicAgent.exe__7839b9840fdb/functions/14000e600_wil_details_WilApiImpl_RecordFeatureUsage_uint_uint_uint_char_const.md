# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x14000e600`
- end: `0x14000e729`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `297`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x14000c55c`
- `0x14000d000`
- `0x14000d158`
- `0x14000d514`
- `0x14000d6a0`
- `0x14000e600`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000e6f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000e6f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000e6de`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000e6de`

## string_xrefs

- `0x14000e6d7`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details::WilApiImpl_RecordFeatureUsage(wil::details *this, int a2, unsigned int a3)
{
  unsigned int v4; // r8d
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v7; // [rsp+20h] [rbp-18h] BYREF
  int v8; // [rsp+24h] [rbp-14h]
  __int64 v9; // [rsp+28h] [rbp-10h]

  v9 = -2;
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
         && (!wil::details::g_pfnDllShutdownInProgress
          || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress(this))
         && wil::details::FeatureStateManager::EnsureStateData((RTL_SRWLOCK *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_1400200D0[25], qword_1400200D0);
    wil::details_abi::FeatureStateData::RecordUsage(qword_1400200D0);
  }
}

```

## disassembly

```asm
0x14000e600  sub     rsp, 38h
0x14000e604  mov     [rsp+38h+var_10], 0FFFFFFFFFFFFFFFEh
0x14000e60d  mov     eax, r8d
0x14000e610  mov     r8d, edx
0x14000e613  btr     r8d, 1Fh; unsigned __int16
0x14000e618  test    ecx, ecx
0x14000e61a  jnz     short loc_14000E678
0x14000e61c  test    eax, eax
0x14000e61e  jnz     short loc_14000E678
0x14000e620  test    r8d, r8d
0x14000e623  jnz     short loc_14000E678
0x14000e625  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x14000e62c  jnz     short loc_14000E673
0x14000e62e  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000e635  test    rax, rax
0x14000e638  jz      short loc_14000E643
0x14000e63a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e63f  test    al, al
0x14000e641  jnz     short loc_14000E673
0x14000e643  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14000e64a  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14000e64f  test    al, al
0x14000e651  jz      short loc_14000E673
0x14000e653  mov     rdx, cs:qword_1400200D0; SRWLock
0x14000e65a  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x14000e661  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x14000e666  mov     rcx, cs:qword_1400200D0; SRWLock
0x14000e66d  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14000e672  nop
0x14000e673  jmp     loc_14000E724
0x14000e678  bt      r8d, 1Eh
0x14000e67d  jnb     short loc_14000E695
0x14000e67f  mov     r9d, eax; unsigned int
0x14000e682  mov     edx, ecx; unsigned int
0x14000e684  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x14000e68b  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x14000e690  jmp     loc_14000E724
0x14000e695  test    eax, eax
0x14000e697  jnz     short loc_14000E713
0x14000e699  cmp     r8d, 0FEh
0x14000e6a0  jz      short loc_14000E713
0x14000e6a2  mov     [rsp+38h+var_18], 0
0x14000e6ab  mov     dword ptr [rsp+38h+var_18], ecx
0x14000e6af  mov     word ptr [rsp+38h+var_18+4], r8w
0x14000e6b5  test    edx, edx
0x14000e6b7  jns     short loc_14000E6BF
0x14000e6b9  or      word ptr [rsp+38h+var_18+6], 1
0x14000e6bf  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x14000e6c6  test    rax, rax
0x14000e6c9  jnz     short loc_14000E707
0x14000e6cb  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000e6d2  test    rax, rax
0x14000e6d5  jnz     short loc_14000E6EB
0x14000e6d7  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14000e6de  call    cs:__imp_GetModuleHandleW
0x14000e6e4  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000e6eb  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x14000e6f2  mov     rcx, rax; hModule
0x14000e6f5  call    cs:__imp_GetProcAddress
0x14000e6fb  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x14000e702  test    rax, rax
0x14000e705  jz      short loc_14000E724
0x14000e707  lea     rcx, [rsp+38h+var_18]
0x14000e70c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e711  jmp     short loc_14000E724
0x14000e713  mov     r9, rax
0x14000e716  mov     edx, ecx
0x14000e718  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000e71f  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x14000e724  add     rsp, 38h
0x14000e728  retn
```
