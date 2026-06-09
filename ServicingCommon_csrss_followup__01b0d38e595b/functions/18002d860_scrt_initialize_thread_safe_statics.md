# __scrt_initialize_thread_safe_statics

- ea: `0x18002d860`
- end: `0x18002d930`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18002d4bc`
- `0x18002d68c`
- `0x18002d860`
- `0x18002db98`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002d8b0`
- `KERNEL32!GetProcAddress` at `0x18002d8c3`
- `KERNEL32!GetProcAddress` at `0x18002d8b0`
- `KERNEL32!GetProcAddress` at `0x18002d8c3`
- `KERNEL32!GetModuleHandleW` at `0x18002d883`
- `KERNEL32!GetModuleHandleW` at `0x18002d898`
- `KERNEL32!GetModuleHandleW` at `0x18002d883`
- `KERNEL32!GetModuleHandleW` at `0x18002d898`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18002d876`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18002d876`
- `KERNEL32!CreateEventW` at `0x18002d8ef`
- `KERNEL32!CreateEventW` at `0x18002d8ef`

## string_xrefs

- `0x18002d87c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18002d891`: `kernel32.dll`

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
    qword_1800D2100 = (__int64)ProcAddress;
    qword_1800D2108 = (__int64)v2;
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
0x18002d860  mov     [rsp+arg_0], rbx
0x18002d865  push    rdi
0x18002d866  sub     rsp, 20h
0x18002d86a  mov     edx, 0FA0h; dwSpinCount
0x18002d86f  lea     rcx, CriticalSection; lpCriticalSection
0x18002d876  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18002d87c  lea     rcx, aApiMsWinCoreSy_0; "api-ms-win-core-synch-l1-2-0.dll"
0x18002d883  call    cs:__imp_GetModuleHandleW
0x18002d889  mov     rbx, rax
0x18002d88c  test    rax, rax
0x18002d88f  jnz     short loc_18002D8A6
0x18002d891  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x18002d898  call    cs:__imp_GetModuleHandleW
0x18002d89e  mov     rbx, rax
0x18002d8a1  test    rax, rax
0x18002d8a4  jz      short loc_18002D925
0x18002d8a6  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18002d8ad  mov     rcx, rbx; hModule
0x18002d8b0  call    cs:__imp_GetProcAddress
0x18002d8b6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18002d8bd  mov     rcx, rbx; hModule
0x18002d8c0  mov     rdi, rax
0x18002d8c3  call    cs:__imp_GetProcAddress
0x18002d8c9  test    rdi, rdi
0x18002d8cc  jz      short loc_18002D8E3
0x18002d8ce  test    rax, rax
0x18002d8d1  jz      short loc_18002D8E3
0x18002d8d3  mov     cs:qword_1800D2100, rdi
0x18002d8da  mov     cs:qword_1800D2108, rax
0x18002d8e1  jmp     short loc_18002D901
0x18002d8e3  xor     r9d, r9d; lpName
0x18002d8e6  xor     r8d, r8d; bInitialState
0x18002d8e9  xor     ecx, ecx; lpEventAttributes
0x18002d8eb  lea     edx, [r9+1]; bManualReset
0x18002d8ef  call    cs:__imp_CreateEventW
0x18002d8f5  mov     cs:hHandle, rax
0x18002d8fc  test    rax, rax
0x18002d8ff  jz      short loc_18002D925
0x18002d901  xor     ecx, ecx
0x18002d903  call    __scrt_initialize_onexit_tables
0x18002d908  test    al, al
0x18002d90a  jz      short loc_18002D925
0x18002d90c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x18002d913  call    atexit
0x18002d918  mov     rbx, [rsp+28h+arg_0]
0x18002d91d  xor     eax, eax
0x18002d91f  add     rsp, 20h
0x18002d923  pop     rdi
0x18002d924  retn
0x18002d925  mov     ecx, 7
0x18002d92a  call    __scrt_fastfail
```
