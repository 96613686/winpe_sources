# __scrt_initialize_thread_safe_statics

- ea: `0x180228c00`
- end: `0x180228cd0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180228670`
- `0x180228840`
- `0x180228c00`
- `0x1802291d0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180228c23`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180228c38`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180228c23`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180228c38`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180228c50`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180228c63`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180228c50`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180228c63`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180228c8f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180228c8f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180228c16`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180228c16`

## string_xrefs

- `0x180228c31`: `kernel32.dll`
- `0x180228c1c`: `api-ms-win-core-synch-l1-2-0.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1803BA368, 0xFA0u);
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
    qword_1803BA390 = (__int64)ProcAddress;
    qword_1803BA398 = (__int64)v2;
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
0x180228c00  mov     [rsp+arg_0], rbx
0x180228c05  push    rdi
0x180228c06  sub     rsp, 20h
0x180228c0a  mov     edx, 0FA0h; dwSpinCount
0x180228c0f  lea     rcx, stru_1803BA368; lpCriticalSection
0x180228c16  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180228c1c  lea     rcx, aApiMsWinCoreSy_3; "api-ms-win-core-synch-l1-2-0.dll"
0x180228c23  call    cs:__imp_GetModuleHandleW
0x180228c29  mov     rbx, rax
0x180228c2c  test    rax, rax
0x180228c2f  jnz     short loc_180228C46
0x180228c31  lea     rcx, ModuleName; "kernel32.dll"
0x180228c38  call    cs:__imp_GetModuleHandleW
0x180228c3e  mov     rbx, rax
0x180228c41  test    rax, rax
0x180228c44  jz      short loc_180228CC5
0x180228c46  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x180228c4d  mov     rcx, rbx; hModule
0x180228c50  call    cs:__imp_GetProcAddress
0x180228c56  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180228c5d  mov     rcx, rbx; hModule
0x180228c60  mov     rdi, rax
0x180228c63  call    cs:__imp_GetProcAddress
0x180228c69  test    rdi, rdi
0x180228c6c  jz      short loc_180228C83
0x180228c6e  test    rax, rax
0x180228c71  jz      short loc_180228C83
0x180228c73  mov     cs:qword_1803BA390, rdi
0x180228c7a  mov     cs:qword_1803BA398, rax
0x180228c81  jmp     short loc_180228CA1
0x180228c83  xor     r9d, r9d; lpName
0x180228c86  xor     r8d, r8d; bInitialState
0x180228c89  xor     ecx, ecx; lpEventAttributes
0x180228c8b  lea     edx, [r9+1]; bManualReset
0x180228c8f  call    cs:__imp_CreateEventW
0x180228c95  mov     cs:hHandle, rax
0x180228c9c  test    rax, rax
0x180228c9f  jz      short loc_180228CC5
0x180228ca1  xor     ecx, ecx
0x180228ca3  call    __scrt_initialize_onexit_tables
0x180228ca8  test    al, al
0x180228caa  jz      short loc_180228CC5
0x180228cac  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180228cb3  call    atexit
0x180228cb8  mov     rbx, [rsp+28h+arg_0]
0x180228cbd  xor     eax, eax
0x180228cbf  add     rsp, 20h
0x180228cc3  pop     rdi
0x180228cc4  retn
0x180228cc5  mov     ecx, 7
0x180228cca  call    __scrt_fastfail
```
