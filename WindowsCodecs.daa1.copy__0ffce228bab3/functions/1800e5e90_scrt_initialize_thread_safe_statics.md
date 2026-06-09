# __scrt_initialize_thread_safe_statics

- ea: `0x1800e5e90`
- end: `0x1800e5f60`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800e5e90`
- `0x1800e63f0`
- `0x1800e65c0`
- `0x1800e65f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e5f1f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e5f1f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800e5ea6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800e5ea6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800e5eb3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800e5ec8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800e5eb3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800e5ec8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e5ee0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e5ef3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e5ee0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e5ef3`

## string_xrefs

- `0x1800e5eac`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800e5ec1`: `kernel32.dll`

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
    qword_180269860 = (__int64)ProcAddress;
    qword_180269868 = (__int64)v2;
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
0x1800e5e90  mov     [rsp+arg_0], rbx
0x1800e5e95  push    rdi
0x1800e5e96  sub     rsp, 20h
0x1800e5e9a  mov     edx, 0FA0h; dwSpinCount
0x1800e5e9f  lea     rcx, CriticalSection; lpCriticalSection
0x1800e5ea6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800e5eac  lea     rcx, aApiMsWinCoreSy_2; "api-ms-win-core-synch-l1-2-0.dll"
0x1800e5eb3  call    cs:__imp_GetModuleHandleW
0x1800e5eb9  mov     rbx, rax
0x1800e5ebc  test    rax, rax
0x1800e5ebf  jnz     short loc_1800E5ED6
0x1800e5ec1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800e5ec8  call    cs:__imp_GetModuleHandleW
0x1800e5ece  mov     rbx, rax
0x1800e5ed1  test    rax, rax
0x1800e5ed4  jz      short loc_1800E5F55
0x1800e5ed6  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x1800e5edd  mov     rcx, rbx; hModule
0x1800e5ee0  call    cs:__imp_GetProcAddress
0x1800e5ee6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800e5eed  mov     rcx, rbx; hModule
0x1800e5ef0  mov     rdi, rax
0x1800e5ef3  call    cs:__imp_GetProcAddress
0x1800e5ef9  test    rdi, rdi
0x1800e5efc  jz      short loc_1800E5F13
0x1800e5efe  test    rax, rax
0x1800e5f01  jz      short loc_1800E5F13
0x1800e5f03  mov     cs:qword_180269860, rdi
0x1800e5f0a  mov     cs:qword_180269868, rax
0x1800e5f11  jmp     short loc_1800E5F31
0x1800e5f13  xor     r9d, r9d; lpName
0x1800e5f16  xor     r8d, r8d; bInitialState
0x1800e5f19  xor     ecx, ecx; lpEventAttributes
0x1800e5f1b  lea     edx, [r9+1]; bManualReset
0x1800e5f1f  call    cs:__imp_CreateEventW
0x1800e5f25  mov     cs:hHandle, rax
0x1800e5f2c  test    rax, rax
0x1800e5f2f  jz      short loc_1800E5F55
0x1800e5f31  xor     ecx, ecx
0x1800e5f33  call    __scrt_initialize_onexit_tables
0x1800e5f38  test    al, al
0x1800e5f3a  jz      short loc_1800E5F55
0x1800e5f3c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800e5f43  call    atexit
0x1800e5f48  mov     rbx, [rsp+28h+arg_0]
0x1800e5f4d  xor     eax, eax
0x1800e5f4f  add     rsp, 20h
0x1800e5f53  pop     rdi
0x1800e5f54  retn
0x1800e5f55  mov     ecx, 7
0x1800e5f5a  call    __scrt_fastfail
```
