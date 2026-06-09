# __scrt_initialize_thread_safe_statics

- ea: `0x18000dad0`
- end: `0x18000dba0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000cd40`
- `0x18000cf10`
- `0x18000d3a0`
- `0x18000dad0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000daf3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000db08`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000daf3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000db08`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000db20`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000db33`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000db20`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000db33`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000dae6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000dae6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000db5f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000db5f`

## string_xrefs

- `0x18000daec`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18000db01`: `kernel32.dll`

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
    qword_180236AF0 = (__int64)ProcAddress;
    qword_180236AF8 = (__int64)v2;
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
0x18000dad0  mov     [rsp+arg_0], rbx
0x18000dad5  push    rdi
0x18000dad6  sub     rsp, 20h
0x18000dada  mov     edx, 0FA0h; dwSpinCount
0x18000dadf  lea     rcx, CriticalSection; lpCriticalSection
0x18000dae6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000daec  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x18000daf3  call    cs:__imp_GetModuleHandleW
0x18000daf9  mov     rbx, rax
0x18000dafc  test    rax, rax
0x18000daff  jnz     short loc_18000DB16
0x18000db01  lea     rcx, aKernel32Dll; "kernel32.dll"
0x18000db08  call    cs:__imp_GetModuleHandleW
0x18000db0e  mov     rbx, rax
0x18000db11  test    rax, rax
0x18000db14  jz      short loc_18000DB95
0x18000db16  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000db1d  mov     rcx, rbx; hModule
0x18000db20  call    cs:__imp_GetProcAddress
0x18000db26  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000db2d  mov     rcx, rbx; hModule
0x18000db30  mov     rdi, rax
0x18000db33  call    cs:__imp_GetProcAddress
0x18000db39  test    rdi, rdi
0x18000db3c  jz      short loc_18000DB53
0x18000db3e  test    rax, rax
0x18000db41  jz      short loc_18000DB53
0x18000db43  mov     cs:qword_180236AF0, rdi
0x18000db4a  mov     cs:qword_180236AF8, rax
0x18000db51  jmp     short loc_18000DB71
0x18000db53  xor     r9d, r9d; lpName
0x18000db56  xor     r8d, r8d; bInitialState
0x18000db59  xor     ecx, ecx; lpEventAttributes
0x18000db5b  lea     edx, [r9+1]; bManualReset
0x18000db5f  call    cs:__imp_CreateEventW
0x18000db65  mov     cs:hHandle, rax
0x18000db6c  test    rax, rax
0x18000db6f  jz      short loc_18000DB95
0x18000db71  xor     ecx, ecx
0x18000db73  call    __scrt_initialize_onexit_tables
0x18000db78  test    al, al
0x18000db7a  jz      short loc_18000DB95
0x18000db7c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x18000db83  call    atexit
0x18000db88  mov     rbx, [rsp+28h+arg_0]
0x18000db8d  xor     eax, eax
0x18000db8f  add     rsp, 20h
0x18000db93  pop     rdi
0x18000db94  retn
0x18000db95  mov     ecx, 7
0x18000db9a  call    __scrt_fastfail
```
