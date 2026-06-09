# __scrt_initialize_thread_safe_statics

- ea: `0x1400032b0`
- end: `0x140003380`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1400026e8`
- `0x1400028b8`
- `0x140002a60`
- `0x1400032b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400032d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400032e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400032d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400032e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003300`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003313`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003300`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003313`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000333f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000333f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1400032c6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1400032c6`

## string_xrefs

- `0x1400032cc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1400032e1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_140030548, 0xFA0u);
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
    qword_140030570 = (__int64)ProcAddress;
    qword_140030578 = (__int64)v2;
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
0x1400032b0  mov     [rsp+arg_0], rbx
0x1400032b5  push    rdi
0x1400032b6  sub     rsp, 20h
0x1400032ba  mov     edx, 0FA0h; dwSpinCount
0x1400032bf  lea     rcx, stru_140030548; lpCriticalSection
0x1400032c6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1400032cc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x1400032d3  call    cs:__imp_GetModuleHandleW
0x1400032d9  mov     rbx, rax
0x1400032dc  test    rax, rax
0x1400032df  jnz     short loc_1400032F6
0x1400032e1  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x1400032e8  call    cs:__imp_GetModuleHandleW
0x1400032ee  mov     rbx, rax
0x1400032f1  test    rax, rax
0x1400032f4  jz      short loc_140003375
0x1400032f6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1400032fd  mov     rcx, rbx; hModule
0x140003300  call    cs:__imp_GetProcAddress
0x140003306  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x14000330d  mov     rcx, rbx; hModule
0x140003310  mov     rdi, rax
0x140003313  call    cs:__imp_GetProcAddress
0x140003319  test    rdi, rdi
0x14000331c  jz      short loc_140003333
0x14000331e  test    rax, rax
0x140003321  jz      short loc_140003333
0x140003323  mov     cs:qword_140030570, rdi
0x14000332a  mov     cs:qword_140030578, rax
0x140003331  jmp     short loc_140003351
0x140003333  xor     r9d, r9d; lpName
0x140003336  xor     r8d, r8d; bInitialState
0x140003339  xor     ecx, ecx; lpEventAttributes
0x14000333b  lea     edx, [r9+1]; bManualReset
0x14000333f  call    cs:__imp_CreateEventW
0x140003345  mov     cs:hHandle, rax
0x14000334c  test    rax, rax
0x14000334f  jz      short loc_140003375
0x140003351  xor     ecx, ecx
0x140003353  call    __scrt_initialize_onexit_tables
0x140003358  test    al, al
0x14000335a  jz      short loc_140003375
0x14000335c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x140003363  call    atexit
0x140003368  mov     rbx, [rsp+28h+arg_0]
0x14000336d  xor     eax, eax
0x14000336f  add     rsp, 20h
0x140003373  pop     rdi
0x140003374  retn
0x140003375  mov     ecx, 7
0x14000337a  call    __scrt_fastfail
```
