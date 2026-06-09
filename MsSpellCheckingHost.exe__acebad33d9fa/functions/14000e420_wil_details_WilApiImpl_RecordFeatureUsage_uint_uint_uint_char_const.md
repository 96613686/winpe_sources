# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x14000e420`
- end: `0x14000e540`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x140009d14`
- `0x14000bbcc`
- `0x14000bde8`
- `0x14000c364`
- `0x14000c560`
- `0x14000e420`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000e4f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000e4f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000e50c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000e50c`

## string_xrefs

- `0x14000e4ee`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_14001B178[25], qword_14001B178);
    wil::details_abi::FeatureStateData::RecordUsage(qword_14001B178);
  }
}

```

## disassembly

```asm
0x14000e420  sub     rsp, 38h
0x14000e424  mov     eax, r8d
0x14000e427  mov     r8d, edx
0x14000e42a  btr     r8d, 1Fh; unsigned __int16
0x14000e42f  test    ecx, ecx
0x14000e431  jnz     short loc_14000E48F
0x14000e433  test    eax, eax
0x14000e435  jnz     short loc_14000E48F
0x14000e437  test    r8d, r8d
0x14000e43a  jnz     short loc_14000E48F
0x14000e43c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x14000e443  jnz     short loc_14000E48A
0x14000e445  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000e44c  test    rax, rax
0x14000e44f  jz      short loc_14000E45A
0x14000e451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e456  test    al, al
0x14000e458  jnz     short loc_14000E48A
0x14000e45a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14000e461  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14000e466  test    al, al
0x14000e468  jz      short loc_14000E48A
0x14000e46a  mov     rdx, cs:qword_14001B178; SRWLock
0x14000e471  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x14000e478  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x14000e47d  mov     rcx, cs:qword_14001B178; SRWLock
0x14000e484  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14000e489  nop
0x14000e48a  jmp     loc_14000E53B
0x14000e48f  bt      r8d, 1Eh
0x14000e494  jnb     short loc_14000E4AC
0x14000e496  mov     r9d, eax; unsigned int
0x14000e499  mov     edx, ecx; unsigned int
0x14000e49b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x14000e4a2  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x14000e4a7  jmp     loc_14000E53B
0x14000e4ac  test    eax, eax
0x14000e4ae  jnz     short loc_14000E52A
0x14000e4b0  cmp     r8d, 0FEh
0x14000e4b7  jz      short loc_14000E52A
0x14000e4b9  mov     [rsp+38h+var_18], 0
0x14000e4c2  mov     dword ptr [rsp+38h+var_18], ecx
0x14000e4c6  mov     word ptr [rsp+38h+var_18+4], r8w
0x14000e4cc  test    edx, edx
0x14000e4ce  jns     short loc_14000E4D6
0x14000e4d0  or      word ptr [rsp+38h+var_18+6], 1
0x14000e4d6  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x14000e4dd  test    rax, rax
0x14000e4e0  jnz     short loc_14000E51E
0x14000e4e2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000e4e9  test    rax, rax
0x14000e4ec  jnz     short loc_14000E502
0x14000e4ee  lea     rcx, aNtdllDll; "ntdll.dll"
0x14000e4f5  call    cs:__imp_GetModuleHandleW
0x14000e4fb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000e502  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x14000e509  mov     rcx, rax; hModule
0x14000e50c  call    cs:__imp_GetProcAddress
0x14000e512  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x14000e519  test    rax, rax
0x14000e51c  jz      short loc_14000E53B
0x14000e51e  lea     rcx, [rsp+38h+var_18]
0x14000e523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e528  jmp     short loc_14000E53B
0x14000e52a  mov     r9, rax
0x14000e52d  mov     edx, ecx
0x14000e52f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000e536  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x14000e53b  add     rsp, 38h
0x14000e53f  retn
```
