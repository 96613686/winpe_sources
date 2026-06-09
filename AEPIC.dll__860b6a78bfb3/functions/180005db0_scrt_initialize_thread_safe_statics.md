# __scrt_initialize_thread_safe_statics

- ea: `0x180005db0`
- end: `0x180005e80`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180005b40`
- `0x180005d10`
- `0x180005db0`
- `0x180006638`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005dd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005de8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005dd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005de8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005e00`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005e13`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005e00`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005e13`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180005dc6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180005dc6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180005e3f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180005e3f`

## string_xrefs

- `0x180005dcc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180005de1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_180121168, 0xFA0u);
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
    qword_180121190 = (__int64)ProcAddress;
    qword_180121198 = (__int64)v2;
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
0x180005db0  mov     [rsp+arg_0], rbx
0x180005db5  push    rdi
0x180005db6  sub     rsp, 20h
0x180005dba  mov     edx, 0FA0h; dwSpinCount
0x180005dbf  lea     rcx, stru_180121168; lpCriticalSection
0x180005dc6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180005dcc  lea     rcx, aApiMsWinCoreSy_3; "api-ms-win-core-synch-l1-2-0.dll"
0x180005dd3  call    cs:__imp_GetModuleHandleW
0x180005dd9  mov     rbx, rax
0x180005ddc  test    rax, rax
0x180005ddf  jnz     short loc_180005DF6
0x180005de1  lea     rcx, SourceString; "kernel32.dll"
0x180005de8  call    cs:__imp_GetModuleHandleW
0x180005dee  mov     rbx, rax
0x180005df1  test    rax, rax
0x180005df4  jz      short loc_180005E75
0x180005df6  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x180005dfd  mov     rcx, rbx; hModule
0x180005e00  call    cs:__imp_GetProcAddress
0x180005e06  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180005e0d  mov     rcx, rbx; hModule
0x180005e10  mov     rdi, rax
0x180005e13  call    cs:__imp_GetProcAddress
0x180005e19  test    rdi, rdi
0x180005e1c  jz      short loc_180005E33
0x180005e1e  test    rax, rax
0x180005e21  jz      short loc_180005E33
0x180005e23  mov     cs:qword_180121190, rdi
0x180005e2a  mov     cs:qword_180121198, rax
0x180005e31  jmp     short loc_180005E51
0x180005e33  xor     r9d, r9d; lpName
0x180005e36  xor     r8d, r8d; bInitialState
0x180005e39  xor     ecx, ecx; lpEventAttributes
0x180005e3b  lea     edx, [r9+1]; bManualReset
0x180005e3f  call    cs:__imp_CreateEventW
0x180005e45  mov     cs:hHandle, rax
0x180005e4c  test    rax, rax
0x180005e4f  jz      short loc_180005E75
0x180005e51  xor     ecx, ecx
0x180005e53  call    __scrt_initialize_onexit_tables
0x180005e58  test    al, al
0x180005e5a  jz      short loc_180005E75
0x180005e5c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180005e63  call    atexit
0x180005e68  mov     rbx, [rsp+28h+arg_0]
0x180005e6d  xor     eax, eax
0x180005e6f  add     rsp, 20h
0x180005e73  pop     rdi
0x180005e74  retn
0x180005e75  mov     ecx, 7
0x180005e7a  call    __scrt_fastfail
```
