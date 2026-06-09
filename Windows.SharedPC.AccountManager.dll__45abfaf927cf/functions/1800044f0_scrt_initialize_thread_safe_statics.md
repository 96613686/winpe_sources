# __scrt_initialize_thread_safe_statics

- ea: `0x1800044f0`
- end: `0x1800045c0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180003748`
- `0x180003918`
- `0x180003a74`
- `0x1800044f0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004513`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004528`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004513`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004528`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004540`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004553`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004540`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004553`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004506`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004506`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000457f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000457f`

## string_xrefs

- `0x18000450c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180004521`: `kernel32.dll`

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
    qword_180036730 = (__int64)ProcAddress;
    qword_180036738 = (__int64)v2;
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
0x1800044f0  mov     [rsp+arg_0], rbx
0x1800044f5  push    rdi
0x1800044f6  sub     rsp, 20h
0x1800044fa  mov     edx, 0FA0h; dwSpinCount
0x1800044ff  lea     rcx, CriticalSection; lpCriticalSection
0x180004506  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000450c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180004513  call    cs:__imp_GetModuleHandleW
0x180004519  mov     rbx, rax
0x18000451c  test    rax, rax
0x18000451f  jnz     short loc_180004536
0x180004521  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180004528  call    cs:__imp_GetModuleHandleW
0x18000452e  mov     rbx, rax
0x180004531  test    rax, rax
0x180004534  jz      short loc_1800045B5
0x180004536  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000453d  mov     rcx, rbx; hModule
0x180004540  call    cs:__imp_GetProcAddress
0x180004546  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000454d  mov     rcx, rbx; hModule
0x180004550  mov     rdi, rax
0x180004553  call    cs:__imp_GetProcAddress
0x180004559  test    rdi, rdi
0x18000455c  jz      short loc_180004573
0x18000455e  test    rax, rax
0x180004561  jz      short loc_180004573
0x180004563  mov     cs:qword_180036730, rdi
0x18000456a  mov     cs:qword_180036738, rax
0x180004571  jmp     short loc_180004591
0x180004573  xor     r9d, r9d; lpName
0x180004576  xor     r8d, r8d; bInitialState
0x180004579  xor     ecx, ecx; lpEventAttributes
0x18000457b  lea     edx, [r9+1]; bManualReset
0x18000457f  call    cs:__imp_CreateEventW
0x180004585  mov     cs:hHandle, rax
0x18000458c  test    rax, rax
0x18000458f  jz      short loc_1800045B5
0x180004591  xor     ecx, ecx
0x180004593  call    __scrt_initialize_onexit_tables
0x180004598  test    al, al
0x18000459a  jz      short loc_1800045B5
0x18000459c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800045a3  call    atexit
0x1800045a8  mov     rbx, [rsp+28h+arg_0]
0x1800045ad  xor     eax, eax
0x1800045af  add     rsp, 20h
0x1800045b3  pop     rdi
0x1800045b4  retn
0x1800045b5  mov     ecx, 7
0x1800045ba  call    __scrt_fastfail
```
