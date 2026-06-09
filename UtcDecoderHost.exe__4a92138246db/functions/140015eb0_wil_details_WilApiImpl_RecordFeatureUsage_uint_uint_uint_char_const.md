# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x140015eb0`
- end: `0x140015fd0`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x140013b40`
- `0x14001461c`
- `0x1400146e0`
- `0x140014a90`
- `0x140014c14`
- `0x140015eb0`
- `0x140018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140015f85`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140015f85`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140015f9c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140015f9c`

## string_xrefs

- `0x140015f7e`: `ntdll.dll`

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
         && wil::details::FeatureStateManager::EnsureStateData((RTL_SRWLOCK *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_140025098[25], qword_140025098);
    wil::details_abi::FeatureStateData::RecordUsage(qword_140025098);
  }
}

```

## disassembly

```asm
0x140015eb0  sub     rsp, 38h
0x140015eb4  mov     eax, r8d
0x140015eb7  mov     r8d, edx
0x140015eba  btr     r8d, 1Fh; unsigned __int16
0x140015ebf  test    ecx, ecx
0x140015ec1  jnz     short loc_140015F1F
0x140015ec3  test    eax, eax
0x140015ec5  jnz     short loc_140015F1F
0x140015ec7  test    r8d, r8d
0x140015eca  jnz     short loc_140015F1F
0x140015ecc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x140015ed3  jnz     short loc_140015F1A
0x140015ed5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140015edc  test    rax, rax
0x140015edf  jz      short loc_140015EEA
0x140015ee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015ee6  test    al, al
0x140015ee8  jnz     short loc_140015F1A
0x140015eea  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x140015ef1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x140015ef6  test    al, al
0x140015ef8  jz      short loc_140015F1A
0x140015efa  mov     rdx, cs:qword_140025098; SRWLock
0x140015f01  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x140015f08  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x140015f0d  mov     rcx, cs:qword_140025098; SRWLock
0x140015f14  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x140015f19  nop
0x140015f1a  jmp     loc_140015FCB
0x140015f1f  bt      r8d, 1Eh
0x140015f24  jnb     short loc_140015F3C
0x140015f26  mov     r9d, eax; unsigned int
0x140015f29  mov     edx, ecx; unsigned int
0x140015f2b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x140015f32  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x140015f37  jmp     loc_140015FCB
0x140015f3c  test    eax, eax
0x140015f3e  jnz     short loc_140015FBA
0x140015f40  cmp     r8d, 0FEh
0x140015f47  jz      short loc_140015FBA
0x140015f49  mov     [rsp+38h+var_18], 0
0x140015f52  mov     dword ptr [rsp+38h+var_18], ecx
0x140015f56  mov     word ptr [rsp+38h+var_18+4], r8w
0x140015f5c  test    edx, edx
0x140015f5e  jns     short loc_140015F66
0x140015f60  or      word ptr [rsp+38h+var_18+6], 1
0x140015f66  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x140015f6d  test    rax, rax
0x140015f70  jnz     short loc_140015FAE
0x140015f72  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140015f79  test    rax, rax
0x140015f7c  jnz     short loc_140015F92
0x140015f7e  lea     rcx, ModuleName; "ntdll.dll"
0x140015f85  call    cs:__imp_GetModuleHandleW
0x140015f8b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140015f92  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x140015f99  mov     rcx, rax; hModule
0x140015f9c  call    cs:__imp_GetProcAddress
0x140015fa2  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x140015fa9  test    rax, rax
0x140015fac  jz      short loc_140015FCB
0x140015fae  lea     rcx, [rsp+38h+var_18]
0x140015fb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015fb8  jmp     short loc_140015FCB
0x140015fba  mov     r9, rax
0x140015fbd  mov     edx, ecx
0x140015fbf  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x140015fc6  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x140015fcb  add     rsp, 38h
0x140015fcf  retn
```
