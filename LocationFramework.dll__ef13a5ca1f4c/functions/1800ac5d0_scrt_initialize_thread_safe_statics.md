# __scrt_initialize_thread_safe_statics

- ea: `0x1800ac5d0`
- end: `0x1800ac6a0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800a9be0`
- `0x1800a9db0`
- `0x1800aa290`
- `0x1800ac5d0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800ac5f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800ac608`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800ac5f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800ac608`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ac620`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ac633`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ac620`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ac633`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800ac5e6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800ac5e6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ac65f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ac65f`

## string_xrefs

- `0x1800ac5ec`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800ac601`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1801E3818, 0xFA0u);
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
    qword_1801E3840 = (__int64)ProcAddress;
    qword_1801E3848 = (__int64)v2;
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
0x1800ac5d0  mov     [rsp+arg_0], rbx
0x1800ac5d5  push    rdi
0x1800ac5d6  sub     rsp, 20h
0x1800ac5da  mov     edx, 0FA0h; dwSpinCount
0x1800ac5df  lea     rcx, stru_1801E3818; lpCriticalSection
0x1800ac5e6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800ac5ec  lea     rcx, aApiMsWinCoreSy_4; "api-ms-win-core-synch-l1-2-0.dll"
0x1800ac5f3  call    cs:__imp_GetModuleHandleW
0x1800ac5f9  mov     rbx, rax
0x1800ac5fc  test    rax, rax
0x1800ac5ff  jnz     short loc_1800AC616
0x1800ac601  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800ac608  call    cs:__imp_GetModuleHandleW
0x1800ac60e  mov     rbx, rax
0x1800ac611  test    rax, rax
0x1800ac614  jz      short loc_1800AC695
0x1800ac616  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x1800ac61d  mov     rcx, rbx; hModule
0x1800ac620  call    cs:__imp_GetProcAddress
0x1800ac626  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800ac62d  mov     rcx, rbx; hModule
0x1800ac630  mov     rdi, rax
0x1800ac633  call    cs:__imp_GetProcAddress
0x1800ac639  test    rdi, rdi
0x1800ac63c  jz      short loc_1800AC653
0x1800ac63e  test    rax, rax
0x1800ac641  jz      short loc_1800AC653
0x1800ac643  mov     cs:qword_1801E3840, rdi
0x1800ac64a  mov     cs:qword_1801E3848, rax
0x1800ac651  jmp     short loc_1800AC671
0x1800ac653  xor     r9d, r9d; lpName
0x1800ac656  xor     r8d, r8d; bInitialState
0x1800ac659  xor     ecx, ecx; lpEventAttributes
0x1800ac65b  lea     edx, [r9+1]; bManualReset
0x1800ac65f  call    cs:__imp_CreateEventW
0x1800ac665  mov     cs:hHandle, rax
0x1800ac66c  test    rax, rax
0x1800ac66f  jz      short loc_1800AC695
0x1800ac671  xor     ecx, ecx
0x1800ac673  call    __scrt_initialize_onexit_tables
0x1800ac678  test    al, al
0x1800ac67a  jz      short loc_1800AC695
0x1800ac67c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800ac683  call    atexit
0x1800ac688  mov     rbx, [rsp+28h+arg_0]
0x1800ac68d  xor     eax, eax
0x1800ac68f  add     rsp, 20h
0x1800ac693  pop     rdi
0x1800ac694  retn
0x1800ac695  mov     ecx, 7
0x1800ac69a  call    __scrt_fastfail
```
