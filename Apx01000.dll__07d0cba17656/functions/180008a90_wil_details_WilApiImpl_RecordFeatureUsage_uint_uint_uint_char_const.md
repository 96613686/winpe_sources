# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180008a90`
- end: `0x180008bb0`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180004994`
- `0x180006134`
- `0x180006338`
- `0x1800068e4`
- `0x180006ae0`
- `0x180008a90`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008b65`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008b65`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008b7c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008b7c`

## string_xrefs

- `0x180008b5e`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180033058[25], qword_180033058);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180033058);
  }
}

```

## disassembly

```asm
0x180008a90  sub     rsp, 38h
0x180008a94  mov     eax, r8d
0x180008a97  mov     r8d, edx
0x180008a9a  btr     r8d, 1Fh; unsigned __int16
0x180008a9f  test    ecx, ecx
0x180008aa1  jnz     short loc_180008AFF
0x180008aa3  test    eax, eax
0x180008aa5  jnz     short loc_180008AFF
0x180008aa7  test    r8d, r8d
0x180008aaa  jnz     short loc_180008AFF
0x180008aac  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180008ab3  jnz     short loc_180008AFA
0x180008ab5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180008abc  test    rax, rax
0x180008abf  jz      short loc_180008ACA
0x180008ac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ac6  test    al, al
0x180008ac8  jnz     short loc_180008AFA
0x180008aca  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180008ad1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180008ad6  test    al, al
0x180008ad8  jz      short loc_180008AFA
0x180008ada  mov     rdx, cs:qword_180033058; SRWLock
0x180008ae1  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180008ae8  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180008aed  mov     rcx, cs:qword_180033058; SRWLock
0x180008af4  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180008af9  nop
0x180008afa  jmp     loc_180008BAB
0x180008aff  bt      r8d, 1Eh
0x180008b04  jnb     short loc_180008B1C
0x180008b06  mov     r9d, eax; unsigned int
0x180008b09  mov     edx, ecx; unsigned int
0x180008b0b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180008b12  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180008b17  jmp     loc_180008BAB
0x180008b1c  test    eax, eax
0x180008b1e  jnz     short loc_180008B9A
0x180008b20  cmp     r8d, 0FEh
0x180008b27  jz      short loc_180008B9A
0x180008b29  mov     [rsp+38h+var_18], 0
0x180008b32  mov     dword ptr [rsp+38h+var_18], ecx
0x180008b36  mov     word ptr [rsp+38h+var_18+4], r8w
0x180008b3c  test    edx, edx
0x180008b3e  jns     short loc_180008B46
0x180008b40  or      word ptr [rsp+38h+var_18+6], 1
0x180008b46  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180008b4d  test    rax, rax
0x180008b50  jnz     short loc_180008B8E
0x180008b52  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008b59  test    rax, rax
0x180008b5c  jnz     short loc_180008B72
0x180008b5e  lea     rcx, ModuleName; "ntdll.dll"
0x180008b65  call    cs:__imp_GetModuleHandleW
0x180008b6b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008b72  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180008b79  mov     rcx, rax; hModule
0x180008b7c  call    cs:__imp_GetProcAddress
0x180008b82  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180008b89  test    rax, rax
0x180008b8c  jz      short loc_180008BAB
0x180008b8e  lea     rcx, [rsp+38h+var_18]
0x180008b93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b98  jmp     short loc_180008BAB
0x180008b9a  mov     r9, rax
0x180008b9d  mov     edx, ecx
0x180008b9f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180008ba6  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180008bab  add     rsp, 38h
0x180008baf  retn
```
