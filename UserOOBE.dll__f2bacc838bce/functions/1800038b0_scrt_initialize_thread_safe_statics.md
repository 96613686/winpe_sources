# __scrt_initialize_thread_safe_statics

- ea: `0x1800038b0`
- end: `0x180003980`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000356c`
- `0x18000373c`
- `0x1800038b0`
- `0x180003f74`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800038d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800038e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800038d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800038e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003900`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003913`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003900`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003913`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800038c6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800038c6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000393f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000393f`

## string_xrefs

- `0x1800038cc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800038e1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_18006DEA8, 0xFA0u);
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
    qword_18006DED0 = (__int64)ProcAddress;
    qword_18006DED8 = (__int64)v2;
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
0x1800038b0  mov     [rsp+arg_0], rbx
0x1800038b5  push    rdi
0x1800038b6  sub     rsp, 20h
0x1800038ba  mov     edx, 0FA0h; dwSpinCount
0x1800038bf  lea     rcx, stru_18006DEA8; lpCriticalSection
0x1800038c6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800038cc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x1800038d3  call    cs:__imp_GetModuleHandleW
0x1800038d9  mov     rbx, rax
0x1800038dc  test    rax, rax
0x1800038df  jnz     short loc_1800038F6
0x1800038e1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800038e8  call    cs:__imp_GetModuleHandleW
0x1800038ee  mov     rbx, rax
0x1800038f1  test    rax, rax
0x1800038f4  jz      short loc_180003975
0x1800038f6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1800038fd  mov     rcx, rbx; hModule
0x180003900  call    cs:__imp_GetProcAddress
0x180003906  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000390d  mov     rcx, rbx; hModule
0x180003910  mov     rdi, rax
0x180003913  call    cs:__imp_GetProcAddress
0x180003919  test    rdi, rdi
0x18000391c  jz      short loc_180003933
0x18000391e  test    rax, rax
0x180003921  jz      short loc_180003933
0x180003923  mov     cs:qword_18006DED0, rdi
0x18000392a  mov     cs:qword_18006DED8, rax
0x180003931  jmp     short loc_180003951
0x180003933  xor     r9d, r9d; lpName
0x180003936  xor     r8d, r8d; bInitialState
0x180003939  xor     ecx, ecx; lpEventAttributes
0x18000393b  lea     edx, [r9+1]; bManualReset
0x18000393f  call    cs:__imp_CreateEventW
0x180003945  mov     cs:hHandle, rax
0x18000394c  test    rax, rax
0x18000394f  jz      short loc_180003975
0x180003951  xor     ecx, ecx
0x180003953  call    __scrt_initialize_onexit_tables
0x180003958  test    al, al
0x18000395a  jz      short loc_180003975
0x18000395c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180003963  call    atexit
0x180003968  mov     rbx, [rsp+28h+arg_0]
0x18000396d  xor     eax, eax
0x18000396f  add     rsp, 20h
0x180003973  pop     rdi
0x180003974  retn
0x180003975  mov     ecx, 7
0x18000397a  call    __scrt_fastfail
```
