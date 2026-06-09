# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180017a90`
- end: `0x180017bbb`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `299`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1800134d0`
- `0x180014b74`
- `0x180014dd4`
- `0x180015598`
- `0x180015750`
- `0x180017a90`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017b87`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017b87`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180017b70`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180017b70`

## string_xrefs

- `0x180017b69`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_1800292A0[25], qword_1800292A0);
    wil::details_abi::FeatureStateData::RecordUsage(qword_1800292A0);
  }
}

```

## disassembly

```asm
0x180017a90  sub     rsp, 38h
0x180017a94  mov     eax, r8d
0x180017a97  mov     r8d, edx
0x180017a9a  btr     r8d, 1Fh; unsigned __int16
0x180017a9f  test    ecx, ecx
0x180017aa1  jnz     short loc_180017B0A
0x180017aa3  test    eax, eax
0x180017aa5  jnz     short loc_180017B0A
0x180017aa7  test    r8d, r8d
0x180017aaa  jnz     short loc_180017B0A
0x180017aac  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180017ab3  jnz     loc_180017BB6
0x180017ab9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180017ac0  test    rax, rax
0x180017ac3  jz      short loc_180017AD2
0x180017ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017aca  test    al, al
0x180017acc  jnz     loc_180017BB6
0x180017ad2  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180017ad9  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180017ade  test    al, al
0x180017ae0  jz      loc_180017BB6
0x180017ae6  mov     rdx, cs:qword_1800292A0; SRWLock
0x180017aed  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180017af4  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180017af9  mov     rcx, cs:qword_1800292A0; SRWLock
0x180017b00  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180017b05  jmp     loc_180017BB6
0x180017b0a  bt      r8d, 1Eh
0x180017b0f  jnb     short loc_180017B27
0x180017b11  mov     edx, ecx; unsigned int
0x180017b13  mov     r9d, eax; unsigned int
0x180017b16  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180017b1d  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180017b22  jmp     loc_180017BB6
0x180017b27  test    eax, eax
0x180017b29  jnz     short loc_180017BA5
0x180017b2b  cmp     r8d, 0FEh
0x180017b32  jz      short loc_180017BA5
0x180017b34  mov     [rsp+38h+var_18], 0
0x180017b3d  mov     dword ptr [rsp+38h+var_18], ecx
0x180017b41  mov     word ptr [rsp+38h+var_18+4], r8w
0x180017b47  test    edx, edx
0x180017b49  jns     short loc_180017B51
0x180017b4b  or      word ptr [rsp+38h+var_18+6], 1
0x180017b51  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180017b58  test    rax, rax
0x180017b5b  jnz     short loc_180017B99
0x180017b5d  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180017b64  test    rax, rax
0x180017b67  jnz     short loc_180017B7D
0x180017b69  lea     rcx, ModuleName; "ntdll.dll"
0x180017b70  call    cs:__imp_GetModuleHandleW
0x180017b76  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180017b7d  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180017b84  mov     rcx, rax; hModule
0x180017b87  call    cs:__imp_GetProcAddress
0x180017b8d  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180017b94  test    rax, rax
0x180017b97  jz      short loc_180017BB6
0x180017b99  lea     rcx, [rsp+38h+var_18]
0x180017b9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ba3  jmp     short loc_180017BB6
0x180017ba5  mov     edx, ecx
0x180017ba7  mov     r9, rax
0x180017baa  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180017bb1  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180017bb6  add     rsp, 38h
0x180017bba  retn
```
