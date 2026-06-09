# __scrt_initialize_thread_safe_statics

- ea: `0x1800bd7c0`
- end: `0x1800bd890`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800bb75c`
- `0x1800bb92c`
- `0x1800bbe34`
- `0x1800bd7c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bd810`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bd823`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bd810`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bd823`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800bd7e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800bd7f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800bd7e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800bd7f8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800bd84f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800bd84f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800bd7d6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800bd7d6`

## string_xrefs

- `0x1800bd7dc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800bd7f1`: `kernel32.dll`

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
    qword_180333100 = (__int64)ProcAddress;
    qword_180333108 = (__int64)v2;
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
0x1800bd7c0  mov     [rsp+arg_0], rbx
0x1800bd7c5  push    rdi
0x1800bd7c6  sub     rsp, 20h
0x1800bd7ca  mov     edx, 0FA0h; dwSpinCount
0x1800bd7cf  lea     rcx, CriticalSection; lpCriticalSection
0x1800bd7d6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800bd7dc  lea     rcx, aApiMsWinCoreSy_3; "api-ms-win-core-synch-l1-2-0.dll"
0x1800bd7e3  call    cs:__imp_GetModuleHandleW
0x1800bd7e9  mov     rbx, rax
0x1800bd7ec  test    rax, rax
0x1800bd7ef  jnz     short loc_1800BD806
0x1800bd7f1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800bd7f8  call    cs:__imp_GetModuleHandleW
0x1800bd7fe  mov     rbx, rax
0x1800bd801  test    rax, rax
0x1800bd804  jz      short loc_1800BD885
0x1800bd806  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x1800bd80d  mov     rcx, rbx; hModule
0x1800bd810  call    cs:__imp_GetProcAddress
0x1800bd816  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800bd81d  mov     rcx, rbx; hModule
0x1800bd820  mov     rdi, rax
0x1800bd823  call    cs:__imp_GetProcAddress
0x1800bd829  test    rdi, rdi
0x1800bd82c  jz      short loc_1800BD843
0x1800bd82e  test    rax, rax
0x1800bd831  jz      short loc_1800BD843
0x1800bd833  mov     cs:qword_180333100, rdi
0x1800bd83a  mov     cs:qword_180333108, rax
0x1800bd841  jmp     short loc_1800BD861
0x1800bd843  xor     r9d, r9d; lpName
0x1800bd846  xor     r8d, r8d; bInitialState
0x1800bd849  xor     ecx, ecx; lpEventAttributes
0x1800bd84b  lea     edx, [r9+1]; bManualReset
0x1800bd84f  call    cs:__imp_CreateEventW
0x1800bd855  mov     cs:hHandle, rax
0x1800bd85c  test    rax, rax
0x1800bd85f  jz      short loc_1800BD885
0x1800bd861  xor     ecx, ecx
0x1800bd863  call    __scrt_initialize_onexit_tables
0x1800bd868  test    al, al
0x1800bd86a  jz      short loc_1800BD885
0x1800bd86c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800bd873  call    atexit
0x1800bd878  mov     rbx, [rsp+28h+arg_0]
0x1800bd87d  xor     eax, eax
0x1800bd87f  add     rsp, 20h
0x1800bd883  pop     rdi
0x1800bd884  retn
0x1800bd885  mov     ecx, 7
0x1800bd88a  call    __scrt_fastfail
```
