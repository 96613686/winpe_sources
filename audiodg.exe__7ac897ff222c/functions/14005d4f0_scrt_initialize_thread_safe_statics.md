# __scrt_initialize_thread_safe_statics

- ea: `0x14005d4f0`
- end: `0x14005d5c0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x14005d2bc`
- `0x14005d48c`
- `0x14005d4f0`
- `0x14005dd0c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005d540`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005d553`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005d540`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005d553`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14005d513`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14005d528`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14005d513`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14005d528`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x14005d506`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x14005d506`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14005d57f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14005d57f`

## string_xrefs

- `0x14005d50c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x14005d521`: `kernel32.dll`

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
    qword_1400E7C90 = (__int64)ProcAddress;
    qword_1400E7C98 = (__int64)v2;
  }
  else
  {
    hEvent = CreateEventW(0, 1, 0, 0);
    if ( !hEvent )
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
0x14005d4f0  mov     [rsp+arg_0], rbx
0x14005d4f5  push    rdi
0x14005d4f6  sub     rsp, 20h
0x14005d4fa  mov     edx, 0FA0h; dwSpinCount
0x14005d4ff  lea     rcx, CriticalSection; lpCriticalSection
0x14005d506  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x14005d50c  lea     rcx, aApiMsWinCoreSy_3; "api-ms-win-core-synch-l1-2-0.dll"
0x14005d513  call    cs:__imp_GetModuleHandleW
0x14005d519  mov     rbx, rax
0x14005d51c  test    rax, rax
0x14005d51f  jnz     short loc_14005D536
0x14005d521  lea     rcx, aKernel32Dll; "kernel32.dll"
0x14005d528  call    cs:__imp_GetModuleHandleW
0x14005d52e  mov     rbx, rax
0x14005d531  test    rax, rax
0x14005d534  jz      short loc_14005D5B5
0x14005d536  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x14005d53d  mov     rcx, rbx; hModule
0x14005d540  call    cs:__imp_GetProcAddress
0x14005d546  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x14005d54d  mov     rcx, rbx; hModule
0x14005d550  mov     rdi, rax
0x14005d553  call    cs:__imp_GetProcAddress
0x14005d559  test    rdi, rdi
0x14005d55c  jz      short loc_14005D573
0x14005d55e  test    rax, rax
0x14005d561  jz      short loc_14005D573
0x14005d563  mov     cs:qword_1400E7C90, rdi
0x14005d56a  mov     cs:qword_1400E7C98, rax
0x14005d571  jmp     short loc_14005D591
0x14005d573  xor     r9d, r9d; lpName
0x14005d576  xor     r8d, r8d; bInitialState
0x14005d579  xor     ecx, ecx; lpEventAttributes
0x14005d57b  lea     edx, [r9+1]; bManualReset
0x14005d57f  call    cs:__imp_CreateEventW
0x14005d585  mov     cs:hEvent, rax
0x14005d58c  test    rax, rax
0x14005d58f  jz      short loc_14005D5B5
0x14005d591  xor     ecx, ecx
0x14005d593  call    __scrt_initialize_onexit_tables
0x14005d598  test    al, al
0x14005d59a  jz      short loc_14005D5B5
0x14005d59c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x14005d5a3  call    atexit
0x14005d5a8  mov     rbx, [rsp+28h+arg_0]
0x14005d5ad  xor     eax, eax
0x14005d5af  add     rsp, 20h
0x14005d5b3  pop     rdi
0x14005d5b4  retn
0x14005d5b5  mov     ecx, 7
0x14005d5ba  call    __scrt_fastfail
```
