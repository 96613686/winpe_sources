# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180008c30`
- end: `0x180008d50`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180004544`
- `0x180005ea4`
- `0x1800060a8`
- `0x180006804`
- `0x180006a00`
- `0x180008c30`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008d1c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008d1c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008d05`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008d05`

## string_xrefs

- `0x180008cfe`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_18001F078[25], qword_18001F078);
    wil::details_abi::FeatureStateData::RecordUsage(qword_18001F078);
  }
}

```

## disassembly

```asm
0x180008c30  sub     rsp, 38h
0x180008c34  mov     eax, r8d
0x180008c37  mov     r8d, edx
0x180008c3a  btr     r8d, 1Fh; unsigned __int16
0x180008c3f  test    ecx, ecx
0x180008c41  jnz     short loc_180008C9F
0x180008c43  test    eax, eax
0x180008c45  jnz     short loc_180008C9F
0x180008c47  test    r8d, r8d
0x180008c4a  jnz     short loc_180008C9F
0x180008c4c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180008c53  jnz     short loc_180008C9A
0x180008c55  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180008c5c  test    rax, rax
0x180008c5f  jz      short loc_180008C6A
0x180008c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c66  test    al, al
0x180008c68  jnz     short loc_180008C9A
0x180008c6a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180008c71  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180008c76  test    al, al
0x180008c78  jz      short loc_180008C9A
0x180008c7a  mov     rdx, cs:qword_18001F078; SRWLock
0x180008c81  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180008c88  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180008c8d  mov     rcx, cs:qword_18001F078; SRWLock
0x180008c94  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180008c99  nop
0x180008c9a  jmp     loc_180008D4B
0x180008c9f  bt      r8d, 1Eh
0x180008ca4  jnb     short loc_180008CBC
0x180008ca6  mov     r9d, eax; unsigned int
0x180008ca9  mov     edx, ecx; unsigned int
0x180008cab  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180008cb2  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180008cb7  jmp     loc_180008D4B
0x180008cbc  test    eax, eax
0x180008cbe  jnz     short loc_180008D3A
0x180008cc0  cmp     r8d, 0FEh
0x180008cc7  jz      short loc_180008D3A
0x180008cc9  mov     [rsp+38h+var_18], 0
0x180008cd2  mov     dword ptr [rsp+38h+var_18], ecx
0x180008cd6  mov     word ptr [rsp+38h+var_18+4], r8w
0x180008cdc  test    edx, edx
0x180008cde  jns     short loc_180008CE6
0x180008ce0  or      word ptr [rsp+38h+var_18+6], 1
0x180008ce6  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180008ced  test    rax, rax
0x180008cf0  jnz     short loc_180008D2E
0x180008cf2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008cf9  test    rax, rax
0x180008cfc  jnz     short loc_180008D12
0x180008cfe  lea     rcx, ModuleName; "ntdll.dll"
0x180008d05  call    cs:__imp_GetModuleHandleW
0x180008d0b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008d12  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180008d19  mov     rcx, rax; hModule
0x180008d1c  call    cs:__imp_GetProcAddress
0x180008d22  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180008d29  test    rax, rax
0x180008d2c  jz      short loc_180008D4B
0x180008d2e  lea     rcx, [rsp+38h+var_18]
0x180008d33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d38  jmp     short loc_180008D4B
0x180008d3a  mov     r9, rax
0x180008d3d  mov     edx, ecx
0x180008d3f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180008d46  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180008d4b  add     rsp, 38h
0x180008d4f  retn
```
