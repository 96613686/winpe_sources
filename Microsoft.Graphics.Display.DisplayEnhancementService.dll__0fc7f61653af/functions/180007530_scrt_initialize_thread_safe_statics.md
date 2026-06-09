# __scrt_initialize_thread_safe_statics

- ea: `0x180007530`
- end: `0x180007600`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180005abc`
- `0x180005c8c`
- `0x180005ea0`
- `0x180007530`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007553`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007568`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007553`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007568`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007580`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007593`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007580`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007593`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800075bf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800075bf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180007546`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180007546`

## string_xrefs

- `0x18000754c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180007561`: `kernel32.dll`

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
    qword_180129B20 = (__int64)ProcAddress;
    qword_180129B28 = (__int64)v2;
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
0x180007530  mov     [rsp+arg_0], rbx
0x180007535  push    rdi
0x180007536  sub     rsp, 20h
0x18000753a  mov     edx, 0FA0h; dwSpinCount
0x18000753f  lea     rcx, CriticalSection; lpCriticalSection
0x180007546  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000754c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180007553  call    cs:__imp_GetModuleHandleW
0x180007559  mov     rbx, rax
0x18000755c  test    rax, rax
0x18000755f  jnz     short loc_180007576
0x180007561  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180007568  call    cs:__imp_GetModuleHandleW
0x18000756e  mov     rbx, rax
0x180007571  test    rax, rax
0x180007574  jz      short loc_1800075F5
0x180007576  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000757d  mov     rcx, rbx; hModule
0x180007580  call    cs:__imp_GetProcAddress
0x180007586  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000758d  mov     rcx, rbx; hModule
0x180007590  mov     rdi, rax
0x180007593  call    cs:__imp_GetProcAddress
0x180007599  test    rdi, rdi
0x18000759c  jz      short loc_1800075B3
0x18000759e  test    rax, rax
0x1800075a1  jz      short loc_1800075B3
0x1800075a3  mov     cs:qword_180129B20, rdi
0x1800075aa  mov     cs:qword_180129B28, rax
0x1800075b1  jmp     short loc_1800075D1
0x1800075b3  xor     r9d, r9d; lpName
0x1800075b6  xor     r8d, r8d; bInitialState
0x1800075b9  xor     ecx, ecx; lpEventAttributes
0x1800075bb  lea     edx, [r9+1]; bManualReset
0x1800075bf  call    cs:__imp_CreateEventW
0x1800075c5  mov     cs:hHandle, rax
0x1800075cc  test    rax, rax
0x1800075cf  jz      short loc_1800075F5
0x1800075d1  xor     ecx, ecx
0x1800075d3  call    __scrt_initialize_onexit_tables
0x1800075d8  test    al, al
0x1800075da  jz      short loc_1800075F5
0x1800075dc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800075e3  call    atexit
0x1800075e8  mov     rbx, [rsp+28h+arg_0]
0x1800075ed  xor     eax, eax
0x1800075ef  add     rsp, 20h
0x1800075f3  pop     rdi
0x1800075f4  retn
0x1800075f5  mov     ecx, 7
0x1800075fa  call    __scrt_fastfail
```
