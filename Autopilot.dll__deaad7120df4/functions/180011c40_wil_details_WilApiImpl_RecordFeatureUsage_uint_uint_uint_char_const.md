# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180011c40`
- end: `0x180011d79`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `313`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000c870`
- `0x18000e60c`
- `0x18000ebe0`
- `0x18000f1c4`
- `0x18000f3e4`
- `0x180011c40`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011d1d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011d1d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011d3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011d3a`

## string_xrefs

- `0x180011d16`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180043170[25], qword_180043170);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180043170);
  }
}

```

## disassembly

```asm
0x180011c40  sub     rsp, 38h
0x180011c44  mov     eax, r8d
0x180011c47  mov     r8d, edx
0x180011c4a  btr     r8d, 1Fh; unsigned __int16
0x180011c4f  test    ecx, ecx
0x180011c51  jnz     short loc_180011CB0
0x180011c53  test    eax, eax
0x180011c55  jnz     short loc_180011CB0
0x180011c57  test    r8d, r8d
0x180011c5a  jnz     short loc_180011CB0
0x180011c5c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180011c63  jnz     short loc_180011CAA
0x180011c65  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180011c6c  test    rax, rax
0x180011c6f  jz      short loc_180011C7A
0x180011c71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c76  test    al, al
0x180011c78  jnz     short loc_180011CAA
0x180011c7a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180011c81  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180011c86  test    al, al
0x180011c88  jz      short loc_180011CAA
0x180011c8a  mov     rdx, cs:qword_180043170; SRWLock
0x180011c91  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180011c98  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180011c9d  mov     rcx, cs:qword_180043170; SRWLock
0x180011ca4  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180011ca9  nop
0x180011caa  add     rsp, 38h
0x180011cae  retn
0x180011cb0  bt      r8d, 1Eh
0x180011cb5  jnb     short loc_180011CCC
0x180011cb7  mov     r9d, eax; unsigned int
0x180011cba  mov     edx, ecx; unsigned int
0x180011cbc  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180011cc3  add     rsp, 38h
0x180011cc7  jmp     ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180011ccc  test    eax, eax
0x180011cce  jnz     loc_180011D62
0x180011cd4  cmp     r8d, 0FEh
0x180011cdb  jz      loc_180011D62
0x180011ce1  mov     [rsp+38h+var_18], 0
0x180011cea  mov     dword ptr [rsp+38h+var_18], ecx
0x180011cee  mov     word ptr [rsp+38h+var_18+4], r8w
0x180011cf4  test    edx, edx
0x180011cf6  jns     short loc_180011CFE
0x180011cf8  or      word ptr [rsp+38h+var_18+6], 1
0x180011cfe  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180011d05  test    rax, rax
0x180011d08  jnz     short loc_180011D52
0x180011d0a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180011d11  test    rax, rax
0x180011d14  jnz     short loc_180011D30
0x180011d16  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180011d1d  call    cs:__imp_GetModuleHandleW
0x180011d24  nop     dword ptr [rax+rax+00h]
0x180011d29  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180011d30  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180011d37  mov     rcx, rax; hModule
0x180011d3a  call    cs:__imp_GetProcAddress
0x180011d41  nop     dword ptr [rax+rax+00h]
0x180011d46  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180011d4d  test    rax, rax
0x180011d50  jz      short loc_180011D73
0x180011d52  lea     rcx, [rsp+38h+var_18]
0x180011d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d5c  add     rsp, 38h
0x180011d60  retn
0x180011d62  mov     r9, rax
0x180011d65  mov     edx, ecx
0x180011d67  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180011d6e  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180011d73  add     rsp, 38h
0x180011d77  retn
```
