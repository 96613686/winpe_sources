# __scrt_initialize_thread_safe_statics

- ea: `0x18001cac0`
- end: `0x18001cb90`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18001a720`
- `0x18001a8f0`
- `0x18001aa94`
- `0x18001cac0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001cae3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001caf8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001cae3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001caf8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001cb10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001cb23`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001cb10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001cb23`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001cb4f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001cb4f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18001cad6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18001cad6`

## string_xrefs

- `0x18001cadc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18001caf1`: `kernel32.dll`

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
    qword_18011B218 = (__int64)ProcAddress;
    qword_18011B220 = (__int64)v2;
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
0x18001cac0  mov     [rsp+arg_0], rbx
0x18001cac5  push    rdi
0x18001cac6  sub     rsp, 20h
0x18001caca  mov     edx, 0FA0h; dwSpinCount
0x18001cacf  lea     rcx, CriticalSection; lpCriticalSection
0x18001cad6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18001cadc  lea     rcx, aApiMsWinCoreSy_2; "api-ms-win-core-synch-l1-2-0.dll"
0x18001cae3  call    cs:__imp_GetModuleHandleW
0x18001cae9  mov     rbx, rax
0x18001caec  test    rax, rax
0x18001caef  jnz     short loc_18001CB06
0x18001caf1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x18001caf8  call    cs:__imp_GetModuleHandleW
0x18001cafe  mov     rbx, rax
0x18001cb01  test    rax, rax
0x18001cb04  jz      short loc_18001CB85
0x18001cb06  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18001cb0d  mov     rcx, rbx; hModule
0x18001cb10  call    cs:__imp_GetProcAddress
0x18001cb16  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18001cb1d  mov     rcx, rbx; hModule
0x18001cb20  mov     rdi, rax
0x18001cb23  call    cs:__imp_GetProcAddress
0x18001cb29  test    rdi, rdi
0x18001cb2c  jz      short loc_18001CB43
0x18001cb2e  test    rax, rax
0x18001cb31  jz      short loc_18001CB43
0x18001cb33  mov     cs:qword_18011B218, rdi
0x18001cb3a  mov     cs:qword_18011B220, rax
0x18001cb41  jmp     short loc_18001CB61
0x18001cb43  xor     r9d, r9d; lpName
0x18001cb46  xor     r8d, r8d; bInitialState
0x18001cb49  xor     ecx, ecx; lpEventAttributes
0x18001cb4b  lea     edx, [r9+1]; bManualReset
0x18001cb4f  call    cs:__imp_CreateEventW
0x18001cb55  mov     cs:hHandle, rax
0x18001cb5c  test    rax, rax
0x18001cb5f  jz      short loc_18001CB85
0x18001cb61  xor     ecx, ecx
0x18001cb63  call    __scrt_initialize_onexit_tables
0x18001cb68  test    al, al
0x18001cb6a  jz      short loc_18001CB85
0x18001cb6c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x18001cb73  call    atexit
0x18001cb78  mov     rbx, [rsp+28h+arg_0]
0x18001cb7d  xor     eax, eax
0x18001cb7f  add     rsp, 20h
0x18001cb83  pop     rdi
0x18001cb84  retn
0x18001cb85  mov     ecx, 7
0x18001cb8a  call    __scrt_fastfail
```
