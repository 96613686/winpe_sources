# __scrt_initialize_thread_safe_statics

- ea: `0x14000f970`
- end: `0x14000fa40`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x14000f744`
- `0x14000f914`
- `0x14000f970`
- `0x140010104`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000f9c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000f9d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000f9c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000f9d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000f993`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000f9a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000f993`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000f9a8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000f9ff`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000f9ff`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x14000f986`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x14000f986`

## string_xrefs

- `0x14000f98c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x14000f9a1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_14009D428, 0xFA0u);
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
    qword_14009D450 = (__int64)ProcAddress;
    qword_14009D458 = (__int64)v2;
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
0x14000f970  mov     [rsp+arg_0], rbx
0x14000f975  push    rdi
0x14000f976  sub     rsp, 20h
0x14000f97a  mov     edx, 0FA0h; dwSpinCount
0x14000f97f  lea     rcx, stru_14009D428; lpCriticalSection
0x14000f986  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x14000f98c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x14000f993  call    cs:__imp_GetModuleHandleW
0x14000f999  mov     rbx, rax
0x14000f99c  test    rax, rax
0x14000f99f  jnz     short loc_14000F9B6
0x14000f9a1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x14000f9a8  call    cs:__imp_GetModuleHandleW
0x14000f9ae  mov     rbx, rax
0x14000f9b1  test    rax, rax
0x14000f9b4  jz      short loc_14000FA35
0x14000f9b6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x14000f9bd  mov     rcx, rbx; hModule
0x14000f9c0  call    cs:__imp_GetProcAddress
0x14000f9c6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x14000f9cd  mov     rcx, rbx; hModule
0x14000f9d0  mov     rdi, rax
0x14000f9d3  call    cs:__imp_GetProcAddress
0x14000f9d9  test    rdi, rdi
0x14000f9dc  jz      short loc_14000F9F3
0x14000f9de  test    rax, rax
0x14000f9e1  jz      short loc_14000F9F3
0x14000f9e3  mov     cs:qword_14009D450, rdi
0x14000f9ea  mov     cs:qword_14009D458, rax
0x14000f9f1  jmp     short loc_14000FA11
0x14000f9f3  xor     r9d, r9d; lpName
0x14000f9f6  xor     r8d, r8d; bInitialState
0x14000f9f9  xor     ecx, ecx; lpEventAttributes
0x14000f9fb  lea     edx, [r9+1]; bManualReset
0x14000f9ff  call    cs:__imp_CreateEventW
0x14000fa05  mov     cs:hHandle, rax
0x14000fa0c  test    rax, rax
0x14000fa0f  jz      short loc_14000FA35
0x14000fa11  xor     ecx, ecx
0x14000fa13  call    __scrt_initialize_onexit_tables
0x14000fa18  test    al, al
0x14000fa1a  jz      short loc_14000FA35
0x14000fa1c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x14000fa23  call    atexit
0x14000fa28  mov     rbx, [rsp+28h+arg_0]
0x14000fa2d  xor     eax, eax
0x14000fa2f  add     rsp, 20h
0x14000fa33  pop     rdi
0x14000fa34  retn
0x14000fa35  mov     ecx, 7
0x14000fa3a  call    __scrt_fastfail
```
