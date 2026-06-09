# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180007710`
- end: `0x18000783b`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `299`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180003c64`
- `0x1800053f4`
- `0x1800055f8`
- `0x180005b74`
- `0x180005d60`
- `0x180007710`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007807`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007807`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800077f0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800077f0`

## string_xrefs

- `0x1800077e9`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180012058[25], qword_180012058);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180012058);
  }
}

```

## disassembly

```asm
0x180007710  sub     rsp, 38h
0x180007714  mov     eax, r8d
0x180007717  mov     r8d, edx
0x18000771a  btr     r8d, 1Fh; unsigned __int16
0x18000771f  test    ecx, ecx
0x180007721  jnz     short loc_18000778A
0x180007723  test    eax, eax
0x180007725  jnz     short loc_18000778A
0x180007727  test    r8d, r8d
0x18000772a  jnz     short loc_18000778A
0x18000772c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180007733  jnz     loc_180007836
0x180007739  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180007740  test    rax, rax
0x180007743  jz      short loc_180007752
0x180007745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000774a  test    al, al
0x18000774c  jnz     loc_180007836
0x180007752  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180007759  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000775e  test    al, al
0x180007760  jz      loc_180007836
0x180007766  mov     rdx, cs:qword_180012058; SRWLock
0x18000776d  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180007774  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180007779  mov     rcx, cs:qword_180012058; SRWLock
0x180007780  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180007785  jmp     loc_180007836
0x18000778a  bt      r8d, 1Eh
0x18000778f  jnb     short loc_1800077A7
0x180007791  mov     edx, ecx; unsigned int
0x180007793  mov     r9d, eax; unsigned int
0x180007796  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000779d  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x1800077a2  jmp     loc_180007836
0x1800077a7  test    eax, eax
0x1800077a9  jnz     short loc_180007825
0x1800077ab  cmp     r8d, 0FEh
0x1800077b2  jz      short loc_180007825
0x1800077b4  mov     [rsp+38h+var_18], 0
0x1800077bd  mov     dword ptr [rsp+38h+var_18], ecx
0x1800077c1  mov     word ptr [rsp+38h+var_18+4], r8w
0x1800077c7  test    edx, edx
0x1800077c9  jns     short loc_1800077D1
0x1800077cb  or      word ptr [rsp+38h+var_18+6], 1
0x1800077d1  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x1800077d8  test    rax, rax
0x1800077db  jnz     short loc_180007819
0x1800077dd  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800077e4  test    rax, rax
0x1800077e7  jnz     short loc_1800077FD
0x1800077e9  lea     rcx, ModuleName; "ntdll.dll"
0x1800077f0  call    cs:__imp_GetModuleHandleW
0x1800077f6  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800077fd  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180007804  mov     rcx, rax; hModule
0x180007807  call    cs:__imp_GetProcAddress
0x18000780d  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180007814  test    rax, rax
0x180007817  jz      short loc_180007836
0x180007819  lea     rcx, [rsp+38h+var_18]
0x18000781e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007823  jmp     short loc_180007836
0x180007825  mov     edx, ecx
0x180007827  mov     r9, rax
0x18000782a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180007831  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180007836  add     rsp, 38h
0x18000783a  retn
```
