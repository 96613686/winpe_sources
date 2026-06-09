# __scrt_initialize_thread_safe_statics

- ea: `0x180003f30`
- end: `0x180004000`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180003c90`
- `0x180003e60`
- `0x180003f30`
- `0x180004314`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003f80`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003f93`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003f80`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003f93`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003f53`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003f68`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003f53`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003f68`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180003f46`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180003f46`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003fbf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003fbf`

## string_xrefs

- `0x180003f4c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180003f61`: `kernel32.dll`

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
    qword_180042870 = (__int64)ProcAddress;
    qword_180042878 = (__int64)v2;
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
0x180003f30  mov     [rsp+arg_0], rbx
0x180003f35  push    rdi
0x180003f36  sub     rsp, 20h
0x180003f3a  mov     edx, 0FA0h; dwSpinCount
0x180003f3f  lea     rcx, CriticalSection; lpCriticalSection
0x180003f46  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180003f4c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180003f53  call    cs:__imp_GetModuleHandleW
0x180003f59  mov     rbx, rax
0x180003f5c  test    rax, rax
0x180003f5f  jnz     short loc_180003F76
0x180003f61  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180003f68  call    cs:__imp_GetModuleHandleW
0x180003f6e  mov     rbx, rax
0x180003f71  test    rax, rax
0x180003f74  jz      short loc_180003FF5
0x180003f76  lea     rdx, ProcName; "SleepConditionVariableCS"
0x180003f7d  mov     rcx, rbx; hModule
0x180003f80  call    cs:__imp_GetProcAddress
0x180003f86  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180003f8d  mov     rcx, rbx; hModule
0x180003f90  mov     rdi, rax
0x180003f93  call    cs:__imp_GetProcAddress
0x180003f99  test    rdi, rdi
0x180003f9c  jz      short loc_180003FB3
0x180003f9e  test    rax, rax
0x180003fa1  jz      short loc_180003FB3
0x180003fa3  mov     cs:qword_180042870, rdi
0x180003faa  mov     cs:qword_180042878, rax
0x180003fb1  jmp     short loc_180003FD1
0x180003fb3  xor     r9d, r9d; lpName
0x180003fb6  xor     r8d, r8d; bInitialState
0x180003fb9  xor     ecx, ecx; lpEventAttributes
0x180003fbb  lea     edx, [r9+1]; bManualReset
0x180003fbf  call    cs:__imp_CreateEventW
0x180003fc5  mov     cs:hHandle, rax
0x180003fcc  test    rax, rax
0x180003fcf  jz      short loc_180003FF5
0x180003fd1  xor     ecx, ecx
0x180003fd3  call    __scrt_initialize_onexit_tables
0x180003fd8  test    al, al
0x180003fda  jz      short loc_180003FF5
0x180003fdc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180003fe3  call    atexit
0x180003fe8  mov     rbx, [rsp+28h+arg_0]
0x180003fed  xor     eax, eax
0x180003fef  add     rsp, 20h
0x180003ff3  pop     rdi
0x180003ff4  retn
0x180003ff5  mov     ecx, 7
0x180003ffa  call    __scrt_fastfail
```
