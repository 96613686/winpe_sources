# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180007d70`
- end: `0x180007e9b`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `299`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180004430`
- `0x180005c94`
- `0x180005e98`
- `0x180006414`
- `0x180006600`
- `0x180007d70`
- `0x180017010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180007e50`
- `KERNEL32!GetModuleHandleW` at `0x180007e50`
- `KERNEL32!GetProcAddress` at `0x180007e67`
- `KERNEL32!GetProcAddress` at `0x180007e67`

## string_xrefs

- `0x180007e49`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_1800201C8[25], qword_1800201C8);
    wil::details_abi::FeatureStateData::RecordUsage(qword_1800201C8);
  }
}

```

## disassembly

```asm
0x180007d70  sub     rsp, 38h
0x180007d74  mov     eax, r8d
0x180007d77  mov     r8d, edx
0x180007d7a  btr     r8d, 1Fh; unsigned __int16
0x180007d7f  test    ecx, ecx
0x180007d81  jnz     short loc_180007DEA
0x180007d83  test    eax, eax
0x180007d85  jnz     short loc_180007DEA
0x180007d87  test    r8d, r8d
0x180007d8a  jnz     short loc_180007DEA
0x180007d8c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180007d93  jnz     loc_180007E96
0x180007d99  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180007da0  test    rax, rax
0x180007da3  jz      short loc_180007DB2
0x180007da5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007daa  test    al, al
0x180007dac  jnz     loc_180007E96
0x180007db2  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180007db9  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180007dbe  test    al, al
0x180007dc0  jz      loc_180007E96
0x180007dc6  mov     rdx, cs:qword_1800201C8; SRWLock
0x180007dcd  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180007dd4  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180007dd9  mov     rcx, cs:qword_1800201C8; SRWLock
0x180007de0  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180007de5  jmp     loc_180007E96
0x180007dea  bt      r8d, 1Eh
0x180007def  jnb     short loc_180007E07
0x180007df1  mov     edx, ecx; unsigned int
0x180007df3  mov     r9d, eax; unsigned int
0x180007df6  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180007dfd  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180007e02  jmp     loc_180007E96
0x180007e07  test    eax, eax
0x180007e09  jnz     short loc_180007E85
0x180007e0b  cmp     r8d, 0FEh
0x180007e12  jz      short loc_180007E85
0x180007e14  mov     [rsp+38h+var_18], 0
0x180007e1d  mov     dword ptr [rsp+38h+var_18], ecx
0x180007e21  mov     word ptr [rsp+38h+var_18+4], r8w
0x180007e27  test    edx, edx
0x180007e29  jns     short loc_180007E31
0x180007e2b  or      word ptr [rsp+38h+var_18+6], 1
0x180007e31  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180007e38  test    rax, rax
0x180007e3b  jnz     short loc_180007E79
0x180007e3d  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007e44  test    rax, rax
0x180007e47  jnz     short loc_180007E5D
0x180007e49  lea     rcx, ModuleName; "ntdll.dll"
0x180007e50  call    cs:__imp_GetModuleHandleW
0x180007e56  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007e5d  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180007e64  mov     rcx, rax; hModule
0x180007e67  call    cs:__imp_GetProcAddress
0x180007e6d  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180007e74  test    rax, rax
0x180007e77  jz      short loc_180007E96
0x180007e79  lea     rcx, [rsp+38h+var_18]
0x180007e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e83  jmp     short loc_180007E96
0x180007e85  mov     edx, ecx
0x180007e87  mov     r9, rax
0x180007e8a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180007e91  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180007e96  add     rsp, 38h
0x180007e9a  retn
```
