# __scrt_initialize_thread_safe_statics

- ea: `0x180005b50`
- end: `0x180005c20`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180003ec8`
- `0x180004098`
- `0x180004214`
- `0x180005b50`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005ba0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005bb3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005ba0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005bb3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005b73`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005b88`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005b73`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005b88`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180005b66`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180005b66`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180005bdf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180005bdf`

## string_xrefs

- `0x180005b6c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180005b81`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_180098248, 0xFA0u);
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
    qword_180098270 = (__int64)ProcAddress;
    qword_180098278 = (__int64)v2;
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
0x180005b50  mov     [rsp+arg_0], rbx
0x180005b55  push    rdi
0x180005b56  sub     rsp, 20h
0x180005b5a  mov     edx, 0FA0h; dwSpinCount
0x180005b5f  lea     rcx, stru_180098248; lpCriticalSection
0x180005b66  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180005b6c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180005b73  call    cs:__imp_GetModuleHandleW
0x180005b79  mov     rbx, rax
0x180005b7c  test    rax, rax
0x180005b7f  jnz     short loc_180005B96
0x180005b81  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180005b88  call    cs:__imp_GetModuleHandleW
0x180005b8e  mov     rbx, rax
0x180005b91  test    rax, rax
0x180005b94  jz      short loc_180005C15
0x180005b96  lea     rdx, ProcName; "SleepConditionVariableCS"
0x180005b9d  mov     rcx, rbx; hModule
0x180005ba0  call    cs:__imp_GetProcAddress
0x180005ba6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180005bad  mov     rcx, rbx; hModule
0x180005bb0  mov     rdi, rax
0x180005bb3  call    cs:__imp_GetProcAddress
0x180005bb9  test    rdi, rdi
0x180005bbc  jz      short loc_180005BD3
0x180005bbe  test    rax, rax
0x180005bc1  jz      short loc_180005BD3
0x180005bc3  mov     cs:qword_180098270, rdi
0x180005bca  mov     cs:qword_180098278, rax
0x180005bd1  jmp     short loc_180005BF1
0x180005bd3  xor     r9d, r9d; lpName
0x180005bd6  xor     r8d, r8d; bInitialState
0x180005bd9  xor     ecx, ecx; lpEventAttributes
0x180005bdb  lea     edx, [r9+1]; bManualReset
0x180005bdf  call    cs:__imp_CreateEventW
0x180005be5  mov     cs:hHandle, rax
0x180005bec  test    rax, rax
0x180005bef  jz      short loc_180005C15
0x180005bf1  xor     ecx, ecx
0x180005bf3  call    __scrt_initialize_onexit_tables
0x180005bf8  test    al, al
0x180005bfa  jz      short loc_180005C15
0x180005bfc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180005c03  call    atexit
0x180005c08  mov     rbx, [rsp+28h+arg_0]
0x180005c0d  xor     eax, eax
0x180005c0f  add     rsp, 20h
0x180005c13  pop     rdi
0x180005c14  retn
0x180005c15  mov     ecx, 7
0x180005c1a  call    __scrt_fastfail
```
