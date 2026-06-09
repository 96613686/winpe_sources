# __scrt_initialize_thread_safe_statics

- ea: `0x180002fb0`
- end: `0x180003080`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180002dbc`
- `0x180002f8c`
- `0x180002fb0`
- `0x180003894`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003000`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003013`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003000`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003013`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002fd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002fe8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002fd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002fe8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000303f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000303f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180002fc6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180002fc6`

## string_xrefs

- `0x180002fcc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180002fe1`: `kernel32.dll`

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
    qword_180072950 = (__int64)ProcAddress;
    qword_180072958 = (__int64)v2;
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
0x180002fb0  mov     [rsp+arg_0], rbx
0x180002fb5  push    rdi
0x180002fb6  sub     rsp, 20h
0x180002fba  mov     edx, 0FA0h; dwSpinCount
0x180002fbf  lea     rcx, CriticalSection; lpCriticalSection
0x180002fc6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180002fcc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180002fd3  call    cs:__imp_GetModuleHandleW
0x180002fd9  mov     rbx, rax
0x180002fdc  test    rax, rax
0x180002fdf  jnz     short loc_180002FF6
0x180002fe1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180002fe8  call    cs:__imp_GetModuleHandleW
0x180002fee  mov     rbx, rax
0x180002ff1  test    rax, rax
0x180002ff4  jz      short loc_180003075
0x180002ff6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x180002ffd  mov     rcx, rbx; hModule
0x180003000  call    cs:__imp_GetProcAddress
0x180003006  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000300d  mov     rcx, rbx; hModule
0x180003010  mov     rdi, rax
0x180003013  call    cs:__imp_GetProcAddress
0x180003019  test    rdi, rdi
0x18000301c  jz      short loc_180003033
0x18000301e  test    rax, rax
0x180003021  jz      short loc_180003033
0x180003023  mov     cs:qword_180072950, rdi
0x18000302a  mov     cs:qword_180072958, rax
0x180003031  jmp     short loc_180003051
0x180003033  xor     r9d, r9d; lpName
0x180003036  xor     r8d, r8d; bInitialState
0x180003039  xor     ecx, ecx; lpEventAttributes
0x18000303b  lea     edx, [r9+1]; bManualReset
0x18000303f  call    cs:__imp_CreateEventW
0x180003045  mov     cs:hHandle, rax
0x18000304c  test    rax, rax
0x18000304f  jz      short loc_180003075
0x180003051  xor     ecx, ecx
0x180003053  call    __scrt_initialize_onexit_tables
0x180003058  test    al, al
0x18000305a  jz      short loc_180003075
0x18000305c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180003063  call    atexit
0x180003068  mov     rbx, [rsp+28h+arg_0]
0x18000306d  xor     eax, eax
0x18000306f  add     rsp, 20h
0x180003073  pop     rdi
0x180003074  retn
0x180003075  mov     ecx, 7
0x18000307a  call    __scrt_fastfail
```
