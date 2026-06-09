# __scrt_initialize_thread_safe_statics

- ea: `0x140009df0`
- end: `0x140009ec0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140008d48`
- `0x140008f18`
- `0x140009070`
- `0x140009df0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140009e13`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140009e28`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140009e13`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140009e28`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009e40`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009e53`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009e40`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009e53`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140009e7f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140009e7f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140009e06`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140009e06`

## string_xrefs

- `0x140009e0c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x140009e21`: `kernel32.dll`

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
    qword_140018480 = (__int64)ProcAddress;
    qword_140018488 = (__int64)v2;
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
0x140009df0  mov     [rsp+arg_0], rbx
0x140009df5  push    rdi
0x140009df6  sub     rsp, 20h
0x140009dfa  mov     edx, 0FA0h; dwSpinCount
0x140009dff  lea     rcx, CriticalSection; lpCriticalSection
0x140009e06  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x140009e0c  lea     rcx, aApiMsWinCoreSy_3; "api-ms-win-core-synch-l1-2-0.dll"
0x140009e13  call    cs:__imp_GetModuleHandleW
0x140009e19  mov     rbx, rax
0x140009e1c  test    rax, rax
0x140009e1f  jnz     short loc_140009E36
0x140009e21  lea     rcx, aKernel32Dll; "kernel32.dll"
0x140009e28  call    cs:__imp_GetModuleHandleW
0x140009e2e  mov     rbx, rax
0x140009e31  test    rax, rax
0x140009e34  jz      short loc_140009EB5
0x140009e36  lea     rdx, ProcName; "SleepConditionVariableCS"
0x140009e3d  mov     rcx, rbx; hModule
0x140009e40  call    cs:__imp_GetProcAddress
0x140009e46  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x140009e4d  mov     rcx, rbx; hModule
0x140009e50  mov     rdi, rax
0x140009e53  call    cs:__imp_GetProcAddress
0x140009e59  test    rdi, rdi
0x140009e5c  jz      short loc_140009E73
0x140009e5e  test    rax, rax
0x140009e61  jz      short loc_140009E73
0x140009e63  mov     cs:qword_140018480, rdi
0x140009e6a  mov     cs:qword_140018488, rax
0x140009e71  jmp     short loc_140009E91
0x140009e73  xor     r9d, r9d; lpName
0x140009e76  xor     r8d, r8d; bInitialState
0x140009e79  xor     ecx, ecx; lpEventAttributes
0x140009e7b  lea     edx, [r9+1]; bManualReset
0x140009e7f  call    cs:__imp_CreateEventW
0x140009e85  mov     cs:hHandle, rax
0x140009e8c  test    rax, rax
0x140009e8f  jz      short loc_140009EB5
0x140009e91  xor     ecx, ecx
0x140009e93  call    __scrt_initialize_onexit_tables
0x140009e98  test    al, al
0x140009e9a  jz      short loc_140009EB5
0x140009e9c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x140009ea3  call    atexit
0x140009ea8  mov     rbx, [rsp+28h+arg_0]
0x140009ead  xor     eax, eax
0x140009eaf  add     rsp, 20h
0x140009eb3  pop     rdi
0x140009eb4  retn
0x140009eb5  mov     ecx, 7
0x140009eba  call    __scrt_fastfail
```
