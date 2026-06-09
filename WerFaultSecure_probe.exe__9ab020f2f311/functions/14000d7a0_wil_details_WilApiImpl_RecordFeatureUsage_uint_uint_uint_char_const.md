# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x14000d7a0`
- end: `0x14000d8c0`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x140009a38`
- `0x14000ab4c`
- `0x14000acb4`
- `0x14000b064`
- `0x14000b1e8`
- `0x14000d7a0`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000d88c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000d88c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000d875`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000d875`

## string_xrefs

- `0x14000d86e`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_14001A0D8[25], qword_14001A0D8);
    wil::details_abi::FeatureStateData::RecordUsage(qword_14001A0D8);
  }
}

```

## disassembly

```asm
0x14000d7a0  sub     rsp, 38h
0x14000d7a4  mov     eax, r8d
0x14000d7a7  mov     r8d, edx
0x14000d7aa  btr     r8d, 1Fh; unsigned __int16
0x14000d7af  test    ecx, ecx
0x14000d7b1  jnz     short loc_14000D80F
0x14000d7b3  test    eax, eax
0x14000d7b5  jnz     short loc_14000D80F
0x14000d7b7  test    r8d, r8d
0x14000d7ba  jnz     short loc_14000D80F
0x14000d7bc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x14000d7c3  jnz     short loc_14000D80A
0x14000d7c5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000d7cc  test    rax, rax
0x14000d7cf  jz      short loc_14000D7DA
0x14000d7d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d7d6  test    al, al
0x14000d7d8  jnz     short loc_14000D80A
0x14000d7da  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14000d7e1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14000d7e6  test    al, al
0x14000d7e8  jz      short loc_14000D80A
0x14000d7ea  mov     rdx, cs:qword_14001A0D8; SRWLock
0x14000d7f1  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x14000d7f8  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x14000d7fd  mov     rcx, cs:qword_14001A0D8; SRWLock
0x14000d804  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14000d809  nop
0x14000d80a  jmp     loc_14000D8BB
0x14000d80f  bt      r8d, 1Eh
0x14000d814  jnb     short loc_14000D82C
0x14000d816  mov     r9d, eax; unsigned int
0x14000d819  mov     edx, ecx; unsigned int
0x14000d81b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x14000d822  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x14000d827  jmp     loc_14000D8BB
0x14000d82c  test    eax, eax
0x14000d82e  jnz     short loc_14000D8AA
0x14000d830  cmp     r8d, 0FEh
0x14000d837  jz      short loc_14000D8AA
0x14000d839  mov     [rsp+38h+var_18], 0
0x14000d842  mov     dword ptr [rsp+38h+var_18], ecx
0x14000d846  mov     word ptr [rsp+38h+var_18+4], r8w
0x14000d84c  test    edx, edx
0x14000d84e  jns     short loc_14000D856
0x14000d850  or      word ptr [rsp+38h+var_18+6], 1
0x14000d856  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x14000d85d  test    rax, rax
0x14000d860  jnz     short loc_14000D89E
0x14000d862  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000d869  test    rax, rax
0x14000d86c  jnz     short loc_14000D882
0x14000d86e  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x14000d875  call    cs:__imp_GetModuleHandleW
0x14000d87b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000d882  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x14000d889  mov     rcx, rax; hModule
0x14000d88c  call    cs:__imp_GetProcAddress
0x14000d892  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x14000d899  test    rax, rax
0x14000d89c  jz      short loc_14000D8BB
0x14000d89e  lea     rcx, [rsp+38h+var_18]
0x14000d8a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d8a8  jmp     short loc_14000D8BB
0x14000d8aa  mov     r9, rax
0x14000d8ad  mov     edx, ecx
0x14000d8af  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000d8b6  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x14000d8bb  add     rsp, 38h
0x14000d8bf  retn
```
