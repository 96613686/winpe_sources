# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180025c10`
- end: `0x180025d30`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1800241dc`
- `0x180024640`
- `0x180024704`
- `0x180024ab4`
- `0x180024c38`
- `0x180025c10`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025ce5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025ce5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025cfc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025cfc`

## string_xrefs

- `0x180025cde`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_18003B0A8[25], qword_18003B0A8);
    wil::details_abi::FeatureStateData::RecordUsage(qword_18003B0A8);
  }
}

```

## disassembly

```asm
0x180025c10  sub     rsp, 38h
0x180025c14  mov     eax, r8d
0x180025c17  mov     r8d, edx
0x180025c1a  btr     r8d, 1Fh; unsigned __int16
0x180025c1f  test    ecx, ecx
0x180025c21  jnz     short loc_180025C7F
0x180025c23  test    eax, eax
0x180025c25  jnz     short loc_180025C7F
0x180025c27  test    r8d, r8d
0x180025c2a  jnz     short loc_180025C7F
0x180025c2c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180025c33  jnz     short loc_180025C7A
0x180025c35  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180025c3c  test    rax, rax
0x180025c3f  jz      short loc_180025C4A
0x180025c41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c46  test    al, al
0x180025c48  jnz     short loc_180025C7A
0x180025c4a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180025c51  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180025c56  test    al, al
0x180025c58  jz      short loc_180025C7A
0x180025c5a  mov     rdx, cs:qword_18003B0A8; SRWLock
0x180025c61  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180025c68  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180025c6d  mov     rcx, cs:qword_18003B0A8; SRWLock
0x180025c74  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180025c79  nop
0x180025c7a  jmp     loc_180025D2B
0x180025c7f  bt      r8d, 1Eh
0x180025c84  jnb     short loc_180025C9C
0x180025c86  mov     r9d, eax; unsigned int
0x180025c89  mov     edx, ecx; unsigned int
0x180025c8b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180025c92  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180025c97  jmp     loc_180025D2B
0x180025c9c  test    eax, eax
0x180025c9e  jnz     short loc_180025D1A
0x180025ca0  cmp     r8d, 0FEh
0x180025ca7  jz      short loc_180025D1A
0x180025ca9  mov     [rsp+38h+var_18], 0
0x180025cb2  mov     dword ptr [rsp+38h+var_18], ecx
0x180025cb6  mov     word ptr [rsp+38h+var_18+4], r8w
0x180025cbc  test    edx, edx
0x180025cbe  jns     short loc_180025CC6
0x180025cc0  or      word ptr [rsp+38h+var_18+6], 1
0x180025cc6  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180025ccd  test    rax, rax
0x180025cd0  jnz     short loc_180025D0E
0x180025cd2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180025cd9  test    rax, rax
0x180025cdc  jnz     short loc_180025CF2
0x180025cde  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180025ce5  call    cs:__imp_GetModuleHandleW
0x180025ceb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180025cf2  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180025cf9  mov     rcx, rax; hModule
0x180025cfc  call    cs:__imp_GetProcAddress
0x180025d02  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180025d09  test    rax, rax
0x180025d0c  jz      short loc_180025D2B
0x180025d0e  lea     rcx, [rsp+38h+var_18]
0x180025d13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d18  jmp     short loc_180025D2B
0x180025d1a  mov     r9, rax
0x180025d1d  mov     edx, ecx
0x180025d1f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180025d26  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180025d2b  add     rsp, 38h
0x180025d2f  retn
```
