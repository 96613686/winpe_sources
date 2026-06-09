# __scrt_initialize_thread_safe_statics

- ea: `0x180037d20`
- end: `0x180037df0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180037a30`
- `0x180037c00`
- `0x180037d20`
- `0x180038498`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180037d43`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180037d58`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180037d43`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180037d58`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180037d70`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180037d83`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180037d70`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180037d83`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180037d36`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180037d36`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180037daf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180037daf`

## string_xrefs

- `0x180037d3c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180037d51`: `kernel32.dll`

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
    qword_1800AD9D0 = (__int64)ProcAddress;
    qword_1800AD9D8 = (__int64)v2;
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
0x180037d20  mov     [rsp+arg_0], rbx
0x180037d25  push    rdi
0x180037d26  sub     rsp, 20h
0x180037d2a  mov     edx, 0FA0h; dwSpinCount
0x180037d2f  lea     rcx, CriticalSection; lpCriticalSection
0x180037d36  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180037d3c  lea     rcx, aApiMsWinCoreSy_3; "api-ms-win-core-synch-l1-2-0.dll"
0x180037d43  call    cs:__imp_GetModuleHandleW
0x180037d49  mov     rbx, rax
0x180037d4c  test    rax, rax
0x180037d4f  jnz     short loc_180037D66
0x180037d51  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180037d58  call    cs:__imp_GetModuleHandleW
0x180037d5e  mov     rbx, rax
0x180037d61  test    rax, rax
0x180037d64  jz      short loc_180037DE5
0x180037d66  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x180037d6d  mov     rcx, rbx; hModule
0x180037d70  call    cs:__imp_GetProcAddress
0x180037d76  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180037d7d  mov     rcx, rbx; hModule
0x180037d80  mov     rdi, rax
0x180037d83  call    cs:__imp_GetProcAddress
0x180037d89  test    rdi, rdi
0x180037d8c  jz      short loc_180037DA3
0x180037d8e  test    rax, rax
0x180037d91  jz      short loc_180037DA3
0x180037d93  mov     cs:qword_1800AD9D0, rdi
0x180037d9a  mov     cs:qword_1800AD9D8, rax
0x180037da1  jmp     short loc_180037DC1
0x180037da3  xor     r9d, r9d; lpName
0x180037da6  xor     r8d, r8d; bInitialState
0x180037da9  xor     ecx, ecx; lpEventAttributes
0x180037dab  lea     edx, [r9+1]; bManualReset
0x180037daf  call    cs:__imp_CreateEventW
0x180037db5  mov     cs:hHandle, rax
0x180037dbc  test    rax, rax
0x180037dbf  jz      short loc_180037DE5
0x180037dc1  xor     ecx, ecx
0x180037dc3  call    __scrt_initialize_onexit_tables
0x180037dc8  test    al, al
0x180037dca  jz      short loc_180037DE5
0x180037dcc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180037dd3  call    atexit
0x180037dd8  mov     rbx, [rsp+28h+arg_0]
0x180037ddd  xor     eax, eax
0x180037ddf  add     rsp, 20h
0x180037de3  pop     rdi
0x180037de4  retn
0x180037de5  mov     ecx, 7
0x180037dea  call    __scrt_fastfail
```
