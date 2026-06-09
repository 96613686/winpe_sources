# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x18001e65c`
- end: `0x18001e719`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `14`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001e720`
- `0x18001e8f4`
- `0x18001ea68`
- `0x18001ebdc`
- `0x18001ed50`
- `0x18001eec4`
- `0x18001f038`
- `0x18001f1ac`
- `0x18001f28c`
- `0x18001f36c`
- `0x18001f44c`
- `0x18001f52c`
- `0x18001f60c`
- `0x18001f6ec`

## callees

- `0x18001e65c`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e6a4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e6fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e6a4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e6fa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e686`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e686`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(), void *); // rax

  v1 = dword_18005F794;
  if ( !dword_18005F794 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_18005F7D8 )
      {
        v1 = dword_18005F794;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_18005F7D8 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_18005F7D8,
          `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl'::`5'::_lambda_1_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_18005F7D8 )
      {
        v1 = 1;
        dword_18005F794 = 1;
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
0x18001e65c  push    rbx
0x18001e65e  sub     rsp, 20h
0x18001e662  mov     ebx, cs:dword_18005F794
0x18001e668  nop
0x18001e669  test    ebx, ebx
0x18001e66b  jnz     loc_18001E702
0x18001e671  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001e677  test    eax, eax
0x18001e679  jz      loc_18001E700
0x18001e67f  lea     rcx, SRWLock; SRWLock
0x18001e686  call    cs:__imp_AcquireSRWLockExclusive
0x18001e68c  cmp     cs:qword_18005F7D8, 0
0x18001e694  jz      short loc_18001E6AC
0x18001e696  mov     ebx, cs:dword_18005F794
0x18001e69c  nop
0x18001e69d  lea     rcx, SRWLock; SRWLock
0x18001e6a4  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e6aa  jmp     short loc_18001E702
0x18001e6ac  mov     cs:qword_18005F7D8, 0
0x18001e6b7  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18001e6be  test    rax, rax
0x18001e6c1  jnz     short loc_18001E6CF
0x18001e6c3  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18001e6ca  test    rax, rax
0x18001e6cd  jz      short loc_18001E6E9
0x18001e6cf  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001e6d6  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ@SA@PEAX@Z; `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x18001e6dd  lea     rcx, qword_18005F7D8
0x18001e6e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6e9  lea     rcx, SRWLock; SRWLock
0x18001e6f0  cmp     cs:qword_18005F7D8, 0
0x18001e6f8  jnz     short loc_18001E70A
0x18001e6fa  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e700  xor     ebx, ebx
0x18001e702  mov     eax, ebx
0x18001e704  add     rsp, 20h
0x18001e708  pop     rbx
0x18001e709  retn
0x18001e70a  nop
0x18001e70b  mov     ebx, 1
0x18001e710  mov     cs:dword_18005F794, ebx
0x18001e716  jmp     short loc_18001E6A4
```
