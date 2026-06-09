# __scrt_initialize_thread_safe_statics

- ea: `0x180052eb0`
- end: `0x180052f80`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180052c00`
- `0x180052dd0`
- `0x180052eb0`
- `0x1800534f4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180052f00`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180052f13`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180052f00`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180052f13`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180052ed3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180052ee8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180052ed3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180052ee8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180052ec6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180052ec6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180052f3f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180052f3f`

## string_xrefs

- `0x180052ecc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180052ee1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1801AE698, 0xFA0u);
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
    qword_1801AE6C0 = (__int64)ProcAddress;
    qword_1801AE6C8 = (__int64)v2;
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
0x180052eb0  mov     [rsp+arg_0], rbx
0x180052eb5  push    rdi
0x180052eb6  sub     rsp, 20h
0x180052eba  mov     edx, 0FA0h; dwSpinCount
0x180052ebf  lea     rcx, stru_1801AE698; lpCriticalSection
0x180052ec6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180052ecc  lea     rcx, aApiMsWinCoreSy_4; "api-ms-win-core-synch-l1-2-0.dll"
0x180052ed3  call    cs:__imp_GetModuleHandleW
0x180052ed9  mov     rbx, rax
0x180052edc  test    rax, rax
0x180052edf  jnz     short loc_180052EF6
0x180052ee1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180052ee8  call    cs:__imp_GetModuleHandleW
0x180052eee  mov     rbx, rax
0x180052ef1  test    rax, rax
0x180052ef4  jz      short loc_180052F75
0x180052ef6  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x180052efd  mov     rcx, rbx; hModule
0x180052f00  call    cs:__imp_GetProcAddress
0x180052f06  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180052f0d  mov     rcx, rbx; hModule
0x180052f10  mov     rdi, rax
0x180052f13  call    cs:__imp_GetProcAddress
0x180052f19  test    rdi, rdi
0x180052f1c  jz      short loc_180052F33
0x180052f1e  test    rax, rax
0x180052f21  jz      short loc_180052F33
0x180052f23  mov     cs:qword_1801AE6C0, rdi
0x180052f2a  mov     cs:qword_1801AE6C8, rax
0x180052f31  jmp     short loc_180052F51
0x180052f33  xor     r9d, r9d; lpName
0x180052f36  xor     r8d, r8d; bInitialState
0x180052f39  xor     ecx, ecx; lpEventAttributes
0x180052f3b  lea     edx, [r9+1]; bManualReset
0x180052f3f  call    cs:__imp_CreateEventW
0x180052f45  mov     cs:hHandle, rax
0x180052f4c  test    rax, rax
0x180052f4f  jz      short loc_180052F75
0x180052f51  xor     ecx, ecx
0x180052f53  call    __scrt_initialize_onexit_tables
0x180052f58  test    al, al
0x180052f5a  jz      short loc_180052F75
0x180052f5c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180052f63  call    atexit
0x180052f68  mov     rbx, [rsp+28h+arg_0]
0x180052f6d  xor     eax, eax
0x180052f6f  add     rsp, 20h
0x180052f73  pop     rdi
0x180052f74  retn
0x180052f75  mov     ecx, 7
0x180052f7a  call    __scrt_fastfail
```
