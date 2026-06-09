# __scrt_initialize_thread_safe_statics

- ea: `0x18001bb00`
- end: `0x18001bbd0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18001b220`
- `0x18001b3f0`
- `0x18001b564`
- `0x18001bb00`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001bb23`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001bb38`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001bb23`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001bb38`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001bb50`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001bb63`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001bb50`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001bb63`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001bb8f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001bb8f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18001bb16`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18001bb16`

## string_xrefs

- `0x18001bb1c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18001bb31`: `kernel32.dll`

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
    qword_1800599B0 = (__int64)ProcAddress;
    qword_1800599B8 = (__int64)v2;
  }
  else
  {
    hEvent = CreateEventW(0, 1, 0, 0);
    if ( !hEvent )
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
0x18001bb00  mov     [rsp+arg_0], rbx
0x18001bb05  push    rdi
0x18001bb06  sub     rsp, 20h
0x18001bb0a  mov     edx, 0FA0h; dwSpinCount
0x18001bb0f  lea     rcx, CriticalSection; lpCriticalSection
0x18001bb16  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18001bb1c  lea     rcx, aApiMsWinCoreSy_4; "api-ms-win-core-synch-l1-2-0.dll"
0x18001bb23  call    cs:__imp_GetModuleHandleW
0x18001bb29  mov     rbx, rax
0x18001bb2c  test    rax, rax
0x18001bb2f  jnz     short loc_18001BB46
0x18001bb31  lea     rcx, aKernel32Dll; "kernel32.dll"
0x18001bb38  call    cs:__imp_GetModuleHandleW
0x18001bb3e  mov     rbx, rax
0x18001bb41  test    rax, rax
0x18001bb44  jz      short loc_18001BBC5
0x18001bb46  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18001bb4d  mov     rcx, rbx; hModule
0x18001bb50  call    cs:__imp_GetProcAddress
0x18001bb56  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18001bb5d  mov     rcx, rbx; hModule
0x18001bb60  mov     rdi, rax
0x18001bb63  call    cs:__imp_GetProcAddress
0x18001bb69  test    rdi, rdi
0x18001bb6c  jz      short loc_18001BB83
0x18001bb6e  test    rax, rax
0x18001bb71  jz      short loc_18001BB83
0x18001bb73  mov     cs:qword_1800599B0, rdi
0x18001bb7a  mov     cs:qword_1800599B8, rax
0x18001bb81  jmp     short loc_18001BBA1
0x18001bb83  xor     r9d, r9d; lpName
0x18001bb86  xor     r8d, r8d; bInitialState
0x18001bb89  xor     ecx, ecx; lpEventAttributes
0x18001bb8b  lea     edx, [r9+1]; bManualReset
0x18001bb8f  call    cs:__imp_CreateEventW
0x18001bb95  mov     cs:hEvent, rax
0x18001bb9c  test    rax, rax
0x18001bb9f  jz      short loc_18001BBC5
0x18001bba1  xor     ecx, ecx
0x18001bba3  call    __scrt_initialize_onexit_tables
0x18001bba8  test    al, al
0x18001bbaa  jz      short loc_18001BBC5
0x18001bbac  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x18001bbb3  call    atexit
0x18001bbb8  mov     rbx, [rsp+28h+arg_0]
0x18001bbbd  xor     eax, eax
0x18001bbbf  add     rsp, 20h
0x18001bbc3  pop     rdi
0x18001bbc4  retn
0x18001bbc5  mov     ecx, 7
0x18001bbca  call    __scrt_fastfail
```
