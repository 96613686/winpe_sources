# __scrt_initialize_thread_safe_statics

- ea: `0x180002f70`
- end: `0x180003040`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180002cb0`
- `0x180002e80`
- `0x180002f70`
- `0x180003660`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002f93`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002fa8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002f93`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002fa8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002fc0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002fd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002fc0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002fd3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180002f86`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180002f86`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002fff`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002fff`

## string_xrefs

- `0x180002f8c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180002fa1`: `kernel32.dll`

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
    qword_1800B2758 = (__int64)ProcAddress;
    qword_1800B2760 = (__int64)v2;
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
0x180002f70  mov     [rsp+arg_0], rbx
0x180002f75  push    rdi
0x180002f76  sub     rsp, 20h
0x180002f7a  mov     edx, 0FA0h; dwSpinCount
0x180002f7f  lea     rcx, CriticalSection; lpCriticalSection
0x180002f86  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180002f8c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180002f93  call    cs:__imp_GetModuleHandleW
0x180002f99  mov     rbx, rax
0x180002f9c  test    rax, rax
0x180002f9f  jnz     short loc_180002FB6
0x180002fa1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180002fa8  call    cs:__imp_GetModuleHandleW
0x180002fae  mov     rbx, rax
0x180002fb1  test    rax, rax
0x180002fb4  jz      short loc_180003035
0x180002fb6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x180002fbd  mov     rcx, rbx; hModule
0x180002fc0  call    cs:__imp_GetProcAddress
0x180002fc6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180002fcd  mov     rcx, rbx; hModule
0x180002fd0  mov     rdi, rax
0x180002fd3  call    cs:__imp_GetProcAddress
0x180002fd9  test    rdi, rdi
0x180002fdc  jz      short loc_180002FF3
0x180002fde  test    rax, rax
0x180002fe1  jz      short loc_180002FF3
0x180002fe3  mov     cs:qword_1800B2758, rdi
0x180002fea  mov     cs:qword_1800B2760, rax
0x180002ff1  jmp     short loc_180003011
0x180002ff3  xor     r9d, r9d; lpName
0x180002ff6  xor     r8d, r8d; bInitialState
0x180002ff9  xor     ecx, ecx; lpEventAttributes
0x180002ffb  lea     edx, [r9+1]; bManualReset
0x180002fff  call    cs:__imp_CreateEventW
0x180003005  mov     cs:hHandle, rax
0x18000300c  test    rax, rax
0x18000300f  jz      short loc_180003035
0x180003011  xor     ecx, ecx
0x180003013  call    __scrt_initialize_onexit_tables
0x180003018  test    al, al
0x18000301a  jz      short loc_180003035
0x18000301c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180003023  call    atexit
0x180003028  mov     rbx, [rsp+28h+arg_0]
0x18000302d  xor     eax, eax
0x18000302f  add     rsp, 20h
0x180003033  pop     rdi
0x180003034  retn
0x180003035  mov     ecx, 7
0x18000303a  call    __scrt_fastfail
```
