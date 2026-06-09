# __scrt_initialize_thread_safe_statics

- ea: `0x1800027c0`
- end: `0x180002890`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001b40`
- `0x180001d10`
- `0x180001e84`
- `0x1800027c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002810`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002823`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002810`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002823`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800027e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800027f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800027e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800027f8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000284f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000284f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800027d6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800027d6`

## string_xrefs

- `0x1800027dc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800027f1`: `kernel32.dll`

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
    qword_18001A500 = (__int64)ProcAddress;
    qword_18001A508 = (__int64)v2;
  }
  else
  {
    hObject = CreateEventW(0, 1, 0, 0);
    if ( !hObject )
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
0x1800027c0  mov     [rsp+arg_0], rbx
0x1800027c5  push    rdi
0x1800027c6  sub     rsp, 20h
0x1800027ca  mov     edx, 0FA0h; dwSpinCount
0x1800027cf  lea     rcx, CriticalSection; lpCriticalSection
0x1800027d6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800027dc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x1800027e3  call    cs:__imp_GetModuleHandleW
0x1800027e9  mov     rbx, rax
0x1800027ec  test    rax, rax
0x1800027ef  jnz     short loc_180002806
0x1800027f1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800027f8  call    cs:__imp_GetModuleHandleW
0x1800027fe  mov     rbx, rax
0x180002801  test    rax, rax
0x180002804  jz      short loc_180002885
0x180002806  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000280d  mov     rcx, rbx; hModule
0x180002810  call    cs:__imp_GetProcAddress
0x180002816  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000281d  mov     rcx, rbx; hModule
0x180002820  mov     rdi, rax
0x180002823  call    cs:__imp_GetProcAddress
0x180002829  test    rdi, rdi
0x18000282c  jz      short loc_180002843
0x18000282e  test    rax, rax
0x180002831  jz      short loc_180002843
0x180002833  mov     cs:qword_18001A500, rdi
0x18000283a  mov     cs:qword_18001A508, rax
0x180002841  jmp     short loc_180002861
0x180002843  xor     r9d, r9d; lpName
0x180002846  xor     r8d, r8d; bInitialState
0x180002849  xor     ecx, ecx; lpEventAttributes
0x18000284b  lea     edx, [r9+1]; bManualReset
0x18000284f  call    cs:__imp_CreateEventW
0x180002855  mov     cs:hObject, rax
0x18000285c  test    rax, rax
0x18000285f  jz      short loc_180002885
0x180002861  xor     ecx, ecx
0x180002863  call    __scrt_initialize_onexit_tables
0x180002868  test    al, al
0x18000286a  jz      short loc_180002885
0x18000286c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180002873  call    atexit
0x180002878  mov     rbx, [rsp+28h+arg_0]
0x18000287d  xor     eax, eax
0x18000287f  add     rsp, 20h
0x180002883  pop     rdi
0x180002884  retn
0x180002885  mov     ecx, 7
0x18000288a  call    __scrt_fastfail
```
