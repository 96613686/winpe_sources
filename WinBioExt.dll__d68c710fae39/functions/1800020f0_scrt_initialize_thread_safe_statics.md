# __scrt_initialize_thread_safe_statics

- ea: `0x1800020f0`
- end: `0x1800021c0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800017f0`
- `0x1800019c0`
- `0x180001b58`
- `0x1800020f0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002113`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002128`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002113`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002128`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002140`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002153`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002140`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002153`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000217f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000217f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180002106`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180002106`

## string_xrefs

- `0x18000210c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180002121`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1800103E8, 0xFA0u);
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
    qword_180010410 = (__int64)ProcAddress;
    qword_180010418 = (__int64)v2;
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
0x1800020f0  mov     [rsp+arg_0], rbx
0x1800020f5  push    rdi
0x1800020f6  sub     rsp, 20h
0x1800020fa  mov     edx, 0FA0h; dwSpinCount
0x1800020ff  lea     rcx, stru_1800103E8; lpCriticalSection
0x180002106  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000210c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180002113  call    cs:__imp_GetModuleHandleW
0x180002119  mov     rbx, rax
0x18000211c  test    rax, rax
0x18000211f  jnz     short loc_180002136
0x180002121  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180002128  call    cs:__imp_GetModuleHandleW
0x18000212e  mov     rbx, rax
0x180002131  test    rax, rax
0x180002134  jz      short loc_1800021B5
0x180002136  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000213d  mov     rcx, rbx; hModule
0x180002140  call    cs:__imp_GetProcAddress
0x180002146  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000214d  mov     rcx, rbx; hModule
0x180002150  mov     rdi, rax
0x180002153  call    cs:__imp_GetProcAddress
0x180002159  test    rdi, rdi
0x18000215c  jz      short loc_180002173
0x18000215e  test    rax, rax
0x180002161  jz      short loc_180002173
0x180002163  mov     cs:qword_180010410, rdi
0x18000216a  mov     cs:qword_180010418, rax
0x180002171  jmp     short loc_180002191
0x180002173  xor     r9d, r9d; lpName
0x180002176  xor     r8d, r8d; bInitialState
0x180002179  xor     ecx, ecx; lpEventAttributes
0x18000217b  lea     edx, [r9+1]; bManualReset
0x18000217f  call    cs:__imp_CreateEventW
0x180002185  mov     cs:hHandle, rax
0x18000218c  test    rax, rax
0x18000218f  jz      short loc_1800021B5
0x180002191  xor     ecx, ecx
0x180002193  call    __scrt_initialize_onexit_tables
0x180002198  test    al, al
0x18000219a  jz      short loc_1800021B5
0x18000219c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800021a3  call    atexit
0x1800021a8  mov     rbx, [rsp+28h+arg_0]
0x1800021ad  xor     eax, eax
0x1800021af  add     rsp, 20h
0x1800021b3  pop     rdi
0x1800021b4  retn
0x1800021b5  mov     ecx, 7
0x1800021ba  call    __scrt_fastfail
```
