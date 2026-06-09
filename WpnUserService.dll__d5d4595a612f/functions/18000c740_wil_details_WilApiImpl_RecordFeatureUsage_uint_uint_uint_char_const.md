# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000c740`
- end: `0x18000c860`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180008d84`
- `0x180009c7c`
- `0x18000a708`
- `0x18000aab8`
- `0x18000ac3c`
- `0x18000c740`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c815`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c815`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c82c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c82c`

## string_xrefs

- `0x18000c80e`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180019098[25], qword_180019098);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180019098);
  }
}

```

## disassembly

```asm
0x18000c740  sub     rsp, 38h
0x18000c744  mov     eax, r8d
0x18000c747  mov     r8d, edx
0x18000c74a  btr     r8d, 1Fh; unsigned __int16
0x18000c74f  test    ecx, ecx
0x18000c751  jnz     short loc_18000C7AF
0x18000c753  test    eax, eax
0x18000c755  jnz     short loc_18000C7AF
0x18000c757  test    r8d, r8d
0x18000c75a  jnz     short loc_18000C7AF
0x18000c75c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x18000c763  jnz     short loc_18000C7AA
0x18000c765  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000c76c  test    rax, rax
0x18000c76f  jz      short loc_18000C77A
0x18000c771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c776  test    al, al
0x18000c778  jnz     short loc_18000C7AA
0x18000c77a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000c781  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000c786  test    al, al
0x18000c788  jz      short loc_18000C7AA
0x18000c78a  mov     rdx, cs:qword_180019098; SRWLock
0x18000c791  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000c798  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000c79d  mov     rcx, cs:qword_180019098; SRWLock
0x18000c7a4  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000c7a9  nop
0x18000c7aa  jmp     loc_18000C85B
0x18000c7af  bt      r8d, 1Eh
0x18000c7b4  jnb     short loc_18000C7CC
0x18000c7b6  mov     r9d, eax; unsigned int
0x18000c7b9  mov     edx, ecx; unsigned int
0x18000c7bb  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000c7c2  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18000c7c7  jmp     loc_18000C85B
0x18000c7cc  test    eax, eax
0x18000c7ce  jnz     short loc_18000C84A
0x18000c7d0  cmp     r8d, 0FEh
0x18000c7d7  jz      short loc_18000C84A
0x18000c7d9  mov     [rsp+38h+var_18], 0
0x18000c7e2  mov     dword ptr [rsp+38h+var_18], ecx
0x18000c7e6  mov     word ptr [rsp+38h+var_18+4], r8w
0x18000c7ec  test    edx, edx
0x18000c7ee  jns     short loc_18000C7F6
0x18000c7f0  or      word ptr [rsp+38h+var_18+6], 1
0x18000c7f6  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000c7fd  test    rax, rax
0x18000c800  jnz     short loc_18000C83E
0x18000c802  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c809  test    rax, rax
0x18000c80c  jnz     short loc_18000C822
0x18000c80e  lea     rcx, ModuleName; "ntdll.dll"
0x18000c815  call    cs:__imp_GetModuleHandleW
0x18000c81b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c822  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000c829  mov     rcx, rax; hModule
0x18000c82c  call    cs:__imp_GetProcAddress
0x18000c832  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000c839  test    rax, rax
0x18000c83c  jz      short loc_18000C85B
0x18000c83e  lea     rcx, [rsp+38h+var_18]
0x18000c843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c848  jmp     short loc_18000C85B
0x18000c84a  mov     r9, rax
0x18000c84d  mov     edx, ecx
0x18000c84f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000c856  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000c85b  add     rsp, 38h
0x18000c85f  retn
```
