# __scrt_initialize_thread_safe_statics

- ea: `0x180002830`
- end: `0x180002900`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180002000`
- `0x1800021d0`
- `0x180002200`
- `0x180002830`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002880`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002893`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002880`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002893`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002853`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002868`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002853`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002868`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800028bf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800028bf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180002846`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180002846`

## string_xrefs

- `0x18000284c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180002861`: `kernel32.dll`

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
    qword_1800298B8 = (__int64)ProcAddress;
    qword_1800298C0 = (__int64)v2;
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
0x180002830  mov     [rsp+arg_0], rbx
0x180002835  push    rdi
0x180002836  sub     rsp, 20h
0x18000283a  mov     edx, 0FA0h; dwSpinCount
0x18000283f  lea     rcx, CriticalSection; lpCriticalSection
0x180002846  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000284c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180002853  call    cs:__imp_GetModuleHandleW
0x180002859  mov     rbx, rax
0x18000285c  test    rax, rax
0x18000285f  jnz     short loc_180002876
0x180002861  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180002868  call    cs:__imp_GetModuleHandleW
0x18000286e  mov     rbx, rax
0x180002871  test    rax, rax
0x180002874  jz      short loc_1800028F5
0x180002876  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000287d  mov     rcx, rbx; hModule
0x180002880  call    cs:__imp_GetProcAddress
0x180002886  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000288d  mov     rcx, rbx; hModule
0x180002890  mov     rdi, rax
0x180002893  call    cs:__imp_GetProcAddress
0x180002899  test    rdi, rdi
0x18000289c  jz      short loc_1800028B3
0x18000289e  test    rax, rax
0x1800028a1  jz      short loc_1800028B3
0x1800028a3  mov     cs:qword_1800298B8, rdi
0x1800028aa  mov     cs:qword_1800298C0, rax
0x1800028b1  jmp     short loc_1800028D1
0x1800028b3  xor     r9d, r9d; lpName
0x1800028b6  xor     r8d, r8d; bInitialState
0x1800028b9  xor     ecx, ecx; lpEventAttributes
0x1800028bb  lea     edx, [r9+1]; bManualReset
0x1800028bf  call    cs:__imp_CreateEventW
0x1800028c5  mov     cs:hHandle, rax
0x1800028cc  test    rax, rax
0x1800028cf  jz      short loc_1800028F5
0x1800028d1  xor     ecx, ecx
0x1800028d3  call    __scrt_initialize_onexit_tables
0x1800028d8  test    al, al
0x1800028da  jz      short loc_1800028F5
0x1800028dc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800028e3  call    atexit
0x1800028e8  mov     rbx, [rsp+28h+arg_0]
0x1800028ed  xor     eax, eax
0x1800028ef  add     rsp, 20h
0x1800028f3  pop     rdi
0x1800028f4  retn
0x1800028f5  mov     ecx, 7
0x1800028fa  call    __scrt_fastfail
```
