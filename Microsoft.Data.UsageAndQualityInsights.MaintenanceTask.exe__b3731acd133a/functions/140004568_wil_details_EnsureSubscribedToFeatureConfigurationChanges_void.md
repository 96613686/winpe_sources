# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x140004568`
- end: `0x140004625`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140005674`
- `0x14000a514`
- `0x14000a694`
- `0x14000a864`

## callees

- `0x140004568`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140004592`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140004592`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400045b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004606`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400045b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004606`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, void (__fastcall *)(__int64), void *); // rax

  v1 = dword_14001169C;
  if ( !dword_14001169C )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_1400116E0 )
      {
        v1 = dword_14001169C;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_1400116E0 = 0;
      v2 = (void (__fastcall *)(__int64 *, void (__fastcall *)(__int64), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, void (__fastcall *)(__int64), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_1400116E0,
          `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl'::`5'::_lambda_1_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_1400116E0 )
      {
        v1 = 1;
        dword_14001169C = 1;
        goto LABEL_5;
      }
      ReleaseSRWLockExclusive(&SRWLock);
    }
    return 0;
  }
  return v1;
}

```

## disassembly

```asm
0x140004568  push    rbx
0x14000456a  sub     rsp, 20h
0x14000456e  mov     ebx, cs:dword_14001169C
0x140004574  nop
0x140004575  test    ebx, ebx
0x140004577  jnz     loc_14000460E
0x14000457d  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140004583  test    eax, eax
0x140004585  jz      loc_14000460C
0x14000458b  lea     rcx, SRWLock; SRWLock
0x140004592  call    cs:__imp_AcquireSRWLockExclusive
0x140004598  cmp     cs:qword_1400116E0, 0
0x1400045a0  jz      short loc_1400045B8
0x1400045a2  mov     ebx, cs:dword_14001169C
0x1400045a8  nop
0x1400045a9  lea     rcx, SRWLock; SRWLock
0x1400045b0  call    cs:__imp_ReleaseSRWLockExclusive
0x1400045b6  jmp     short loc_14000460E
0x1400045b8  mov     cs:qword_1400116E0, 0
0x1400045c3  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1400045ca  test    rax, rax
0x1400045cd  jnz     short loc_1400045DB
0x1400045cf  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1400045d6  test    rax, rax
0x1400045d9  jz      short loc_1400045F5
0x1400045db  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1400045e2  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ@SA@PEAX@Z; `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x1400045e9  lea     rcx, qword_1400116E0
0x1400045f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400045f5  lea     rcx, SRWLock; SRWLock
0x1400045fc  cmp     cs:qword_1400116E0, 0
0x140004604  jnz     short loc_140004616
0x140004606  call    cs:__imp_ReleaseSRWLockExclusive
0x14000460c  xor     ebx, ebx
0x14000460e  mov     eax, ebx
0x140004610  add     rsp, 20h
0x140004614  pop     rbx
0x140004615  retn
0x140004616  nop
0x140004617  mov     ebx, 1
0x14000461c  mov     cs:dword_14001169C, ebx
0x140004622  jmp     short loc_1400045B0
```
