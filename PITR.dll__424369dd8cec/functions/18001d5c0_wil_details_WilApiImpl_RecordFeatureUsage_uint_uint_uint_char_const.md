# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18001d5c0`
- end: `0x18001d7b7`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `503`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x18000ca18`
- `0x18000cb08`
- `0x18001205c`
- `0x180013a74`
- `0x180013cb0`
- `0x18001d5c0`
- `0x18001e26c`
- `0x180050300`
- `0x180053010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001d6e5`
- `msvcrt!memcpy_s` at `0x18001d6e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001d759`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001d759`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d770`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d770`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d690`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d690`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d705`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d705`

## string_xrefs

- `0x18001d752`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
        AcquireSRWLockExclusive(&stru_18007D0B0);
        Source = v4;
        Source_4 = (unsigned __int16)v5;
        v10 = a3;
        if ( wil::details_abi::heap_buffer::ensure(
               (wil::details_abi::heap_buffer *)((char *)&xmmword_18007D168 + 8),
               0xCu) )
        {
          memcpy_s(
            xmmword_18007D178,
            ((_BYTE *)*(&xmmword_18007D178 + 1) - (_BYTE *)xmmword_18007D178)
          & -(__int64)(xmmword_18007D178 < *(&xmmword_18007D178 + 1)),
            &Source,
            0xCu);
          xmmword_18007D178 = (char *)xmmword_18007D178 + 12;
        }
        wil::details::FeatureStateManager::EnsureSRUMTimerUnderLock((struct _TP_TIMER **)&wil::details::g_featureStateManager);
        ReleaseSRWLockExclusive(&stru_18007D0B0);
      }
    }
    else if ( a3 || v5 == 254 )
    {
      wil::details::FeatureStateManager::RecordFeatureUsage(
        &wil::details::g_featureStateManager,
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
         && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_18007D0A0[25], qword_18007D0A0);
    wil::details_abi::FeatureStateData::RecordUsage(qword_18007D0A0);
  }
}

```

## disassembly

```asm
0x18001d5c0  push    rbx
0x18001d5c2  push    rsi
0x18001d5c3  push    rdi
0x18001d5c4  sub     rsp, 40h
0x18001d5c8  mov     rax, cs:__security_cookie
0x18001d5cf  xor     rax, rsp
0x18001d5d2  mov     [rsp+58h+var_28], rax
0x18001d5d7  mov     edi, r8d
0x18001d5da  mov     esi, ecx
0x18001d5dc  mov     ebx, edx
0x18001d5de  btr     ebx, 1Fh
0x18001d5e2  test    ecx, ecx
0x18001d5e4  jnz     short loc_18001D64C
0x18001d5e6  test    r8d, r8d
0x18001d5e9  jnz     short loc_18001D64C
0x18001d5eb  test    ebx, ebx
0x18001d5ed  jnz     short loc_18001D64C
0x18001d5ef  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, bl; bool wil::details::g_processShutdownInProgress
0x18001d5f5  jnz     loc_18001D70C
0x18001d5fb  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001d602  test    rax, rax
0x18001d605  jz      short loc_18001D614
0x18001d607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d60c  test    al, al
0x18001d60e  jnz     loc_18001D70C
0x18001d614  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18001d61b  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18001d620  test    al, al
0x18001d622  jz      loc_18001D70C
0x18001d628  mov     rdx, cs:qword_18007D0A0; SRWLock
0x18001d62f  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18001d636  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18001d63b  mov     rcx, cs:qword_18007D0A0; SRWLock
0x18001d642  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18001d647  jmp     loc_18001D70C
0x18001d64c  bt      ebx, 1Eh
0x18001d650  jnb     loc_18001D711
0x18001d656  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18001d65d  jz      loc_18001D70C
0x18001d663  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001d66a  jnz     loc_18001D70C
0x18001d670  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001d677  test    rax, rax
0x18001d67a  jz      short loc_18001D689
0x18001d67c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d681  test    al, al
0x18001d683  jnz     loc_18001D70C
0x18001d689  lea     rcx, stru_18007D0B0; SRWLock
0x18001d690  call    cs:__imp_AcquireSRWLockExclusive
0x18001d696  xor     eax, eax
0x18001d698  mov     word ptr [rsp+58h+Source+6], ax
0x18001d69d  mov     dword ptr [rsp+58h+Source], esi
0x18001d6a1  mov     word ptr [rsp+58h+Source+4], bx
0x18001d6a6  mov     [rsp+58h+var_30], edi
0x18001d6aa  lea     ebx, [rax+0Ch]
0x18001d6ad  mov     edx, ebx; unsigned __int64
0x18001d6af  lea     rcx, xmmword_18007D168+8; this
0x18001d6b6  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18001d6bb  test    al, al
0x18001d6bd  jz      short loc_18001D6F2
0x18001d6bf  mov     rcx, qword ptr cs:xmmword_18007D178; Destination
0x18001d6c6  mov     rax, qword ptr cs:xmmword_18007D178+8
0x18001d6cd  sub     rax, rcx
0x18001d6d0  cmp     rcx, qword ptr cs:xmmword_18007D178+8
0x18001d6d7  sbb     rdx, rdx
0x18001d6da  and     rdx, rax; DestinationSize
0x18001d6dd  mov     r9d, ebx; SourceSize
0x18001d6e0  lea     r8, [rsp+58h+Source]; Source
0x18001d6e5  call    cs:__imp_memcpy_s
0x18001d6eb  add     qword ptr cs:xmmword_18007D178, rbx
0x18001d6f2  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18001d6f9  call    ?EnsureSRUMTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureSRUMTimerUnderLock(void)
0x18001d6fe  lea     rcx, stru_18007D0B0; SRWLock
0x18001d705  call    cs:__imp_ReleaseSRWLockExclusive
0x18001d70b  nop
0x18001d70c  jmp     loc_18001D7A2
0x18001d711  test    r8d, r8d
0x18001d714  jnz     short loc_18001D78E
0x18001d716  cmp     ebx, 0FEh
0x18001d71c  jz      short loc_18001D78E
0x18001d71e  mov     [rsp+58h+Source], 0
0x18001d727  mov     dword ptr [rsp+58h+Source], esi
0x18001d72b  mov     word ptr [rsp+58h+Source+4], bx
0x18001d730  test    edx, edx
0x18001d732  jns     short loc_18001D73A
0x18001d734  or      word ptr [rsp+58h+Source+6], 1
0x18001d73a  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18001d741  test    rax, rax
0x18001d744  jnz     short loc_18001D782
0x18001d746  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001d74d  test    rax, rax
0x18001d750  jnz     short loc_18001D766
0x18001d752  lea     rcx, aNtdllDll_2; "ntdll.dll"
0x18001d759  call    cs:__imp_GetModuleHandleW
0x18001d75f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001d766  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18001d76d  mov     rcx, rax; hModule
0x18001d770  call    cs:__imp_GetProcAddress
0x18001d776  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18001d77d  test    rax, rax
0x18001d780  jz      short loc_18001D7A2
0x18001d782  lea     rcx, [rsp+58h+Source]
0x18001d787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d78c  jmp     short loc_18001D7A2
0x18001d78e  mov     r9, rdi
0x18001d791  mov     r8d, ebx
0x18001d794  mov     edx, esi
0x18001d796  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18001d79d  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18001d7a2  mov     rcx, [rsp+58h+var_28]
0x18001d7a7  xor     rcx, rsp; StackCookie
0x18001d7aa  call    __security_check_cookie
0x18001d7af  add     rsp, 40h
0x18001d7b3  pop     rdi
0x18001d7b4  pop     rsi
0x18001d7b5  pop     rbx
0x18001d7b6  retn
```
