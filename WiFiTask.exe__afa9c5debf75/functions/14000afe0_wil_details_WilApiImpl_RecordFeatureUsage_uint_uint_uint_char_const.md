# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x14000afe0`
- end: `0x14000b100`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x14000492c`
- `0x140007c14`
- `0x140007ed0`
- `0x140008634`
- `0x140008830`
- `0x14000afe0`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000b0b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000b0b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b0cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b0cc`

## string_xrefs

- `0x14000b0ae`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_1400190A8[25], qword_1400190A8);
    wil::details_abi::FeatureStateData::RecordUsage(qword_1400190A8);
  }
}

```

## disassembly

```asm
0x14000afe0  sub     rsp, 38h
0x14000afe4  mov     eax, r8d
0x14000afe7  mov     r8d, edx
0x14000afea  btr     r8d, 1Fh; unsigned __int16
0x14000afef  test    ecx, ecx
0x14000aff1  jnz     short loc_14000B04F
0x14000aff3  test    eax, eax
0x14000aff5  jnz     short loc_14000B04F
0x14000aff7  test    r8d, r8d
0x14000affa  jnz     short loc_14000B04F
0x14000affc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x14000b003  jnz     short loc_14000B04A
0x14000b005  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000b00c  test    rax, rax
0x14000b00f  jz      short loc_14000B01A
0x14000b011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b016  test    al, al
0x14000b018  jnz     short loc_14000B04A
0x14000b01a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14000b021  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14000b026  test    al, al
0x14000b028  jz      short loc_14000B04A
0x14000b02a  mov     rdx, cs:qword_1400190A8; SRWLock
0x14000b031  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x14000b038  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x14000b03d  mov     rcx, cs:qword_1400190A8; SRWLock
0x14000b044  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14000b049  nop
0x14000b04a  jmp     loc_14000B0FB
0x14000b04f  bt      r8d, 1Eh
0x14000b054  jnb     short loc_14000B06C
0x14000b056  mov     r9d, eax; unsigned int
0x14000b059  mov     edx, ecx; unsigned int
0x14000b05b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x14000b062  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x14000b067  jmp     loc_14000B0FB
0x14000b06c  test    eax, eax
0x14000b06e  jnz     short loc_14000B0EA
0x14000b070  cmp     r8d, 0FEh
0x14000b077  jz      short loc_14000B0EA
0x14000b079  mov     [rsp+38h+var_18], 0
0x14000b082  mov     dword ptr [rsp+38h+var_18], ecx
0x14000b086  mov     word ptr [rsp+38h+var_18+4], r8w
0x14000b08c  test    edx, edx
0x14000b08e  jns     short loc_14000B096
0x14000b090  or      word ptr [rsp+38h+var_18+6], 1
0x14000b096  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x14000b09d  test    rax, rax
0x14000b0a0  jnz     short loc_14000B0DE
0x14000b0a2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b0a9  test    rax, rax
0x14000b0ac  jnz     short loc_14000B0C2
0x14000b0ae  lea     rcx, ModuleName; "ntdll.dll"
0x14000b0b5  call    cs:__imp_GetModuleHandleW
0x14000b0bb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b0c2  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x14000b0c9  mov     rcx, rax; hModule
0x14000b0cc  call    cs:__imp_GetProcAddress
0x14000b0d2  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x14000b0d9  test    rax, rax
0x14000b0dc  jz      short loc_14000B0FB
0x14000b0de  lea     rcx, [rsp+38h+var_18]
0x14000b0e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b0e8  jmp     short loc_14000B0FB
0x14000b0ea  mov     r9, rax
0x14000b0ed  mov     edx, ecx
0x14000b0ef  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000b0f6  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x14000b0fb  add     rsp, 38h
0x14000b0ff  retn
```
