# __scrt_initialize_thread_safe_statics

- ea: `0x180004860`
- end: `0x180004930`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180002814`
- `0x1800029e4`
- `0x180002b4c`
- `0x180004860`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800048b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800048c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800048b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800048c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004883`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004898`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004883`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004898`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800048ef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800048ef`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004876`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004876`

## string_xrefs

- `0x18000487c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180004891`: `kernel32.dll`

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
    qword_18007E810 = (__int64)ProcAddress;
    qword_18007E818 = (__int64)v2;
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
0x180004860  mov     [rsp+arg_0], rbx
0x180004865  push    rdi
0x180004866  sub     rsp, 20h
0x18000486a  mov     edx, 0FA0h; dwSpinCount
0x18000486f  lea     rcx, CriticalSection; lpCriticalSection
0x180004876  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000487c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180004883  call    cs:__imp_GetModuleHandleW
0x180004889  mov     rbx, rax
0x18000488c  test    rax, rax
0x18000488f  jnz     short loc_1800048A6
0x180004891  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180004898  call    cs:__imp_GetModuleHandleW
0x18000489e  mov     rbx, rax
0x1800048a1  test    rax, rax
0x1800048a4  jz      short loc_180004925
0x1800048a6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1800048ad  mov     rcx, rbx; hModule
0x1800048b0  call    cs:__imp_GetProcAddress
0x1800048b6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800048bd  mov     rcx, rbx; hModule
0x1800048c0  mov     rdi, rax
0x1800048c3  call    cs:__imp_GetProcAddress
0x1800048c9  test    rdi, rdi
0x1800048cc  jz      short loc_1800048E3
0x1800048ce  test    rax, rax
0x1800048d1  jz      short loc_1800048E3
0x1800048d3  mov     cs:qword_18007E810, rdi
0x1800048da  mov     cs:qword_18007E818, rax
0x1800048e1  jmp     short loc_180004901
0x1800048e3  xor     r9d, r9d; lpName
0x1800048e6  xor     r8d, r8d; bInitialState
0x1800048e9  xor     ecx, ecx; lpEventAttributes
0x1800048eb  lea     edx, [r9+1]; bManualReset
0x1800048ef  call    cs:__imp_CreateEventW
0x1800048f5  mov     cs:hHandle, rax
0x1800048fc  test    rax, rax
0x1800048ff  jz      short loc_180004925
0x180004901  xor     ecx, ecx
0x180004903  call    __scrt_initialize_onexit_tables
0x180004908  test    al, al
0x18000490a  jz      short loc_180004925
0x18000490c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180004913  call    atexit
0x180004918  mov     rbx, [rsp+28h+arg_0]
0x18000491d  xor     eax, eax
0x18000491f  add     rsp, 20h
0x180004923  pop     rdi
0x180004924  retn
0x180004925  mov     ecx, 7
0x18000492a  call    __scrt_fastfail
```
