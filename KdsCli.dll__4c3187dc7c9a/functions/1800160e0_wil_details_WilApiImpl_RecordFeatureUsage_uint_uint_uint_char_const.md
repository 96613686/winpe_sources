# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x1800160e0`
- end: `0x18001620b`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `299`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180012c84`
- `0x180014354`
- `0x180014418`
- `0x1800147d4`
- `0x1800149c0`
- `0x1800160e0`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800161c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800161c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800161d7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800161d7`

## string_xrefs

- `0x1800161b9`: `ntdll.dll`

## pseudocode

```c
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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180023068[25], qword_180023068);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180023068);
  }
}

```

## disassembly

```asm
0x1800160e0  sub     rsp, 38h
0x1800160e4  mov     eax, r8d
0x1800160e7  mov     r8d, edx
0x1800160ea  btr     r8d, 1Fh; unsigned __int16
0x1800160ef  test    ecx, ecx
0x1800160f1  jnz     short loc_18001615A
0x1800160f3  test    eax, eax
0x1800160f5  jnz     short loc_18001615A
0x1800160f7  test    r8d, r8d
0x1800160fa  jnz     short loc_18001615A
0x1800160fc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180016103  jnz     loc_180016206
0x180016109  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180016110  test    rax, rax
0x180016113  jz      short loc_180016122
0x180016115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001611a  test    al, al
0x18001611c  jnz     loc_180016206
0x180016122  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180016129  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18001612e  test    al, al
0x180016130  jz      loc_180016206
0x180016136  mov     rdx, cs:qword_180023068; SRWLock
0x18001613d  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180016144  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180016149  mov     rcx, cs:qword_180023068; SRWLock
0x180016150  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180016155  jmp     loc_180016206
0x18001615a  bt      r8d, 1Eh
0x18001615f  jnb     short loc_180016177
0x180016161  mov     edx, ecx; unsigned int
0x180016163  mov     r9d, eax; unsigned int
0x180016166  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18001616d  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180016172  jmp     loc_180016206
0x180016177  test    eax, eax
0x180016179  jnz     short loc_1800161F5
0x18001617b  cmp     r8d, 0FEh
0x180016182  jz      short loc_1800161F5
0x180016184  mov     [rsp+38h+var_18], 0
0x18001618d  mov     dword ptr [rsp+38h+var_18], ecx
0x180016191  mov     word ptr [rsp+38h+var_18+4], r8w
0x180016197  test    edx, edx
0x180016199  jns     short loc_1800161A1
0x18001619b  or      word ptr [rsp+38h+var_18+6], 1
0x1800161a1  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x1800161a8  test    rax, rax
0x1800161ab  jnz     short loc_1800161E9
0x1800161ad  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800161b4  test    rax, rax
0x1800161b7  jnz     short loc_1800161CD
0x1800161b9  lea     rcx, ModuleName; "ntdll.dll"
0x1800161c0  call    cs:__imp_GetModuleHandleW
0x1800161c6  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800161cd  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x1800161d4  mov     rcx, rax; hModule
0x1800161d7  call    cs:__imp_GetProcAddress
0x1800161dd  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x1800161e4  test    rax, rax
0x1800161e7  jz      short loc_180016206
0x1800161e9  lea     rcx, [rsp+38h+var_18]
0x1800161ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161f3  jmp     short loc_180016206
0x1800161f5  mov     edx, ecx
0x1800161f7  mov     r9, rax
0x1800161fa  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180016201  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180016206  add     rsp, 38h
0x18001620a  retn
```
