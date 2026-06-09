# __scrt_initialize_thread_safe_statics

- ea: `0x180040360`
- end: `0x180040430`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18003e3fc`
- `0x18003e5cc`
- `0x18003e754`
- `0x180040360`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800403b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800403c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800403b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800403c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180040383`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180040398`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180040383`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180040398`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180040376`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180040376`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800403ef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800403ef`

## string_xrefs

- `0x18004037c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180040391`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1800A4418, 0xFA0u);
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
    qword_1800A4440 = (__int64)ProcAddress;
    qword_1800A4448 = (__int64)v2;
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
0x180040360  mov     [rsp+arg_0], rbx
0x180040365  push    rdi
0x180040366  sub     rsp, 20h
0x18004036a  mov     edx, 0FA0h; dwSpinCount
0x18004036f  lea     rcx, stru_1800A4418; lpCriticalSection
0x180040376  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18004037c  lea     rcx, aApiMsWinCoreSy_4; "api-ms-win-core-synch-l1-2-0.dll"
0x180040383  call    cs:__imp_GetModuleHandleW
0x180040389  mov     rbx, rax
0x18004038c  test    rax, rax
0x18004038f  jnz     short loc_1800403A6
0x180040391  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180040398  call    cs:__imp_GetModuleHandleW
0x18004039e  mov     rbx, rax
0x1800403a1  test    rax, rax
0x1800403a4  jz      short loc_180040425
0x1800403a6  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x1800403ad  mov     rcx, rbx; hModule
0x1800403b0  call    cs:__imp_GetProcAddress
0x1800403b6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800403bd  mov     rcx, rbx; hModule
0x1800403c0  mov     rdi, rax
0x1800403c3  call    cs:__imp_GetProcAddress
0x1800403c9  test    rdi, rdi
0x1800403cc  jz      short loc_1800403E3
0x1800403ce  test    rax, rax
0x1800403d1  jz      short loc_1800403E3
0x1800403d3  mov     cs:qword_1800A4440, rdi
0x1800403da  mov     cs:qword_1800A4448, rax
0x1800403e1  jmp     short loc_180040401
0x1800403e3  xor     r9d, r9d; lpName
0x1800403e6  xor     r8d, r8d; bInitialState
0x1800403e9  xor     ecx, ecx; lpEventAttributes
0x1800403eb  lea     edx, [r9+1]; bManualReset
0x1800403ef  call    cs:__imp_CreateEventW
0x1800403f5  mov     cs:hHandle, rax
0x1800403fc  test    rax, rax
0x1800403ff  jz      short loc_180040425
0x180040401  xor     ecx, ecx
0x180040403  call    __scrt_initialize_onexit_tables
0x180040408  test    al, al
0x18004040a  jz      short loc_180040425
0x18004040c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180040413  call    atexit
0x180040418  mov     rbx, [rsp+28h+arg_0]
0x18004041d  xor     eax, eax
0x18004041f  add     rsp, 20h
0x180040423  pop     rdi
0x180040424  retn
0x180040425  mov     ecx, 7
0x18004042a  call    __scrt_fastfail
```
