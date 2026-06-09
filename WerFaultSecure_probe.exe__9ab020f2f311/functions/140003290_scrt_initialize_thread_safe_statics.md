# __scrt_initialize_thread_safe_statics

- ea: `0x140003290`
- end: `0x140003360`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1400024e4`
- `0x1400026b4`
- `0x14000280c`
- `0x140003290`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400032e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400032f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400032e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400032f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400032b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400032c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400032b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400032c8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1400032a6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1400032a6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000331f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000331f`

## string_xrefs

- `0x1400032ac`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1400032c1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_14001A450, 0xFA0u);
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
    qword_14001A478 = (__int64)ProcAddress;
    qword_14001A480 = (__int64)v2;
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
0x140003290  mov     [rsp+arg_0], rbx
0x140003295  push    rdi
0x140003296  sub     rsp, 20h
0x14000329a  mov     edx, 0FA0h; dwSpinCount
0x14000329f  lea     rcx, stru_14001A450; lpCriticalSection
0x1400032a6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1400032ac  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x1400032b3  call    cs:__imp_GetModuleHandleW
0x1400032b9  mov     rbx, rax
0x1400032bc  test    rax, rax
0x1400032bf  jnz     short loc_1400032D6
0x1400032c1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1400032c8  call    cs:__imp_GetModuleHandleW
0x1400032ce  mov     rbx, rax
0x1400032d1  test    rax, rax
0x1400032d4  jz      short loc_140003355
0x1400032d6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1400032dd  mov     rcx, rbx; hModule
0x1400032e0  call    cs:__imp_GetProcAddress
0x1400032e6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1400032ed  mov     rcx, rbx; hModule
0x1400032f0  mov     rdi, rax
0x1400032f3  call    cs:__imp_GetProcAddress
0x1400032f9  test    rdi, rdi
0x1400032fc  jz      short loc_140003313
0x1400032fe  test    rax, rax
0x140003301  jz      short loc_140003313
0x140003303  mov     cs:qword_14001A478, rdi
0x14000330a  mov     cs:qword_14001A480, rax
0x140003311  jmp     short loc_140003331
0x140003313  xor     r9d, r9d; lpName
0x140003316  xor     r8d, r8d; bInitialState
0x140003319  xor     ecx, ecx; lpEventAttributes
0x14000331b  lea     edx, [r9+1]; bManualReset
0x14000331f  call    cs:__imp_CreateEventW
0x140003325  mov     cs:hObject, rax
0x14000332c  test    rax, rax
0x14000332f  jz      short loc_140003355
0x140003331  xor     ecx, ecx
0x140003333  call    __scrt_initialize_onexit_tables
0x140003338  test    al, al
0x14000333a  jz      short loc_140003355
0x14000333c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x140003343  call    atexit
0x140003348  mov     rbx, [rsp+28h+arg_0]
0x14000334d  xor     eax, eax
0x14000334f  add     rsp, 20h
0x140003353  pop     rdi
0x140003354  retn
0x140003355  mov     ecx, 7
0x14000335a  call    __scrt_fastfail
```
