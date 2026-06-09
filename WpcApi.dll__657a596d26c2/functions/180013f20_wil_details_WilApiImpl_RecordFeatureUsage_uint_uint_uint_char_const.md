# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180013f20`
- end: `0x180014040`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180010024`
- `0x180010ccc`
- `0x180010fd0`
- `0x180011398`
- `0x18001151c`
- `0x180013f20`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013ff5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013ff5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001400c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001400c`

## string_xrefs

- `0x180013fee`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_1800440F0[25], qword_1800440F0);
    wil::details_abi::FeatureStateData::RecordUsage(qword_1800440F0);
  }
}

```

## disassembly

```asm
0x180013f20  sub     rsp, 38h
0x180013f24  mov     eax, r8d
0x180013f27  mov     r8d, edx
0x180013f2a  btr     r8d, 1Fh; unsigned __int16
0x180013f2f  test    ecx, ecx
0x180013f31  jnz     short loc_180013F8F
0x180013f33  test    eax, eax
0x180013f35  jnz     short loc_180013F8F
0x180013f37  test    r8d, r8d
0x180013f3a  jnz     short loc_180013F8F
0x180013f3c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180013f43  jnz     short loc_180013F8A
0x180013f45  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180013f4c  test    rax, rax
0x180013f4f  jz      short loc_180013F5A
0x180013f51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f56  test    al, al
0x180013f58  jnz     short loc_180013F8A
0x180013f5a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180013f61  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180013f66  test    al, al
0x180013f68  jz      short loc_180013F8A
0x180013f6a  mov     rdx, cs:qword_1800440F0; SRWLock
0x180013f71  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180013f78  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180013f7d  mov     rcx, cs:qword_1800440F0; SRWLock
0x180013f84  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180013f89  nop
0x180013f8a  jmp     loc_18001403B
0x180013f8f  bt      r8d, 1Eh
0x180013f94  jnb     short loc_180013FAC
0x180013f96  mov     r9d, eax; unsigned int
0x180013f99  mov     edx, ecx; unsigned int
0x180013f9b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180013fa2  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180013fa7  jmp     loc_18001403B
0x180013fac  test    eax, eax
0x180013fae  jnz     short loc_18001402A
0x180013fb0  cmp     r8d, 0FEh
0x180013fb7  jz      short loc_18001402A
0x180013fb9  mov     [rsp+38h+var_18], 0
0x180013fc2  mov     dword ptr [rsp+38h+var_18], ecx
0x180013fc6  mov     word ptr [rsp+38h+var_18+4], r8w
0x180013fcc  test    edx, edx
0x180013fce  jns     short loc_180013FD6
0x180013fd0  or      word ptr [rsp+38h+var_18+6], 1
0x180013fd6  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180013fdd  test    rax, rax
0x180013fe0  jnz     short loc_18001401E
0x180013fe2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180013fe9  test    rax, rax
0x180013fec  jnz     short loc_180014002
0x180013fee  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180013ff5  call    cs:__imp_GetModuleHandleW
0x180013ffb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180014002  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180014009  mov     rcx, rax; hModule
0x18001400c  call    cs:__imp_GetProcAddress
0x180014012  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180014019  test    rax, rax
0x18001401c  jz      short loc_18001403B
0x18001401e  lea     rcx, [rsp+38h+var_18]
0x180014023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014028  jmp     short loc_18001403B
0x18001402a  mov     r9, rax
0x18001402d  mov     edx, ecx
0x18001402f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180014036  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18001403b  add     rsp, 38h
0x18001403f  retn
```
