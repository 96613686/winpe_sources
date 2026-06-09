# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180007640`
- end: `0x18000776b`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `299`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180004134`
- `0x180005714`
- `0x18000587c`
- `0x180005c64`
- `0x180005e1c`
- `0x180007640`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007720`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007720`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007737`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007737`

## string_xrefs

- `0x180007719`: `ntdll.dll`

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
         && wil::details::FeatureStateManager::EnsureStateData((RTL_SRWLOCK *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_18002F1C8[25], qword_18002F1C8);
    wil::details_abi::FeatureStateData::RecordUsage(qword_18002F1C8);
  }
}

```

## disassembly

```asm
0x180007640  sub     rsp, 38h
0x180007644  mov     eax, r8d
0x180007647  mov     r8d, edx
0x18000764a  btr     r8d, 1Fh; unsigned __int16
0x18000764f  test    ecx, ecx
0x180007651  jnz     short loc_1800076BA
0x180007653  test    eax, eax
0x180007655  jnz     short loc_1800076BA
0x180007657  test    r8d, r8d
0x18000765a  jnz     short loc_1800076BA
0x18000765c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180007663  jnz     loc_180007766
0x180007669  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180007670  test    rax, rax
0x180007673  jz      short loc_180007682
0x180007675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000767a  test    al, al
0x18000767c  jnz     loc_180007766
0x180007682  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180007689  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000768e  test    al, al
0x180007690  jz      loc_180007766
0x180007696  mov     rdx, cs:qword_18002F1C8; SRWLock
0x18000769d  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800076a4  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x1800076a9  mov     rcx, cs:qword_18002F1C8; SRWLock
0x1800076b0  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800076b5  jmp     loc_180007766
0x1800076ba  bt      r8d, 1Eh
0x1800076bf  jnb     short loc_1800076D7
0x1800076c1  mov     edx, ecx; unsigned int
0x1800076c3  mov     r9d, eax; unsigned int
0x1800076c6  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x1800076cd  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x1800076d2  jmp     loc_180007766
0x1800076d7  test    eax, eax
0x1800076d9  jnz     short loc_180007755
0x1800076db  cmp     r8d, 0FEh
0x1800076e2  jz      short loc_180007755
0x1800076e4  mov     [rsp+38h+var_18], 0
0x1800076ed  mov     dword ptr [rsp+38h+var_18], ecx
0x1800076f1  mov     word ptr [rsp+38h+var_18+4], r8w
0x1800076f7  test    edx, edx
0x1800076f9  jns     short loc_180007701
0x1800076fb  or      word ptr [rsp+38h+var_18+6], 1
0x180007701  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180007708  test    rax, rax
0x18000770b  jnz     short loc_180007749
0x18000770d  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007714  test    rax, rax
0x180007717  jnz     short loc_18000772D
0x180007719  lea     rcx, ModuleName; "ntdll.dll"
0x180007720  call    cs:__imp_GetModuleHandleW
0x180007726  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000772d  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180007734  mov     rcx, rax; hModule
0x180007737  call    cs:__imp_GetProcAddress
0x18000773d  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180007744  test    rax, rax
0x180007747  jz      short loc_180007766
0x180007749  lea     rcx, [rsp+38h+var_18]
0x18000774e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007753  jmp     short loc_180007766
0x180007755  mov     edx, ecx
0x180007757  mov     r9, rax
0x18000775a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180007761  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180007766  add     rsp, 38h
0x18000776a  retn
```
