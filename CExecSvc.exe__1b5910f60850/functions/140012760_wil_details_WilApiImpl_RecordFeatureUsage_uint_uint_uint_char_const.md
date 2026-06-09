# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x140012760`
- end: `0x14001289c`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `316`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x140002310`
- `0x1400104d0`
- `0x140010a54`
- `0x140011024`
- `0x140011334`
- `0x1400114fc`
- `0x140012760`
- `0x140024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001285b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001285b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140012844`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140012844`

## string_xrefs

- `0x14001283d`: `ntdll.dll`

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
        &wil::details::g_featureStateManager,
        (unsigned int)this,
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
         && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&SRWLock[25], SRWLock);
    wil::details_abi::FeatureStateData::RecordUsage(SRWLock);
  }
}

```

## disassembly

```asm
0x140012760  sub     rsp, 38h
0x140012764  mov     rax, cs:__security_cookie
0x14001276b  xor     rax, rsp
0x14001276e  mov     [rsp+38h+var_10], rax
0x140012773  mov     eax, r8d
0x140012776  mov     r8d, edx
0x140012779  btr     r8d, 1Fh; unsigned __int16
0x14001277e  test    ecx, ecx
0x140012780  jnz     short loc_1400127DE
0x140012782  test    eax, eax
0x140012784  jnz     short loc_1400127DE
0x140012786  test    r8d, r8d
0x140012789  jnz     short loc_1400127DE
0x14001278b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x140012792  jnz     short loc_1400127D9
0x140012794  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14001279b  test    rax, rax
0x14001279e  jz      short loc_1400127A9
0x1400127a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400127a5  test    al, al
0x1400127a7  jnz     short loc_1400127D9
0x1400127a9  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x1400127b0  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1400127b5  test    al, al
0x1400127b7  jz      short loc_1400127D9
0x1400127b9  mov     rdx, cs:SRWLock; SRWLock
0x1400127c0  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1400127c7  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x1400127cc  mov     rcx, cs:SRWLock; SRWLock
0x1400127d3  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1400127d8  nop
0x1400127d9  jmp     loc_14001288A
0x1400127de  bt      r8d, 1Eh
0x1400127e3  jnb     short loc_1400127FB
0x1400127e5  mov     r9d, eax; unsigned int
0x1400127e8  mov     edx, ecx; unsigned int
0x1400127ea  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x1400127f1  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x1400127f6  jmp     loc_14001288A
0x1400127fb  test    eax, eax
0x1400127fd  jnz     short loc_140012879
0x1400127ff  cmp     r8d, 0FEh
0x140012806  jz      short loc_140012879
0x140012808  mov     [rsp+38h+var_18], 0
0x140012811  mov     dword ptr [rsp+38h+var_18], ecx
0x140012815  mov     word ptr [rsp+38h+var_18+4], r8w
0x14001281b  test    edx, edx
0x14001281d  jns     short loc_140012825
0x14001281f  or      word ptr [rsp+38h+var_18+6], 1
0x140012825  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x14001282c  test    rax, rax
0x14001282f  jnz     short loc_14001286D
0x140012831  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140012838  test    rax, rax
0x14001283b  jnz     short loc_140012851
0x14001283d  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x140012844  call    cs:__imp_GetModuleHandleW
0x14001284a  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140012851  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x140012858  mov     rcx, rax; hModule
0x14001285b  call    cs:__imp_GetProcAddress
0x140012861  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x140012868  test    rax, rax
0x14001286b  jz      short loc_14001288A
0x14001286d  lea     rcx, [rsp+38h+var_18]
0x140012872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012877  jmp     short loc_14001288A
0x140012879  mov     r9, rax
0x14001287c  mov     edx, ecx
0x14001287e  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x140012885  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x14001288a  mov     rcx, [rsp+38h+var_10]
0x14001288f  xor     rcx, rsp; StackCookie
0x140012892  call    __security_check_cookie
0x140012897  add     rsp, 38h
0x14001289b  retn
```
