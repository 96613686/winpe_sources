# __scrt_initialize_thread_safe_statics

- ea: `0x180051d90`
- end: `0x180051e60`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180007450`
- `0x180007620`
- `0x180007794`
- `0x180051d90`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180051db3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180051dc8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180051db3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180051dc8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180051de0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180051df3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180051de0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180051df3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180051e1f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180051e1f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180051da6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180051da6`

## string_xrefs

- `0x180051dac`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180051dc1`: `kernel32.dll`

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
    qword_18010DC88 = (__int64)ProcAddress;
    qword_18010DC90 = (__int64)v2;
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
0x180051d90  mov     [rsp+arg_0], rbx
0x180051d95  push    rdi
0x180051d96  sub     rsp, 20h
0x180051d9a  mov     edx, 0FA0h; dwSpinCount
0x180051d9f  lea     rcx, CriticalSection; lpCriticalSection
0x180051da6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180051dac  lea     rcx, aApiMsWinCoreSy_3; "api-ms-win-core-synch-l1-2-0.dll"
0x180051db3  call    cs:__imp_GetModuleHandleW
0x180051db9  mov     rbx, rax
0x180051dbc  test    rax, rax
0x180051dbf  jnz     short loc_180051DD6
0x180051dc1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180051dc8  call    cs:__imp_GetModuleHandleW
0x180051dce  mov     rbx, rax
0x180051dd1  test    rax, rax
0x180051dd4  jz      short loc_180051E55
0x180051dd6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x180051ddd  mov     rcx, rbx; hModule
0x180051de0  call    cs:__imp_GetProcAddress
0x180051de6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180051ded  mov     rcx, rbx; hModule
0x180051df0  mov     rdi, rax
0x180051df3  call    cs:__imp_GetProcAddress
0x180051df9  test    rdi, rdi
0x180051dfc  jz      short loc_180051E13
0x180051dfe  test    rax, rax
0x180051e01  jz      short loc_180051E13
0x180051e03  mov     cs:qword_18010DC88, rdi
0x180051e0a  mov     cs:qword_18010DC90, rax
0x180051e11  jmp     short loc_180051E31
0x180051e13  xor     r9d, r9d; lpName
0x180051e16  xor     r8d, r8d; bInitialState
0x180051e19  xor     ecx, ecx; lpEventAttributes
0x180051e1b  lea     edx, [r9+1]; bManualReset
0x180051e1f  call    cs:__imp_CreateEventW
0x180051e25  mov     cs:hHandle, rax
0x180051e2c  test    rax, rax
0x180051e2f  jz      short loc_180051E55
0x180051e31  xor     ecx, ecx
0x180051e33  call    __scrt_initialize_onexit_tables
0x180051e38  test    al, al
0x180051e3a  jz      short loc_180051E55
0x180051e3c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180051e43  call    atexit
0x180051e48  mov     rbx, [rsp+28h+arg_0]
0x180051e4d  xor     eax, eax
0x180051e4f  add     rsp, 20h
0x180051e53  pop     rdi
0x180051e54  retn
0x180051e55  mov     ecx, 7
0x180051e5a  call    __scrt_fastfail
```
