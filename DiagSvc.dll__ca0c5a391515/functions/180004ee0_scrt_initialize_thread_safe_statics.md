# __scrt_initialize_thread_safe_statics

- ea: `0x180004ee0`
- end: `0x180004fb0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000427c`
- `0x18000444c`
- `0x18000460c`
- `0x180004ee0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004f03`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004f18`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004f03`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004f18`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004f30`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004f43`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004f30`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004f43`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004f6f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004f6f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004ef6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004ef6`

## string_xrefs

- `0x180004efc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180004f11`: `kernel32.dll`

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
    qword_180039860 = (__int64)ProcAddress;
    qword_180039868 = (__int64)v2;
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
0x180004ee0  mov     [rsp+arg_0], rbx
0x180004ee5  push    rdi
0x180004ee6  sub     rsp, 20h
0x180004eea  mov     edx, 0FA0h; dwSpinCount
0x180004eef  lea     rcx, CriticalSection; lpCriticalSection
0x180004ef6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180004efc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180004f03  call    cs:__imp_GetModuleHandleW
0x180004f09  mov     rbx, rax
0x180004f0c  test    rax, rax
0x180004f0f  jnz     short loc_180004F26
0x180004f11  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180004f18  call    cs:__imp_GetModuleHandleW
0x180004f1e  mov     rbx, rax
0x180004f21  test    rax, rax
0x180004f24  jz      short loc_180004FA5
0x180004f26  lea     rdx, ProcName; "SleepConditionVariableCS"
0x180004f2d  mov     rcx, rbx; hModule
0x180004f30  call    cs:__imp_GetProcAddress
0x180004f36  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180004f3d  mov     rcx, rbx; hModule
0x180004f40  mov     rdi, rax
0x180004f43  call    cs:__imp_GetProcAddress
0x180004f49  test    rdi, rdi
0x180004f4c  jz      short loc_180004F63
0x180004f4e  test    rax, rax
0x180004f51  jz      short loc_180004F63
0x180004f53  mov     cs:qword_180039860, rdi
0x180004f5a  mov     cs:qword_180039868, rax
0x180004f61  jmp     short loc_180004F81
0x180004f63  xor     r9d, r9d; lpName
0x180004f66  xor     r8d, r8d; bInitialState
0x180004f69  xor     ecx, ecx; lpEventAttributes
0x180004f6b  lea     edx, [r9+1]; bManualReset
0x180004f6f  call    cs:__imp_CreateEventW
0x180004f75  mov     cs:hHandle, rax
0x180004f7c  test    rax, rax
0x180004f7f  jz      short loc_180004FA5
0x180004f81  xor     ecx, ecx
0x180004f83  call    __scrt_initialize_onexit_tables
0x180004f88  test    al, al
0x180004f8a  jz      short loc_180004FA5
0x180004f8c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180004f93  call    atexit
0x180004f98  mov     rbx, [rsp+28h+arg_0]
0x180004f9d  xor     eax, eax
0x180004f9f  add     rsp, 20h
0x180004fa3  pop     rdi
0x180004fa4  retn
0x180004fa5  mov     ecx, 7
0x180004faa  call    __scrt_fastfail
```
