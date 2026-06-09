# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180015630`
- end: `0x180015750`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1800119d4`
- `0x180013094`
- `0x180013438`
- `0x180013804`
- `0x1800139c0`
- `0x180015630`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180015705`
- `KERNEL32!GetModuleHandleW` at `0x180015705`
- `KERNEL32!GetProcAddress` at `0x18001571c`
- `KERNEL32!GetProcAddress` at `0x18001571c`

## string_xrefs

- `0x1800156fe`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180070028[25], qword_180070028);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180070028);
  }
}

```

## disassembly

```asm
0x180015630  sub     rsp, 38h
0x180015634  mov     eax, r8d
0x180015637  mov     r8d, edx
0x18001563a  btr     r8d, 1Fh; unsigned __int16
0x18001563f  test    ecx, ecx
0x180015641  jnz     short loc_18001569F
0x180015643  test    eax, eax
0x180015645  jnz     short loc_18001569F
0x180015647  test    r8d, r8d
0x18001564a  jnz     short loc_18001569F
0x18001564c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180015653  jnz     short loc_18001569A
0x180015655  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001565c  test    rax, rax
0x18001565f  jz      short loc_18001566A
0x180015661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015666  test    al, al
0x180015668  jnz     short loc_18001569A
0x18001566a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180015671  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180015676  test    al, al
0x180015678  jz      short loc_18001569A
0x18001567a  mov     rdx, cs:qword_180070028; SRWLock
0x180015681  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180015688  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18001568d  mov     rcx, cs:qword_180070028; SRWLock
0x180015694  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180015699  nop
0x18001569a  jmp     loc_18001574B
0x18001569f  bt      r8d, 1Eh
0x1800156a4  jnb     short loc_1800156BC
0x1800156a6  mov     r9d, eax; unsigned int
0x1800156a9  mov     edx, ecx; unsigned int
0x1800156ab  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x1800156b2  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x1800156b7  jmp     loc_18001574B
0x1800156bc  test    eax, eax
0x1800156be  jnz     short loc_18001573A
0x1800156c0  cmp     r8d, 0FEh
0x1800156c7  jz      short loc_18001573A
0x1800156c9  mov     [rsp+38h+var_18], 0
0x1800156d2  mov     dword ptr [rsp+38h+var_18], ecx
0x1800156d6  mov     word ptr [rsp+38h+var_18+4], r8w
0x1800156dc  test    edx, edx
0x1800156de  jns     short loc_1800156E6
0x1800156e0  or      word ptr [rsp+38h+var_18+6], 1
0x1800156e6  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x1800156ed  test    rax, rax
0x1800156f0  jnz     short loc_18001572E
0x1800156f2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x1800156f9  test    rax, rax
0x1800156fc  jnz     short loc_180015712
0x1800156fe  lea     rcx, ModuleName; "ntdll.dll"
0x180015705  call    cs:__imp_GetModuleHandleW
0x18001570b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180015712  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180015719  mov     rcx, rax; hModule
0x18001571c  call    cs:__imp_GetProcAddress
0x180015722  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180015729  test    rax, rax
0x18001572c  jz      short loc_18001574B
0x18001572e  lea     rcx, [rsp+38h+var_18]
0x180015733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015738  jmp     short loc_18001574B
0x18001573a  mov     r9, rax
0x18001573d  mov     edx, ecx
0x18001573f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180015746  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18001574b  add     rsp, 38h
0x18001574f  retn
```
