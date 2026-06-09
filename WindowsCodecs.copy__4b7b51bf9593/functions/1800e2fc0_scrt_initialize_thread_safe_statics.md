# __scrt_initialize_thread_safe_statics

- ea: `0x1800e2fc0`
- end: `0x1800e3090`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800e2fc0`
- `0x1800e3520`
- `0x1800e36f0`
- `0x1800e3720`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e304f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e304f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800e2fd6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800e2fd6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800e2fe3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800e2ff8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800e2fe3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800e2ff8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e3010`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e3023`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e3010`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e3023`

## string_xrefs

- `0x1800e2fdc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800e2ff1`: `kernel32.dll`

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
    qword_180265720 = (__int64)ProcAddress;
    qword_180265728 = (__int64)v2;
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
0x1800e2fc0  mov     [rsp+arg_0], rbx
0x1800e2fc5  push    rdi
0x1800e2fc6  sub     rsp, 20h
0x1800e2fca  mov     edx, 0FA0h; dwSpinCount
0x1800e2fcf  lea     rcx, CriticalSection; lpCriticalSection
0x1800e2fd6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800e2fdc  lea     rcx, aApiMsWinCoreSy_2; "api-ms-win-core-synch-l1-2-0.dll"
0x1800e2fe3  call    cs:__imp_GetModuleHandleW
0x1800e2fe9  mov     rbx, rax
0x1800e2fec  test    rax, rax
0x1800e2fef  jnz     short loc_1800E3006
0x1800e2ff1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800e2ff8  call    cs:__imp_GetModuleHandleW
0x1800e2ffe  mov     rbx, rax
0x1800e3001  test    rax, rax
0x1800e3004  jz      short loc_1800E3085
0x1800e3006  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x1800e300d  mov     rcx, rbx; hModule
0x1800e3010  call    cs:__imp_GetProcAddress
0x1800e3016  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800e301d  mov     rcx, rbx; hModule
0x1800e3020  mov     rdi, rax
0x1800e3023  call    cs:__imp_GetProcAddress
0x1800e3029  test    rdi, rdi
0x1800e302c  jz      short loc_1800E3043
0x1800e302e  test    rax, rax
0x1800e3031  jz      short loc_1800E3043
0x1800e3033  mov     cs:qword_180265720, rdi
0x1800e303a  mov     cs:qword_180265728, rax
0x1800e3041  jmp     short loc_1800E3061
0x1800e3043  xor     r9d, r9d; lpName
0x1800e3046  xor     r8d, r8d; bInitialState
0x1800e3049  xor     ecx, ecx; lpEventAttributes
0x1800e304b  lea     edx, [r9+1]; bManualReset
0x1800e304f  call    cs:__imp_CreateEventW
0x1800e3055  mov     cs:hHandle, rax
0x1800e305c  test    rax, rax
0x1800e305f  jz      short loc_1800E3085
0x1800e3061  xor     ecx, ecx
0x1800e3063  call    __scrt_initialize_onexit_tables
0x1800e3068  test    al, al
0x1800e306a  jz      short loc_1800E3085
0x1800e306c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800e3073  call    atexit
0x1800e3078  mov     rbx, [rsp+28h+arg_0]
0x1800e307d  xor     eax, eax
0x1800e307f  add     rsp, 20h
0x1800e3083  pop     rdi
0x1800e3084  retn
0x1800e3085  mov     ecx, 7
0x1800e308a  call    __scrt_fastfail
```
