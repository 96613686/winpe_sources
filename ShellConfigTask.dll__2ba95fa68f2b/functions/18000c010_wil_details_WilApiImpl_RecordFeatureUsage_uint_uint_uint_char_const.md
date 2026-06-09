# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000c010`
- end: `0x18000c130`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180006a64`
- `0x18000875c`
- `0x180008b0c`
- `0x1800092b4`
- `0x1800094b0`
- `0x18000c010`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c0e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c0e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c0fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c0fc`

## string_xrefs

- `0x18000c0de`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_1800410B8[25], qword_1800410B8);
    wil::details_abi::FeatureStateData::RecordUsage(qword_1800410B8);
  }
}

```

## disassembly

```asm
0x18000c010  sub     rsp, 38h
0x18000c014  mov     eax, r8d
0x18000c017  mov     r8d, edx
0x18000c01a  btr     r8d, 1Fh; unsigned __int16
0x18000c01f  test    ecx, ecx
0x18000c021  jnz     short loc_18000C07F
0x18000c023  test    eax, eax
0x18000c025  jnz     short loc_18000C07F
0x18000c027  test    r8d, r8d
0x18000c02a  jnz     short loc_18000C07F
0x18000c02c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x18000c033  jnz     short loc_18000C07A
0x18000c035  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000c03c  test    rax, rax
0x18000c03f  jz      short loc_18000C04A
0x18000c041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c046  test    al, al
0x18000c048  jnz     short loc_18000C07A
0x18000c04a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000c051  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000c056  test    al, al
0x18000c058  jz      short loc_18000C07A
0x18000c05a  mov     rdx, cs:qword_1800410B8; SRWLock
0x18000c061  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000c068  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000c06d  mov     rcx, cs:qword_1800410B8; SRWLock
0x18000c074  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000c079  nop
0x18000c07a  jmp     loc_18000C12B
0x18000c07f  bt      r8d, 1Eh
0x18000c084  jnb     short loc_18000C09C
0x18000c086  mov     r9d, eax; unsigned int
0x18000c089  mov     edx, ecx; unsigned int
0x18000c08b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000c092  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18000c097  jmp     loc_18000C12B
0x18000c09c  test    eax, eax
0x18000c09e  jnz     short loc_18000C11A
0x18000c0a0  cmp     r8d, 0FEh
0x18000c0a7  jz      short loc_18000C11A
0x18000c0a9  mov     [rsp+38h+var_18], 0
0x18000c0b2  mov     dword ptr [rsp+38h+var_18], ecx
0x18000c0b6  mov     word ptr [rsp+38h+var_18+4], r8w
0x18000c0bc  test    edx, edx
0x18000c0be  jns     short loc_18000C0C6
0x18000c0c0  or      word ptr [rsp+38h+var_18+6], 1
0x18000c0c6  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000c0cd  test    rax, rax
0x18000c0d0  jnz     short loc_18000C10E
0x18000c0d2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c0d9  test    rax, rax
0x18000c0dc  jnz     short loc_18000C0F2
0x18000c0de  lea     rcx, ModuleName; "ntdll.dll"
0x18000c0e5  call    cs:__imp_GetModuleHandleW
0x18000c0eb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c0f2  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000c0f9  mov     rcx, rax; hModule
0x18000c0fc  call    cs:__imp_GetProcAddress
0x18000c102  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000c109  test    rax, rax
0x18000c10c  jz      short loc_18000C12B
0x18000c10e  lea     rcx, [rsp+38h+var_18]
0x18000c113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c118  jmp     short loc_18000C12B
0x18000c11a  mov     r9, rax
0x18000c11d  mov     edx, ecx
0x18000c11f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000c126  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000c12b  add     rsp, 38h
0x18000c12f  retn
```
