# __scrt_initialize_thread_safe_statics

- ea: `0x1400045b0`
- end: `0x140004680`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140004368`
- `0x140004538`
- `0x1400045b0`
- `0x140004ad8`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x14000463f`
- `KERNEL32!CreateEventW` at `0x14000463f`
- `KERNEL32!GetModuleHandleW` at `0x1400045d3`
- `KERNEL32!GetModuleHandleW` at `0x1400045e8`
- `KERNEL32!GetModuleHandleW` at `0x1400045d3`
- `KERNEL32!GetModuleHandleW` at `0x1400045e8`
- `KERNEL32!GetProcAddress` at `0x140004600`
- `KERNEL32!GetProcAddress` at `0x140004613`
- `KERNEL32!GetProcAddress` at `0x140004600`
- `KERNEL32!GetProcAddress` at `0x140004613`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1400045c6`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1400045c6`

## string_xrefs

- `0x1400045cc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1400045e1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1400B09D8, 0xFA0u);
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
    qword_1400B0A00 = (__int64)ProcAddress;
    qword_1400B0A08 = (__int64)v2;
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
0x1400045b0  mov     [rsp+arg_0], rbx
0x1400045b5  push    rdi
0x1400045b6  sub     rsp, 20h
0x1400045ba  mov     edx, 0FA0h; dwSpinCount
0x1400045bf  lea     rcx, stru_1400B09D8; lpCriticalSection
0x1400045c6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1400045cc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x1400045d3  call    cs:__imp_GetModuleHandleW
0x1400045d9  mov     rbx, rax
0x1400045dc  test    rax, rax
0x1400045df  jnz     short loc_1400045F6
0x1400045e1  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x1400045e8  call    cs:__imp_GetModuleHandleW
0x1400045ee  mov     rbx, rax
0x1400045f1  test    rax, rax
0x1400045f4  jz      short loc_140004675
0x1400045f6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1400045fd  mov     rcx, rbx; hModule
0x140004600  call    cs:__imp_GetProcAddress
0x140004606  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x14000460d  mov     rcx, rbx; hModule
0x140004610  mov     rdi, rax
0x140004613  call    cs:__imp_GetProcAddress
0x140004619  test    rdi, rdi
0x14000461c  jz      short loc_140004633
0x14000461e  test    rax, rax
0x140004621  jz      short loc_140004633
0x140004623  mov     cs:qword_1400B0A00, rdi
0x14000462a  mov     cs:qword_1400B0A08, rax
0x140004631  jmp     short loc_140004651
0x140004633  xor     r9d, r9d; lpName
0x140004636  xor     r8d, r8d; bInitialState
0x140004639  xor     ecx, ecx; lpEventAttributes
0x14000463b  lea     edx, [r9+1]; bManualReset
0x14000463f  call    cs:__imp_CreateEventW
0x140004645  mov     cs:hHandle, rax
0x14000464c  test    rax, rax
0x14000464f  jz      short loc_140004675
0x140004651  xor     ecx, ecx
0x140004653  call    __scrt_initialize_onexit_tables
0x140004658  test    al, al
0x14000465a  jz      short loc_140004675
0x14000465c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x140004663  call    atexit
0x140004668  mov     rbx, [rsp+28h+arg_0]
0x14000466d  xor     eax, eax
0x14000466f  add     rsp, 20h
0x140004673  pop     rdi
0x140004674  retn
0x140004675  mov     ecx, 7
0x14000467a  call    __scrt_fastfail
```
