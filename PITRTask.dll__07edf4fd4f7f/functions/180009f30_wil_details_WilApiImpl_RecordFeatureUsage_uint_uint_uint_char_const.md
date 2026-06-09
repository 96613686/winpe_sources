# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180009f30`
- end: `0x18000a127`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `503`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x180004dc0`
- `0x180004eb0`
- `0x180007010`
- `0x1800077c4`
- `0x180007a00`
- `0x180009f30`
- `0x18000bf6c`
- `0x1800107c0`
- `0x180012010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000a055`
- `msvcrt!memcpy_s` at `0x18000a055`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a0e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a0e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a0c9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a0c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a075`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a075`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a000`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a000`

## string_xrefs

- `0x18000a0c2`: `ntdll.dll`

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
        AcquireSRWLockExclusive(&stru_18001B078);
        Source = v4;
        Source_4 = (unsigned __int16)v5;
        v10 = a3;
        if ( wil::details_abi::heap_buffer::ensure(
               (wil::details_abi::heap_buffer *)((char *)&xmmword_18001B130 + 8),
               0xCu) )
        {
          memcpy_s(
            xmmword_18001B140,
            ((_BYTE *)*(&xmmword_18001B140 + 1) - (_BYTE *)xmmword_18001B140)
          & -(__int64)(xmmword_18001B140 < *(&xmmword_18001B140 + 1)),
            &Source,
            0xCu);
          xmmword_18001B140 = (char *)xmmword_18001B140 + 12;
        }
        wil::details::FeatureStateManager::EnsureSRUMTimerUnderLock((struct _TP_TIMER **)&wil::details::g_featureStateManager);
        ReleaseSRWLockExclusive(&stru_18001B078);
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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_18001B068[25], qword_18001B068);
    wil::details_abi::FeatureStateData::RecordUsage(qword_18001B068);
  }
}

```

## disassembly

```asm
0x180009f30  push    rbx
0x180009f32  push    rsi
0x180009f33  push    rdi
0x180009f34  sub     rsp, 40h
0x180009f38  mov     rax, cs:__security_cookie
0x180009f3f  xor     rax, rsp
0x180009f42  mov     [rsp+58h+var_28], rax
0x180009f47  mov     edi, r8d
0x180009f4a  mov     esi, ecx
0x180009f4c  mov     ebx, edx
0x180009f4e  btr     ebx, 1Fh
0x180009f52  test    ecx, ecx
0x180009f54  jnz     short loc_180009FBC
0x180009f56  test    r8d, r8d
0x180009f59  jnz     short loc_180009FBC
0x180009f5b  test    ebx, ebx
0x180009f5d  jnz     short loc_180009FBC
0x180009f5f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, bl; bool wil::details::g_processShutdownInProgress
0x180009f65  jnz     loc_18000A07C
0x180009f6b  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180009f72  test    rax, rax
0x180009f75  jz      short loc_180009F84
0x180009f77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f7c  test    al, al
0x180009f7e  jnz     loc_18000A07C
0x180009f84  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180009f8b  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180009f90  test    al, al
0x180009f92  jz      loc_18000A07C
0x180009f98  mov     rdx, cs:qword_18001B068; SRWLock
0x180009f9f  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180009fa6  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180009fab  mov     rcx, cs:qword_18001B068; SRWLock
0x180009fb2  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180009fb7  jmp     loc_18000A07C
0x180009fbc  bt      ebx, 1Eh
0x180009fc0  jnb     loc_18000A081
0x180009fc6  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180009fcd  jz      loc_18000A07C
0x180009fd3  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180009fda  jnz     loc_18000A07C
0x180009fe0  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180009fe7  test    rax, rax
0x180009fea  jz      short loc_180009FF9
0x180009fec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ff1  test    al, al
0x180009ff3  jnz     loc_18000A07C
0x180009ff9  lea     rcx, stru_18001B078; SRWLock
0x18000a000  call    cs:__imp_AcquireSRWLockExclusive
0x18000a006  xor     eax, eax
0x18000a008  mov     word ptr [rsp+58h+Source+6], ax
0x18000a00d  mov     dword ptr [rsp+58h+Source], esi
0x18000a011  mov     word ptr [rsp+58h+Source+4], bx
0x18000a016  mov     [rsp+58h+var_30], edi
0x18000a01a  lea     ebx, [rax+0Ch]
0x18000a01d  mov     edx, ebx; unsigned __int64
0x18000a01f  lea     rcx, xmmword_18001B130+8; this
0x18000a026  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000a02b  test    al, al
0x18000a02d  jz      short loc_18000A062
0x18000a02f  mov     rcx, qword ptr cs:xmmword_18001B140; Destination
0x18000a036  mov     rax, qword ptr cs:xmmword_18001B140+8
0x18000a03d  sub     rax, rcx
0x18000a040  cmp     rcx, qword ptr cs:xmmword_18001B140+8
0x18000a047  sbb     rdx, rdx
0x18000a04a  and     rdx, rax; DestinationSize
0x18000a04d  mov     r9d, ebx; SourceSize
0x18000a050  lea     r8, [rsp+58h+Source]; Source
0x18000a055  call    cs:__imp_memcpy_s
0x18000a05b  add     qword ptr cs:xmmword_18001B140, rbx
0x18000a062  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000a069  call    ?EnsureSRUMTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureSRUMTimerUnderLock(void)
0x18000a06e  lea     rcx, stru_18001B078; SRWLock
0x18000a075  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a07b  nop
0x18000a07c  jmp     loc_18000A112
0x18000a081  test    r8d, r8d
0x18000a084  jnz     short loc_18000A0FE
0x18000a086  cmp     ebx, 0FEh
0x18000a08c  jz      short loc_18000A0FE
0x18000a08e  mov     [rsp+58h+Source], 0
0x18000a097  mov     dword ptr [rsp+58h+Source], esi
0x18000a09b  mov     word ptr [rsp+58h+Source+4], bx
0x18000a0a0  test    edx, edx
0x18000a0a2  jns     short loc_18000A0AA
0x18000a0a4  or      word ptr [rsp+58h+Source+6], 1
0x18000a0aa  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000a0b1  test    rax, rax
0x18000a0b4  jnz     short loc_18000A0F2
0x18000a0b6  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a0bd  test    rax, rax
0x18000a0c0  jnz     short loc_18000A0D6
0x18000a0c2  lea     rcx, ModuleName; "ntdll.dll"
0x18000a0c9  call    cs:__imp_GetModuleHandleW
0x18000a0cf  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a0d6  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000a0dd  mov     rcx, rax; hModule
0x18000a0e0  call    cs:__imp_GetProcAddress
0x18000a0e6  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000a0ed  test    rax, rax
0x18000a0f0  jz      short loc_18000A112
0x18000a0f2  lea     rcx, [rsp+58h+Source]
0x18000a0f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0fc  jmp     short loc_18000A112
0x18000a0fe  mov     r9, rdi
0x18000a101  mov     r8d, ebx
0x18000a104  mov     edx, esi
0x18000a106  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000a10d  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000a112  mov     rcx, [rsp+58h+var_28]
0x18000a117  xor     rcx, rsp; StackCookie
0x18000a11a  call    __security_check_cookie
0x18000a11f  add     rsp, 40h
0x18000a123  pop     rdi
0x18000a124  pop     rsi
0x18000a125  pop     rbx
0x18000a126  retn
```
