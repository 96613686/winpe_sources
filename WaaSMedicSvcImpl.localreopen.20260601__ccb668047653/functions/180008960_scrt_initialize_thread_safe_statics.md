# __scrt_initialize_thread_safe_statics

- ea: `0x180008960`
- end: `0x180008a30`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180005394`
- `0x180005564`
- `0x1800056d4`
- `0x180008960`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800089b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800089c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800089b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800089c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008983`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008998`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008983`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008998`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180008976`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180008976`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800089ef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800089ef`

## string_xrefs

- `0x18000897c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180008991`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1800A4D80, 0xFA0u);
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
    qword_1800A4DA8 = (__int64)ProcAddress;
    qword_1800A4DB0 = (__int64)v2;
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
0x180008960  mov     [rsp+arg_0], rbx
0x180008965  push    rdi
0x180008966  sub     rsp, 20h
0x18000896a  mov     edx, 0FA0h; dwSpinCount
0x18000896f  lea     rcx, stru_1800A4D80; lpCriticalSection
0x180008976  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000897c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180008983  call    cs:__imp_GetModuleHandleW
0x180008989  mov     rbx, rax
0x18000898c  test    rax, rax
0x18000898f  jnz     short loc_1800089A6
0x180008991  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180008998  call    cs:__imp_GetModuleHandleW
0x18000899e  mov     rbx, rax
0x1800089a1  test    rax, rax
0x1800089a4  jz      short loc_180008A25
0x1800089a6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1800089ad  mov     rcx, rbx; hModule
0x1800089b0  call    cs:__imp_GetProcAddress
0x1800089b6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800089bd  mov     rcx, rbx; hModule
0x1800089c0  mov     rdi, rax
0x1800089c3  call    cs:__imp_GetProcAddress
0x1800089c9  test    rdi, rdi
0x1800089cc  jz      short loc_1800089E3
0x1800089ce  test    rax, rax
0x1800089d1  jz      short loc_1800089E3
0x1800089d3  mov     cs:qword_1800A4DA8, rdi
0x1800089da  mov     cs:qword_1800A4DB0, rax
0x1800089e1  jmp     short loc_180008A01
0x1800089e3  xor     r9d, r9d; lpName
0x1800089e6  xor     r8d, r8d; bInitialState
0x1800089e9  xor     ecx, ecx; lpEventAttributes
0x1800089eb  lea     edx, [r9+1]; bManualReset
0x1800089ef  call    cs:__imp_CreateEventW
0x1800089f5  mov     cs:hHandle, rax
0x1800089fc  test    rax, rax
0x1800089ff  jz      short loc_180008A25
0x180008a01  xor     ecx, ecx
0x180008a03  call    __scrt_initialize_onexit_tables
0x180008a08  test    al, al
0x180008a0a  jz      short loc_180008A25
0x180008a0c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180008a13  call    atexit
0x180008a18  mov     rbx, [rsp+28h+arg_0]
0x180008a1d  xor     eax, eax
0x180008a1f  add     rsp, 20h
0x180008a23  pop     rdi
0x180008a24  retn
0x180008a25  mov     ecx, 7
0x180008a2a  call    __scrt_fastfail
```
