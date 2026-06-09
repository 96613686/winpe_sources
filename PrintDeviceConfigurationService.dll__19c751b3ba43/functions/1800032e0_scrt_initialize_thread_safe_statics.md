# __scrt_initialize_thread_safe_statics

- ea: `0x1800032e0`
- end: `0x1800033b0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800022a0`
- `0x180002470`
- `0x180002628`
- `0x1800032e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003330`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003343`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003330`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003343`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003303`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003318`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003303`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003318`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000336f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000336f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800032f6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800032f6`

## string_xrefs

- `0x1800032fc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180003311`: `kernel32.dll`

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
    qword_180024360 = (__int64)ProcAddress;
    qword_180024368 = (__int64)v2;
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
0x1800032e0  mov     [rsp+arg_0], rbx
0x1800032e5  push    rdi
0x1800032e6  sub     rsp, 20h
0x1800032ea  mov     edx, 0FA0h; dwSpinCount
0x1800032ef  lea     rcx, CriticalSection; lpCriticalSection
0x1800032f6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800032fc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180003303  call    cs:__imp_GetModuleHandleW
0x180003309  mov     rbx, rax
0x18000330c  test    rax, rax
0x18000330f  jnz     short loc_180003326
0x180003311  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180003318  call    cs:__imp_GetModuleHandleW
0x18000331e  mov     rbx, rax
0x180003321  test    rax, rax
0x180003324  jz      short loc_1800033A5
0x180003326  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000332d  mov     rcx, rbx; hModule
0x180003330  call    cs:__imp_GetProcAddress
0x180003336  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000333d  mov     rcx, rbx; hModule
0x180003340  mov     rdi, rax
0x180003343  call    cs:__imp_GetProcAddress
0x180003349  test    rdi, rdi
0x18000334c  jz      short loc_180003363
0x18000334e  test    rax, rax
0x180003351  jz      short loc_180003363
0x180003353  mov     cs:qword_180024360, rdi
0x18000335a  mov     cs:qword_180024368, rax
0x180003361  jmp     short loc_180003381
0x180003363  xor     r9d, r9d; lpName
0x180003366  xor     r8d, r8d; bInitialState
0x180003369  xor     ecx, ecx; lpEventAttributes
0x18000336b  lea     edx, [r9+1]; bManualReset
0x18000336f  call    cs:__imp_CreateEventW
0x180003375  mov     cs:hHandle, rax
0x18000337c  test    rax, rax
0x18000337f  jz      short loc_1800033A5
0x180003381  xor     ecx, ecx
0x180003383  call    __scrt_initialize_onexit_tables
0x180003388  test    al, al
0x18000338a  jz      short loc_1800033A5
0x18000338c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180003393  call    atexit
0x180003398  mov     rbx, [rsp+28h+arg_0]
0x18000339d  xor     eax, eax
0x18000339f  add     rsp, 20h
0x1800033a3  pop     rdi
0x1800033a4  retn
0x1800033a5  mov     ecx, 7
0x1800033aa  call    __scrt_fastfail
```
