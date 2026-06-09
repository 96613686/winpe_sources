# __scrt_initialize_thread_safe_statics

- ea: `0x180004330`
- end: `0x180004400`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000370c`
- `0x1800038dc`
- `0x180003ad0`
- `0x180004330`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004353`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004368`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004353`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004368`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004380`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004393`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004380`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004393`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004346`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004346`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800043bf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800043bf`

## string_xrefs

- `0x18000434c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180004361`: `kernel32.dll`

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
    qword_180069F70 = (__int64)ProcAddress;
    qword_180069F78 = (__int64)v2;
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
0x180004330  mov     [rsp+arg_0], rbx
0x180004335  push    rdi
0x180004336  sub     rsp, 20h
0x18000433a  mov     edx, 0FA0h; dwSpinCount
0x18000433f  lea     rcx, CriticalSection; lpCriticalSection
0x180004346  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000434c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180004353  call    cs:__imp_GetModuleHandleW
0x180004359  mov     rbx, rax
0x18000435c  test    rax, rax
0x18000435f  jnz     short loc_180004376
0x180004361  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180004368  call    cs:__imp_GetModuleHandleW
0x18000436e  mov     rbx, rax
0x180004371  test    rax, rax
0x180004374  jz      short loc_1800043F5
0x180004376  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000437d  mov     rcx, rbx; hModule
0x180004380  call    cs:__imp_GetProcAddress
0x180004386  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000438d  mov     rcx, rbx; hModule
0x180004390  mov     rdi, rax
0x180004393  call    cs:__imp_GetProcAddress
0x180004399  test    rdi, rdi
0x18000439c  jz      short loc_1800043B3
0x18000439e  test    rax, rax
0x1800043a1  jz      short loc_1800043B3
0x1800043a3  mov     cs:qword_180069F70, rdi
0x1800043aa  mov     cs:qword_180069F78, rax
0x1800043b1  jmp     short loc_1800043D1
0x1800043b3  xor     r9d, r9d; lpName
0x1800043b6  xor     r8d, r8d; bInitialState
0x1800043b9  xor     ecx, ecx; lpEventAttributes
0x1800043bb  lea     edx, [r9+1]; bManualReset
0x1800043bf  call    cs:__imp_CreateEventW
0x1800043c5  mov     cs:hHandle, rax
0x1800043cc  test    rax, rax
0x1800043cf  jz      short loc_1800043F5
0x1800043d1  xor     ecx, ecx
0x1800043d3  call    __scrt_initialize_onexit_tables
0x1800043d8  test    al, al
0x1800043da  jz      short loc_1800043F5
0x1800043dc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800043e3  call    atexit
0x1800043e8  mov     rbx, [rsp+28h+arg_0]
0x1800043ed  xor     eax, eax
0x1800043ef  add     rsp, 20h
0x1800043f3  pop     rdi
0x1800043f4  retn
0x1800043f5  mov     ecx, 7
0x1800043fa  call    __scrt_fastfail
```
