# __scrt_initialize_thread_safe_statics

- ea: `0x180004a30`
- end: `0x180004b00`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800047f8`
- `0x1800049c8`
- `0x180004a30`
- `0x180004e3c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004a53`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004a68`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004a53`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004a68`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004a80`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004a93`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004a80`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004a93`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004abf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004abf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004a46`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004a46`

## string_xrefs

- `0x180004a4c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180004a61`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_180042A28, 0xFA0u);
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
    qword_180042A50 = (__int64)ProcAddress;
    qword_180042A58 = (__int64)v2;
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
0x180004a30  mov     [rsp+arg_0], rbx
0x180004a35  push    rdi
0x180004a36  sub     rsp, 20h
0x180004a3a  mov     edx, 0FA0h; dwSpinCount
0x180004a3f  lea     rcx, stru_180042A28; lpCriticalSection
0x180004a46  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180004a4c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180004a53  call    cs:__imp_GetModuleHandleW
0x180004a59  mov     rbx, rax
0x180004a5c  test    rax, rax
0x180004a5f  jnz     short loc_180004A76
0x180004a61  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180004a68  call    cs:__imp_GetModuleHandleW
0x180004a6e  mov     rbx, rax
0x180004a71  test    rax, rax
0x180004a74  jz      short loc_180004AF5
0x180004a76  lea     rdx, ProcName; "SleepConditionVariableCS"
0x180004a7d  mov     rcx, rbx; hModule
0x180004a80  call    cs:__imp_GetProcAddress
0x180004a86  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180004a8d  mov     rcx, rbx; hModule
0x180004a90  mov     rdi, rax
0x180004a93  call    cs:__imp_GetProcAddress
0x180004a99  test    rdi, rdi
0x180004a9c  jz      short loc_180004AB3
0x180004a9e  test    rax, rax
0x180004aa1  jz      short loc_180004AB3
0x180004aa3  mov     cs:qword_180042A50, rdi
0x180004aaa  mov     cs:qword_180042A58, rax
0x180004ab1  jmp     short loc_180004AD1
0x180004ab3  xor     r9d, r9d; lpName
0x180004ab6  xor     r8d, r8d; bInitialState
0x180004ab9  xor     ecx, ecx; lpEventAttributes
0x180004abb  lea     edx, [r9+1]; bManualReset
0x180004abf  call    cs:__imp_CreateEventW
0x180004ac5  mov     cs:hHandle, rax
0x180004acc  test    rax, rax
0x180004acf  jz      short loc_180004AF5
0x180004ad1  xor     ecx, ecx
0x180004ad3  call    __scrt_initialize_onexit_tables
0x180004ad8  test    al, al
0x180004ada  jz      short loc_180004AF5
0x180004adc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180004ae3  call    atexit
0x180004ae8  mov     rbx, [rsp+28h+arg_0]
0x180004aed  xor     eax, eax
0x180004aef  add     rsp, 20h
0x180004af3  pop     rdi
0x180004af4  retn
0x180004af5  mov     ecx, 7
0x180004afa  call    __scrt_fastfail
```
