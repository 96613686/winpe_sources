# __scrt_initialize_thread_safe_statics

- ea: `0x1800078e0`
- end: `0x1800079b0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000516c`
- `0x18000533c`
- `0x180005540`
- `0x1800078e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007903`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007918`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007903`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007918`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007930`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007943`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007930`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007943`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000796f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000796f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800078f6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800078f6`

## string_xrefs

- `0x1800078fc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180007911`: `kernel32.dll`

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
    qword_1800FEF90 = (__int64)ProcAddress;
    qword_1800FEF98 = (__int64)v2;
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
0x1800078e0  mov     [rsp+arg_0], rbx
0x1800078e5  push    rdi
0x1800078e6  sub     rsp, 20h
0x1800078ea  mov     edx, 0FA0h; dwSpinCount
0x1800078ef  lea     rcx, CriticalSection; lpCriticalSection
0x1800078f6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800078fc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180007903  call    cs:__imp_GetModuleHandleW
0x180007909  mov     rbx, rax
0x18000790c  test    rax, rax
0x18000790f  jnz     short loc_180007926
0x180007911  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180007918  call    cs:__imp_GetModuleHandleW
0x18000791e  mov     rbx, rax
0x180007921  test    rax, rax
0x180007924  jz      short loc_1800079A5
0x180007926  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000792d  mov     rcx, rbx; hModule
0x180007930  call    cs:__imp_GetProcAddress
0x180007936  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000793d  mov     rcx, rbx; hModule
0x180007940  mov     rdi, rax
0x180007943  call    cs:__imp_GetProcAddress
0x180007949  test    rdi, rdi
0x18000794c  jz      short loc_180007963
0x18000794e  test    rax, rax
0x180007951  jz      short loc_180007963
0x180007953  mov     cs:qword_1800FEF90, rdi
0x18000795a  mov     cs:qword_1800FEF98, rax
0x180007961  jmp     short loc_180007981
0x180007963  xor     r9d, r9d; lpName
0x180007966  xor     r8d, r8d; bInitialState
0x180007969  xor     ecx, ecx; lpEventAttributes
0x18000796b  lea     edx, [r9+1]; bManualReset
0x18000796f  call    cs:__imp_CreateEventW
0x180007975  mov     cs:hHandle, rax
0x18000797c  test    rax, rax
0x18000797f  jz      short loc_1800079A5
0x180007981  xor     ecx, ecx
0x180007983  call    __scrt_initialize_onexit_tables
0x180007988  test    al, al
0x18000798a  jz      short loc_1800079A5
0x18000798c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180007993  call    atexit
0x180007998  mov     rbx, [rsp+28h+arg_0]
0x18000799d  xor     eax, eax
0x18000799f  add     rsp, 20h
0x1800079a3  pop     rdi
0x1800079a4  retn
0x1800079a5  mov     ecx, 7
0x1800079aa  call    __scrt_fastfail
```
