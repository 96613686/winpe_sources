# __scrt_initialize_thread_safe_statics

- ea: `0x180002ef0`
- end: `0x180002fc0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180002cb4`
- `0x180002e84`
- `0x180002ef0`
- `0x1800035fc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002f40`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002f53`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002f40`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002f53`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002f13`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002f28`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002f13`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002f28`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180002f06`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180002f06`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002f7f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002f7f`

## string_xrefs

- `0x180002f0c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180002f21`: `kernel32.dll`

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
    qword_180039358 = (__int64)ProcAddress;
    qword_180039360 = (__int64)v2;
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
0x180002ef0  mov     [rsp+arg_0], rbx
0x180002ef5  push    rdi
0x180002ef6  sub     rsp, 20h
0x180002efa  mov     edx, 0FA0h; dwSpinCount
0x180002eff  lea     rcx, CriticalSection; lpCriticalSection
0x180002f06  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180002f0c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180002f13  call    cs:__imp_GetModuleHandleW
0x180002f19  mov     rbx, rax
0x180002f1c  test    rax, rax
0x180002f1f  jnz     short loc_180002F36
0x180002f21  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180002f28  call    cs:__imp_GetModuleHandleW
0x180002f2e  mov     rbx, rax
0x180002f31  test    rax, rax
0x180002f34  jz      short loc_180002FB5
0x180002f36  lea     rdx, ProcName; "SleepConditionVariableCS"
0x180002f3d  mov     rcx, rbx; hModule
0x180002f40  call    cs:__imp_GetProcAddress
0x180002f46  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180002f4d  mov     rcx, rbx; hModule
0x180002f50  mov     rdi, rax
0x180002f53  call    cs:__imp_GetProcAddress
0x180002f59  test    rdi, rdi
0x180002f5c  jz      short loc_180002F73
0x180002f5e  test    rax, rax
0x180002f61  jz      short loc_180002F73
0x180002f63  mov     cs:qword_180039358, rdi
0x180002f6a  mov     cs:qword_180039360, rax
0x180002f71  jmp     short loc_180002F91
0x180002f73  xor     r9d, r9d; lpName
0x180002f76  xor     r8d, r8d; bInitialState
0x180002f79  xor     ecx, ecx; lpEventAttributes
0x180002f7b  lea     edx, [r9+1]; bManualReset
0x180002f7f  call    cs:__imp_CreateEventW
0x180002f85  mov     cs:hHandle, rax
0x180002f8c  test    rax, rax
0x180002f8f  jz      short loc_180002FB5
0x180002f91  xor     ecx, ecx
0x180002f93  call    __scrt_initialize_onexit_tables
0x180002f98  test    al, al
0x180002f9a  jz      short loc_180002FB5
0x180002f9c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180002fa3  call    atexit
0x180002fa8  mov     rbx, [rsp+28h+arg_0]
0x180002fad  xor     eax, eax
0x180002faf  add     rsp, 20h
0x180002fb3  pop     rdi
0x180002fb4  retn
0x180002fb5  mov     ecx, 7
0x180002fba  call    __scrt_fastfail
```
