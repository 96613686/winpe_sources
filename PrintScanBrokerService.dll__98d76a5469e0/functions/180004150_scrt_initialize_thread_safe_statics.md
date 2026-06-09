# __scrt_initialize_thread_safe_statics

- ea: `0x180004150`
- end: `0x180004220`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180003064`
- `0x180003234`
- `0x180003790`
- `0x180004150`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004173`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004188`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004173`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004188`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800041a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800041b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800041a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800041b3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004166`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004166`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800041df`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800041df`

## string_xrefs

- `0x18000416c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180004181`: `kernel32.dll`

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
    qword_180060920 = (__int64)ProcAddress;
    qword_180060928 = (__int64)v2;
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
0x180004150  mov     [rsp+arg_0], rbx
0x180004155  push    rdi
0x180004156  sub     rsp, 20h
0x18000415a  mov     edx, 0FA0h; dwSpinCount
0x18000415f  lea     rcx, CriticalSection; lpCriticalSection
0x180004166  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000416c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180004173  call    cs:__imp_GetModuleHandleW
0x180004179  mov     rbx, rax
0x18000417c  test    rax, rax
0x18000417f  jnz     short loc_180004196
0x180004181  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180004188  call    cs:__imp_GetModuleHandleW
0x18000418e  mov     rbx, rax
0x180004191  test    rax, rax
0x180004194  jz      short loc_180004215
0x180004196  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000419d  mov     rcx, rbx; hModule
0x1800041a0  call    cs:__imp_GetProcAddress
0x1800041a6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800041ad  mov     rcx, rbx; hModule
0x1800041b0  mov     rdi, rax
0x1800041b3  call    cs:__imp_GetProcAddress
0x1800041b9  test    rdi, rdi
0x1800041bc  jz      short loc_1800041D3
0x1800041be  test    rax, rax
0x1800041c1  jz      short loc_1800041D3
0x1800041c3  mov     cs:qword_180060920, rdi
0x1800041ca  mov     cs:qword_180060928, rax
0x1800041d1  jmp     short loc_1800041F1
0x1800041d3  xor     r9d, r9d; lpName
0x1800041d6  xor     r8d, r8d; bInitialState
0x1800041d9  xor     ecx, ecx; lpEventAttributes
0x1800041db  lea     edx, [r9+1]; bManualReset
0x1800041df  call    cs:__imp_CreateEventW
0x1800041e5  mov     cs:hHandle, rax
0x1800041ec  test    rax, rax
0x1800041ef  jz      short loc_180004215
0x1800041f1  xor     ecx, ecx
0x1800041f3  call    __scrt_initialize_onexit_tables
0x1800041f8  test    al, al
0x1800041fa  jz      short loc_180004215
0x1800041fc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180004203  call    atexit
0x180004208  mov     rbx, [rsp+28h+arg_0]
0x18000420d  xor     eax, eax
0x18000420f  add     rsp, 20h
0x180004213  pop     rdi
0x180004214  retn
0x180004215  mov     ecx, 7
0x18000421a  call    __scrt_fastfail
```
