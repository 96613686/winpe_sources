# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x140012d90`
- end: `0x140012eb0`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x14000e684`
- `0x1400101c8`
- `0x140010be0`
- `0x140011150`
- `0x140011310`
- `0x140012d90`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140012e65`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140012e65`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140012e7c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140012e7c`

## string_xrefs

- `0x140012e5e`: `ntdll.dll`

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
         && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_140030150[25], qword_140030150);
    wil::details_abi::FeatureStateData::RecordUsage(qword_140030150);
  }
}

```

## disassembly

```asm
0x140012d90  sub     rsp, 38h
0x140012d94  mov     eax, r8d
0x140012d97  mov     r8d, edx
0x140012d9a  btr     r8d, 1Fh; unsigned __int16
0x140012d9f  test    ecx, ecx
0x140012da1  jnz     short loc_140012DFF
0x140012da3  test    eax, eax
0x140012da5  jnz     short loc_140012DFF
0x140012da7  test    r8d, r8d
0x140012daa  jnz     short loc_140012DFF
0x140012dac  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x140012db3  jnz     short loc_140012DFA
0x140012db5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140012dbc  test    rax, rax
0x140012dbf  jz      short loc_140012DCA
0x140012dc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012dc6  test    al, al
0x140012dc8  jnz     short loc_140012DFA
0x140012dca  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x140012dd1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x140012dd6  test    al, al
0x140012dd8  jz      short loc_140012DFA
0x140012dda  mov     rdx, cs:qword_140030150; SRWLock
0x140012de1  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x140012de8  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x140012ded  mov     rcx, cs:qword_140030150; SRWLock
0x140012df4  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x140012df9  nop
0x140012dfa  jmp     loc_140012EAB
0x140012dff  bt      r8d, 1Eh
0x140012e04  jnb     short loc_140012E1C
0x140012e06  mov     r9d, eax; unsigned int
0x140012e09  mov     edx, ecx; unsigned int
0x140012e0b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x140012e12  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x140012e17  jmp     loc_140012EAB
0x140012e1c  test    eax, eax
0x140012e1e  jnz     short loc_140012E9A
0x140012e20  cmp     r8d, 0FEh
0x140012e27  jz      short loc_140012E9A
0x140012e29  mov     [rsp+38h+var_18], 0
0x140012e32  mov     dword ptr [rsp+38h+var_18], ecx
0x140012e36  mov     word ptr [rsp+38h+var_18+4], r8w
0x140012e3c  test    edx, edx
0x140012e3e  jns     short loc_140012E46
0x140012e40  or      word ptr [rsp+38h+var_18+6], 1
0x140012e46  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x140012e4d  test    rax, rax
0x140012e50  jnz     short loc_140012E8E
0x140012e52  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140012e59  test    rax, rax
0x140012e5c  jnz     short loc_140012E72
0x140012e5e  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x140012e65  call    cs:__imp_GetModuleHandleW
0x140012e6b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140012e72  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x140012e79  mov     rcx, rax; hModule
0x140012e7c  call    cs:__imp_GetProcAddress
0x140012e82  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x140012e89  test    rax, rax
0x140012e8c  jz      short loc_140012EAB
0x140012e8e  lea     rcx, [rsp+38h+var_18]
0x140012e93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012e98  jmp     short loc_140012EAB
0x140012e9a  mov     r9, rax
0x140012e9d  mov     edx, ecx
0x140012e9f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x140012ea6  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x140012eab  add     rsp, 38h
0x140012eaf  retn
```
