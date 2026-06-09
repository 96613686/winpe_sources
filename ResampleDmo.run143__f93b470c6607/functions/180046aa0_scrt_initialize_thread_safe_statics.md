# __scrt_initialize_thread_safe_statics

- ea: `0x180046aa0`
- end: `0x180046b70`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000af04`
- `0x18000b0d4`
- `0x18000b104`
- `0x180046aa0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180046b2f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180046b2f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180046ab6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180046ab6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180046af0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180046b03`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180046af0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180046b03`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180046ac3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180046ad8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180046ac3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180046ad8`

## string_xrefs

- `0x180046abc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180046ad1`: `kernel32.dll`

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
    qword_1800B4C18 = (__int64)ProcAddress;
    qword_1800B4C20 = (__int64)v2;
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
0x180046aa0  mov     [rsp+arg_0], rbx
0x180046aa5  push    rdi
0x180046aa6  sub     rsp, 20h
0x180046aaa  mov     edx, 0FA0h; dwSpinCount
0x180046aaf  lea     rcx, CriticalSection; lpCriticalSection
0x180046ab6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180046abc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180046ac3  call    cs:__imp_GetModuleHandleW
0x180046ac9  mov     rbx, rax
0x180046acc  test    rax, rax
0x180046acf  jnz     short loc_180046AE6
0x180046ad1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180046ad8  call    cs:__imp_GetModuleHandleW
0x180046ade  mov     rbx, rax
0x180046ae1  test    rax, rax
0x180046ae4  jz      short loc_180046B65
0x180046ae6  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x180046aed  mov     rcx, rbx; hModule
0x180046af0  call    cs:__imp_GetProcAddress
0x180046af6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180046afd  mov     rcx, rbx; hModule
0x180046b00  mov     rdi, rax
0x180046b03  call    cs:__imp_GetProcAddress
0x180046b09  test    rdi, rdi
0x180046b0c  jz      short loc_180046B23
0x180046b0e  test    rax, rax
0x180046b11  jz      short loc_180046B23
0x180046b13  mov     cs:qword_1800B4C18, rdi
0x180046b1a  mov     cs:qword_1800B4C20, rax
0x180046b21  jmp     short loc_180046B41
0x180046b23  xor     r9d, r9d; lpName
0x180046b26  xor     r8d, r8d; bInitialState
0x180046b29  xor     ecx, ecx; lpEventAttributes
0x180046b2b  lea     edx, [r9+1]; bManualReset
0x180046b2f  call    cs:__imp_CreateEventW
0x180046b35  mov     cs:hHandle, rax
0x180046b3c  test    rax, rax
0x180046b3f  jz      short loc_180046B65
0x180046b41  xor     ecx, ecx
0x180046b43  call    __scrt_initialize_onexit_tables
0x180046b48  test    al, al
0x180046b4a  jz      short loc_180046B65
0x180046b4c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180046b53  call    atexit
0x180046b58  mov     rbx, [rsp+28h+arg_0]
0x180046b5d  xor     eax, eax
0x180046b5f  add     rsp, 20h
0x180046b63  pop     rdi
0x180046b64  retn
0x180046b65  mov     ecx, 7
0x180046b6a  call    __scrt_fastfail
```
