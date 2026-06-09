# __scrt_initialize_thread_safe_statics

- ea: `0x1800f7320`
- end: `0x1800f73f0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800f70fc`
- `0x1800f72cc`
- `0x1800f7320`
- `0x1800f790c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800f7370`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800f7383`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800f7370`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800f7383`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800f7343`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800f7358`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800f7343`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800f7358`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800f7336`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800f7336`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f73af`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f73af`

## string_xrefs

- `0x1800f7351`: `kernel32.dll`
- `0x1800f733c`: `api-ms-win-core-synch-l1-2-0.dll`

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
    qword_1801DD018 = (__int64)ProcAddress;
    qword_1801DD020 = (__int64)v2;
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
0x1800f7320  mov     [rsp+arg_0], rbx
0x1800f7325  push    rdi
0x1800f7326  sub     rsp, 20h
0x1800f732a  mov     edx, 0FA0h; dwSpinCount
0x1800f732f  lea     rcx, CriticalSection; lpCriticalSection
0x1800f7336  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800f733c  lea     rcx, aApiMsWinCoreSy_4; "api-ms-win-core-synch-l1-2-0.dll"
0x1800f7343  call    cs:__imp_GetModuleHandleW
0x1800f7349  mov     rbx, rax
0x1800f734c  test    rax, rax
0x1800f734f  jnz     short loc_1800F7366
0x1800f7351  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800f7358  call    cs:__imp_GetModuleHandleW
0x1800f735e  mov     rbx, rax
0x1800f7361  test    rax, rax
0x1800f7364  jz      short loc_1800F73E5
0x1800f7366  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x1800f736d  mov     rcx, rbx; hModule
0x1800f7370  call    cs:__imp_GetProcAddress
0x1800f7376  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800f737d  mov     rcx, rbx; hModule
0x1800f7380  mov     rdi, rax
0x1800f7383  call    cs:__imp_GetProcAddress
0x1800f7389  test    rdi, rdi
0x1800f738c  jz      short loc_1800F73A3
0x1800f738e  test    rax, rax
0x1800f7391  jz      short loc_1800F73A3
0x1800f7393  mov     cs:qword_1801DD018, rdi
0x1800f739a  mov     cs:qword_1801DD020, rax
0x1800f73a1  jmp     short loc_1800F73C1
0x1800f73a3  xor     r9d, r9d; lpName
0x1800f73a6  xor     r8d, r8d; bInitialState
0x1800f73a9  xor     ecx, ecx; lpEventAttributes
0x1800f73ab  lea     edx, [r9+1]; bManualReset
0x1800f73af  call    cs:__imp_CreateEventW
0x1800f73b5  mov     cs:hHandle, rax
0x1800f73bc  test    rax, rax
0x1800f73bf  jz      short loc_1800F73E5
0x1800f73c1  xor     ecx, ecx
0x1800f73c3  call    __scrt_initialize_onexit_tables
0x1800f73c8  test    al, al
0x1800f73ca  jz      short loc_1800F73E5
0x1800f73cc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800f73d3  call    atexit
0x1800f73d8  mov     rbx, [rsp+28h+arg_0]
0x1800f73dd  xor     eax, eax
0x1800f73df  add     rsp, 20h
0x1800f73e3  pop     rdi
0x1800f73e4  retn
0x1800f73e5  mov     ecx, 7
0x1800f73ea  call    __scrt_fastfail
```
