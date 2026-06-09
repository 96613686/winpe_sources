# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x1800191d0`
- end: `0x1800192f0`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1800157d4`
- `0x180016dc4`
- `0x180016f2c`
- `0x180017314`
- `0x1800174d0`
- `0x1800191d0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800192bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800192bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800192a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800192a5`

## string_xrefs

- `0x18001929e`: `ntdll.dll`

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
         && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_1800373F8[25], qword_1800373F8);
    wil::details_abi::FeatureStateData::RecordUsage(qword_1800373F8);
  }
}

```

## disassembly

```asm
0x1800191d0  sub     rsp, 38h
0x1800191d4  mov     eax, r8d
0x1800191d7  mov     r8d, edx
0x1800191da  btr     r8d, 1Fh; unsigned __int16
0x1800191df  test    ecx, ecx
0x1800191e1  jnz     short loc_18001923F
0x1800191e3  test    eax, eax
0x1800191e5  jnz     short loc_18001923F
0x1800191e7  test    r8d, r8d
0x1800191ea  jnz     short loc_18001923F
0x1800191ec  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x1800191f3  jnz     short loc_18001923A
0x1800191f5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800191fc  test    rax, rax
0x1800191ff  jz      short loc_18001920A
0x180019201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019206  test    al, al
0x180019208  jnz     short loc_18001923A
0x18001920a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180019211  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180019216  test    al, al
0x180019218  jz      short loc_18001923A
0x18001921a  mov     rdx, cs:qword_1800373F8; SRWLock
0x180019221  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180019228  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18001922d  mov     rcx, cs:qword_1800373F8; SRWLock
0x180019234  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180019239  nop
0x18001923a  jmp     loc_1800192EB
0x18001923f  bt      r8d, 1Eh
0x180019244  jnb     short loc_18001925C
0x180019246  mov     r9d, eax; unsigned int
0x180019249  mov     edx, ecx; unsigned int
0x18001924b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180019252  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180019257  jmp     loc_1800192EB
0x18001925c  test    eax, eax
0x18001925e  jnz     short loc_1800192DA
0x180019260  cmp     r8d, 0FEh
0x180019267  jz      short loc_1800192DA
0x180019269  mov     [rsp+38h+var_18], 0
0x180019272  mov     dword ptr [rsp+38h+var_18], ecx
0x180019276  mov     word ptr [rsp+38h+var_18+4], r8w
0x18001927c  test    edx, edx
0x18001927e  jns     short loc_180019286
0x180019280  or      word ptr [rsp+38h+var_18+6], 1
0x180019286  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18001928d  test    rax, rax
0x180019290  jnz     short loc_1800192CE
0x180019292  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180019299  test    rax, rax
0x18001929c  jnz     short loc_1800192B2
0x18001929e  lea     rcx, ModuleName; "ntdll.dll"
0x1800192a5  call    cs:__imp_GetModuleHandleW
0x1800192ab  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800192b2  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x1800192b9  mov     rcx, rax; hModule
0x1800192bc  call    cs:__imp_GetProcAddress
0x1800192c2  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x1800192c9  test    rax, rax
0x1800192cc  jz      short loc_1800192EB
0x1800192ce  lea     rcx, [rsp+38h+var_18]
0x1800192d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800192d8  jmp     short loc_1800192EB
0x1800192da  mov     r9, rax
0x1800192dd  mov     edx, ecx
0x1800192df  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800192e6  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1800192eb  add     rsp, 38h
0x1800192ef  retn
```
