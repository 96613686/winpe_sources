# __scrt_initialize_thread_safe_statics

- ea: `0x140004740`
- end: `0x140004810`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140002e04`
- `0x140002fd4`
- `0x140003184`
- `0x140004740`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004790`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400047a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004790`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400047a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140004763`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140004778`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140004763`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140004778`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140004756`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140004756`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400047cf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400047cf`

## string_xrefs

- `0x14000475c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x140004771`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_14004D4A0, 0xFA0u);
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
    qword_14004D4C8 = (__int64)ProcAddress;
    qword_14004D4D0 = (__int64)v2;
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
0x140004740  mov     [rsp+arg_0], rbx
0x140004745  push    rdi
0x140004746  sub     rsp, 20h
0x14000474a  mov     edx, 0FA0h; dwSpinCount
0x14000474f  lea     rcx, stru_14004D4A0; lpCriticalSection
0x140004756  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x14000475c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x140004763  call    cs:__imp_GetModuleHandleW
0x140004769  mov     rbx, rax
0x14000476c  test    rax, rax
0x14000476f  jnz     short loc_140004786
0x140004771  lea     rcx, aKernel32Dll; "kernel32.dll"
0x140004778  call    cs:__imp_GetModuleHandleW
0x14000477e  mov     rbx, rax
0x140004781  test    rax, rax
0x140004784  jz      short loc_140004805
0x140004786  lea     rdx, ProcName; "SleepConditionVariableCS"
0x14000478d  mov     rcx, rbx; hModule
0x140004790  call    cs:__imp_GetProcAddress
0x140004796  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x14000479d  mov     rcx, rbx; hModule
0x1400047a0  mov     rdi, rax
0x1400047a3  call    cs:__imp_GetProcAddress
0x1400047a9  test    rdi, rdi
0x1400047ac  jz      short loc_1400047C3
0x1400047ae  test    rax, rax
0x1400047b1  jz      short loc_1400047C3
0x1400047b3  mov     cs:qword_14004D4C8, rdi
0x1400047ba  mov     cs:qword_14004D4D0, rax
0x1400047c1  jmp     short loc_1400047E1
0x1400047c3  xor     r9d, r9d; lpName
0x1400047c6  xor     r8d, r8d; bInitialState
0x1400047c9  xor     ecx, ecx; lpEventAttributes
0x1400047cb  lea     edx, [r9+1]; bManualReset
0x1400047cf  call    cs:__imp_CreateEventW
0x1400047d5  mov     cs:hHandle, rax
0x1400047dc  test    rax, rax
0x1400047df  jz      short loc_140004805
0x1400047e1  xor     ecx, ecx
0x1400047e3  call    __scrt_initialize_onexit_tables
0x1400047e8  test    al, al
0x1400047ea  jz      short loc_140004805
0x1400047ec  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1400047f3  call    atexit
0x1400047f8  mov     rbx, [rsp+28h+arg_0]
0x1400047fd  xor     eax, eax
0x1400047ff  add     rsp, 20h
0x140004803  pop     rdi
0x140004804  retn
0x140004805  mov     ecx, 7
0x14000480a  call    __scrt_fastfail
```
