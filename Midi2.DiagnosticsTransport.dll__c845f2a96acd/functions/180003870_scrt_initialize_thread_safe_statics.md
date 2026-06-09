# __scrt_initialize_thread_safe_statics

- ea: `0x180003870`
- end: `0x180003940`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180003620`
- `0x1800037f0`
- `0x180003870`
- `0x180003f34`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800038c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800038d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800038c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800038d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003893`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800038a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003893`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800038a8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180003886`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180003886`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800038ff`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800038ff`

## string_xrefs

- `0x18000388c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800038a1`: `kernel32.dll`

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
    qword_18001A490 = (__int64)ProcAddress;
    qword_18001A498 = (__int64)v2;
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
0x180003870  mov     [rsp+arg_0], rbx
0x180003875  push    rdi
0x180003876  sub     rsp, 20h
0x18000387a  mov     edx, 0FA0h; dwSpinCount
0x18000387f  lea     rcx, CriticalSection; lpCriticalSection
0x180003886  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000388c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180003893  call    cs:__imp_GetModuleHandleW
0x180003899  mov     rbx, rax
0x18000389c  test    rax, rax
0x18000389f  jnz     short loc_1800038B6
0x1800038a1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800038a8  call    cs:__imp_GetModuleHandleW
0x1800038ae  mov     rbx, rax
0x1800038b1  test    rax, rax
0x1800038b4  jz      short loc_180003935
0x1800038b6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1800038bd  mov     rcx, rbx; hModule
0x1800038c0  call    cs:__imp_GetProcAddress
0x1800038c6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800038cd  mov     rcx, rbx; hModule
0x1800038d0  mov     rdi, rax
0x1800038d3  call    cs:__imp_GetProcAddress
0x1800038d9  test    rdi, rdi
0x1800038dc  jz      short loc_1800038F3
0x1800038de  test    rax, rax
0x1800038e1  jz      short loc_1800038F3
0x1800038e3  mov     cs:qword_18001A490, rdi
0x1800038ea  mov     cs:qword_18001A498, rax
0x1800038f1  jmp     short loc_180003911
0x1800038f3  xor     r9d, r9d; lpName
0x1800038f6  xor     r8d, r8d; bInitialState
0x1800038f9  xor     ecx, ecx; lpEventAttributes
0x1800038fb  lea     edx, [r9+1]; bManualReset
0x1800038ff  call    cs:__imp_CreateEventW
0x180003905  mov     cs:hHandle, rax
0x18000390c  test    rax, rax
0x18000390f  jz      short loc_180003935
0x180003911  xor     ecx, ecx
0x180003913  call    __scrt_initialize_onexit_tables
0x180003918  test    al, al
0x18000391a  jz      short loc_180003935
0x18000391c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180003923  call    atexit
0x180003928  mov     rbx, [rsp+28h+arg_0]
0x18000392d  xor     eax, eax
0x18000392f  add     rsp, 20h
0x180003933  pop     rdi
0x180003934  retn
0x180003935  mov     ecx, 7
0x18000393a  call    __scrt_fastfail
```
