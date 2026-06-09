# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000f640`
- end: `0x18000f760`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000ac34`
- `0x18000c9fc`
- `0x18000cc00`
- `0x18000d1a4`
- `0x18000d3a0`
- `0x18000f640`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f715`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f715`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f72c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f72c`

## string_xrefs

- `0x18000f70e`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_18003A080[25], qword_18003A080);
    wil::details_abi::FeatureStateData::RecordUsage(qword_18003A080);
  }
}

```

## disassembly

```asm
0x18000f640  sub     rsp, 38h
0x18000f644  mov     eax, r8d
0x18000f647  mov     r8d, edx
0x18000f64a  btr     r8d, 1Fh; unsigned __int16
0x18000f64f  test    ecx, ecx
0x18000f651  jnz     short loc_18000F6AF
0x18000f653  test    eax, eax
0x18000f655  jnz     short loc_18000F6AF
0x18000f657  test    r8d, r8d
0x18000f65a  jnz     short loc_18000F6AF
0x18000f65c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x18000f663  jnz     short loc_18000F6AA
0x18000f665  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000f66c  test    rax, rax
0x18000f66f  jz      short loc_18000F67A
0x18000f671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f676  test    al, al
0x18000f678  jnz     short loc_18000F6AA
0x18000f67a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000f681  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000f686  test    al, al
0x18000f688  jz      short loc_18000F6AA
0x18000f68a  mov     rdx, cs:qword_18003A080; SRWLock
0x18000f691  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000f698  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000f69d  mov     rcx, cs:qword_18003A080; SRWLock
0x18000f6a4  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000f6a9  nop
0x18000f6aa  jmp     loc_18000F75B
0x18000f6af  bt      r8d, 1Eh
0x18000f6b4  jnb     short loc_18000F6CC
0x18000f6b6  mov     r9d, eax; unsigned int
0x18000f6b9  mov     edx, ecx; unsigned int
0x18000f6bb  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000f6c2  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18000f6c7  jmp     loc_18000F75B
0x18000f6cc  test    eax, eax
0x18000f6ce  jnz     short loc_18000F74A
0x18000f6d0  cmp     r8d, 0FEh
0x18000f6d7  jz      short loc_18000F74A
0x18000f6d9  mov     [rsp+38h+var_18], 0
0x18000f6e2  mov     dword ptr [rsp+38h+var_18], ecx
0x18000f6e6  mov     word ptr [rsp+38h+var_18+4], r8w
0x18000f6ec  test    edx, edx
0x18000f6ee  jns     short loc_18000F6F6
0x18000f6f0  or      word ptr [rsp+38h+var_18+6], 1
0x18000f6f6  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000f6fd  test    rax, rax
0x18000f700  jnz     short loc_18000F73E
0x18000f702  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000f709  test    rax, rax
0x18000f70c  jnz     short loc_18000F722
0x18000f70e  lea     rcx, aNtdllDll; "ntdll.dll"
0x18000f715  call    cs:__imp_GetModuleHandleW
0x18000f71b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000f722  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000f729  mov     rcx, rax; hModule
0x18000f72c  call    cs:__imp_GetProcAddress
0x18000f732  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000f739  test    rax, rax
0x18000f73c  jz      short loc_18000F75B
0x18000f73e  lea     rcx, [rsp+38h+var_18]
0x18000f743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f748  jmp     short loc_18000F75B
0x18000f74a  mov     r9, rax
0x18000f74d  mov     edx, ecx
0x18000f74f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000f756  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000f75b  add     rsp, 38h
0x18000f75f  retn
```
