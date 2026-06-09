# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000dae0`
- end: `0x18000dc00`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1800077a0`
- `0x180009bfc`
- `0x18000a018`
- `0x18000a7c4`
- `0x18000a9c0`
- `0x18000dae0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dbcc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dbcc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000dbb5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000dbb5`

## string_xrefs

- `0x18000dbae`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180019050[25], qword_180019050);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180019050);
  }
}

```

## disassembly

```asm
0x18000dae0  sub     rsp, 38h
0x18000dae4  mov     eax, r8d
0x18000dae7  mov     r8d, edx
0x18000daea  btr     r8d, 1Fh; unsigned __int16
0x18000daef  test    ecx, ecx
0x18000daf1  jnz     short loc_18000DB4F
0x18000daf3  test    eax, eax
0x18000daf5  jnz     short loc_18000DB4F
0x18000daf7  test    r8d, r8d
0x18000dafa  jnz     short loc_18000DB4F
0x18000dafc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x18000db03  jnz     short loc_18000DB4A
0x18000db05  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000db0c  test    rax, rax
0x18000db0f  jz      short loc_18000DB1A
0x18000db11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db16  test    al, al
0x18000db18  jnz     short loc_18000DB4A
0x18000db1a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000db21  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000db26  test    al, al
0x18000db28  jz      short loc_18000DB4A
0x18000db2a  mov     rdx, cs:qword_180019050; SRWLock
0x18000db31  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000db38  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000db3d  mov     rcx, cs:qword_180019050; SRWLock
0x18000db44  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000db49  nop
0x18000db4a  jmp     loc_18000DBFB
0x18000db4f  bt      r8d, 1Eh
0x18000db54  jnb     short loc_18000DB6C
0x18000db56  mov     r9d, eax; unsigned int
0x18000db59  mov     edx, ecx; unsigned int
0x18000db5b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000db62  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18000db67  jmp     loc_18000DBFB
0x18000db6c  test    eax, eax
0x18000db6e  jnz     short loc_18000DBEA
0x18000db70  cmp     r8d, 0FEh
0x18000db77  jz      short loc_18000DBEA
0x18000db79  mov     [rsp+38h+var_18], 0
0x18000db82  mov     dword ptr [rsp+38h+var_18], ecx
0x18000db86  mov     word ptr [rsp+38h+var_18+4], r8w
0x18000db8c  test    edx, edx
0x18000db8e  jns     short loc_18000DB96
0x18000db90  or      word ptr [rsp+38h+var_18+6], 1
0x18000db96  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000db9d  test    rax, rax
0x18000dba0  jnz     short loc_18000DBDE
0x18000dba2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000dba9  test    rax, rax
0x18000dbac  jnz     short loc_18000DBC2
0x18000dbae  lea     rcx, ModuleName; "ntdll.dll"
0x18000dbb5  call    cs:__imp_GetModuleHandleW
0x18000dbbb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000dbc2  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000dbc9  mov     rcx, rax; hModule
0x18000dbcc  call    cs:__imp_GetProcAddress
0x18000dbd2  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000dbd9  test    rax, rax
0x18000dbdc  jz      short loc_18000DBFB
0x18000dbde  lea     rcx, [rsp+38h+var_18]
0x18000dbe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbe8  jmp     short loc_18000DBFB
0x18000dbea  mov     r9, rax
0x18000dbed  mov     edx, ecx
0x18000dbef  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000dbf6  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000dbfb  add     rsp, 38h
0x18000dbff  retn
```
