# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000b6a0`
- end: `0x18000b7c0`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1800076c4`
- `0x180008dd4`
- `0x18000903c`
- `0x180009424`
- `0x1800095e0`
- `0x18000b6a0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b775`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b775`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b78c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b78c`

## string_xrefs

- `0x18000b76e`: `ntdll.dll`

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
         && wil::details::FeatureStateManager::EnsureStateData((RTL_SRWLOCK *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180014028[25], qword_180014028);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180014028);
  }
}

```

## disassembly

```asm
0x18000b6a0  sub     rsp, 38h
0x18000b6a4  mov     eax, r8d
0x18000b6a7  mov     r8d, edx
0x18000b6aa  btr     r8d, 1Fh; unsigned __int16
0x18000b6af  test    ecx, ecx
0x18000b6b1  jnz     short loc_18000B70F
0x18000b6b3  test    eax, eax
0x18000b6b5  jnz     short loc_18000B70F
0x18000b6b7  test    r8d, r8d
0x18000b6ba  jnz     short loc_18000B70F
0x18000b6bc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x18000b6c3  jnz     short loc_18000B70A
0x18000b6c5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000b6cc  test    rax, rax
0x18000b6cf  jz      short loc_18000B6DA
0x18000b6d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6d6  test    al, al
0x18000b6d8  jnz     short loc_18000B70A
0x18000b6da  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000b6e1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000b6e6  test    al, al
0x18000b6e8  jz      short loc_18000B70A
0x18000b6ea  mov     rdx, cs:qword_180014028; SRWLock
0x18000b6f1  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000b6f8  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000b6fd  mov     rcx, cs:qword_180014028; SRWLock
0x18000b704  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000b709  nop
0x18000b70a  jmp     loc_18000B7BB
0x18000b70f  bt      r8d, 1Eh
0x18000b714  jnb     short loc_18000B72C
0x18000b716  mov     r9d, eax; unsigned int
0x18000b719  mov     edx, ecx; unsigned int
0x18000b71b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000b722  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18000b727  jmp     loc_18000B7BB
0x18000b72c  test    eax, eax
0x18000b72e  jnz     short loc_18000B7AA
0x18000b730  cmp     r8d, 0FEh
0x18000b737  jz      short loc_18000B7AA
0x18000b739  mov     [rsp+38h+var_18], 0
0x18000b742  mov     dword ptr [rsp+38h+var_18], ecx
0x18000b746  mov     word ptr [rsp+38h+var_18+4], r8w
0x18000b74c  test    edx, edx
0x18000b74e  jns     short loc_18000B756
0x18000b750  or      word ptr [rsp+38h+var_18+6], 1
0x18000b756  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000b75d  test    rax, rax
0x18000b760  jnz     short loc_18000B79E
0x18000b762  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b769  test    rax, rax
0x18000b76c  jnz     short loc_18000B782
0x18000b76e  lea     rcx, ModuleName; "ntdll.dll"
0x18000b775  call    cs:__imp_GetModuleHandleW
0x18000b77b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b782  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000b789  mov     rcx, rax; hModule
0x18000b78c  call    cs:__imp_GetProcAddress
0x18000b792  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000b799  test    rax, rax
0x18000b79c  jz      short loc_18000B7BB
0x18000b79e  lea     rcx, [rsp+38h+var_18]
0x18000b7a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7a8  jmp     short loc_18000B7BB
0x18000b7aa  mov     r9, rax
0x18000b7ad  mov     edx, ecx
0x18000b7af  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000b7b6  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000b7bb  add     rsp, 38h
0x18000b7bf  retn
```
