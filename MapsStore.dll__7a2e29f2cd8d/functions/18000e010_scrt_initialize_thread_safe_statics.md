# __scrt_initialize_thread_safe_statics

- ea: `0x18000e010`
- end: `0x18000e0e0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000d270`
- `0x18000d440`
- `0x18000d9f0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e033`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e048`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e033`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e048`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e060`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e073`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e060`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e073`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000e026`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000e026`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e09f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e09f`

## string_xrefs

- `0x18000e02c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18000e041`: `kernel32.dll`

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
    qword_1800F11B0 = (__int64)ProcAddress;
    qword_1800F11B8 = (__int64)v2;
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
0x18000e010  mov     [rsp+arg_0], rbx
0x18000e015  push    rdi
0x18000e016  sub     rsp, 20h
0x18000e01a  mov     edx, 0FA0h; dwSpinCount
0x18000e01f  lea     rcx, CriticalSection; lpCriticalSection
0x18000e026  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000e02c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x18000e033  call    cs:__imp_GetModuleHandleW
0x18000e039  mov     rbx, rax
0x18000e03c  test    rax, rax
0x18000e03f  jnz     short loc_18000E056
0x18000e041  lea     rcx, aKernel32Dll; "kernel32.dll"
0x18000e048  call    cs:__imp_GetModuleHandleW
0x18000e04e  mov     rbx, rax
0x18000e051  test    rax, rax
0x18000e054  jz      short loc_18000E0D5
0x18000e056  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000e05d  mov     rcx, rbx; hModule
0x18000e060  call    cs:__imp_GetProcAddress
0x18000e066  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000e06d  mov     rcx, rbx; hModule
0x18000e070  mov     rdi, rax
0x18000e073  call    cs:__imp_GetProcAddress
0x18000e079  test    rdi, rdi
0x18000e07c  jz      short loc_18000E093
0x18000e07e  test    rax, rax
0x18000e081  jz      short loc_18000E093
0x18000e083  mov     cs:qword_1800F11B0, rdi
0x18000e08a  mov     cs:qword_1800F11B8, rax
0x18000e091  jmp     short loc_18000E0B1
0x18000e093  xor     r9d, r9d; lpName
0x18000e096  xor     r8d, r8d; bInitialState
0x18000e099  xor     ecx, ecx; lpEventAttributes
0x18000e09b  lea     edx, [r9+1]; bManualReset
0x18000e09f  call    cs:__imp_CreateEventW
0x18000e0a5  mov     cs:hHandle, rax
0x18000e0ac  test    rax, rax
0x18000e0af  jz      short loc_18000E0D5
0x18000e0b1  xor     ecx, ecx
0x18000e0b3  call    __scrt_initialize_onexit_tables
0x18000e0b8  test    al, al
0x18000e0ba  jz      short loc_18000E0D5
0x18000e0bc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x18000e0c3  call    atexit
0x18000e0c8  mov     rbx, [rsp+28h+arg_0]
0x18000e0cd  xor     eax, eax
0x18000e0cf  add     rsp, 20h
0x18000e0d3  pop     rdi
0x18000e0d4  retn
0x18000e0d5  mov     ecx, 7
0x18000e0da  call    __scrt_fastfail
```
