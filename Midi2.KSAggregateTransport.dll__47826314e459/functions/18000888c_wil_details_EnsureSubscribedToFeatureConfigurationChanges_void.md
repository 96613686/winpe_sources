# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x18000888c`
- end: `0x180008949`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `189`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `20`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000e3e4`
- `0x18000e5b8`
- `0x18000e72c`
- `0x18000e8a0`
- `0x18000ea14`
- `0x18000eb88`
- `0x18000ecfc`
- `0x18000ee70`
- `0x18000ef50`
- `0x18000f030`
- `0x18000f110`
- `0x18000f1f0`
- `0x18000f2d0`
- `0x18000f3b0`
- `0x180024e9c`
- `0x180046c78`
- `0x180046e4c`
- `0x180046f2c`
- `0x18004d748`
- `0x180057ee4`

## callees

- `0x18000888c`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800088d4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000892a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800088d4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000892a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800088b6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800088b6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int v1; // ebx
  void (__fastcall *v2)(__int64 *, __int64 (__fastcall *)(), void *); // rax

  v1 = dword_1800968D4;
  if ( !dword_1800968D4 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_180096918 )
      {
        v1 = dword_1800968D4;
LABEL_5:
        ReleaseSRWLockExclusive(&SRWLock);
        return v1;
      }
      qword_180096918 = 0;
      v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v2 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v2(
          &qword_180096918,
          `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl'::`5'::_lambda_1_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
      }
      if ( qword_180096918 )
      {
        v1 = 1;
        dword_1800968D4 = 1;
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
0x18000888c  push    rbx
0x18000888e  sub     rsp, 20h
0x180008892  mov     ebx, cs:dword_1800968D4
0x180008898  nop
0x180008899  test    ebx, ebx
0x18000889b  jnz     loc_180008932
0x1800088a1  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800088a7  test    eax, eax
0x1800088a9  jz      loc_180008930
0x1800088af  lea     rcx, SRWLock; SRWLock
0x1800088b6  call    cs:__imp_AcquireSRWLockExclusive
0x1800088bc  cmp     cs:qword_180096918, 0
0x1800088c4  jz      short loc_1800088DC
0x1800088c6  mov     ebx, cs:dword_1800968D4
0x1800088cc  nop
0x1800088cd  lea     rcx, SRWLock; SRWLock
0x1800088d4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800088da  jmp     short loc_180008932
0x1800088dc  mov     cs:qword_180096918, 0
0x1800088e7  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1800088ee  test    rax, rax
0x1800088f1  jnz     short loc_1800088FF
0x1800088f3  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1800088fa  test    rax, rax
0x1800088fd  jz      short loc_180008919
0x1800088ff  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180008906  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ@SA@PEAX@Z; `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x18000890d  lea     rcx, qword_180096918
0x180008914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008919  lea     rcx, SRWLock; SRWLock
0x180008920  cmp     cs:qword_180096918, 0
0x180008928  jnz     short loc_18000893A
0x18000892a  call    cs:__imp_ReleaseSRWLockExclusive
0x180008930  xor     ebx, ebx
0x180008932  mov     eax, ebx
0x180008934  add     rsp, 20h
0x180008938  pop     rbx
0x180008939  retn
0x18000893a  nop
0x18000893b  mov     ebx, 1
0x180008940  mov     cs:dword_1800968D4, ebx
0x180008946  jmp     short loc_1800088D4
```
