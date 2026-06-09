# __scrt_initialize_thread_safe_statics

- ea: `0x180002190`
- end: `0x180002260`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001f20`
- `0x1800020f0`
- `0x180002190`
- `0x180002564`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800021e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800021f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800021e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800021f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800021b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800021c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800021b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800021c8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800021a6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800021a6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000221f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000221f`

## string_xrefs

- `0x1800021ac`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800021c1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_180023528, 0xFA0u);
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
    qword_180023550 = (__int64)ProcAddress;
    qword_180023558 = (__int64)v2;
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
0x180002190  mov     [rsp+arg_0], rbx
0x180002195  push    rdi
0x180002196  sub     rsp, 20h
0x18000219a  mov     edx, 0FA0h; dwSpinCount
0x18000219f  lea     rcx, stru_180023528; lpCriticalSection
0x1800021a6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800021ac  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x1800021b3  call    cs:__imp_GetModuleHandleW
0x1800021b9  mov     rbx, rax
0x1800021bc  test    rax, rax
0x1800021bf  jnz     short loc_1800021D6
0x1800021c1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800021c8  call    cs:__imp_GetModuleHandleW
0x1800021ce  mov     rbx, rax
0x1800021d1  test    rax, rax
0x1800021d4  jz      short loc_180002255
0x1800021d6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1800021dd  mov     rcx, rbx; hModule
0x1800021e0  call    cs:__imp_GetProcAddress
0x1800021e6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800021ed  mov     rcx, rbx; hModule
0x1800021f0  mov     rdi, rax
0x1800021f3  call    cs:__imp_GetProcAddress
0x1800021f9  test    rdi, rdi
0x1800021fc  jz      short loc_180002213
0x1800021fe  test    rax, rax
0x180002201  jz      short loc_180002213
0x180002203  mov     cs:qword_180023550, rdi
0x18000220a  mov     cs:qword_180023558, rax
0x180002211  jmp     short loc_180002231
0x180002213  xor     r9d, r9d; lpName
0x180002216  xor     r8d, r8d; bInitialState
0x180002219  xor     ecx, ecx; lpEventAttributes
0x18000221b  lea     edx, [r9+1]; bManualReset
0x18000221f  call    cs:__imp_CreateEventW
0x180002225  mov     cs:hHandle, rax
0x18000222c  test    rax, rax
0x18000222f  jz      short loc_180002255
0x180002231  xor     ecx, ecx
0x180002233  call    __scrt_initialize_onexit_tables
0x180002238  test    al, al
0x18000223a  jz      short loc_180002255
0x18000223c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180002243  call    atexit
0x180002248  mov     rbx, [rsp+28h+arg_0]
0x18000224d  xor     eax, eax
0x18000224f  add     rsp, 20h
0x180002253  pop     rdi
0x180002254  retn
0x180002255  mov     ecx, 7
0x18000225a  call    __scrt_fastfail
```
