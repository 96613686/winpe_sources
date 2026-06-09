# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180011bc0`
- end: `0x180011ce0`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000a8d8`
- `0x18000ddbc`
- `0x18000ebc0`
- `0x18000f2f4`
- `0x18000f4b0`
- `0x180011bc0`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011cac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011cac`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011c95`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011c95`

## string_xrefs

- `0x180011c8e`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_1800820F8[25], qword_1800820F8);
    wil::details_abi::FeatureStateData::RecordUsage(qword_1800820F8);
  }
}

```

## disassembly

```asm
0x180011bc0  sub     rsp, 38h
0x180011bc4  mov     eax, r8d
0x180011bc7  mov     r8d, edx
0x180011bca  btr     r8d, 1Fh; unsigned __int16
0x180011bcf  test    ecx, ecx
0x180011bd1  jnz     short loc_180011C2F
0x180011bd3  test    eax, eax
0x180011bd5  jnz     short loc_180011C2F
0x180011bd7  test    r8d, r8d
0x180011bda  jnz     short loc_180011C2F
0x180011bdc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180011be3  jnz     short loc_180011C2A
0x180011be5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180011bec  test    rax, rax
0x180011bef  jz      short loc_180011BFA
0x180011bf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011bf6  test    al, al
0x180011bf8  jnz     short loc_180011C2A
0x180011bfa  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180011c01  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180011c06  test    al, al
0x180011c08  jz      short loc_180011C2A
0x180011c0a  mov     rdx, cs:qword_1800820F8; SRWLock
0x180011c11  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180011c18  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180011c1d  mov     rcx, cs:qword_1800820F8; SRWLock
0x180011c24  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180011c29  nop
0x180011c2a  jmp     loc_180011CDB
0x180011c2f  bt      r8d, 1Eh
0x180011c34  jnb     short loc_180011C4C
0x180011c36  mov     r9d, eax; unsigned int
0x180011c39  mov     edx, ecx; unsigned int
0x180011c3b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180011c42  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180011c47  jmp     loc_180011CDB
0x180011c4c  test    eax, eax
0x180011c4e  jnz     short loc_180011CCA
0x180011c50  cmp     r8d, 0FEh
0x180011c57  jz      short loc_180011CCA
0x180011c59  mov     [rsp+38h+var_18], 0
0x180011c62  mov     dword ptr [rsp+38h+var_18], ecx
0x180011c66  mov     word ptr [rsp+38h+var_18+4], r8w
0x180011c6c  test    edx, edx
0x180011c6e  jns     short loc_180011C76
0x180011c70  or      word ptr [rsp+38h+var_18+6], 1
0x180011c76  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180011c7d  test    rax, rax
0x180011c80  jnz     short loc_180011CBE
0x180011c82  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180011c89  test    rax, rax
0x180011c8c  jnz     short loc_180011CA2
0x180011c8e  lea     rcx, ModuleName; "ntdll.dll"
0x180011c95  call    cs:__imp_GetModuleHandleW
0x180011c9b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180011ca2  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180011ca9  mov     rcx, rax; hModule
0x180011cac  call    cs:__imp_GetProcAddress
0x180011cb2  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180011cb9  test    rax, rax
0x180011cbc  jz      short loc_180011CDB
0x180011cbe  lea     rcx, [rsp+38h+var_18]
0x180011cc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cc8  jmp     short loc_180011CDB
0x180011cca  mov     r9, rax
0x180011ccd  mov     edx, ecx
0x180011ccf  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180011cd6  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180011cdb  add     rsp, 38h
0x180011cdf  retn
```
