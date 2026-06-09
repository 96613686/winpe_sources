# __scrt_initialize_thread_safe_statics

- ea: `0x18003eec0`
- end: `0x18003ef90`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18003ebd0`
- `0x18003eda0`
- `0x18003eec0`
- `0x18003f58c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ef10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ef23`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ef10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ef23`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003eee3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003eef8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003eee3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003eef8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18003eed6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18003eed6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003ef4f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003ef4f`

## string_xrefs

- `0x18003eedc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18003eef1`: `kernel32.dll`

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
    qword_180086350 = (__int64)ProcAddress;
    qword_180086358 = (__int64)v2;
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
0x18003eec0  mov     [rsp+arg_0], rbx
0x18003eec5  push    rdi
0x18003eec6  sub     rsp, 20h
0x18003eeca  mov     edx, 0FA0h; dwSpinCount
0x18003eecf  lea     rcx, CriticalSection; lpCriticalSection
0x18003eed6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18003eedc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x18003eee3  call    cs:__imp_GetModuleHandleW
0x18003eee9  mov     rbx, rax
0x18003eeec  test    rax, rax
0x18003eeef  jnz     short loc_18003EF06
0x18003eef1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x18003eef8  call    cs:__imp_GetModuleHandleW
0x18003eefe  mov     rbx, rax
0x18003ef01  test    rax, rax
0x18003ef04  jz      short loc_18003EF85
0x18003ef06  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18003ef0d  mov     rcx, rbx; hModule
0x18003ef10  call    cs:__imp_GetProcAddress
0x18003ef16  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18003ef1d  mov     rcx, rbx; hModule
0x18003ef20  mov     rdi, rax
0x18003ef23  call    cs:__imp_GetProcAddress
0x18003ef29  test    rdi, rdi
0x18003ef2c  jz      short loc_18003EF43
0x18003ef2e  test    rax, rax
0x18003ef31  jz      short loc_18003EF43
0x18003ef33  mov     cs:qword_180086350, rdi
0x18003ef3a  mov     cs:qword_180086358, rax
0x18003ef41  jmp     short loc_18003EF61
0x18003ef43  xor     r9d, r9d; lpName
0x18003ef46  xor     r8d, r8d; bInitialState
0x18003ef49  xor     ecx, ecx; lpEventAttributes
0x18003ef4b  lea     edx, [r9+1]; bManualReset
0x18003ef4f  call    cs:__imp_CreateEventW
0x18003ef55  mov     cs:hHandle, rax
0x18003ef5c  test    rax, rax
0x18003ef5f  jz      short loc_18003EF85
0x18003ef61  xor     ecx, ecx
0x18003ef63  call    __scrt_initialize_onexit_tables
0x18003ef68  test    al, al
0x18003ef6a  jz      short loc_18003EF85
0x18003ef6c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x18003ef73  call    atexit
0x18003ef78  mov     rbx, [rsp+28h+arg_0]
0x18003ef7d  xor     eax, eax
0x18003ef7f  add     rsp, 20h
0x18003ef83  pop     rdi
0x18003ef84  retn
0x18003ef85  mov     ecx, 7
0x18003ef8a  call    __scrt_fastfail
```
