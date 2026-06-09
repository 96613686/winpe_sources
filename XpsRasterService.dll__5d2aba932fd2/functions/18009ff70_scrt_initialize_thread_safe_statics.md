# __scrt_initialize_thread_safe_statics

- ea: `0x18009ff70`
- end: `0x1800a0040`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180003384`
- `0x180003554`
- `0x180003714`
- `0x18009ff70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18009ff86`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18009ff86`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009ffff`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009ffff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18009ff93`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18009ffa8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18009ff93`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18009ffa8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009ffc0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009ffd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009ffc0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009ffd3`

## string_xrefs

- `0x18009ff8c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18009ffa1`: `kernel32.dll`

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
    qword_18012A288 = (__int64)ProcAddress;
    qword_18012A290 = (__int64)v2;
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
0x18009ff70  mov     [rsp+arg_0], rbx
0x18009ff75  push    rdi
0x18009ff76  sub     rsp, 20h
0x18009ff7a  mov     edx, 0FA0h; dwSpinCount
0x18009ff7f  lea     rcx, CriticalSection; lpCriticalSection
0x18009ff86  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18009ff8c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x18009ff93  call    cs:__imp_GetModuleHandleW
0x18009ff99  mov     rbx, rax
0x18009ff9c  test    rax, rax
0x18009ff9f  jnz     short loc_18009FFB6
0x18009ffa1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x18009ffa8  call    cs:__imp_GetModuleHandleW
0x18009ffae  mov     rbx, rax
0x18009ffb1  test    rax, rax
0x18009ffb4  jz      short loc_1800A0035
0x18009ffb6  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18009ffbd  mov     rcx, rbx; hModule
0x18009ffc0  call    cs:__imp_GetProcAddress
0x18009ffc6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18009ffcd  mov     rcx, rbx; hModule
0x18009ffd0  mov     rdi, rax
0x18009ffd3  call    cs:__imp_GetProcAddress
0x18009ffd9  test    rdi, rdi
0x18009ffdc  jz      short loc_18009FFF3
0x18009ffde  test    rax, rax
0x18009ffe1  jz      short loc_18009FFF3
0x18009ffe3  mov     cs:qword_18012A288, rdi
0x18009ffea  mov     cs:qword_18012A290, rax
0x18009fff1  jmp     short loc_1800A0011
0x18009fff3  xor     r9d, r9d; lpName
0x18009fff6  xor     r8d, r8d; bInitialState
0x18009fff9  xor     ecx, ecx; lpEventAttributes
0x18009fffb  lea     edx, [r9+1]; bManualReset
0x18009ffff  call    cs:__imp_CreateEventW
0x1800a0005  mov     cs:hHandle, rax
0x1800a000c  test    rax, rax
0x1800a000f  jz      short loc_1800A0035
0x1800a0011  xor     ecx, ecx
0x1800a0013  call    __scrt_initialize_onexit_tables
0x1800a0018  test    al, al
0x1800a001a  jz      short loc_1800A0035
0x1800a001c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800a0023  call    atexit
0x1800a0028  mov     rbx, [rsp+28h+arg_0]
0x1800a002d  xor     eax, eax
0x1800a002f  add     rsp, 20h
0x1800a0033  pop     rdi
0x1800a0034  retn
0x1800a0035  mov     ecx, 7
0x1800a003a  call    __scrt_fastfail
```
