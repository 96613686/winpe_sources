# __scrt_initialize_thread_safe_statics

- ea: `0x18001cdf0`
- end: `0x18001cec0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18001be00`
- `0x18001bfd0`
- `0x18001c1b4`
- `0x18001cdf0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001ce13`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001ce28`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001ce13`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001ce28`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ce40`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ce53`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ce40`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ce53`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ce7f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ce7f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18001ce06`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18001ce06`

## string_xrefs

- `0x18001ce0c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18001ce21`: `kernel32.dll`

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
    qword_1800419E0 = (__int64)ProcAddress;
    qword_1800419E8 = (__int64)v2;
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
0x18001cdf0  mov     [rsp+arg_0], rbx
0x18001cdf5  push    rdi
0x18001cdf6  sub     rsp, 20h
0x18001cdfa  mov     edx, 0FA0h; dwSpinCount
0x18001cdff  lea     rcx, CriticalSection; lpCriticalSection
0x18001ce06  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18001ce0c  lea     rcx, aApiMsWinCoreSy_4; "api-ms-win-core-synch-l1-2-0.dll"
0x18001ce13  call    cs:__imp_GetModuleHandleW
0x18001ce19  mov     rbx, rax
0x18001ce1c  test    rax, rax
0x18001ce1f  jnz     short loc_18001CE36
0x18001ce21  lea     rcx, aKernel32Dll; "kernel32.dll"
0x18001ce28  call    cs:__imp_GetModuleHandleW
0x18001ce2e  mov     rbx, rax
0x18001ce31  test    rax, rax
0x18001ce34  jz      short loc_18001CEB5
0x18001ce36  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18001ce3d  mov     rcx, rbx; hModule
0x18001ce40  call    cs:__imp_GetProcAddress
0x18001ce46  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18001ce4d  mov     rcx, rbx; hModule
0x18001ce50  mov     rdi, rax
0x18001ce53  call    cs:__imp_GetProcAddress
0x18001ce59  test    rdi, rdi
0x18001ce5c  jz      short loc_18001CE73
0x18001ce5e  test    rax, rax
0x18001ce61  jz      short loc_18001CE73
0x18001ce63  mov     cs:qword_1800419E0, rdi
0x18001ce6a  mov     cs:qword_1800419E8, rax
0x18001ce71  jmp     short loc_18001CE91
0x18001ce73  xor     r9d, r9d; lpName
0x18001ce76  xor     r8d, r8d; bInitialState
0x18001ce79  xor     ecx, ecx; lpEventAttributes
0x18001ce7b  lea     edx, [r9+1]; bManualReset
0x18001ce7f  call    cs:__imp_CreateEventW
0x18001ce85  mov     cs:hHandle, rax
0x18001ce8c  test    rax, rax
0x18001ce8f  jz      short loc_18001CEB5
0x18001ce91  xor     ecx, ecx
0x18001ce93  call    __scrt_initialize_onexit_tables
0x18001ce98  test    al, al
0x18001ce9a  jz      short loc_18001CEB5
0x18001ce9c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x18001cea3  call    atexit
0x18001cea8  mov     rbx, [rsp+28h+arg_0]
0x18001cead  xor     eax, eax
0x18001ceaf  add     rsp, 20h
0x18001ceb3  pop     rdi
0x18001ceb4  retn
0x18001ceb5  mov     ecx, 7
0x18001ceba  call    __scrt_fastfail
```
