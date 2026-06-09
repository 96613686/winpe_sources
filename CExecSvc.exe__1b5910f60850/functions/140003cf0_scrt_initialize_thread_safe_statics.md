# __scrt_initialize_thread_safe_statics

- ea: `0x140003cf0`
- end: `0x140003dc0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1400024c8`
- `0x140002698`
- `0x140002858`
- `0x140003cf0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003d40`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003d53`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003d40`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003d53`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140003d13`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140003d28`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140003d13`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140003d28`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140003d7f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140003d7f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140003d06`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140003d06`

## string_xrefs

- `0x140003d0c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x140003d21`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_140039DB8, 0xFA0u);
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
    qword_140039DE0 = (__int64)ProcAddress;
    qword_140039DE8 = (__int64)v2;
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
0x140003cf0  mov     [rsp+arg_0], rbx
0x140003cf5  push    rdi
0x140003cf6  sub     rsp, 20h
0x140003cfa  mov     edx, 0FA0h; dwSpinCount
0x140003cff  lea     rcx, stru_140039DB8; lpCriticalSection
0x140003d06  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x140003d0c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x140003d13  call    cs:__imp_GetModuleHandleW
0x140003d19  mov     rbx, rax
0x140003d1c  test    rax, rax
0x140003d1f  jnz     short loc_140003D36
0x140003d21  lea     rcx, aKernel32Dll; "kernel32.dll"
0x140003d28  call    cs:__imp_GetModuleHandleW
0x140003d2e  mov     rbx, rax
0x140003d31  test    rax, rax
0x140003d34  jz      short loc_140003DB5
0x140003d36  lea     rdx, ProcName; "SleepConditionVariableCS"
0x140003d3d  mov     rcx, rbx; hModule
0x140003d40  call    cs:__imp_GetProcAddress
0x140003d46  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x140003d4d  mov     rcx, rbx; hModule
0x140003d50  mov     rdi, rax
0x140003d53  call    cs:__imp_GetProcAddress
0x140003d59  test    rdi, rdi
0x140003d5c  jz      short loc_140003D73
0x140003d5e  test    rax, rax
0x140003d61  jz      short loc_140003D73
0x140003d63  mov     cs:qword_140039DE0, rdi
0x140003d6a  mov     cs:qword_140039DE8, rax
0x140003d71  jmp     short loc_140003D91
0x140003d73  xor     r9d, r9d; lpName
0x140003d76  xor     r8d, r8d; bInitialState
0x140003d79  xor     ecx, ecx; lpEventAttributes
0x140003d7b  lea     edx, [r9+1]; bManualReset
0x140003d7f  call    cs:__imp_CreateEventW
0x140003d85  mov     cs:hHandle, rax
0x140003d8c  test    rax, rax
0x140003d8f  jz      short loc_140003DB5
0x140003d91  xor     ecx, ecx
0x140003d93  call    __scrt_initialize_onexit_tables
0x140003d98  test    al, al
0x140003d9a  jz      short loc_140003DB5
0x140003d9c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x140003da3  call    atexit
0x140003da8  mov     rbx, [rsp+28h+arg_0]
0x140003dad  xor     eax, eax
0x140003daf  add     rsp, 20h
0x140003db3  pop     rdi
0x140003db4  retn
0x140003db5  mov     ecx, 7
0x140003dba  call    __scrt_fastfail
```
