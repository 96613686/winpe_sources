# __scrt_initialize_thread_safe_statics

- ea: `0x14001c010`
- end: `0x14001c0e0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x14001bde4`
- `0x14001bfb4`
- `0x14001c010`
- `0x14001c7a0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001c060`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001c073`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001c060`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001c073`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001c033`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001c048`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001c033`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001c048`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x14001c026`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x14001c026`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001c09f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001c09f`

## string_xrefs

- `0x14001c02c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x14001c041`: `kernel32.dll`

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
    qword_1400ABA50 = (__int64)ProcAddress;
    qword_1400ABA58 = (__int64)v2;
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
0x14001c010  mov     [rsp+arg_0], rbx
0x14001c015  push    rdi
0x14001c016  sub     rsp, 20h
0x14001c01a  mov     edx, 0FA0h; dwSpinCount
0x14001c01f  lea     rcx, CriticalSection; lpCriticalSection
0x14001c026  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x14001c02c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x14001c033  call    cs:__imp_GetModuleHandleW
0x14001c039  mov     rbx, rax
0x14001c03c  test    rax, rax
0x14001c03f  jnz     short loc_14001C056
0x14001c041  lea     rcx, aKernel32Dll; "kernel32.dll"
0x14001c048  call    cs:__imp_GetModuleHandleW
0x14001c04e  mov     rbx, rax
0x14001c051  test    rax, rax
0x14001c054  jz      short loc_14001C0D5
0x14001c056  lea     rdx, ProcName; "SleepConditionVariableCS"
0x14001c05d  mov     rcx, rbx; hModule
0x14001c060  call    cs:__imp_GetProcAddress
0x14001c066  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x14001c06d  mov     rcx, rbx; hModule
0x14001c070  mov     rdi, rax
0x14001c073  call    cs:__imp_GetProcAddress
0x14001c079  test    rdi, rdi
0x14001c07c  jz      short loc_14001C093
0x14001c07e  test    rax, rax
0x14001c081  jz      short loc_14001C093
0x14001c083  mov     cs:qword_1400ABA50, rdi
0x14001c08a  mov     cs:qword_1400ABA58, rax
0x14001c091  jmp     short loc_14001C0B1
0x14001c093  xor     r9d, r9d; lpName
0x14001c096  xor     r8d, r8d; bInitialState
0x14001c099  xor     ecx, ecx; lpEventAttributes
0x14001c09b  lea     edx, [r9+1]; bManualReset
0x14001c09f  call    cs:__imp_CreateEventW
0x14001c0a5  mov     cs:hHandle, rax
0x14001c0ac  test    rax, rax
0x14001c0af  jz      short loc_14001C0D5
0x14001c0b1  xor     ecx, ecx
0x14001c0b3  call    __scrt_initialize_onexit_tables
0x14001c0b8  test    al, al
0x14001c0ba  jz      short loc_14001C0D5
0x14001c0bc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x14001c0c3  call    atexit
0x14001c0c8  mov     rbx, [rsp+28h+arg_0]
0x14001c0cd  xor     eax, eax
0x14001c0cf  add     rsp, 20h
0x14001c0d3  pop     rdi
0x14001c0d4  retn
0x14001c0d5  mov     ecx, 7
0x14001c0da  call    __scrt_fastfail
```
