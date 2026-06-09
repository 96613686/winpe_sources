# __scrt_initialize_thread_safe_statics

- ea: `0x180007770`
- end: `0x180007840`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000500c`
- `0x1800051dc`
- `0x1800053e0`
- `0x180007770`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800077c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800077d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800077c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800077d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007793`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800077a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007793`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800077a8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800077ff`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800077ff`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180007786`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180007786`

## string_xrefs

- `0x18000778c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800077a1`: `kernel32.dll`

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
    qword_1800FAE90 = (__int64)ProcAddress;
    qword_1800FAE98 = (__int64)v2;
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
0x180007770  mov     [rsp+arg_0], rbx
0x180007775  push    rdi
0x180007776  sub     rsp, 20h
0x18000777a  mov     edx, 0FA0h; dwSpinCount
0x18000777f  lea     rcx, CriticalSection; lpCriticalSection
0x180007786  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000778c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180007793  call    cs:__imp_GetModuleHandleW
0x180007799  mov     rbx, rax
0x18000779c  test    rax, rax
0x18000779f  jnz     short loc_1800077B6
0x1800077a1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800077a8  call    cs:__imp_GetModuleHandleW
0x1800077ae  mov     rbx, rax
0x1800077b1  test    rax, rax
0x1800077b4  jz      short loc_180007835
0x1800077b6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1800077bd  mov     rcx, rbx; hModule
0x1800077c0  call    cs:__imp_GetProcAddress
0x1800077c6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800077cd  mov     rcx, rbx; hModule
0x1800077d0  mov     rdi, rax
0x1800077d3  call    cs:__imp_GetProcAddress
0x1800077d9  test    rdi, rdi
0x1800077dc  jz      short loc_1800077F3
0x1800077de  test    rax, rax
0x1800077e1  jz      short loc_1800077F3
0x1800077e3  mov     cs:qword_1800FAE90, rdi
0x1800077ea  mov     cs:qword_1800FAE98, rax
0x1800077f1  jmp     short loc_180007811
0x1800077f3  xor     r9d, r9d; lpName
0x1800077f6  xor     r8d, r8d; bInitialState
0x1800077f9  xor     ecx, ecx; lpEventAttributes
0x1800077fb  lea     edx, [r9+1]; bManualReset
0x1800077ff  call    cs:__imp_CreateEventW
0x180007805  mov     cs:hHandle, rax
0x18000780c  test    rax, rax
0x18000780f  jz      short loc_180007835
0x180007811  xor     ecx, ecx
0x180007813  call    __scrt_initialize_onexit_tables
0x180007818  test    al, al
0x18000781a  jz      short loc_180007835
0x18000781c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180007823  call    atexit
0x180007828  mov     rbx, [rsp+28h+arg_0]
0x18000782d  xor     eax, eax
0x18000782f  add     rsp, 20h
0x180007833  pop     rdi
0x180007834  retn
0x180007835  mov     ecx, 7
0x18000783a  call    __scrt_fastfail
```
