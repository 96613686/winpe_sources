# __scrt_initialize_thread_safe_statics

- ea: `0x180002bb0`
- end: `0x180002c80`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001fb0`
- `0x180002180`
- `0x180002470`
- `0x180002bb0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002bd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002be8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002bd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002be8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002c00`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002c13`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002c00`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002c13`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002c3f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002c3f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180002bc6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180002bc6`

## string_xrefs

- `0x180002bcc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180002be1`: `kernel32.dll`

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
    qword_180076B90 = (__int64)ProcAddress;
    qword_180076B98 = (__int64)v2;
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
0x180002bb0  mov     [rsp+arg_0], rbx
0x180002bb5  push    rdi
0x180002bb6  sub     rsp, 20h
0x180002bba  mov     edx, 0FA0h; dwSpinCount
0x180002bbf  lea     rcx, CriticalSection; lpCriticalSection
0x180002bc6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180002bcc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180002bd3  call    cs:__imp_GetModuleHandleW
0x180002bd9  mov     rbx, rax
0x180002bdc  test    rax, rax
0x180002bdf  jnz     short loc_180002BF6
0x180002be1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180002be8  call    cs:__imp_GetModuleHandleW
0x180002bee  mov     rbx, rax
0x180002bf1  test    rax, rax
0x180002bf4  jz      short loc_180002C75
0x180002bf6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x180002bfd  mov     rcx, rbx; hModule
0x180002c00  call    cs:__imp_GetProcAddress
0x180002c06  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180002c0d  mov     rcx, rbx; hModule
0x180002c10  mov     rdi, rax
0x180002c13  call    cs:__imp_GetProcAddress
0x180002c19  test    rdi, rdi
0x180002c1c  jz      short loc_180002C33
0x180002c1e  test    rax, rax
0x180002c21  jz      short loc_180002C33
0x180002c23  mov     cs:qword_180076B90, rdi
0x180002c2a  mov     cs:qword_180076B98, rax
0x180002c31  jmp     short loc_180002C51
0x180002c33  xor     r9d, r9d; lpName
0x180002c36  xor     r8d, r8d; bInitialState
0x180002c39  xor     ecx, ecx; lpEventAttributes
0x180002c3b  lea     edx, [r9+1]; bManualReset
0x180002c3f  call    cs:__imp_CreateEventW
0x180002c45  mov     cs:hHandle, rax
0x180002c4c  test    rax, rax
0x180002c4f  jz      short loc_180002C75
0x180002c51  xor     ecx, ecx
0x180002c53  call    __scrt_initialize_onexit_tables
0x180002c58  test    al, al
0x180002c5a  jz      short loc_180002C75
0x180002c5c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180002c63  call    atexit
0x180002c68  mov     rbx, [rsp+28h+arg_0]
0x180002c6d  xor     eax, eax
0x180002c6f  add     rsp, 20h
0x180002c73  pop     rdi
0x180002c74  retn
0x180002c75  mov     ecx, 7
0x180002c7a  call    __scrt_fastfail
```
