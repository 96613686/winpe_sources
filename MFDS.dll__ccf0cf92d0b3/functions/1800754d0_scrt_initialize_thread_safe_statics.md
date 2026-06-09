# __scrt_initialize_thread_safe_statics

- ea: `0x1800754d0`
- end: `0x1800755a0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18007436c`
- `0x18007453c`
- `0x180074674`
- `0x1800754d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007555f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007555f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800754e6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800754e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800754f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180075508`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800754f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180075508`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180075520`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180075533`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180075520`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180075533`

## string_xrefs

- `0x1800754ec`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180075501`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1800EAC60, 0xFA0u);
  ModuleHandleW = GetModuleHandleW(L"api-ms-win-core-synch-l1-2-0.dll");
  if ( !ModuleHandleW )
  {
    ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
    if ( !ModuleHandleW )
      goto LABEL_9;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "SleepConditionVariableCS");
  v2 = GetProcAddress(ModuleHandleW, "WakeAllConditionVariable");
  if ( ProcAddress && v2 )
  {
    qword_1800EAC88 = (__int64)ProcAddress;
    qword_1800EAC90 = (__int64)v2;
  }
  else
  {
    hHandle = CreateEventW(0, 1, 0, 0);
    if ( !hHandle )
      goto LABEL_9;
  }
  if ( !(unsigned __int8)_scrt_initialize_onexit_tables(0) )
LABEL_9:
    _scrt_fastfail(7);
  atexit(_scrt_uninitialize_thread_safe_statics);
  return 0;
}

```

## disassembly

```asm
0x1800754d0  mov     [rsp+arg_0], rbx
0x1800754d5  push    rdi
0x1800754d6  sub     rsp, 20h
0x1800754da  mov     edx, 0FA0h; dwSpinCount
0x1800754df  lea     rcx, stru_1800EAC60; lpCriticalSection
0x1800754e6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800754ec  lea     rcx, aApiMsWinCoreSy_3; "api-ms-win-core-synch-l1-2-0.dll"
0x1800754f3  call    cs:__imp_GetModuleHandleW
0x1800754f9  mov     rbx, rax
0x1800754fc  test    rax, rax
0x1800754ff  jnz     short loc_180075516
0x180075501  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180075508  call    cs:__imp_GetModuleHandleW
0x18007550e  mov     rbx, rax
0x180075511  test    rax, rax
0x180075514  jz      short loc_180075595
0x180075516  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18007551d  mov     rcx, rbx; hModule
0x180075520  call    cs:__imp_GetProcAddress
0x180075526  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18007552d  mov     rcx, rbx; hModule
0x180075530  mov     rdi, rax
0x180075533  call    cs:__imp_GetProcAddress
0x180075539  test    rdi, rdi
0x18007553c  jz      short loc_180075553
0x18007553e  test    rax, rax
0x180075541  jz      short loc_180075553
0x180075543  mov     cs:qword_1800EAC88, rdi
0x18007554a  mov     cs:qword_1800EAC90, rax
0x180075551  jmp     short loc_180075571
0x180075553  xor     r9d, r9d; lpName
0x180075556  xor     r8d, r8d; bInitialState
0x180075559  xor     ecx, ecx; lpEventAttributes
0x18007555b  lea     edx, [r9+1]; bManualReset
0x18007555f  call    cs:__imp_CreateEventW
0x180075565  mov     cs:hHandle, rax
0x18007556c  test    rax, rax
0x18007556f  jz      short loc_180075595
0x180075571  xor     ecx, ecx
0x180075573  call    __scrt_initialize_onexit_tables
0x180075578  test    al, al
0x18007557a  jz      short loc_180075595
0x18007557c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180075583  call    atexit
0x180075588  mov     rbx, [rsp+28h+arg_0]
0x18007558d  xor     eax, eax
0x18007558f  add     rsp, 20h
0x180075593  pop     rdi
0x180075594  retn
0x180075595  mov     ecx, 7
0x18007559a  call    __scrt_fastfail
```
