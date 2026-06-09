# __scrt_initialize_thread_safe_statics

- ea: `0x1800058d0`
- end: `0x1800059a0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180003f80`
- `0x180004150`
- `0x1800042f4`
- `0x1800058d0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800058f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005908`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800058f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005908`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005920`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005933`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005920`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005933`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800058e6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800058e6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000595f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000595f`

## string_xrefs

- `0x1800058ec`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180005901`: `kernel32.dll`

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
    qword_180061440 = (__int64)ProcAddress;
    qword_180061448 = (__int64)v2;
  }
  else
  {
    hObject = CreateEventW(0, 1, 0, 0);
    if ( !hObject )
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
0x1800058d0  mov     [rsp+arg_0], rbx
0x1800058d5  push    rdi
0x1800058d6  sub     rsp, 20h
0x1800058da  mov     edx, 0FA0h; dwSpinCount
0x1800058df  lea     rcx, CriticalSection; lpCriticalSection
0x1800058e6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800058ec  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x1800058f3  call    cs:__imp_GetModuleHandleW
0x1800058f9  mov     rbx, rax
0x1800058fc  test    rax, rax
0x1800058ff  jnz     short loc_180005916
0x180005901  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180005908  call    cs:__imp_GetModuleHandleW
0x18000590e  mov     rbx, rax
0x180005911  test    rax, rax
0x180005914  jz      short loc_180005995
0x180005916  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000591d  mov     rcx, rbx; hModule
0x180005920  call    cs:__imp_GetProcAddress
0x180005926  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000592d  mov     rcx, rbx; hModule
0x180005930  mov     rdi, rax
0x180005933  call    cs:__imp_GetProcAddress
0x180005939  test    rdi, rdi
0x18000593c  jz      short loc_180005953
0x18000593e  test    rax, rax
0x180005941  jz      short loc_180005953
0x180005943  mov     cs:qword_180061440, rdi
0x18000594a  mov     cs:qword_180061448, rax
0x180005951  jmp     short loc_180005971
0x180005953  xor     r9d, r9d; lpName
0x180005956  xor     r8d, r8d; bInitialState
0x180005959  xor     ecx, ecx; lpEventAttributes
0x18000595b  lea     edx, [r9+1]; bManualReset
0x18000595f  call    cs:__imp_CreateEventW
0x180005965  mov     cs:hObject, rax
0x18000596c  test    rax, rax
0x18000596f  jz      short loc_180005995
0x180005971  xor     ecx, ecx
0x180005973  call    __scrt_initialize_onexit_tables
0x180005978  test    al, al
0x18000597a  jz      short loc_180005995
0x18000597c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180005983  call    atexit
0x180005988  mov     rbx, [rsp+28h+arg_0]
0x18000598d  xor     eax, eax
0x18000598f  add     rsp, 20h
0x180005993  pop     rdi
0x180005994  retn
0x180005995  mov     ecx, 7
0x18000599a  call    __scrt_fastfail
```
