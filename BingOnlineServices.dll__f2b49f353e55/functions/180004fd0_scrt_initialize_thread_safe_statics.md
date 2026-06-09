# __scrt_initialize_thread_safe_statics

- ea: `0x180004fd0`
- end: `0x1800050a0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180004fd0`
- `0x18000556c`
- `0x18000573c`
- `0x180005bd0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004ff3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005008`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004ff3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005008`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005020`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005033`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005020`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005033`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004fe6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004fe6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000505f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000505f`

## string_xrefs

- `0x180004fec`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180005001`: `kernel32.dll`

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
    qword_18009B7B8 = (__int64)ProcAddress;
    qword_18009B7C0 = (__int64)v2;
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
0x180004fd0  mov     [rsp+arg_0], rbx
0x180004fd5  push    rdi
0x180004fd6  sub     rsp, 20h
0x180004fda  mov     edx, 0FA0h; dwSpinCount
0x180004fdf  lea     rcx, CriticalSection; lpCriticalSection
0x180004fe6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180004fec  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180004ff3  call    cs:__imp_GetModuleHandleW
0x180004ff9  mov     rbx, rax
0x180004ffc  test    rax, rax
0x180004fff  jnz     short loc_180005016
0x180005001  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180005008  call    cs:__imp_GetModuleHandleW
0x18000500e  mov     rbx, rax
0x180005011  test    rax, rax
0x180005014  jz      short loc_180005095
0x180005016  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000501d  mov     rcx, rbx; hModule
0x180005020  call    cs:__imp_GetProcAddress
0x180005026  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000502d  mov     rcx, rbx; hModule
0x180005030  mov     rdi, rax
0x180005033  call    cs:__imp_GetProcAddress
0x180005039  test    rdi, rdi
0x18000503c  jz      short loc_180005053
0x18000503e  test    rax, rax
0x180005041  jz      short loc_180005053
0x180005043  mov     cs:qword_18009B7B8, rdi
0x18000504a  mov     cs:qword_18009B7C0, rax
0x180005051  jmp     short loc_180005071
0x180005053  xor     r9d, r9d; lpName
0x180005056  xor     r8d, r8d; bInitialState
0x180005059  xor     ecx, ecx; lpEventAttributes
0x18000505b  lea     edx, [r9+1]; bManualReset
0x18000505f  call    cs:__imp_CreateEventW
0x180005065  mov     cs:hHandle, rax
0x18000506c  test    rax, rax
0x18000506f  jz      short loc_180005095
0x180005071  xor     ecx, ecx
0x180005073  call    __scrt_initialize_onexit_tables
0x180005078  test    al, al
0x18000507a  jz      short loc_180005095
0x18000507c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180005083  call    atexit
0x180005088  mov     rbx, [rsp+28h+arg_0]
0x18000508d  xor     eax, eax
0x18000508f  add     rsp, 20h
0x180005093  pop     rdi
0x180005094  retn
0x180005095  mov     ecx, 7
0x18000509a  call    __scrt_fastfail
```
