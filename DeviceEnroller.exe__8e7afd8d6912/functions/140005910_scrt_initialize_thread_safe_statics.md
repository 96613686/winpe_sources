# __scrt_initialize_thread_safe_statics

- ea: `0x140005910`
- end: `0x1400059e0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1400043b8`
- `0x140004588`
- `0x1400047b0`
- `0x140005910`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005960`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005973`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005960`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005973`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005933`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005948`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005933`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005948`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140005926`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140005926`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000599f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000599f`

## string_xrefs

- `0x14000592c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x140005941`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_14007E0F8, 0xFA0u);
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
    qword_14007E120 = (__int64)ProcAddress;
    qword_14007E128 = (__int64)v2;
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
0x140005910  mov     [rsp+arg_0], rbx
0x140005915  push    rdi
0x140005916  sub     rsp, 20h
0x14000591a  mov     edx, 0FA0h; dwSpinCount
0x14000591f  lea     rcx, stru_14007E0F8; lpCriticalSection
0x140005926  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x14000592c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x140005933  call    cs:__imp_GetModuleHandleW
0x140005939  mov     rbx, rax
0x14000593c  test    rax, rax
0x14000593f  jnz     short loc_140005956
0x140005941  lea     rcx, aKernel32Dll; "kernel32.dll"
0x140005948  call    cs:__imp_GetModuleHandleW
0x14000594e  mov     rbx, rax
0x140005951  test    rax, rax
0x140005954  jz      short loc_1400059D5
0x140005956  lea     rdx, ProcName; "SleepConditionVariableCS"
0x14000595d  mov     rcx, rbx; hModule
0x140005960  call    cs:__imp_GetProcAddress
0x140005966  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x14000596d  mov     rcx, rbx; hModule
0x140005970  mov     rdi, rax
0x140005973  call    cs:__imp_GetProcAddress
0x140005979  test    rdi, rdi
0x14000597c  jz      short loc_140005993
0x14000597e  test    rax, rax
0x140005981  jz      short loc_140005993
0x140005983  mov     cs:qword_14007E120, rdi
0x14000598a  mov     cs:qword_14007E128, rax
0x140005991  jmp     short loc_1400059B1
0x140005993  xor     r9d, r9d; lpName
0x140005996  xor     r8d, r8d; bInitialState
0x140005999  xor     ecx, ecx; lpEventAttributes
0x14000599b  lea     edx, [r9+1]; bManualReset
0x14000599f  call    cs:__imp_CreateEventW
0x1400059a5  mov     cs:hHandle, rax
0x1400059ac  test    rax, rax
0x1400059af  jz      short loc_1400059D5
0x1400059b1  xor     ecx, ecx
0x1400059b3  call    __scrt_initialize_onexit_tables
0x1400059b8  test    al, al
0x1400059ba  jz      short loc_1400059D5
0x1400059bc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1400059c3  call    atexit
0x1400059c8  mov     rbx, [rsp+28h+arg_0]
0x1400059cd  xor     eax, eax
0x1400059cf  add     rsp, 20h
0x1400059d3  pop     rdi
0x1400059d4  retn
0x1400059d5  mov     ecx, 7
0x1400059da  call    __scrt_fastfail
```
