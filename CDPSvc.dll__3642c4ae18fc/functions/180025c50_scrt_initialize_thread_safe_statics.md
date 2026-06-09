# __scrt_initialize_thread_safe_statics

- ea: `0x180025c50`
- end: `0x180025d20`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800228a0`
- `0x180022a70`
- `0x180022c44`
- `0x180025c50`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025c73`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025c88`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025c73`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025c88`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025ca0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025cb3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025ca0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025cb3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180025c66`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180025c66`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180025cdf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180025cdf`

## string_xrefs

- `0x180025c6c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180025c81`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1800C6B78, 0xFA0u);
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
    qword_1800C6BA0 = (__int64)ProcAddress;
    qword_1800C6BA8 = (__int64)v2;
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
0x180025c50  mov     [rsp+arg_0], rbx
0x180025c55  push    rdi
0x180025c56  sub     rsp, 20h
0x180025c5a  mov     edx, 0FA0h; dwSpinCount
0x180025c5f  lea     rcx, stru_1800C6B78; lpCriticalSection
0x180025c66  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180025c6c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180025c73  call    cs:__imp_GetModuleHandleW
0x180025c79  mov     rbx, rax
0x180025c7c  test    rax, rax
0x180025c7f  jnz     short loc_180025C96
0x180025c81  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180025c88  call    cs:__imp_GetModuleHandleW
0x180025c8e  mov     rbx, rax
0x180025c91  test    rax, rax
0x180025c94  jz      short loc_180025D15
0x180025c96  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x180025c9d  mov     rcx, rbx; hModule
0x180025ca0  call    cs:__imp_GetProcAddress
0x180025ca6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180025cad  mov     rcx, rbx; hModule
0x180025cb0  mov     rdi, rax
0x180025cb3  call    cs:__imp_GetProcAddress
0x180025cb9  test    rdi, rdi
0x180025cbc  jz      short loc_180025CD3
0x180025cbe  test    rax, rax
0x180025cc1  jz      short loc_180025CD3
0x180025cc3  mov     cs:qword_1800C6BA0, rdi
0x180025cca  mov     cs:qword_1800C6BA8, rax
0x180025cd1  jmp     short loc_180025CF1
0x180025cd3  xor     r9d, r9d; lpName
0x180025cd6  xor     r8d, r8d; bInitialState
0x180025cd9  xor     ecx, ecx; lpEventAttributes
0x180025cdb  lea     edx, [r9+1]; bManualReset
0x180025cdf  call    cs:__imp_CreateEventW
0x180025ce5  mov     cs:hHandle, rax
0x180025cec  test    rax, rax
0x180025cef  jz      short loc_180025D15
0x180025cf1  xor     ecx, ecx
0x180025cf3  call    __scrt_initialize_onexit_tables
0x180025cf8  test    al, al
0x180025cfa  jz      short loc_180025D15
0x180025cfc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180025d03  call    atexit
0x180025d08  mov     rbx, [rsp+28h+arg_0]
0x180025d0d  xor     eax, eax
0x180025d0f  add     rsp, 20h
0x180025d13  pop     rdi
0x180025d14  retn
0x180025d15  mov     ecx, 7
0x180025d1a  call    __scrt_fastfail
```
