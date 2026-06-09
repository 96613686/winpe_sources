# __scrt_initialize_thread_safe_statics

- ea: `0x180001cb0`
- end: `0x180001d80`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001a7c`
- `0x180001c4c`
- `0x180001cb0`
- `0x1800020cc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001d00`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001d13`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001d00`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001d13`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180001cd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180001ce8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180001cd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180001ce8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180001d3f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180001d3f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180001cc6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180001cc6`

## string_xrefs

- `0x180001ccc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180001ce1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_180017668, 0xFA0u);
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
    qword_180017690 = (__int64)ProcAddress;
    qword_180017698 = (__int64)v2;
  }
  else
  {
    hHandle = CreateEventW(0, 1, 0, 0);
    if ( !hHandle )
      goto LABEL_9;
  }
  if ( !(unsigned __int8)_scrt_initialize_onexit_tables(0) )
LABEL_9:
    _scrt_fastfail(7u);
  atexit(_scrt_uninitialize_thread_safe_statics);
  return 0;
}

```

## disassembly

```asm
0x180001cb0  mov     [rsp+arg_0], rbx
0x180001cb5  push    rdi
0x180001cb6  sub     rsp, 20h
0x180001cba  mov     edx, 0FA0h; dwSpinCount
0x180001cbf  lea     rcx, stru_180017668; lpCriticalSection
0x180001cc6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180001ccc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180001cd3  call    cs:__imp_GetModuleHandleW
0x180001cd9  mov     rbx, rax
0x180001cdc  test    rax, rax
0x180001cdf  jnz     short loc_180001CF6
0x180001ce1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180001ce8  call    cs:__imp_GetModuleHandleW
0x180001cee  mov     rbx, rax
0x180001cf1  test    rax, rax
0x180001cf4  jz      short loc_180001D75
0x180001cf6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x180001cfd  mov     rcx, rbx; hModule
0x180001d00  call    cs:__imp_GetProcAddress
0x180001d06  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180001d0d  mov     rcx, rbx; hModule
0x180001d10  mov     rdi, rax
0x180001d13  call    cs:__imp_GetProcAddress
0x180001d19  test    rdi, rdi
0x180001d1c  jz      short loc_180001D33
0x180001d1e  test    rax, rax
0x180001d21  jz      short loc_180001D33
0x180001d23  mov     cs:qword_180017690, rdi
0x180001d2a  mov     cs:qword_180017698, rax
0x180001d31  jmp     short loc_180001D51
0x180001d33  xor     r9d, r9d; lpName
0x180001d36  xor     r8d, r8d; bInitialState
0x180001d39  xor     ecx, ecx; lpEventAttributes
0x180001d3b  lea     edx, [r9+1]; bManualReset
0x180001d3f  call    cs:__imp_CreateEventW
0x180001d45  mov     cs:hHandle, rax
0x180001d4c  test    rax, rax
0x180001d4f  jz      short loc_180001D75
0x180001d51  xor     ecx, ecx
0x180001d53  call    __scrt_initialize_onexit_tables
0x180001d58  test    al, al
0x180001d5a  jz      short loc_180001D75
0x180001d5c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180001d63  call    atexit
0x180001d68  mov     rbx, [rsp+28h+arg_0]
0x180001d6d  xor     eax, eax
0x180001d6f  add     rsp, 20h
0x180001d73  pop     rdi
0x180001d74  retn
0x180001d75  mov     ecx, 7
0x180001d7a  call    __scrt_fastfail
```
