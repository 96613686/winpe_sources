# __scrt_initialize_thread_safe_statics_platform_specific(void)

- ea: `0x40d0c7`
- end: `0x40d148`
- name: `?__scrt_initialize_thread_safe_statics_platform_specific@@YAXXZ`
- size: `129`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x40d0a0`

## callees

- `0x40d0c7`
- `0x40d86c`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x40d0de`
- `KERNEL32!GetModuleHandleW` at `0x40d0ef`
- `KERNEL32!GetModuleHandleW` at `0x40d0de`
- `KERNEL32!GetModuleHandleW` at `0x40d0ef`
- `KERNEL32!GetProcAddress` at `0x40d101`
- `KERNEL32!GetProcAddress` at `0x40d10f`
- `KERNEL32!GetProcAddress` at `0x40d101`
- `KERNEL32!GetProcAddress` at `0x40d10f`
- `KERNEL32!CreateEventW` at `0x40d132`
- `KERNEL32!CreateEventW` at `0x40d132`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x40d0d3`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x40d0d3`

## string_xrefs

- `0x40d0d9`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x40d0ea`: `kernel32.dll`

## pseudocode

```c
void __cdecl __scrt_initialize_thread_safe_statics_platform_specific()
{
  HMODULE ModuleHandleW; // esi
  BOOL (__stdcall *SleepConditionVariableCS)(PCONDITION_VARIABLE, PCRITICAL_SECTION, DWORD); // edi
  void (__stdcall *WakeAllConditionVariable)(PCONDITION_VARIABLE); // eax

  InitializeCriticalSectionAndSpinCount(&stru_43DCA4, 0xFA0u);
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
    dword_43DCBC = (int)SleepConditionVariableCS;
    dword_43DCC0 = (int)WakeAllConditionVariable;
    return;
  }
  hHandle = CreateEventW(0, 1, 0, 0);
  if ( !hHandle )
  {
LABEL_8:
    __scrt_fastfail(7);
    JUMPOUT(0x40D148);
  }
}

```

## disassembly

```asm
0x40d0c7  push    esi
0x40d0c8  push    edi
0x40d0c9  push    0FA0h; dwSpinCount
0x40d0ce  push    offset stru_43DCA4; lpCriticalSection
0x40d0d3  call    ds:InitializeCriticalSectionAndSpinCount
0x40d0d9  push    offset aApiMsWinCoreSy
0x40d0de  call    ds:GetModuleHandleW
0x40d0e4  mov     esi, eax
0x40d0e6  test    esi, esi
0x40d0e8  jnz     short loc_40D0FB
0x40d0ea  push    offset aKernel32Dll_0
0x40d0ef  call    ds:GetModuleHandleW
0x40d0f5  mov     esi, eax
0x40d0f7  test    esi, esi
0x40d0f9  jz      short loc_40D141
0x40d0fb  push    offset aSleepcondition
0x40d100  push    esi; hModule
0x40d101  call    ds:GetProcAddress
0x40d107  push    offset aWakeallconditi
0x40d10c  push    esi; hModule
0x40d10d  mov     edi, eax
0x40d10f  call    ds:GetProcAddress
0x40d115  test    edi, edi
0x40d117  jz      short loc_40D12B
0x40d119  test    eax, eax
0x40d11b  jz      short loc_40D12B
0x40d11d  mov     dword_43DCBC, edi
0x40d123  mov     dword_43DCC0, eax
0x40d128  pop     edi
0x40d129  pop     esi
0x40d12a  retn
0x40d12b  xor     eax, eax
0x40d12d  push    eax; lpName
0x40d12e  push    eax; bInitialState
0x40d12f  push    1; bManualReset
0x40d131  push    eax; lpEventAttributes
0x40d132  call    ds:CreateEventW
0x40d138  mov     hHandle, eax
0x40d13d  test    eax, eax
0x40d13f  jnz     short loc_40D128
0x40d141  push    7
0x40d143  call    ___scrt_fastfail
```
