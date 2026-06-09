# __scrt_initialize_thread_safe_statics

- ea: `0x140003590`
- end: `0x140003660`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140002af4`
- `0x140002cc4`
- `0x140002e74`
- `0x140003590`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400035b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400035c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400035b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400035c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400035e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400035f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400035e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400035f3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1400035a6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1400035a6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000361f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000361f`

## string_xrefs

- `0x1400035ac`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1400035c1`: `kernel32.dll`

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
    qword_1400244B0 = (__int64)ProcAddress;
    qword_1400244B8 = (__int64)v2;
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
0x140003590  mov     [rsp+arg_0], rbx
0x140003595  push    rdi
0x140003596  sub     rsp, 20h
0x14000359a  mov     edx, 0FA0h; dwSpinCount
0x14000359f  lea     rcx, CriticalSection; lpCriticalSection
0x1400035a6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1400035ac  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x1400035b3  call    cs:__imp_GetModuleHandleW
0x1400035b9  mov     rbx, rax
0x1400035bc  test    rax, rax
0x1400035bf  jnz     short loc_1400035D6
0x1400035c1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1400035c8  call    cs:__imp_GetModuleHandleW
0x1400035ce  mov     rbx, rax
0x1400035d1  test    rax, rax
0x1400035d4  jz      short loc_140003655
0x1400035d6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1400035dd  mov     rcx, rbx; hModule
0x1400035e0  call    cs:__imp_GetProcAddress
0x1400035e6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1400035ed  mov     rcx, rbx; hModule
0x1400035f0  mov     rdi, rax
0x1400035f3  call    cs:__imp_GetProcAddress
0x1400035f9  test    rdi, rdi
0x1400035fc  jz      short loc_140003613
0x1400035fe  test    rax, rax
0x140003601  jz      short loc_140003613
0x140003603  mov     cs:qword_1400244B0, rdi
0x14000360a  mov     cs:qword_1400244B8, rax
0x140003611  jmp     short loc_140003631
0x140003613  xor     r9d, r9d; lpName
0x140003616  xor     r8d, r8d; bInitialState
0x140003619  xor     ecx, ecx; lpEventAttributes
0x14000361b  lea     edx, [r9+1]; bManualReset
0x14000361f  call    cs:__imp_CreateEventW
0x140003625  mov     cs:hHandle, rax
0x14000362c  test    rax, rax
0x14000362f  jz      short loc_140003655
0x140003631  xor     ecx, ecx
0x140003633  call    __scrt_initialize_onexit_tables
0x140003638  test    al, al
0x14000363a  jz      short loc_140003655
0x14000363c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x140003643  call    atexit
0x140003648  mov     rbx, [rsp+28h+arg_0]
0x14000364d  xor     eax, eax
0x14000364f  add     rsp, 20h
0x140003653  pop     rdi
0x140003654  retn
0x140003655  mov     ecx, 7
0x14000365a  call    __scrt_fastfail
```
