# __scrt_initialize_thread_safe_statics

- ea: `0x180031ee0`
- end: `0x180031fb0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180031c10`
- `0x180031de0`
- `0x180031ee0`
- `0x1800325b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180031f03`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180031f18`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180031f03`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180031f18`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031f30`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031f43`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031f30`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031f43`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180031f6f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180031f6f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180031ef6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180031ef6`

## string_xrefs

- `0x180031efc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180031f11`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_180063F28, 0xFA0u);
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
    qword_180063F50 = (__int64)ProcAddress;
    qword_180063F58 = (__int64)v2;
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
0x180031ee0  mov     [rsp+arg_0], rbx
0x180031ee5  push    rdi
0x180031ee6  sub     rsp, 20h
0x180031eea  mov     edx, 0FA0h; dwSpinCount
0x180031eef  lea     rcx, stru_180063F28; lpCriticalSection
0x180031ef6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180031efc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180031f03  call    cs:__imp_GetModuleHandleW
0x180031f09  mov     rbx, rax
0x180031f0c  test    rax, rax
0x180031f0f  jnz     short loc_180031F26
0x180031f11  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180031f18  call    cs:__imp_GetModuleHandleW
0x180031f1e  mov     rbx, rax
0x180031f21  test    rax, rax
0x180031f24  jz      short loc_180031FA5
0x180031f26  lea     rdx, ProcName; "SleepConditionVariableCS"
0x180031f2d  mov     rcx, rbx; hModule
0x180031f30  call    cs:__imp_GetProcAddress
0x180031f36  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180031f3d  mov     rcx, rbx; hModule
0x180031f40  mov     rdi, rax
0x180031f43  call    cs:__imp_GetProcAddress
0x180031f49  test    rdi, rdi
0x180031f4c  jz      short loc_180031F63
0x180031f4e  test    rax, rax
0x180031f51  jz      short loc_180031F63
0x180031f53  mov     cs:qword_180063F50, rdi
0x180031f5a  mov     cs:qword_180063F58, rax
0x180031f61  jmp     short loc_180031F81
0x180031f63  xor     r9d, r9d; lpName
0x180031f66  xor     r8d, r8d; bInitialState
0x180031f69  xor     ecx, ecx; lpEventAttributes
0x180031f6b  lea     edx, [r9+1]; bManualReset
0x180031f6f  call    cs:__imp_CreateEventW
0x180031f75  mov     cs:hHandle, rax
0x180031f7c  test    rax, rax
0x180031f7f  jz      short loc_180031FA5
0x180031f81  xor     ecx, ecx
0x180031f83  call    __scrt_initialize_onexit_tables
0x180031f88  test    al, al
0x180031f8a  jz      short loc_180031FA5
0x180031f8c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180031f93  call    atexit
0x180031f98  mov     rbx, [rsp+28h+arg_0]
0x180031f9d  xor     eax, eax
0x180031f9f  add     rsp, 20h
0x180031fa3  pop     rdi
0x180031fa4  retn
0x180031fa5  mov     ecx, 7
0x180031faa  call    __scrt_fastfail
```
