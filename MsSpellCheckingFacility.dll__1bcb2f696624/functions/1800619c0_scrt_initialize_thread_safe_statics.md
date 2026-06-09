# __scrt_initialize_thread_safe_statics

- ea: `0x1800619c0`
- end: `0x180061a90`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18006164c`
- `0x18006181c`
- `0x1800619c0`
- `0x1800620c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800619e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800619f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800619e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800619f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180061a10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180061a23`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180061a10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180061a23`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180061a4f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180061a4f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800619d6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800619d6`

## string_xrefs

- `0x1800619dc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800619f1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_18013F620, 0xFA0u);
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
    qword_18013F648 = (__int64)ProcAddress;
    qword_18013F650 = (__int64)v2;
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
0x1800619c0  mov     [rsp+arg_0], rbx
0x1800619c5  push    rdi
0x1800619c6  sub     rsp, 20h
0x1800619ca  mov     edx, 0FA0h; dwSpinCount
0x1800619cf  lea     rcx, stru_18013F620; lpCriticalSection
0x1800619d6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800619dc  lea     rcx, aApiMsWinCoreSy_2; "api-ms-win-core-synch-l1-2-0.dll"
0x1800619e3  call    cs:__imp_GetModuleHandleW
0x1800619e9  mov     rbx, rax
0x1800619ec  test    rax, rax
0x1800619ef  jnz     short loc_180061A06
0x1800619f1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800619f8  call    cs:__imp_GetModuleHandleW
0x1800619fe  mov     rbx, rax
0x180061a01  test    rax, rax
0x180061a04  jz      short loc_180061A85
0x180061a06  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x180061a0d  mov     rcx, rbx; hModule
0x180061a10  call    cs:__imp_GetProcAddress
0x180061a16  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180061a1d  mov     rcx, rbx; hModule
0x180061a20  mov     rdi, rax
0x180061a23  call    cs:__imp_GetProcAddress
0x180061a29  test    rdi, rdi
0x180061a2c  jz      short loc_180061A43
0x180061a2e  test    rax, rax
0x180061a31  jz      short loc_180061A43
0x180061a33  mov     cs:qword_18013F648, rdi
0x180061a3a  mov     cs:qword_18013F650, rax
0x180061a41  jmp     short loc_180061A61
0x180061a43  xor     r9d, r9d; lpName
0x180061a46  xor     r8d, r8d; bInitialState
0x180061a49  xor     ecx, ecx; lpEventAttributes
0x180061a4b  lea     edx, [r9+1]; bManualReset
0x180061a4f  call    cs:__imp_CreateEventW
0x180061a55  mov     cs:hHandle, rax
0x180061a5c  test    rax, rax
0x180061a5f  jz      short loc_180061A85
0x180061a61  xor     ecx, ecx
0x180061a63  call    __scrt_initialize_onexit_tables
0x180061a68  test    al, al
0x180061a6a  jz      short loc_180061A85
0x180061a6c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180061a73  call    atexit
0x180061a78  mov     rbx, [rsp+28h+arg_0]
0x180061a7d  xor     eax, eax
0x180061a7f  add     rsp, 20h
0x180061a83  pop     rdi
0x180061a84  retn
0x180061a85  mov     ecx, 7
0x180061a8a  call    __scrt_fastfail
```
