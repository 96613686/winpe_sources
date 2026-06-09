# __scrt_initialize_thread_safe_statics

- ea: `0x180004100`
- end: `0x1800041d0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180003edc`
- `0x1800040ac`
- `0x180004100`
- `0x1800044e4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004123`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004138`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004123`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004138`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004150`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004163`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004150`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004163`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000418f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000418f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004116`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004116`

## string_xrefs

- `0x18000411c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180004131`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1800E57A8, 0xFA0u);
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
    qword_1800E57D0 = (__int64)ProcAddress;
    qword_1800E57D8 = (__int64)v2;
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
0x180004100  mov     [rsp+arg_0], rbx
0x180004105  push    rdi
0x180004106  sub     rsp, 20h
0x18000410a  mov     edx, 0FA0h; dwSpinCount
0x18000410f  lea     rcx, stru_1800E57A8; lpCriticalSection
0x180004116  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000411c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180004123  call    cs:__imp_GetModuleHandleW
0x180004129  mov     rbx, rax
0x18000412c  test    rax, rax
0x18000412f  jnz     short loc_180004146
0x180004131  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180004138  call    cs:__imp_GetModuleHandleW
0x18000413e  mov     rbx, rax
0x180004141  test    rax, rax
0x180004144  jz      short loc_1800041C5
0x180004146  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000414d  mov     rcx, rbx; hModule
0x180004150  call    cs:__imp_GetProcAddress
0x180004156  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000415d  mov     rcx, rbx; hModule
0x180004160  mov     rdi, rax
0x180004163  call    cs:__imp_GetProcAddress
0x180004169  test    rdi, rdi
0x18000416c  jz      short loc_180004183
0x18000416e  test    rax, rax
0x180004171  jz      short loc_180004183
0x180004173  mov     cs:qword_1800E57D0, rdi
0x18000417a  mov     cs:qword_1800E57D8, rax
0x180004181  jmp     short loc_1800041A1
0x180004183  xor     r9d, r9d; lpName
0x180004186  xor     r8d, r8d; bInitialState
0x180004189  xor     ecx, ecx; lpEventAttributes
0x18000418b  lea     edx, [r9+1]; bManualReset
0x18000418f  call    cs:__imp_CreateEventW
0x180004195  mov     cs:hHandle, rax
0x18000419c  test    rax, rax
0x18000419f  jz      short loc_1800041C5
0x1800041a1  xor     ecx, ecx
0x1800041a3  call    __scrt_initialize_onexit_tables
0x1800041a8  test    al, al
0x1800041aa  jz      short loc_1800041C5
0x1800041ac  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800041b3  call    atexit
0x1800041b8  mov     rbx, [rsp+28h+arg_0]
0x1800041bd  xor     eax, eax
0x1800041bf  add     rsp, 20h
0x1800041c3  pop     rdi
0x1800041c4  retn
0x1800041c5  mov     ecx, 7
0x1800041ca  call    __scrt_fastfail
```
