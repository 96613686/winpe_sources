# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180024040`
- end: `0x18002416b`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `299`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18001b0a0`
- `0x18001ea04`
- `0x18001f594`
- `0x180020e44`
- `0x180020ffc`
- `0x180024040`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180024120`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180024120`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024137`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024137`

## string_xrefs

- `0x180024119`: `ntdll.dll`

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
        goto LABEL_19;
      ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
      if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
      {
        ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
        `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
      }
      ProcAddress = GetProcAddress(ModuleHandleW, "RtlNotifyFeatureUsage");
      g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)ProcAddress;
      if ( ProcAddress )
LABEL_19:
        ((void (__fastcall *)(int *))ProcAddress)(&v7);
    }
  }
  else if ( !wil::details::g_processShutdownInProgress
         && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress())
         && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_1800510B0[25], qword_1800510B0);
    wil::details_abi::FeatureStateData::RecordUsage(qword_1800510B0);
  }
}

```

## disassembly

```asm
0x180024040  sub     rsp, 38h
0x180024044  mov     eax, r8d
0x180024047  mov     r8d, edx
0x18002404a  btr     r8d, 1Fh; unsigned __int16
0x18002404f  test    ecx, ecx
0x180024051  jnz     short loc_1800240BA
0x180024053  test    eax, eax
0x180024055  jnz     short loc_1800240BA
0x180024057  test    r8d, r8d
0x18002405a  jnz     short loc_1800240BA
0x18002405c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180024063  jnz     loc_180024166
0x180024069  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180024070  test    rax, rax
0x180024073  jz      short loc_180024082
0x180024075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002407a  test    al, al
0x18002407c  jnz     loc_180024166
0x180024082  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180024089  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18002408e  test    al, al
0x180024090  jz      loc_180024166
0x180024096  mov     rdx, cs:qword_1800510B0; SRWLock
0x18002409d  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800240a4  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x1800240a9  mov     rcx, cs:qword_1800510B0; SRWLock
0x1800240b0  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800240b5  jmp     loc_180024166
0x1800240ba  bt      r8d, 1Eh
0x1800240bf  jnb     short loc_1800240D7
0x1800240c1  mov     edx, ecx; unsigned int
0x1800240c3  mov     r9d, eax; unsigned int
0x1800240c6  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x1800240cd  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x1800240d2  jmp     loc_180024166
0x1800240d7  test    eax, eax
0x1800240d9  jnz     short loc_180024155
0x1800240db  cmp     r8d, 0FEh
0x1800240e2  jz      short loc_180024155
0x1800240e4  mov     [rsp+38h+var_18], 0
0x1800240ed  mov     dword ptr [rsp+38h+var_18], ecx
0x1800240f1  mov     word ptr [rsp+38h+var_18+4], r8w
0x1800240f7  test    edx, edx
0x1800240f9  jns     short loc_180024101
0x1800240fb  or      word ptr [rsp+38h+var_18+6], 1
0x180024101  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180024108  test    rax, rax
0x18002410b  jnz     short loc_180024149
0x18002410d  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180024114  test    rax, rax
0x180024117  jnz     short loc_18002412D
0x180024119  lea     rcx, LibFileName; "ntdll.dll"
0x180024120  call    cs:__imp_GetModuleHandleW
0x180024126  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002412d  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180024134  mov     rcx, rax; hModule
0x180024137  call    cs:__imp_GetProcAddress
0x18002413d  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180024144  test    rax, rax
0x180024147  jz      short loc_180024166
0x180024149  lea     rcx, [rsp+38h+var_18]
0x18002414e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024153  jmp     short loc_180024166
0x180024155  mov     edx, ecx
0x180024157  mov     r9, rax
0x18002415a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180024161  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180024166  add     rsp, 38h
0x18002416a  retn
```
