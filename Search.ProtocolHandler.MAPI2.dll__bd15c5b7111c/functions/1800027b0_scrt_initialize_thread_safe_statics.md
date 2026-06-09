# __scrt_initialize_thread_safe_statics

- ea: `0x1800027b0`
- end: `0x180002880`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180002524`
- `0x1800026f4`
- `0x1800027b0`
- `0x180002b7c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002800`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002813`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002800`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002813`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800027d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800027e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800027d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800027e8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000283f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000283f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800027c6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800027c6`

## string_xrefs

- `0x1800027cc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800027e1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_180059B28, 0xFA0u);
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
    qword_180059B50 = (__int64)ProcAddress;
    qword_180059B58 = (__int64)v2;
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
0x1800027b0  mov     [rsp+arg_0], rbx
0x1800027b5  push    rdi
0x1800027b6  sub     rsp, 20h
0x1800027ba  mov     edx, 0FA0h; dwSpinCount
0x1800027bf  lea     rcx, stru_180059B28; lpCriticalSection
0x1800027c6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800027cc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x1800027d3  call    cs:__imp_GetModuleHandleW
0x1800027d9  mov     rbx, rax
0x1800027dc  test    rax, rax
0x1800027df  jnz     short loc_1800027F6
0x1800027e1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800027e8  call    cs:__imp_GetModuleHandleW
0x1800027ee  mov     rbx, rax
0x1800027f1  test    rax, rax
0x1800027f4  jz      short loc_180002875
0x1800027f6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1800027fd  mov     rcx, rbx; hModule
0x180002800  call    cs:__imp_GetProcAddress
0x180002806  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000280d  mov     rcx, rbx; hModule
0x180002810  mov     rdi, rax
0x180002813  call    cs:__imp_GetProcAddress
0x180002819  test    rdi, rdi
0x18000281c  jz      short loc_180002833
0x18000281e  test    rax, rax
0x180002821  jz      short loc_180002833
0x180002823  mov     cs:qword_180059B50, rdi
0x18000282a  mov     cs:qword_180059B58, rax
0x180002831  jmp     short loc_180002851
0x180002833  xor     r9d, r9d; lpName
0x180002836  xor     r8d, r8d; bInitialState
0x180002839  xor     ecx, ecx; lpEventAttributes
0x18000283b  lea     edx, [r9+1]; bManualReset
0x18000283f  call    cs:__imp_CreateEventW
0x180002845  mov     cs:hHandle, rax
0x18000284c  test    rax, rax
0x18000284f  jz      short loc_180002875
0x180002851  xor     ecx, ecx
0x180002853  call    __scrt_initialize_onexit_tables
0x180002858  test    al, al
0x18000285a  jz      short loc_180002875
0x18000285c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180002863  call    atexit
0x180002868  mov     rbx, [rsp+28h+arg_0]
0x18000286d  xor     eax, eax
0x18000286f  add     rsp, 20h
0x180002873  pop     rdi
0x180002874  retn
0x180002875  mov     ecx, 7
0x18000287a  call    __scrt_fastfail
```
