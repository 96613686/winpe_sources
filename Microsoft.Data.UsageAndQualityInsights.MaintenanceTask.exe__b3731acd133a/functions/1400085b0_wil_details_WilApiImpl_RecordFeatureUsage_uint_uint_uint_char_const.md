# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x1400085b0`
- end: `0x1400086d0`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1400044b4`
- `0x140005c54`
- `0x140005e58`
- `0x140006404`
- `0x140006600`
- `0x1400085b0`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140008685`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140008685`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000869c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000869c`

## string_xrefs

- `0x14000867e`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_140011018[25], qword_140011018);
    wil::details_abi::FeatureStateData::RecordUsage(qword_140011018);
  }
}

```

## disassembly

```asm
0x1400085b0  sub     rsp, 38h
0x1400085b4  mov     eax, r8d
0x1400085b7  mov     r8d, edx
0x1400085ba  btr     r8d, 1Fh; unsigned __int16
0x1400085bf  test    ecx, ecx
0x1400085c1  jnz     short loc_14000861F
0x1400085c3  test    eax, eax
0x1400085c5  jnz     short loc_14000861F
0x1400085c7  test    r8d, r8d
0x1400085ca  jnz     short loc_14000861F
0x1400085cc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x1400085d3  jnz     short loc_14000861A
0x1400085d5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1400085dc  test    rax, rax
0x1400085df  jz      short loc_1400085EA
0x1400085e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400085e6  test    al, al
0x1400085e8  jnz     short loc_14000861A
0x1400085ea  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x1400085f1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1400085f6  test    al, al
0x1400085f8  jz      short loc_14000861A
0x1400085fa  mov     rdx, cs:qword_140011018; SRWLock
0x140008601  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x140008608  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x14000860d  mov     rcx, cs:qword_140011018; SRWLock
0x140008614  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x140008619  nop
0x14000861a  jmp     loc_1400086CB
0x14000861f  bt      r8d, 1Eh
0x140008624  jnb     short loc_14000863C
0x140008626  mov     r9d, eax; unsigned int
0x140008629  mov     edx, ecx; unsigned int
0x14000862b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x140008632  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x140008637  jmp     loc_1400086CB
0x14000863c  test    eax, eax
0x14000863e  jnz     short loc_1400086BA
0x140008640  cmp     r8d, 0FEh
0x140008647  jz      short loc_1400086BA
0x140008649  mov     [rsp+38h+var_18], 0
0x140008652  mov     dword ptr [rsp+38h+var_18], ecx
0x140008656  mov     word ptr [rsp+38h+var_18+4], r8w
0x14000865c  test    edx, edx
0x14000865e  jns     short loc_140008666
0x140008660  or      word ptr [rsp+38h+var_18+6], 1
0x140008666  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x14000866d  test    rax, rax
0x140008670  jnz     short loc_1400086AE
0x140008672  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140008679  test    rax, rax
0x14000867c  jnz     short loc_140008692
0x14000867e  lea     rcx, ModuleName; "ntdll.dll"
0x140008685  call    cs:__imp_GetModuleHandleW
0x14000868b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140008692  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x140008699  mov     rcx, rax; hModule
0x14000869c  call    cs:__imp_GetProcAddress
0x1400086a2  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x1400086a9  test    rax, rax
0x1400086ac  jz      short loc_1400086CB
0x1400086ae  lea     rcx, [rsp+38h+var_18]
0x1400086b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400086b8  jmp     short loc_1400086CB
0x1400086ba  mov     r9, rax
0x1400086bd  mov     edx, ecx
0x1400086bf  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1400086c6  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1400086cb  add     rsp, 38h
0x1400086cf  retn
```
