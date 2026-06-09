# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x14000c220`
- end: `0x14000c340`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1400091c4`
- `0x140009f14`
- `0x140009fd8`
- `0x14000a334`
- `0x14000a4b8`
- `0x14000c220`
- `0x140013010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000c2f5`
- `KERNEL32!GetModuleHandleW` at `0x14000c2f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000c30c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000c30c`

## string_xrefs

- `0x14000c2ee`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_14001B048[25], qword_14001B048);
    wil::details_abi::FeatureStateData::RecordUsage(qword_14001B048);
  }
}

```

## disassembly

```asm
0x14000c220  sub     rsp, 38h
0x14000c224  mov     eax, r8d
0x14000c227  mov     r8d, edx
0x14000c22a  btr     r8d, 1Fh; unsigned __int16
0x14000c22f  test    ecx, ecx
0x14000c231  jnz     short loc_14000C28F
0x14000c233  test    eax, eax
0x14000c235  jnz     short loc_14000C28F
0x14000c237  test    r8d, r8d
0x14000c23a  jnz     short loc_14000C28F
0x14000c23c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x14000c243  jnz     short loc_14000C28A
0x14000c245  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000c24c  test    rax, rax
0x14000c24f  jz      short loc_14000C25A
0x14000c251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c256  test    al, al
0x14000c258  jnz     short loc_14000C28A
0x14000c25a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14000c261  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14000c266  test    al, al
0x14000c268  jz      short loc_14000C28A
0x14000c26a  mov     rdx, cs:qword_14001B048; SRWLock
0x14000c271  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x14000c278  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x14000c27d  mov     rcx, cs:qword_14001B048; SRWLock
0x14000c284  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14000c289  nop
0x14000c28a  jmp     loc_14000C33B
0x14000c28f  bt      r8d, 1Eh
0x14000c294  jnb     short loc_14000C2AC
0x14000c296  mov     r9d, eax; unsigned int
0x14000c299  mov     edx, ecx; unsigned int
0x14000c29b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x14000c2a2  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x14000c2a7  jmp     loc_14000C33B
0x14000c2ac  test    eax, eax
0x14000c2ae  jnz     short loc_14000C32A
0x14000c2b0  cmp     r8d, 0FEh
0x14000c2b7  jz      short loc_14000C32A
0x14000c2b9  mov     [rsp+38h+var_18], 0
0x14000c2c2  mov     dword ptr [rsp+38h+var_18], ecx
0x14000c2c6  mov     word ptr [rsp+38h+var_18+4], r8w
0x14000c2cc  test    edx, edx
0x14000c2ce  jns     short loc_14000C2D6
0x14000c2d0  or      word ptr [rsp+38h+var_18+6], 1
0x14000c2d6  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x14000c2dd  test    rax, rax
0x14000c2e0  jnz     short loc_14000C31E
0x14000c2e2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c2e9  test    rax, rax
0x14000c2ec  jnz     short loc_14000C302
0x14000c2ee  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14000c2f5  call    cs:__imp_GetModuleHandleW
0x14000c2fb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c302  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x14000c309  mov     rcx, rax; hModule
0x14000c30c  call    cs:__imp_GetProcAddress
0x14000c312  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x14000c319  test    rax, rax
0x14000c31c  jz      short loc_14000C33B
0x14000c31e  lea     rcx, [rsp+38h+var_18]
0x14000c323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c328  jmp     short loc_14000C33B
0x14000c32a  mov     r9, rax
0x14000c32d  mov     edx, ecx
0x14000c32f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000c336  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x14000c33b  add     rsp, 38h
0x14000c33f  retn
```
