# __scrt_initialize_thread_safe_statics

- ea: `0x180004d00`
- end: `0x180004dd0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180003ca0`
- `0x180003e70`
- `0x180003ea0`
- `0x180004d00`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004d23`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004d38`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004d23`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004d38`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004d50`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004d63`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004d50`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004d63`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004d16`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004d16`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004d8f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004d8f`

## string_xrefs

- `0x180004d1c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180004d31`: `kernel32.dll`

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
    qword_180046940 = (__int64)ProcAddress;
    qword_180046948 = (__int64)v2;
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
0x180004d00  mov     [rsp+arg_0], rbx
0x180004d05  push    rdi
0x180004d06  sub     rsp, 20h
0x180004d0a  mov     edx, 0FA0h; dwSpinCount
0x180004d0f  lea     rcx, CriticalSection; lpCriticalSection
0x180004d16  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180004d1c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180004d23  call    cs:__imp_GetModuleHandleW
0x180004d29  mov     rbx, rax
0x180004d2c  test    rax, rax
0x180004d2f  jnz     short loc_180004D46
0x180004d31  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180004d38  call    cs:__imp_GetModuleHandleW
0x180004d3e  mov     rbx, rax
0x180004d41  test    rax, rax
0x180004d44  jz      short loc_180004DC5
0x180004d46  lea     rdx, ProcName; "SleepConditionVariableCS"
0x180004d4d  mov     rcx, rbx; hModule
0x180004d50  call    cs:__imp_GetProcAddress
0x180004d56  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180004d5d  mov     rcx, rbx; hModule
0x180004d60  mov     rdi, rax
0x180004d63  call    cs:__imp_GetProcAddress
0x180004d69  test    rdi, rdi
0x180004d6c  jz      short loc_180004D83
0x180004d6e  test    rax, rax
0x180004d71  jz      short loc_180004D83
0x180004d73  mov     cs:qword_180046940, rdi
0x180004d7a  mov     cs:qword_180046948, rax
0x180004d81  jmp     short loc_180004DA1
0x180004d83  xor     r9d, r9d; lpName
0x180004d86  xor     r8d, r8d; bInitialState
0x180004d89  xor     ecx, ecx; lpEventAttributes
0x180004d8b  lea     edx, [r9+1]; bManualReset
0x180004d8f  call    cs:__imp_CreateEventW
0x180004d95  mov     cs:hHandle, rax
0x180004d9c  test    rax, rax
0x180004d9f  jz      short loc_180004DC5
0x180004da1  xor     ecx, ecx
0x180004da3  call    __scrt_initialize_onexit_tables
0x180004da8  test    al, al
0x180004daa  jz      short loc_180004DC5
0x180004dac  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180004db3  call    atexit
0x180004db8  mov     rbx, [rsp+28h+arg_0]
0x180004dbd  xor     eax, eax
0x180004dbf  add     rsp, 20h
0x180004dc3  pop     rdi
0x180004dc4  retn
0x180004dc5  mov     ecx, 7
0x180004dca  call    __scrt_fastfail
```
