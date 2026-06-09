# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180007f20`
- end: `0x180008040`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180004254`
- `0x180005834`
- `0x18000599c`
- `0x180005dc4`
- `0x180005f80`
- `0x180007f20`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000800c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000800c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007ff5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007ff5`

## string_xrefs

- `0x180007fee`: `ntdll.dll`

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
         && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180017058[25], qword_180017058);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180017058);
  }
}

```

## disassembly

```asm
0x180007f20  sub     rsp, 38h
0x180007f24  mov     eax, r8d
0x180007f27  mov     r8d, edx
0x180007f2a  btr     r8d, 1Fh; unsigned __int16
0x180007f2f  test    ecx, ecx
0x180007f31  jnz     short loc_180007F8F
0x180007f33  test    eax, eax
0x180007f35  jnz     short loc_180007F8F
0x180007f37  test    r8d, r8d
0x180007f3a  jnz     short loc_180007F8F
0x180007f3c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180007f43  jnz     short loc_180007F8A
0x180007f45  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180007f4c  test    rax, rax
0x180007f4f  jz      short loc_180007F5A
0x180007f51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f56  test    al, al
0x180007f58  jnz     short loc_180007F8A
0x180007f5a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180007f61  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180007f66  test    al, al
0x180007f68  jz      short loc_180007F8A
0x180007f6a  mov     rdx, cs:qword_180017058; SRWLock
0x180007f71  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180007f78  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180007f7d  mov     rcx, cs:qword_180017058; SRWLock
0x180007f84  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180007f89  nop
0x180007f8a  jmp     loc_18000803B
0x180007f8f  bt      r8d, 1Eh
0x180007f94  jnb     short loc_180007FAC
0x180007f96  mov     r9d, eax; unsigned int
0x180007f99  mov     edx, ecx; unsigned int
0x180007f9b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180007fa2  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180007fa7  jmp     loc_18000803B
0x180007fac  test    eax, eax
0x180007fae  jnz     short loc_18000802A
0x180007fb0  cmp     r8d, 0FEh
0x180007fb7  jz      short loc_18000802A
0x180007fb9  mov     [rsp+38h+var_18], 0
0x180007fc2  mov     dword ptr [rsp+38h+var_18], ecx
0x180007fc6  mov     word ptr [rsp+38h+var_18+4], r8w
0x180007fcc  test    edx, edx
0x180007fce  jns     short loc_180007FD6
0x180007fd0  or      word ptr [rsp+38h+var_18+6], 1
0x180007fd6  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180007fdd  test    rax, rax
0x180007fe0  jnz     short loc_18000801E
0x180007fe2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007fe9  test    rax, rax
0x180007fec  jnz     short loc_180008002
0x180007fee  lea     rcx, ModuleName; "ntdll.dll"
0x180007ff5  call    cs:__imp_GetModuleHandleW
0x180007ffb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008002  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180008009  mov     rcx, rax; hModule
0x18000800c  call    cs:__imp_GetProcAddress
0x180008012  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180008019  test    rax, rax
0x18000801c  jz      short loc_18000803B
0x18000801e  lea     rcx, [rsp+38h+var_18]
0x180008023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008028  jmp     short loc_18000803B
0x18000802a  mov     r9, rax
0x18000802d  mov     edx, ecx
0x18000802f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180008036  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000803b  add     rsp, 38h
0x18000803f  retn
```
