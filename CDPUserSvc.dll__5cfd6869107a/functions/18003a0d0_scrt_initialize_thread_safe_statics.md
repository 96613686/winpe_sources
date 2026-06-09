# __scrt_initialize_thread_safe_statics

- ea: `0x18003a0d0`
- end: `0x18003a1a0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18002c894`
- `0x18002ca64`
- `0x18002cf30`
- `0x18003a0d0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003a0f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003a108`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003a0f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003a108`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003a120`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003a133`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003a120`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003a133`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18003a0e6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18003a0e6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003a15f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003a15f`

## string_xrefs

- `0x18003a0ec`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18003a101`: `kernel32.dll`

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
    qword_1800A32D8 = (__int64)ProcAddress;
    qword_1800A32E0 = (__int64)v2;
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
0x18003a0d0  mov     [rsp+arg_0], rbx
0x18003a0d5  push    rdi
0x18003a0d6  sub     rsp, 20h
0x18003a0da  mov     edx, 0FA0h; dwSpinCount
0x18003a0df  lea     rcx, CriticalSection; lpCriticalSection
0x18003a0e6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18003a0ec  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x18003a0f3  call    cs:__imp_GetModuleHandleW
0x18003a0f9  mov     rbx, rax
0x18003a0fc  test    rax, rax
0x18003a0ff  jnz     short loc_18003A116
0x18003a101  lea     rcx, aKernel32Dll; "kernel32.dll"
0x18003a108  call    cs:__imp_GetModuleHandleW
0x18003a10e  mov     rbx, rax
0x18003a111  test    rax, rax
0x18003a114  jz      short loc_18003A195
0x18003a116  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18003a11d  mov     rcx, rbx; hModule
0x18003a120  call    cs:__imp_GetProcAddress
0x18003a126  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18003a12d  mov     rcx, rbx; hModule
0x18003a130  mov     rdi, rax
0x18003a133  call    cs:__imp_GetProcAddress
0x18003a139  test    rdi, rdi
0x18003a13c  jz      short loc_18003A153
0x18003a13e  test    rax, rax
0x18003a141  jz      short loc_18003A153
0x18003a143  mov     cs:qword_1800A32D8, rdi
0x18003a14a  mov     cs:qword_1800A32E0, rax
0x18003a151  jmp     short loc_18003A171
0x18003a153  xor     r9d, r9d; lpName
0x18003a156  xor     r8d, r8d; bInitialState
0x18003a159  xor     ecx, ecx; lpEventAttributes
0x18003a15b  lea     edx, [r9+1]; bManualReset
0x18003a15f  call    cs:__imp_CreateEventW
0x18003a165  mov     cs:hHandle, rax
0x18003a16c  test    rax, rax
0x18003a16f  jz      short loc_18003A195
0x18003a171  xor     ecx, ecx
0x18003a173  call    __scrt_initialize_onexit_tables
0x18003a178  test    al, al
0x18003a17a  jz      short loc_18003A195
0x18003a17c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x18003a183  call    atexit
0x18003a188  mov     rbx, [rsp+28h+arg_0]
0x18003a18d  xor     eax, eax
0x18003a18f  add     rsp, 20h
0x18003a193  pop     rdi
0x18003a194  retn
0x18003a195  mov     ecx, 7
0x18003a19a  call    __scrt_fastfail
```
