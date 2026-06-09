# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x140008a70`
- end: `0x140008b2d`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `20`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000e640`
- `0x14000e814`
- `0x14000e988`
- `0x14000eafc`
- `0x14000ec70`
- `0x14000ede4`
- `0x14000ef58`
- `0x14000f0cc`
- `0x14000f1ac`
- `0x14000f28c`
- `0x14000f36c`
- `0x14000f44c`
- `0x14000f52c`
- `0x14000f60c`
- `0x140016e6c`
- `0x140017040`
- `0x140017120`
- `0x14002edfc`
- `0x14003a794`
- `0x1400466fc`

## callees

- `0x140008a70`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008a9a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008a9a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008ab8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008b0e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008ab8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008b0e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, void (__fastcall *)(__int64), void *); // rax

  v1 = dword_1400966A4;
  if ( !dword_1400966A4 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_1400966E8 )
      {
        v1 = dword_1400966A4;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_1400966E8 = 0;
      v2 = (void (__fastcall *)(__int64 *, void (__fastcall *)(__int64), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, void (__fastcall *)(__int64), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_1400966E8,
          `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl'::`5'::_lambda_1_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_1400966E8 )
      {
        v1 = 1;
        dword_1400966A4 = 1;
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
0x140008a70  push    rbx
0x140008a72  sub     rsp, 20h
0x140008a76  mov     ebx, cs:dword_1400966A4
0x140008a7c  nop
0x140008a7d  test    ebx, ebx
0x140008a7f  jnz     loc_140008B16
0x140008a85  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140008a8b  test    eax, eax
0x140008a8d  jz      loc_140008B14
0x140008a93  lea     rcx, SRWLock; SRWLock
0x140008a9a  call    cs:__imp_AcquireSRWLockExclusive
0x140008aa0  cmp     cs:qword_1400966E8, 0
0x140008aa8  jz      short loc_140008AC0
0x140008aaa  mov     ebx, cs:dword_1400966A4
0x140008ab0  nop
0x140008ab1  lea     rcx, SRWLock; SRWLock
0x140008ab8  call    cs:__imp_ReleaseSRWLockExclusive
0x140008abe  jmp     short loc_140008B16
0x140008ac0  mov     cs:qword_1400966E8, 0
0x140008acb  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x140008ad2  test    rax, rax
0x140008ad5  jnz     short loc_140008AE3
0x140008ad7  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x140008ade  test    rax, rax
0x140008ae1  jz      short loc_140008AFD
0x140008ae3  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140008aea  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ@SA@PEAX@Z; `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x140008af1  lea     rcx, qword_1400966E8
0x140008af8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008afd  lea     rcx, SRWLock; SRWLock
0x140008b04  cmp     cs:qword_1400966E8, 0
0x140008b0c  jnz     short loc_140008B1E
0x140008b0e  call    cs:__imp_ReleaseSRWLockExclusive
0x140008b14  xor     ebx, ebx
0x140008b16  mov     eax, ebx
0x140008b18  add     rsp, 20h
0x140008b1c  pop     rbx
0x140008b1d  retn
0x140008b1e  nop
0x140008b1f  mov     ebx, 1
0x140008b24  mov     cs:dword_1400966A4, ebx
0x140008b2a  jmp     short loc_140008AB8
```
