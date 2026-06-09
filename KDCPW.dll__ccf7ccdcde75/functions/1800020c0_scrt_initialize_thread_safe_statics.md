# __scrt_initialize_thread_safe_statics

- ea: `0x1800020c0`
- end: `0x180002190`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001810`
- `0x1800019e0`
- `0x180001b24`
- `0x1800020c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002110`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002123`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002110`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002123`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800020e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800020f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800020e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800020f8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800020d6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800020d6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000214f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000214f`

## string_xrefs

- `0x1800020dc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800020f1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_180012470, 0xFA0u);
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
    qword_180012498 = (__int64)ProcAddress;
    qword_1800124A0 = (__int64)v2;
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
0x1800020c0  mov     [rsp+arg_0], rbx
0x1800020c5  push    rdi
0x1800020c6  sub     rsp, 20h
0x1800020ca  mov     edx, 0FA0h; dwSpinCount
0x1800020cf  lea     rcx, stru_180012470; lpCriticalSection
0x1800020d6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800020dc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x1800020e3  call    cs:__imp_GetModuleHandleW
0x1800020e9  mov     rbx, rax
0x1800020ec  test    rax, rax
0x1800020ef  jnz     short loc_180002106
0x1800020f1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800020f8  call    cs:__imp_GetModuleHandleW
0x1800020fe  mov     rbx, rax
0x180002101  test    rax, rax
0x180002104  jz      short loc_180002185
0x180002106  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000210d  mov     rcx, rbx; hModule
0x180002110  call    cs:__imp_GetProcAddress
0x180002116  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000211d  mov     rcx, rbx; hModule
0x180002120  mov     rdi, rax
0x180002123  call    cs:__imp_GetProcAddress
0x180002129  test    rdi, rdi
0x18000212c  jz      short loc_180002143
0x18000212e  test    rax, rax
0x180002131  jz      short loc_180002143
0x180002133  mov     cs:qword_180012498, rdi
0x18000213a  mov     cs:qword_1800124A0, rax
0x180002141  jmp     short loc_180002161
0x180002143  xor     r9d, r9d; lpName
0x180002146  xor     r8d, r8d; bInitialState
0x180002149  xor     ecx, ecx; lpEventAttributes
0x18000214b  lea     edx, [r9+1]; bManualReset
0x18000214f  call    cs:__imp_CreateEventW
0x180002155  mov     cs:hHandle, rax
0x18000215c  test    rax, rax
0x18000215f  jz      short loc_180002185
0x180002161  xor     ecx, ecx
0x180002163  call    __scrt_initialize_onexit_tables
0x180002168  test    al, al
0x18000216a  jz      short loc_180002185
0x18000216c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180002173  call    atexit
0x180002178  mov     rbx, [rsp+28h+arg_0]
0x18000217d  xor     eax, eax
0x18000217f  add     rsp, 20h
0x180002183  pop     rdi
0x180002184  retn
0x180002185  mov     ecx, 7
0x18000218a  call    __scrt_fastfail
```
