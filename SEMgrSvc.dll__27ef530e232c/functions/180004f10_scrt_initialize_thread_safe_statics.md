# __scrt_initialize_thread_safe_statics

- ea: `0x180004f10`
- end: `0x180004fe0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180004c5c`
- `0x180004e2c`
- `0x180004f10`
- `0x180005610`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004f60`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004f73`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004f60`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004f73`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004f33`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004f48`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004f33`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004f48`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004f26`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004f26`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004f9f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004f9f`

## string_xrefs

- `0x180004f2c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180004f41`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1801329E8, 0xFA0u);
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
    qword_180132A10 = (__int64)ProcAddress;
    qword_180132A18 = (__int64)v2;
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
0x180004f10  mov     [rsp+arg_0], rbx
0x180004f15  push    rdi
0x180004f16  sub     rsp, 20h
0x180004f1a  mov     edx, 0FA0h; dwSpinCount
0x180004f1f  lea     rcx, stru_1801329E8; lpCriticalSection
0x180004f26  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180004f2c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180004f33  call    cs:__imp_GetModuleHandleW
0x180004f39  mov     rbx, rax
0x180004f3c  test    rax, rax
0x180004f3f  jnz     short loc_180004F56
0x180004f41  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180004f48  call    cs:__imp_GetModuleHandleW
0x180004f4e  mov     rbx, rax
0x180004f51  test    rax, rax
0x180004f54  jz      short loc_180004FD5
0x180004f56  lea     rdx, ProcName; "SleepConditionVariableCS"
0x180004f5d  mov     rcx, rbx; hModule
0x180004f60  call    cs:__imp_GetProcAddress
0x180004f66  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180004f6d  mov     rcx, rbx; hModule
0x180004f70  mov     rdi, rax
0x180004f73  call    cs:__imp_GetProcAddress
0x180004f79  test    rdi, rdi
0x180004f7c  jz      short loc_180004F93
0x180004f7e  test    rax, rax
0x180004f81  jz      short loc_180004F93
0x180004f83  mov     cs:qword_180132A10, rdi
0x180004f8a  mov     cs:qword_180132A18, rax
0x180004f91  jmp     short loc_180004FB1
0x180004f93  xor     r9d, r9d; lpName
0x180004f96  xor     r8d, r8d; bInitialState
0x180004f99  xor     ecx, ecx; lpEventAttributes
0x180004f9b  lea     edx, [r9+1]; bManualReset
0x180004f9f  call    cs:__imp_CreateEventW
0x180004fa5  mov     cs:hHandle, rax
0x180004fac  test    rax, rax
0x180004faf  jz      short loc_180004FD5
0x180004fb1  xor     ecx, ecx
0x180004fb3  call    __scrt_initialize_onexit_tables
0x180004fb8  test    al, al
0x180004fba  jz      short loc_180004FD5
0x180004fbc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180004fc3  call    atexit
0x180004fc8  mov     rbx, [rsp+28h+arg_0]
0x180004fcd  xor     eax, eax
0x180004fcf  add     rsp, 20h
0x180004fd3  pop     rdi
0x180004fd4  retn
0x180004fd5  mov     ecx, 7
0x180004fda  call    __scrt_fastfail
```
