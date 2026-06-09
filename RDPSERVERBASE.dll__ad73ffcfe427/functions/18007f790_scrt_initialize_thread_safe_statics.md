# __scrt_initialize_thread_safe_statics

- ea: `0x18007f790`
- end: `0x18007f860`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18007ecc8`
- `0x18007ee98`
- `0x18007eec8`
- `0x18007f790`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007f7e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007f7f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007f7e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007f7f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18007f7b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18007f7c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18007f7b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18007f7c8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18007f7a6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18007f7a6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007f81f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007f81f`

## string_xrefs

- `0x18007f7ac`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18007f7c1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1802BBE40, 0xFA0u);
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
    qword_1802BBE68 = (__int64)ProcAddress;
    qword_1802BBE70 = (__int64)v2;
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
0x18007f790  mov     [rsp+arg_0], rbx
0x18007f795  push    rdi
0x18007f796  sub     rsp, 20h
0x18007f79a  mov     edx, 0FA0h; dwSpinCount
0x18007f79f  lea     rcx, stru_1802BBE40; lpCriticalSection
0x18007f7a6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18007f7ac  lea     rcx, aApiMsWinCoreSy_4; "api-ms-win-core-synch-l1-2-0.dll"
0x18007f7b3  call    cs:__imp_GetModuleHandleW
0x18007f7b9  mov     rbx, rax
0x18007f7bc  test    rax, rax
0x18007f7bf  jnz     short loc_18007F7D6
0x18007f7c1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x18007f7c8  call    cs:__imp_GetModuleHandleW
0x18007f7ce  mov     rbx, rax
0x18007f7d1  test    rax, rax
0x18007f7d4  jz      short loc_18007F855
0x18007f7d6  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18007f7dd  mov     rcx, rbx; hModule
0x18007f7e0  call    cs:__imp_GetProcAddress
0x18007f7e6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18007f7ed  mov     rcx, rbx; hModule
0x18007f7f0  mov     rdi, rax
0x18007f7f3  call    cs:__imp_GetProcAddress
0x18007f7f9  test    rdi, rdi
0x18007f7fc  jz      short loc_18007F813
0x18007f7fe  test    rax, rax
0x18007f801  jz      short loc_18007F813
0x18007f803  mov     cs:qword_1802BBE68, rdi
0x18007f80a  mov     cs:qword_1802BBE70, rax
0x18007f811  jmp     short loc_18007F831
0x18007f813  xor     r9d, r9d; lpName
0x18007f816  xor     r8d, r8d; bInitialState
0x18007f819  xor     ecx, ecx; lpEventAttributes
0x18007f81b  lea     edx, [r9+1]; bManualReset
0x18007f81f  call    cs:__imp_CreateEventW
0x18007f825  mov     cs:hHandle, rax
0x18007f82c  test    rax, rax
0x18007f82f  jz      short loc_18007F855
0x18007f831  xor     ecx, ecx
0x18007f833  call    __scrt_initialize_onexit_tables
0x18007f838  test    al, al
0x18007f83a  jz      short loc_18007F855
0x18007f83c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x18007f843  call    atexit
0x18007f848  mov     rbx, [rsp+28h+arg_0]
0x18007f84d  xor     eax, eax
0x18007f84f  add     rsp, 20h
0x18007f853  pop     rdi
0x18007f854  retn
0x18007f855  mov     ecx, 7
0x18007f85a  call    __scrt_fastfail
```
