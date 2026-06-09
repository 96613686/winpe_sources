# __scrt_initialize_thread_safe_statics

- ea: `0x1800097b0`
- end: `0x180009880`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000710c`
- `0x1800072dc`
- `0x180007484`
- `0x1800097b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009800`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009813`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009800`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009813`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800097d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800097e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800097d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800097e8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000983f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000983f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800097c6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800097c6`

## string_xrefs

- `0x1800097cc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800097e1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_180189B78, 0xFA0u);
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
    qword_180189BA0 = (__int64)ProcAddress;
    qword_180189BA8 = (__int64)v2;
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
0x1800097b0  mov     [rsp+arg_0], rbx
0x1800097b5  push    rdi
0x1800097b6  sub     rsp, 20h
0x1800097ba  mov     edx, 0FA0h; dwSpinCount
0x1800097bf  lea     rcx, stru_180189B78; lpCriticalSection
0x1800097c6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800097cc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x1800097d3  call    cs:__imp_GetModuleHandleW
0x1800097d9  mov     rbx, rax
0x1800097dc  test    rax, rax
0x1800097df  jnz     short loc_1800097F6
0x1800097e1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800097e8  call    cs:__imp_GetModuleHandleW
0x1800097ee  mov     rbx, rax
0x1800097f1  test    rax, rax
0x1800097f4  jz      short loc_180009875
0x1800097f6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1800097fd  mov     rcx, rbx; hModule
0x180009800  call    cs:__imp_GetProcAddress
0x180009806  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000980d  mov     rcx, rbx; hModule
0x180009810  mov     rdi, rax
0x180009813  call    cs:__imp_GetProcAddress
0x180009819  test    rdi, rdi
0x18000981c  jz      short loc_180009833
0x18000981e  test    rax, rax
0x180009821  jz      short loc_180009833
0x180009823  mov     cs:qword_180189BA0, rdi
0x18000982a  mov     cs:qword_180189BA8, rax
0x180009831  jmp     short loc_180009851
0x180009833  xor     r9d, r9d; lpName
0x180009836  xor     r8d, r8d; bInitialState
0x180009839  xor     ecx, ecx; lpEventAttributes
0x18000983b  lea     edx, [r9+1]; bManualReset
0x18000983f  call    cs:__imp_CreateEventW
0x180009845  mov     cs:hHandle, rax
0x18000984c  test    rax, rax
0x18000984f  jz      short loc_180009875
0x180009851  xor     ecx, ecx
0x180009853  call    __scrt_initialize_onexit_tables
0x180009858  test    al, al
0x18000985a  jz      short loc_180009875
0x18000985c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180009863  call    atexit
0x180009868  mov     rbx, [rsp+28h+arg_0]
0x18000986d  xor     eax, eax
0x18000986f  add     rsp, 20h
0x180009873  pop     rdi
0x180009874  retn
0x180009875  mov     ecx, 7
0x18000987a  call    __scrt_fastfail
```
