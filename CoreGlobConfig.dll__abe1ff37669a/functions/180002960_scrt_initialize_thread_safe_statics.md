# __scrt_initialize_thread_safe_statics

- ea: `0x180002960`
- end: `0x180002a30`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180002560`
- `0x180002730`
- `0x180002960`
- `0x18000306c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800029b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800029c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800029b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800029c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002983`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002998`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002983`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002998`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180002976`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180002976`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800029ef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800029ef`

## string_xrefs

- `0x18000297c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180002991`: `kernel32.dll`

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
    qword_180032A70 = (__int64)ProcAddress;
    qword_180032A78 = (__int64)v2;
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
0x180002960  mov     [rsp+arg_0], rbx
0x180002965  push    rdi
0x180002966  sub     rsp, 20h
0x18000296a  mov     edx, 0FA0h; dwSpinCount
0x18000296f  lea     rcx, CriticalSection; lpCriticalSection
0x180002976  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000297c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180002983  call    cs:__imp_GetModuleHandleW
0x180002989  mov     rbx, rax
0x18000298c  test    rax, rax
0x18000298f  jnz     short loc_1800029A6
0x180002991  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180002998  call    cs:__imp_GetModuleHandleW
0x18000299e  mov     rbx, rax
0x1800029a1  test    rax, rax
0x1800029a4  jz      short loc_180002A25
0x1800029a6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1800029ad  mov     rcx, rbx; hModule
0x1800029b0  call    cs:__imp_GetProcAddress
0x1800029b6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800029bd  mov     rcx, rbx; hModule
0x1800029c0  mov     rdi, rax
0x1800029c3  call    cs:__imp_GetProcAddress
0x1800029c9  test    rdi, rdi
0x1800029cc  jz      short loc_1800029E3
0x1800029ce  test    rax, rax
0x1800029d1  jz      short loc_1800029E3
0x1800029d3  mov     cs:qword_180032A70, rdi
0x1800029da  mov     cs:qword_180032A78, rax
0x1800029e1  jmp     short loc_180002A01
0x1800029e3  xor     r9d, r9d; lpName
0x1800029e6  xor     r8d, r8d; bInitialState
0x1800029e9  xor     ecx, ecx; lpEventAttributes
0x1800029eb  lea     edx, [r9+1]; bManualReset
0x1800029ef  call    cs:__imp_CreateEventW
0x1800029f5  mov     cs:hHandle, rax
0x1800029fc  test    rax, rax
0x1800029ff  jz      short loc_180002A25
0x180002a01  xor     ecx, ecx
0x180002a03  call    __scrt_initialize_onexit_tables
0x180002a08  test    al, al
0x180002a0a  jz      short loc_180002A25
0x180002a0c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180002a13  call    atexit
0x180002a18  mov     rbx, [rsp+28h+arg_0]
0x180002a1d  xor     eax, eax
0x180002a1f  add     rsp, 20h
0x180002a23  pop     rdi
0x180002a24  retn
0x180002a25  mov     ecx, 7
0x180002a2a  call    __scrt_fastfail
```
