# __scrt_initialize_thread_safe_statics_platform_specific(void)

- ea: `0x419527`
- end: `0x4195a8`
- name: `?__scrt_initialize_thread_safe_statics_platform_specific@@YAXXZ`
- size: `129`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x419500`

## callees

- `0x40877f`
- `0x419527`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x419561`
- `KERNEL32!GetProcAddress` at `0x41956f`
- `KERNEL32!GetProcAddress` at `0x419561`
- `KERNEL32!GetProcAddress` at `0x41956f`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x419533`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x419533`
- `KERNEL32!GetModuleHandleW` at `0x41953e`
- `KERNEL32!GetModuleHandleW` at `0x41954f`
- `KERNEL32!GetModuleHandleW` at `0x41953e`
- `KERNEL32!GetModuleHandleW` at `0x41954f`
- `KERNEL32!CreateEventW` at `0x419592`
- `KERNEL32!CreateEventW` at `0x419592`

## string_xrefs

- `0x419539`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x41954a`: `kernel32.dll`

## pseudocode

```c
void __cdecl __scrt_initialize_thread_safe_statics_platform_specific()
{
  HMODULE ModuleHandleW; // esi
  BOOL (__stdcall *SleepConditionVariableCS)(PCONDITION_VARIABLE, PCRITICAL_SECTION, DWORD); // edi
  void (__stdcall *WakeAllConditionVariable)(PCONDITION_VARIABLE); // eax

  InitializeCriticalSectionAndSpinCount(&CriticalSection, 0xFA0u);
  ModuleHandleW = GetModuleHandleW(L"api-ms-win-core-synch-l1-2-0.dll");
  if ( !ModuleHandleW )
  {
    ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
    if ( !ModuleHandleW )
      goto LABEL_8;
  }
  SleepConditionVariableCS = (BOOL (__stdcall *)(PCONDITION_VARIABLE, PCRITICAL_SECTION, DWORD))GetProcAddress(
                                                                                                  ModuleHandleW,
                                                                                                  "SleepConditionVariableCS");
  WakeAllConditionVariable = (void (__stdcall *)(PCONDITION_VARIABLE))GetProcAddress(
                                                                        ModuleHandleW,
                                                                        "WakeAllConditionVariable");
  if ( SleepConditionVariableCS && WakeAllConditionVariable )
  {
    dword_4273A0 = (int)SleepConditionVariableCS;
    dword_4273A4 = (int)WakeAllConditionVariable;
    return;
  }
  hHandle = CreateEventW(0, 1, 0, 0);
  if ( !hHandle )
  {
LABEL_8:
    __scrt_fastfail(7);
    JUMPOUT(0x4195A8);
  }
}

```

## disassembly

```asm
0x419527  push    esi
0x419528  push    edi
0x419529  push    0FA0h; dwSpinCount
0x41952e  push    offset CriticalSection; lpCriticalSection
0x419533  call    ds:InitializeCriticalSectionAndSpinCount
0x419539  push    offset aApiMsWinCoreSy
0x41953e  call    ds:GetModuleHandleW
0x419544  mov     esi, eax
0x419546  test    esi, esi
0x419548  jnz     short loc_41955B
0x41954a  push    offset ModuleName
0x41954f  call    ds:GetModuleHandleW
0x419555  mov     esi, eax
0x419557  test    esi, esi
0x419559  jz      short loc_4195A1
0x41955b  push    offset aSleepcondition
0x419560  push    esi; hModule
0x419561  call    ds:GetProcAddress
0x419567  push    offset aWakeallconditi
0x41956c  push    esi; hModule
0x41956d  mov     edi, eax
0x41956f  call    ds:GetProcAddress
0x419575  test    edi, edi
0x419577  jz      short loc_41958B
0x419579  test    eax, eax
0x41957b  jz      short loc_41958B
0x41957d  mov     dword_4273A0, edi
0x419583  mov     dword_4273A4, eax
0x419588  pop     edi
0x419589  pop     esi
0x41958a  retn
0x41958b  xor     eax, eax
0x41958d  push    eax; lpName
0x41958e  push    eax; bInitialState
0x41958f  push    1; bManualReset
0x419591  push    eax; lpEventAttributes
0x419592  call    ds:CreateEventW
0x419598  mov     hHandle, eax
0x41959d  test    eax, eax
0x41959f  jnz     short loc_419588
0x4195a1  push    7
0x4195a3  call    ___scrt_fastfail
```
