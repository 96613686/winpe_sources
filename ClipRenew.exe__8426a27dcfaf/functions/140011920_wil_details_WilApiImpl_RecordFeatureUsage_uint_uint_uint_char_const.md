# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x140011920`
- end: `0x140011a4b`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `299`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x140006bf8`
- `0x14000fab8`
- `0x14000fc18`
- `0x140010314`
- `0x1400104d0`
- `0x140011920`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140011a17`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140011a17`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140011a00`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140011a00`

## string_xrefs

- `0x1400119f9`: `ntdll.dll`

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
        goto LABEL_19;
      ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
         && wil::details::FeatureStateManager::EnsureStateData((RTL_SRWLOCK *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_140019068[25], qword_140019068);
    wil::details_abi::FeatureStateData::RecordUsage(qword_140019068);
  }
}

```

## disassembly

```asm
0x140011920  sub     rsp, 38h
0x140011924  mov     eax, r8d
0x140011927  mov     r8d, edx
0x14001192a  btr     r8d, 1Fh; unsigned __int16
0x14001192f  test    ecx, ecx
0x140011931  jnz     short loc_14001199A
0x140011933  test    eax, eax
0x140011935  jnz     short loc_14001199A
0x140011937  test    r8d, r8d
0x14001193a  jnz     short loc_14001199A
0x14001193c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x140011943  jnz     loc_140011A46
0x140011949  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140011950  test    rax, rax
0x140011953  jz      short loc_140011962
0x140011955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001195a  test    al, al
0x14001195c  jnz     loc_140011A46
0x140011962  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x140011969  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14001196e  test    al, al
0x140011970  jz      loc_140011A46
0x140011976  mov     rdx, cs:qword_140019068; SRWLock
0x14001197d  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x140011984  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x140011989  mov     rcx, cs:qword_140019068; SRWLock
0x140011990  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x140011995  jmp     loc_140011A46
0x14001199a  bt      r8d, 1Eh
0x14001199f  jnb     short loc_1400119B7
0x1400119a1  mov     edx, ecx; unsigned int
0x1400119a3  mov     r9d, eax; unsigned int
0x1400119a6  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x1400119ad  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x1400119b2  jmp     loc_140011A46
0x1400119b7  test    eax, eax
0x1400119b9  jnz     short loc_140011A35
0x1400119bb  cmp     r8d, 0FEh
0x1400119c2  jz      short loc_140011A35
0x1400119c4  mov     [rsp+38h+var_18], 0
0x1400119cd  mov     dword ptr [rsp+38h+var_18], ecx
0x1400119d1  mov     word ptr [rsp+38h+var_18+4], r8w
0x1400119d7  test    edx, edx
0x1400119d9  jns     short loc_1400119E1
0x1400119db  or      word ptr [rsp+38h+var_18+6], 1
0x1400119e1  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x1400119e8  test    rax, rax
0x1400119eb  jnz     short loc_140011A29
0x1400119ed  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400119f4  test    rax, rax
0x1400119f7  jnz     short loc_140011A0D
0x1400119f9  lea     rcx, ModuleName; "ntdll.dll"
0x140011a00  call    cs:__imp_GetModuleHandleW
0x140011a06  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140011a0d  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x140011a14  mov     rcx, rax; hModule
0x140011a17  call    cs:__imp_GetProcAddress
0x140011a1d  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x140011a24  test    rax, rax
0x140011a27  jz      short loc_140011A46
0x140011a29  lea     rcx, [rsp+38h+var_18]
0x140011a2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011a33  jmp     short loc_140011A46
0x140011a35  mov     edx, ecx
0x140011a37  mov     r9, rax
0x140011a3a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x140011a41  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x140011a46  add     rsp, 38h
0x140011a4a  retn
```
