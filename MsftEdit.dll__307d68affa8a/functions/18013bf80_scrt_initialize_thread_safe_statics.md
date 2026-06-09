# __scrt_initialize_thread_safe_statics

- ea: `0x18013bf80`
- end: `0x18013c050`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18013bcb0`
- `0x18013be80`
- `0x18013bf80`
- `0x18013c674`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18013bfd0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18013bfe3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18013bfd0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18013bfe3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18013bfa3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18013bfb8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18013bfa3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18013bfb8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18013c00f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18013c00f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18013bf96`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18013bf96`

## string_xrefs

- `0x18013bf9c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18013bfb1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&CriticalSection, 0xFA0u);
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
    qword_1802DCE88 = (__int64)ProcAddress;
    qword_1802DCE90 = (__int64)v2;
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
0x18013bf80  mov     [rsp+arg_0], rbx
0x18013bf85  push    rdi
0x18013bf86  sub     rsp, 20h
0x18013bf8a  mov     edx, 0FA0h; dwSpinCount
0x18013bf8f  lea     rcx, CriticalSection; lpCriticalSection
0x18013bf96  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18013bf9c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x18013bfa3  call    cs:__imp_GetModuleHandleW
0x18013bfa9  mov     rbx, rax
0x18013bfac  test    rax, rax
0x18013bfaf  jnz     short loc_18013BFC6
0x18013bfb1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x18013bfb8  call    cs:__imp_GetModuleHandleW
0x18013bfbe  mov     rbx, rax
0x18013bfc1  test    rax, rax
0x18013bfc4  jz      short loc_18013C045
0x18013bfc6  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18013bfcd  mov     rcx, rbx; hModule
0x18013bfd0  call    cs:__imp_GetProcAddress
0x18013bfd6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18013bfdd  mov     rcx, rbx; hModule
0x18013bfe0  mov     rdi, rax
0x18013bfe3  call    cs:__imp_GetProcAddress
0x18013bfe9  test    rdi, rdi
0x18013bfec  jz      short loc_18013C003
0x18013bfee  test    rax, rax
0x18013bff1  jz      short loc_18013C003
0x18013bff3  mov     cs:qword_1802DCE88, rdi
0x18013bffa  mov     cs:qword_1802DCE90, rax
0x18013c001  jmp     short loc_18013C021
0x18013c003  xor     r9d, r9d; lpName
0x18013c006  xor     r8d, r8d; bInitialState
0x18013c009  xor     ecx, ecx; lpEventAttributes
0x18013c00b  lea     edx, [r9+1]; bManualReset
0x18013c00f  call    cs:__imp_CreateEventW
0x18013c015  mov     cs:hHandle, rax
0x18013c01c  test    rax, rax
0x18013c01f  jz      short loc_18013C045
0x18013c021  xor     ecx, ecx
0x18013c023  call    __scrt_initialize_onexit_tables
0x18013c028  test    al, al
0x18013c02a  jz      short loc_18013C045
0x18013c02c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x18013c033  call    atexit
0x18013c038  mov     rbx, [rsp+28h+arg_0]
0x18013c03d  xor     eax, eax
0x18013c03f  add     rsp, 20h
0x18013c043  pop     rdi
0x18013c044  retn
0x18013c045  mov     ecx, 7
0x18013c04a  call    __scrt_fastfail
```
