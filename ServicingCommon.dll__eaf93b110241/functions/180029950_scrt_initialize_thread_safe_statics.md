# __scrt_initialize_thread_safe_statics

- ea: `0x180029950`
- end: `0x180029a20`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800295ac`
- `0x18002977c`
- `0x180029950`
- `0x180029c88`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800299a0`
- `KERNEL32!GetProcAddress` at `0x1800299b3`
- `KERNEL32!GetProcAddress` at `0x1800299a0`
- `KERNEL32!GetProcAddress` at `0x1800299b3`
- `KERNEL32!GetModuleHandleW` at `0x180029973`
- `KERNEL32!GetModuleHandleW` at `0x180029988`
- `KERNEL32!GetModuleHandleW` at `0x180029973`
- `KERNEL32!GetModuleHandleW` at `0x180029988`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180029966`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180029966`
- `KERNEL32!CreateEventW` at `0x1800299df`
- `KERNEL32!CreateEventW` at `0x1800299df`

## string_xrefs

- `0x18002996c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180029981`: `kernel32.dll`

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
    qword_1800D4100 = (__int64)ProcAddress;
    qword_1800D4108 = (__int64)v2;
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
0x180029950  mov     [rsp+arg_0], rbx
0x180029955  push    rdi
0x180029956  sub     rsp, 20h
0x18002995a  mov     edx, 0FA0h; dwSpinCount
0x18002995f  lea     rcx, CriticalSection; lpCriticalSection
0x180029966  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18002996c  lea     rcx, aApiMsWinCoreSy_0; "api-ms-win-core-synch-l1-2-0.dll"
0x180029973  call    cs:__imp_GetModuleHandleW
0x180029979  mov     rbx, rax
0x18002997c  test    rax, rax
0x18002997f  jnz     short loc_180029996
0x180029981  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x180029988  call    cs:__imp_GetModuleHandleW
0x18002998e  mov     rbx, rax
0x180029991  test    rax, rax
0x180029994  jz      short loc_180029A15
0x180029996  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18002999d  mov     rcx, rbx; hModule
0x1800299a0  call    cs:__imp_GetProcAddress
0x1800299a6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800299ad  mov     rcx, rbx; hModule
0x1800299b0  mov     rdi, rax
0x1800299b3  call    cs:__imp_GetProcAddress
0x1800299b9  test    rdi, rdi
0x1800299bc  jz      short loc_1800299D3
0x1800299be  test    rax, rax
0x1800299c1  jz      short loc_1800299D3
0x1800299c3  mov     cs:qword_1800D4100, rdi
0x1800299ca  mov     cs:qword_1800D4108, rax
0x1800299d1  jmp     short loc_1800299F1
0x1800299d3  xor     r9d, r9d; lpName
0x1800299d6  xor     r8d, r8d; bInitialState
0x1800299d9  xor     ecx, ecx; lpEventAttributes
0x1800299db  lea     edx, [r9+1]; bManualReset
0x1800299df  call    cs:__imp_CreateEventW
0x1800299e5  mov     cs:hHandle, rax
0x1800299ec  test    rax, rax
0x1800299ef  jz      short loc_180029A15
0x1800299f1  xor     ecx, ecx
0x1800299f3  call    __scrt_initialize_onexit_tables
0x1800299f8  test    al, al
0x1800299fa  jz      short loc_180029A15
0x1800299fc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180029a03  call    atexit
0x180029a08  mov     rbx, [rsp+28h+arg_0]
0x180029a0d  xor     eax, eax
0x180029a0f  add     rsp, 20h
0x180029a13  pop     rdi
0x180029a14  retn
0x180029a15  mov     ecx, 7
0x180029a1a  call    __scrt_fastfail
```
