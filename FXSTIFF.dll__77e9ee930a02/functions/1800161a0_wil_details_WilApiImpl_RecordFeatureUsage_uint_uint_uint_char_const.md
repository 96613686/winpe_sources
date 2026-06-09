# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x1800161a0`
- end: `0x1800162d9`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `313`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180012020`
- `0x1800137b0`
- `0x180013c64`
- `0x180014024`
- `0x180014208`
- `0x1800161a0`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18001627d`
- `KERNEL32!GetModuleHandleW` at `0x18001627d`
- `KERNEL32!GetProcAddress` at `0x18001629a`
- `KERNEL32!GetProcAddress` at `0x18001629a`

## string_xrefs

- `0x180016276`: `ntdll.dll`

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
        &wil::details::g_featureStateManager,
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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180071020[25], qword_180071020);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180071020);
  }
}

```

## disassembly

```asm
0x1800161a0  sub     rsp, 38h
0x1800161a4  mov     eax, r8d
0x1800161a7  mov     r8d, edx
0x1800161aa  btr     r8d, 1Fh; unsigned __int16
0x1800161af  test    ecx, ecx
0x1800161b1  jnz     short loc_180016210
0x1800161b3  test    eax, eax
0x1800161b5  jnz     short loc_180016210
0x1800161b7  test    r8d, r8d
0x1800161ba  jnz     short loc_180016210
0x1800161bc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x1800161c3  jnz     short loc_18001620A
0x1800161c5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800161cc  test    rax, rax
0x1800161cf  jz      short loc_1800161DA
0x1800161d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161d6  test    al, al
0x1800161d8  jnz     short loc_18001620A
0x1800161da  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x1800161e1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800161e6  test    al, al
0x1800161e8  jz      short loc_18001620A
0x1800161ea  mov     rdx, cs:qword_180071020; SRWLock
0x1800161f1  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800161f8  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x1800161fd  mov     rcx, cs:qword_180071020; SRWLock
0x180016204  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180016209  nop
0x18001620a  add     rsp, 38h
0x18001620e  retn
0x180016210  bt      r8d, 1Eh
0x180016215  jnb     short loc_18001622C
0x180016217  mov     r9d, eax; unsigned int
0x18001621a  mov     edx, ecx; unsigned int
0x18001621c  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180016223  add     rsp, 38h
0x180016227  jmp     ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18001622c  test    eax, eax
0x18001622e  jnz     loc_1800162C2
0x180016234  cmp     r8d, 0FEh
0x18001623b  jz      loc_1800162C2
0x180016241  mov     [rsp+38h+var_18], 0
0x18001624a  mov     dword ptr [rsp+38h+var_18], ecx
0x18001624e  mov     word ptr [rsp+38h+var_18+4], r8w
0x180016254  test    edx, edx
0x180016256  jns     short loc_18001625E
0x180016258  or      word ptr [rsp+38h+var_18+6], 1
0x18001625e  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180016265  test    rax, rax
0x180016268  jnz     short loc_1800162B2
0x18001626a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180016271  test    rax, rax
0x180016274  jnz     short loc_180016290
0x180016276  lea     rcx, ModuleName; "ntdll.dll"
0x18001627d  call    cs:__imp_GetModuleHandleW
0x180016284  nop     dword ptr [rax+rax+00h]
0x180016289  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180016290  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180016297  mov     rcx, rax; hModule
0x18001629a  call    cs:__imp_GetProcAddress
0x1800162a1  nop     dword ptr [rax+rax+00h]
0x1800162a6  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x1800162ad  test    rax, rax
0x1800162b0  jz      short loc_1800162D3
0x1800162b2  lea     rcx, [rsp+38h+var_18]
0x1800162b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162bc  add     rsp, 38h
0x1800162c0  retn
0x1800162c2  mov     r9, rax
0x1800162c5  mov     edx, ecx
0x1800162c7  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800162ce  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1800162d3  add     rsp, 38h
0x1800162d7  retn
```
