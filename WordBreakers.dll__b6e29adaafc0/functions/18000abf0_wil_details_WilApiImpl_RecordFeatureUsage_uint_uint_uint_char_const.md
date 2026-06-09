# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000abf0`
- end: `0x18000ad10`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1800081a8`
- `0x1800093ec`
- `0x1800094b0`
- `0x18000983c`
- `0x1800099c0`
- `0x18000abf0`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000acdc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000acdc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000acc5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000acc5`

## string_xrefs

- `0x18000acbe`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180012130[25], qword_180012130);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180012130);
  }
}

```

## disassembly

```asm
0x18000abf0  sub     rsp, 38h
0x18000abf4  mov     eax, r8d
0x18000abf7  mov     r8d, edx
0x18000abfa  btr     r8d, 1Fh; unsigned __int16
0x18000abff  test    ecx, ecx
0x18000ac01  jnz     short loc_18000AC5F
0x18000ac03  test    eax, eax
0x18000ac05  jnz     short loc_18000AC5F
0x18000ac07  test    r8d, r8d
0x18000ac0a  jnz     short loc_18000AC5F
0x18000ac0c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x18000ac13  jnz     short loc_18000AC5A
0x18000ac15  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000ac1c  test    rax, rax
0x18000ac1f  jz      short loc_18000AC2A
0x18000ac21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac26  test    al, al
0x18000ac28  jnz     short loc_18000AC5A
0x18000ac2a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000ac31  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000ac36  test    al, al
0x18000ac38  jz      short loc_18000AC5A
0x18000ac3a  mov     rdx, cs:qword_180012130; SRWLock
0x18000ac41  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000ac48  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000ac4d  mov     rcx, cs:qword_180012130; SRWLock
0x18000ac54  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000ac59  nop
0x18000ac5a  jmp     loc_18000AD0B
0x18000ac5f  bt      r8d, 1Eh
0x18000ac64  jnb     short loc_18000AC7C
0x18000ac66  mov     r9d, eax; unsigned int
0x18000ac69  mov     edx, ecx; unsigned int
0x18000ac6b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000ac72  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18000ac77  jmp     loc_18000AD0B
0x18000ac7c  test    eax, eax
0x18000ac7e  jnz     short loc_18000ACFA
0x18000ac80  cmp     r8d, 0FEh
0x18000ac87  jz      short loc_18000ACFA
0x18000ac89  mov     [rsp+38h+var_18], 0
0x18000ac92  mov     dword ptr [rsp+38h+var_18], ecx
0x18000ac96  mov     word ptr [rsp+38h+var_18+4], r8w
0x18000ac9c  test    edx, edx
0x18000ac9e  jns     short loc_18000ACA6
0x18000aca0  or      word ptr [rsp+38h+var_18+6], 1
0x18000aca6  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000acad  test    rax, rax
0x18000acb0  jnz     short loc_18000ACEE
0x18000acb2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000acb9  test    rax, rax
0x18000acbc  jnz     short loc_18000ACD2
0x18000acbe  lea     rcx, ModuleName; "ntdll.dll"
0x18000acc5  call    cs:__imp_GetModuleHandleW
0x18000accb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000acd2  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000acd9  mov     rcx, rax; hModule
0x18000acdc  call    cs:__imp_GetProcAddress
0x18000ace2  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000ace9  test    rax, rax
0x18000acec  jz      short loc_18000AD0B
0x18000acee  lea     rcx, [rsp+38h+var_18]
0x18000acf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acf8  jmp     short loc_18000AD0B
0x18000acfa  mov     r9, rax
0x18000acfd  mov     edx, ecx
0x18000acff  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000ad06  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000ad0b  add     rsp, 38h
0x18000ad0f  retn
```
