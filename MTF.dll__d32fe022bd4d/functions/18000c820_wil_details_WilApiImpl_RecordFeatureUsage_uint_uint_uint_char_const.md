# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000c820`
- end: `0x18000c940`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000a2b0`
- `0x18000acc4`
- `0x18000ae30`
- `0x18000b1bc`
- `0x18000b340`
- `0x18000c820`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c90c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c90c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c8f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c8f5`

## string_xrefs

- `0x18000c8ee`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_18003E140[25], qword_18003E140);
    wil::details_abi::FeatureStateData::RecordUsage(qword_18003E140);
  }
}

```

## disassembly

```asm
0x18000c820  sub     rsp, 38h
0x18000c824  mov     eax, r8d
0x18000c827  mov     r8d, edx
0x18000c82a  btr     r8d, 1Fh; unsigned __int16
0x18000c82f  test    ecx, ecx
0x18000c831  jnz     short loc_18000C88F
0x18000c833  test    eax, eax
0x18000c835  jnz     short loc_18000C88F
0x18000c837  test    r8d, r8d
0x18000c83a  jnz     short loc_18000C88F
0x18000c83c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x18000c843  jnz     short loc_18000C88A
0x18000c845  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000c84c  test    rax, rax
0x18000c84f  jz      short loc_18000C85A
0x18000c851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c856  test    al, al
0x18000c858  jnz     short loc_18000C88A
0x18000c85a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000c861  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000c866  test    al, al
0x18000c868  jz      short loc_18000C88A
0x18000c86a  mov     rdx, cs:qword_18003E140; SRWLock
0x18000c871  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000c878  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000c87d  mov     rcx, cs:qword_18003E140; SRWLock
0x18000c884  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000c889  nop
0x18000c88a  jmp     loc_18000C93B
0x18000c88f  bt      r8d, 1Eh
0x18000c894  jnb     short loc_18000C8AC
0x18000c896  mov     r9d, eax; unsigned int
0x18000c899  mov     edx, ecx; unsigned int
0x18000c89b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000c8a2  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18000c8a7  jmp     loc_18000C93B
0x18000c8ac  test    eax, eax
0x18000c8ae  jnz     short loc_18000C92A
0x18000c8b0  cmp     r8d, 0FEh
0x18000c8b7  jz      short loc_18000C92A
0x18000c8b9  mov     [rsp+38h+var_18], 0
0x18000c8c2  mov     dword ptr [rsp+38h+var_18], ecx
0x18000c8c6  mov     word ptr [rsp+38h+var_18+4], r8w
0x18000c8cc  test    edx, edx
0x18000c8ce  jns     short loc_18000C8D6
0x18000c8d0  or      word ptr [rsp+38h+var_18+6], 1
0x18000c8d6  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000c8dd  test    rax, rax
0x18000c8e0  jnz     short loc_18000C91E
0x18000c8e2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c8e9  test    rax, rax
0x18000c8ec  jnz     short loc_18000C902
0x18000c8ee  lea     rcx, ModuleName; "ntdll.dll"
0x18000c8f5  call    cs:__imp_GetModuleHandleW
0x18000c8fb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c902  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000c909  mov     rcx, rax; hModule
0x18000c90c  call    cs:__imp_GetProcAddress
0x18000c912  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000c919  test    rax, rax
0x18000c91c  jz      short loc_18000C93B
0x18000c91e  lea     rcx, [rsp+38h+var_18]
0x18000c923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c928  jmp     short loc_18000C93B
0x18000c92a  mov     r9, rax
0x18000c92d  mov     edx, ecx
0x18000c92f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000c936  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000c93b  add     rsp, 38h
0x18000c93f  retn
```
