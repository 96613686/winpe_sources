# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180009c50`
- end: `0x180009e47`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `503`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x180004840`
- `0x180004930`
- `0x180006f20`
- `0x1800076d4`
- `0x180007910`
- `0x180009c50`
- `0x18000af9c`
- `0x18000c610`
- `0x18000d010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180009d75`
- `msvcrt!memcpy_s` at `0x180009d75`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009e00`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009e00`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009de9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009de9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009d20`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009d20`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009d95`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009d95`

## string_xrefs

- `0x180009de2`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details::WilApiImpl_RecordFeatureUsage(wil::details *this, int a2, unsigned int a3)
{
  int v4; // esi
  unsigned int v5; // ebx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int Source; // [rsp+20h] [rbp-38h] BYREF
  int Source_4; // [rsp+24h] [rbp-34h]
  unsigned int v10; // [rsp+28h] [rbp-30h]

  v4 = (int)this;
  v5 = a2 & 0x7FFFFFFF;
  if ( (_DWORD)this || a3 || v5 )
  {
    if ( (a2 & 0x40000000) != 0 )
    {
      if ( wil::details::g_featureStateManager
        && !wil::details::g_processShutdownInProgress
        && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
      {
        AcquireSRWLockExclusive(&stru_180015078);
        Source = v4;
        Source_4 = (unsigned __int16)v5;
        v10 = a3;
        if ( wil::details_abi::heap_buffer::ensure(
               (wil::details_abi::heap_buffer *)((char *)&xmmword_180015130 + 8),
               0xCu) )
        {
          memcpy_s(
            xmmword_180015140,
            ((_BYTE *)*(&xmmword_180015140 + 1) - (_BYTE *)xmmword_180015140)
          & -(__int64)(xmmword_180015140 < *(&xmmword_180015140 + 1)),
            &Source,
            0xCu);
          xmmword_180015140 = (char *)xmmword_180015140 + 12;
        }
        wil::details::FeatureStateManager::EnsureSRUMTimerUnderLock((struct _TP_TIMER **)&wil::details::g_featureStateManager);
        ReleaseSRWLockExclusive(&stru_180015078);
      }
    }
    else if ( a3 || v5 == 254 )
    {
      wil::details::FeatureStateManager::RecordFeatureUsage(
        (__int64)&wil::details::g_featureStateManager,
        (unsigned int)this,
        v5,
        a3);
    }
    else
    {
      Source = (int)this;
      Source_4 = (unsigned __int16)a2;
      if ( a2 < 0 )
        HIWORD(Source_4) |= 1u;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlNotifyFeatureUsage;
      if ( g_wil_details_pfnRtlNotifyFeatureUsage )
        goto LABEL_26;
      ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
      if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
      {
        ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
        `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
      }
      ProcAddress = GetProcAddress(ModuleHandleW, "RtlNotifyFeatureUsage");
      g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)ProcAddress;
      if ( ProcAddress )
LABEL_26:
        ((void (__fastcall *)(int *))ProcAddress)(&Source);
    }
  }
  else if ( !wil::details::g_processShutdownInProgress
         && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress())
         && wil::details::FeatureStateManager::EnsureStateData((RTL_SRWLOCK *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180015068[25], qword_180015068);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180015068);
  }
}

```

## disassembly

```asm
0x180009c50  push    rbx
0x180009c52  push    rsi
0x180009c53  push    rdi
0x180009c54  sub     rsp, 40h
0x180009c58  mov     rax, cs:__security_cookie
0x180009c5f  xor     rax, rsp
0x180009c62  mov     [rsp+58h+var_28], rax
0x180009c67  mov     edi, r8d
0x180009c6a  mov     esi, ecx
0x180009c6c  mov     ebx, edx
0x180009c6e  btr     ebx, 1Fh
0x180009c72  test    ecx, ecx
0x180009c74  jnz     short loc_180009CDC
0x180009c76  test    r8d, r8d
0x180009c79  jnz     short loc_180009CDC
0x180009c7b  test    ebx, ebx
0x180009c7d  jnz     short loc_180009CDC
0x180009c7f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, bl; bool wil::details::g_processShutdownInProgress
0x180009c85  jnz     loc_180009D9C
0x180009c8b  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180009c92  test    rax, rax
0x180009c95  jz      short loc_180009CA4
0x180009c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c9c  test    al, al
0x180009c9e  jnz     loc_180009D9C
0x180009ca4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180009cab  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180009cb0  test    al, al
0x180009cb2  jz      loc_180009D9C
0x180009cb8  mov     rdx, cs:qword_180015068; SRWLock
0x180009cbf  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180009cc6  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180009ccb  mov     rcx, cs:qword_180015068; SRWLock
0x180009cd2  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180009cd7  jmp     loc_180009D9C
0x180009cdc  bt      ebx, 1Eh
0x180009ce0  jnb     loc_180009DA1
0x180009ce6  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180009ced  jz      loc_180009D9C
0x180009cf3  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180009cfa  jnz     loc_180009D9C
0x180009d00  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180009d07  test    rax, rax
0x180009d0a  jz      short loc_180009D19
0x180009d0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d11  test    al, al
0x180009d13  jnz     loc_180009D9C
0x180009d19  lea     rcx, stru_180015078; SRWLock
0x180009d20  call    cs:__imp_AcquireSRWLockExclusive
0x180009d26  xor     eax, eax
0x180009d28  mov     word ptr [rsp+58h+Source+6], ax
0x180009d2d  mov     dword ptr [rsp+58h+Source], esi
0x180009d31  mov     word ptr [rsp+58h+Source+4], bx
0x180009d36  mov     [rsp+58h+var_30], edi
0x180009d3a  lea     ebx, [rax+0Ch]
0x180009d3d  mov     edx, ebx; unsigned __int64
0x180009d3f  lea     rcx, xmmword_180015130+8; this
0x180009d46  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180009d4b  test    al, al
0x180009d4d  jz      short loc_180009D82
0x180009d4f  mov     rcx, qword ptr cs:xmmword_180015140; Destination
0x180009d56  mov     rax, qword ptr cs:xmmword_180015140+8
0x180009d5d  sub     rax, rcx
0x180009d60  cmp     rcx, qword ptr cs:xmmword_180015140+8
0x180009d67  sbb     rdx, rdx
0x180009d6a  and     rdx, rax; DestinationSize
0x180009d6d  mov     r9d, ebx; SourceSize
0x180009d70  lea     r8, [rsp+58h+Source]; Source
0x180009d75  call    cs:__imp_memcpy_s
0x180009d7b  add     qword ptr cs:xmmword_180015140, rbx
0x180009d82  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180009d89  call    ?EnsureSRUMTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureSRUMTimerUnderLock(void)
0x180009d8e  lea     rcx, stru_180015078; SRWLock
0x180009d95  call    cs:__imp_ReleaseSRWLockExclusive
0x180009d9b  nop
0x180009d9c  jmp     loc_180009E32
0x180009da1  test    r8d, r8d
0x180009da4  jnz     short loc_180009E1E
0x180009da6  cmp     ebx, 0FEh
0x180009dac  jz      short loc_180009E1E
0x180009dae  mov     [rsp+58h+Source], 0
0x180009db7  mov     dword ptr [rsp+58h+Source], esi
0x180009dbb  mov     word ptr [rsp+58h+Source+4], bx
0x180009dc0  test    edx, edx
0x180009dc2  jns     short loc_180009DCA
0x180009dc4  or      word ptr [rsp+58h+Source+6], 1
0x180009dca  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180009dd1  test    rax, rax
0x180009dd4  jnz     short loc_180009E12
0x180009dd6  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009ddd  test    rax, rax
0x180009de0  jnz     short loc_180009DF6
0x180009de2  lea     rcx, ModuleName; "ntdll.dll"
0x180009de9  call    cs:__imp_GetModuleHandleW
0x180009def  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009df6  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180009dfd  mov     rcx, rax; hModule
0x180009e00  call    cs:__imp_GetProcAddress
0x180009e06  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180009e0d  test    rax, rax
0x180009e10  jz      short loc_180009E32
0x180009e12  lea     rcx, [rsp+58h+Source]
0x180009e17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e1c  jmp     short loc_180009E32
0x180009e1e  mov     r9, rdi
0x180009e21  mov     r8d, ebx
0x180009e24  mov     edx, esi
0x180009e26  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180009e2d  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180009e32  mov     rcx, [rsp+58h+var_28]
0x180009e37  xor     rcx, rsp; StackCookie
0x180009e3a  call    __security_check_cookie
0x180009e3f  add     rsp, 40h
0x180009e43  pop     rdi
0x180009e44  pop     rsi
0x180009e45  pop     rbx
0x180009e46  retn
```
