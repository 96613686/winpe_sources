# __scrt_initialize_thread_safe_statics

- ea: `0x1800024b0`
- end: `0x180002580`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800022bc`
- `0x18000248c`
- `0x1800024b0`
- `0x180002b74`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002500`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002513`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002500`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002513`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800024d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800024e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800024d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800024e8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800024c6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800024c6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000253f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000253f`

## string_xrefs

- `0x1800024cc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800024e1`: `kernel32.dll`

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
    qword_1800234F0 = (__int64)ProcAddress;
    qword_1800234F8 = (__int64)v2;
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
0x1800024b0  mov     [rsp+arg_0], rbx
0x1800024b5  push    rdi
0x1800024b6  sub     rsp, 20h
0x1800024ba  mov     edx, 0FA0h; dwSpinCount
0x1800024bf  lea     rcx, CriticalSection; lpCriticalSection
0x1800024c6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800024cc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x1800024d3  call    cs:__imp_GetModuleHandleW
0x1800024d9  mov     rbx, rax
0x1800024dc  test    rax, rax
0x1800024df  jnz     short loc_1800024F6
0x1800024e1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800024e8  call    cs:__imp_GetModuleHandleW
0x1800024ee  mov     rbx, rax
0x1800024f1  test    rax, rax
0x1800024f4  jz      short loc_180002575
0x1800024f6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1800024fd  mov     rcx, rbx; hModule
0x180002500  call    cs:__imp_GetProcAddress
0x180002506  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000250d  mov     rcx, rbx; hModule
0x180002510  mov     rdi, rax
0x180002513  call    cs:__imp_GetProcAddress
0x180002519  test    rdi, rdi
0x18000251c  jz      short loc_180002533
0x18000251e  test    rax, rax
0x180002521  jz      short loc_180002533
0x180002523  mov     cs:qword_1800234F0, rdi
0x18000252a  mov     cs:qword_1800234F8, rax
0x180002531  jmp     short loc_180002551
0x180002533  xor     r9d, r9d; lpName
0x180002536  xor     r8d, r8d; bInitialState
0x180002539  xor     ecx, ecx; lpEventAttributes
0x18000253b  lea     edx, [r9+1]; bManualReset
0x18000253f  call    cs:__imp_CreateEventW
0x180002545  mov     cs:hHandle, rax
0x18000254c  test    rax, rax
0x18000254f  jz      short loc_180002575
0x180002551  xor     ecx, ecx
0x180002553  call    __scrt_initialize_onexit_tables
0x180002558  test    al, al
0x18000255a  jz      short loc_180002575
0x18000255c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180002563  call    atexit
0x180002568  mov     rbx, [rsp+28h+arg_0]
0x18000256d  xor     eax, eax
0x18000256f  add     rsp, 20h
0x180002573  pop     rdi
0x180002574  retn
0x180002575  mov     ecx, 7
0x18000257a  call    __scrt_fastfail
```
