# __scrt_initialize_thread_safe_statics

- ea: `0x180002720`
- end: `0x1800027f0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001ca0`
- `0x180001e70`
- `0x180002034`
- `0x180002720`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002770`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002783`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002770`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002783`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002743`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002758`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002743`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002758`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180002736`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180002736`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800027af`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800027af`

## string_xrefs

- `0x18000273c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180002751`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_18002F848, 0xFA0u);
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
    qword_18002F870 = (__int64)ProcAddress;
    qword_18002F878 = (__int64)v2;
  }
  else
  {
    hObject = CreateEventW(0, 1, 0, 0);
    if ( !hObject )
      goto LABEL_9;
  }
  if ( !(unsigned __int8)_scrt_initialize_onexit_tables(0) )
LABEL_9:
    _scrt_fastfail(7u);
  atexit(_scrt_uninitialize_thread_safe_statics);
  return 0;
}

```

## disassembly

```asm
0x180002720  mov     [rsp+arg_0], rbx
0x180002725  push    rdi
0x180002726  sub     rsp, 20h
0x18000272a  mov     edx, 0FA0h; dwSpinCount
0x18000272f  lea     rcx, stru_18002F848; lpCriticalSection
0x180002736  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000273c  lea     rcx, aApiMsWinCoreSy_1; "api-ms-win-core-synch-l1-2-0.dll"
0x180002743  call    cs:__imp_GetModuleHandleW
0x180002749  mov     rbx, rax
0x18000274c  test    rax, rax
0x18000274f  jnz     short loc_180002766
0x180002751  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x180002758  call    cs:__imp_GetModuleHandleW
0x18000275e  mov     rbx, rax
0x180002761  test    rax, rax
0x180002764  jz      short loc_1800027E5
0x180002766  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18000276d  mov     rcx, rbx; hModule
0x180002770  call    cs:__imp_GetProcAddress
0x180002776  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000277d  mov     rcx, rbx; hModule
0x180002780  mov     rdi, rax
0x180002783  call    cs:__imp_GetProcAddress
0x180002789  test    rdi, rdi
0x18000278c  jz      short loc_1800027A3
0x18000278e  test    rax, rax
0x180002791  jz      short loc_1800027A3
0x180002793  mov     cs:qword_18002F870, rdi
0x18000279a  mov     cs:qword_18002F878, rax
0x1800027a1  jmp     short loc_1800027C1
0x1800027a3  xor     r9d, r9d; lpName
0x1800027a6  xor     r8d, r8d; bInitialState
0x1800027a9  xor     ecx, ecx; lpEventAttributes
0x1800027ab  lea     edx, [r9+1]; bManualReset
0x1800027af  call    cs:__imp_CreateEventW
0x1800027b5  mov     cs:hObject, rax
0x1800027bc  test    rax, rax
0x1800027bf  jz      short loc_1800027E5
0x1800027c1  xor     ecx, ecx
0x1800027c3  call    __scrt_initialize_onexit_tables
0x1800027c8  test    al, al
0x1800027ca  jz      short loc_1800027E5
0x1800027cc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800027d3  call    atexit
0x1800027d8  mov     rbx, [rsp+28h+arg_0]
0x1800027dd  xor     eax, eax
0x1800027df  add     rsp, 20h
0x1800027e3  pop     rdi
0x1800027e4  retn
0x1800027e5  mov     ecx, 7
0x1800027ea  call    __scrt_fastfail
```
